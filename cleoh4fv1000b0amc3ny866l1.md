# Hosting a Discord Bot on Cloudflare Workers

Hi everyone,

Welcome to my blog. This post will show you **How to host your Discord Bot on Cloudflare Worker.**

The bot is written in **TypeScript** and will be **hosted on Cloudflare workers.**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677548469394/0567f36d-a8da-4010-b411-7143b6ba5ffa.gif align="center")

**All of the code for this app can be found** [on GitHub](https://github.com/Real-Dev-Squad/discord-slash-commands).

---

## **How to Create a bot on Discord**

**Step 1:** Create a personal discord server.

**Step 2:** Visit [Discord Developer Portal](https://discord.com/developers/applications) for creating a Bot.

**Step 3: Click** `New Application`, and choose a name

**Step 4:** Copy your Public Key and Application ID, and put them somewhere locally (we'll need these later)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677550208877/da69c696-9e31-4ae5-a685-525257096941.jpeg align="center")

**Step 5:** Now click on the `Bot` tab on the left sidebar, and create a bot! You can choose the same name as your app.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677552431300/24838e47-0613-448f-8531-7ea6652eb99b.png align="left")

**Step 6:** Grab the `token` for your bot after clicking the reset token button, and store it somewhere safe.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677550534234/8feaa723-db71-427d-a9a2-3545b2d7a37a.png align="center")

⚠️ For security reasons, you can only view your bot token once. If you misplace your token, you'll have to generate a new one.

**Step 7: Adding bot permissions**

**Now we'll configure the bot with** [**permissions**](https://discord.com/developers/docs/topics/permissions) **required to create and use slash commands.**

* **Click on the** `OAuth2` tab, and choose the `URL Generator`. Click the `bot` and `applications.commands` scopes.
    
* **Check the boxes to** set following permissions for your bot.
    
* After providing all the permissions you will get an url at the bottom of the page use that to invite the bot to your server.
    
    Open the Url you get and invite the bot to your test server.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677552709483/5ae09a5d-f001-4ac2-8095-c28a7796fd73.png align="center")

---

## **Creating your Cloudflare Worker**

**Cloudflare Workers are a convenient way to host Discord Bot due to the free tier, simple development model, and automatically managed environment.**

* **Visit the** [**Cloudflare Dashboard**](https://dash.cloudflare.com/)
    
* **Click on the** [`Workers`](https://developers.cloudflare.com/workers/get-started/guide/) tab, and create a new service using the same name as your Discord bot
    
* **Make sure to** [**install the Wrangler CLI**](https://developers.cloudflare.com/workers/wrangler/install-and-update/) **and set it up.**
    

---

## **Setting Up Local Development**

* Clone the [Repository](https://github.com/Real-Dev-Squad/discord-slash-commands) to your machine
    
* Create a .env file in the project folder because we need a few environment variables for the bot to work which is given below.
    
    ```typescript
    DISCORD_TOKEN="" //The token generated for your bot while creating a discord application
    DISCORD_PUBLIC_KEY="" //Public key of your Discord bot helps to verify the bot and apply interaction url
    DISCORD_APPLICATION_ID=""  //The application id of your bot.
    DISCORD_GUILD_ID=""   //Id of the guild where you want to install the slash commands.
    ```
    
* run `npm install`
    

### **Project structure**

**Registering commands**

Discord provides us with an endpoint to register all our commands to our bots.  
For this app, w**e'll have a** `/hello` **command, and a** `/verify` **command. The name and description for these are kept separate in** `commands.ts`**:**

```typescript
export const HELLO = {
  name: "hello",
  description: "Replies with hello in the channel",
};

export const VERIFY = {
  name: "verify",
  description:
    "Generate a link with user specific token to link with RDS backend.",
};
```

**The code to register commands lives in** `register.js`. It hist that endpoint with all the commands that we want to register.

**Step 1:** Setting up the staging environment variable to register the commands and deploy code to the Cloudflare workers.

```yaml
name: Register and deploy Slash Commands
on:
  push:
    branches: develop
jobs:
  Register-Commands:
    runs-on: ubuntu-latest
    environment: staging
    steps:
      - uses: actions/checkout@v2
      - run: npm install
      - run: npm run register
        env:
          DISCORD_TOKEN: ${{secrets.DISCORD_TOKEN}}
          DISCORD_APPLICATION_ID: ${{secrets.DISCORD_APPLICATION_ID}}
          DISCORD_GUILD_ID: ${{secrets.DISCORD_GUILD_ID}}
  Deploy-to-Cloudflare:
    needs: [Register-Commands]
    runs-on: ubuntu-latest
    environment: staging
    steps:
      - uses: actions/checkout@v2
      - run: npm install
      - uses: cloudflare/wrangler-action@2.0.0
        with:
          apiToken: ${{secrets.CLOUDFLARE_API_TOKEN}}
          secrets: |
            DISCORD_PUBLIC_KEY
            DISCORD_TOKEN
        env:
          CLOUDFLARE_API_TOKEN: ${{secrets.CLOUDFLARE_API_TOKEN}}
          DISCORD_PUBLIC_KEY: ${{secrets.DISCORD_PUBLIC_KEY}}
          DISCORD_TOKEN: ${{secrets.DISCORD_TOKEN}}
```

**Step 2:** Created a few files to register all the commands given in commands.ts to the bot.

```typescript
import { HELLO, VERIFY } from "./constants/commands";
import { config } from "dotenv";
import { DISCORD_BASE_URL } from "./constants/urls";
import { registerCommands } from "./utils/registerCommands";

config();

/**
 *
 * @param discordBotToken { String }: Token for your Discord Bot
 * @param discordApplicationId { String }: Application Id of your discord bot
 * @param discordGuildId { String }: Guild id in which commands are to be installed.
 */

async function registerGuildCommands(
  discordBotToken?: string,
  discordApplicationId?: string,
  discordGuildId?: string
) {
  const commands = [HELLO, VERIFY];

  try {
    if (!discordBotToken) throw new Error("Please provide a BOT TOKEN");
    if (!discordApplicationId)
      throw new Error("Please provide a DISCORD_APPLICATION_ID");
    if (!discordGuildId) throw new Error("Please provide a GUILD_ID");

    const registrationUrl = `${DISCORD_BASE_URL}/applications/${discordApplicationId}/guilds/${discordGuildId}/commands`;
    await registerCommands(registrationUrl, discordBotToken, commands);
  } catch (e) {
    console.log(e);
  }
}

registerGuildCommands(
  process.env.DISCORD_TOKEN,
  process.env.DISCORD_APPLICATION_ID,
  process.env.DISCORD_GUILD_ID
);
```

```typescript
/**
 * handle fetch request
*/
/**
 *
 * @param url { String }: DISCORD HTTP end point for command registration
 * @param discordBotToken { String }: Token of your bot to send as authorization header
 * @param commands { Array }: Array of commands to be registered
 */
import { fetch } from "./fetch";
import { commandTypes } from "../typeDefinitions/register.types";

export async function registerCommands(
  url: string,
  discordBotToken: string,
  commands: Array<commandTypes>
) {
  try {
    const response = await fetch(url, {
      headers: {
        "Content-Type": "application/json",
        Authorization: `Bot ${discordBotToken}`,
      },
      method: "PUT",
      body: JSON.stringify(commands),
    });

    if (response.ok) console.log("Registered all commands");
    else console.error("Error Registering Commands");
  } catch (error) {
    console.error(error);
  }
}
```

* Now, run the command `npm run register`(This will register all the commands to your discord bot.)
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677582732977/27a83704-8508-48c9-9658-7f4ef07bacfc.png align="center")
    
* Now let's link our local development server to our bot.
    
    After all the commands are installed we need to save a few secrets in wrangler cli.
    
    * run command `wrangler secret put DISCORD_TOKEN` and then enter the value of your token.
        
    * run command `wrangler secret put DISCORD_PUBLIC_KEY` and enter the public key.
        

### **Setup** Route in Cloudflare Worker and Verify Bot Request from Discord to Cloudflare Worker

***Note*:- We are using** [**itty-router**](https://github.com/kwhitley/itty-router)**, a lightweight router developed for Cloudflare workers.**

* Define Route in the case `get('/')`
    
* Define Route in the case of any apart from `get('/')`i.e. configured it to return 404
    
* We want to verify if the request we received is a valid discord request.
    
    ```typescript
    export const UNKNOWN_INTERACTION = {
      error: "Unknown Interaction",
    };
    
    export const NOT_FOUND = {
      error: "🥹 oops! No fish 🐟 caught 🎣",
    };
    
    export const BAD_SIGNATURE = {
      error: "🚫 Bad Request Signature",
    };
    
    export const STATUS_CHECK = {
      message: "Welcome to our discord Bot Server 👋",
    };
    
    export const COMMAND_NOT_FOUND = "Command Not Found";
    ```
    
    ```typescript
    import { Router } from "itty-router";
    import { InteractionResponseType, InteractionType } from "discord-interactions";
    import * as response from "./constants/responses";
    import { baseHandler } from "./controllers/baseHandler";
    import { env } from "./typeDefinitions/default.types";
    import { discordMessageRequest } from "./typeDefinitions/discordMessage.types";
    import JSONResponse from "./utils/JsonResponse";
    import { verifyBot } from "./utils/verifyBot";
    
    const router = Router();
    
    router.get("/", async () => {
      return new JSONResponse(response.STATUS_CHECK, {
        status: 200,
      });
    });
    
    router.post("/", async (request, env) => {
      const message: discordMessageRequest = await request.json();
      if (message.type === InteractionType.PING) {
        return new JSONResponse({
          type: InteractionResponseType.PONG,
        });
      }
      if (message.type === InteractionType.APPLICATION_COMMAND) {
        return baseHandler(message, env);
      }
      return new JSONResponse(response.UNKNOWN_INTERACTION, { status: 400 });
    });
    
    router.all("*", async () => {
      return new JSONResponse(response.NOT_FOUND, {
        status: 404,
      });
    });
    
    export default {
      async fetch(request: Request, env: env): Promise<Response> {
        if (request.method === "POST") {
          const isVerifiedRequest = await verifyBot(request, env);
          if (!isVerifiedRequest) {
            console.error("Invalid Request");
            return new JSONResponse(response.BAD_SIGNATURE, { status: 401 });
          }
        }
        return router.handle(request, env);
      },
    };
    ```
    

### Add Handler for /hello command and /verify command in chat

* We want to add a base handler that checks for commands in chat and call its respective handler
    
* When we write /hello in the discord server chat the handler return \`Hello &lt;@${userId}&gt;\`
    
* When we write /verify in the discord server chat the handler "Please check the DM"  
    In Dm you see "Hello" message
    

```typescript
import { HELLO, VERIFY } from "../constants/commands";
import { env } from "../typeDefinitions/default.types";
import { discordMessageRequest } from "../typeDefinitions/discordMessage.types";
import { getCommandName } from "../utils/getCommandName";
import JSONResponse from "../utils/JsonResponse";
import { lowerCaseMessageCommands } from "../utils/lowerCaseMessageCommand";
import { commandNotFound } from "./commandNotFound";
import { helloCommand } from "./helloCommand";
import { verifyCommand } from "./verifyCommand";

export async function baseHandler(
  message: discordMessageRequest,
  env: env
): Promise<JSONResponse> {
  const command = lowerCaseMessageCommands(message);
  switch (command) {
    case getCommandName(HELLO): {
      return helloCommand(message.member.user.id);
    }
    case getCommandName(VERIFY): {
      return await verifyCommand(message.member.user.id, env);
    }
    default: {
      return commandNotFound();
    }
  }
}
```

```typescript
import { env } from "../typeDefinitions/default.types";
import { discordTextResponse } from "../utils/discordResponse";
import { sendDiscordDm } from "../utils/sendDiscordDm";
import JSONResponse from "../utils/JsonResponse";

export function helloCommand(userId: number): JSONResponse {
  return discordTextResponse(`Hello <@${userId}>`);
}

export async function verifyCommand(userId: number, env: env) {
  await sendDiscordDm(userId, env);
  return discordTextResponse("Please check the DM");
}
```

```typescript
import { DISCORD_BASE_URL } from "../constants/urls";
import { env } from "../typeDefinitions/default.types";
import { createDmChannel } from "../typeDefinitions/discordMessage.types";

/**
 *
 * @param userId {number}: user id of the person using the slash command received from the interaction.
 * @param env {env}: contains environment variables.
 */

export const sendDiscordDm = async (
  userId: number,
  env: env,
) => {
  // "/users/@me/channels" is an endpoint provided by discord to create a dm channel
  try {
    const createDmChannel: createDmChannel = await fetch(
      `${DISCORD_BASE_URL}/users/@me/channels`,
      {
        method: "POST",
        headers: {
          "Content-Type": "application/json",
          Authorization: `Bot ${env.DISCORD_TOKEN}`,
        },
        body: JSON.stringify({
          content: discordTextResponse("Hello"),
          recipient_id: userId,
        }),
      }
    ).then((res) => {
      return res.json();
    });

    const channelId = createDmChannel.id;

    // "/channels/{channel.id}/messages" is used to send a message to the specified channel
    await fetch(`${DISCORD_BASE_URL}/channels/${channelId}/messages`, {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
        Authorization: `Bot ${env.DISCORD_TOKEN}`,
      },
      body: JSON.stringify({
        content: "Hello",
      }),
    });
  } catch (e) {
    console.log("Could not send the DM. Error: ", e);
  }
};
```

### **Running the server**

1. **This command needs to be run locally, once before getting started:** `npm start`
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677587307361/2eeda698-c8c4-4038-97e3-2db81b2c02d8.png align="center")
    
2. Once the wrangler starts make sure it is running on port `8787`\-&gt;click \[b\]
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677587446687/51967a26-4276-488c-9747-3975a0c9ff9f.png align="center")
    

### **Setting up ngrok**

When a user types a slash command, Discord will send an HTTP request to a public endpoint. During local development this can be a little challenging, so we're going to use [a tool called `ngrok`](https://ngrok.com/) to create an HTTP tunnel.

Once the server starts on desired port 8787 open another terminal and type in the command `npm run ngrok`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677587557863/48a5a596-cec3-43a5-bbee-c8ae03b24a17.png align="center")

This is going to bounce requests off of an external endpoint, and forward them to your machine. Copy the HTTPS link provided by the tool. It should look something like [`https://8098-24-22-245-250.ngrok.io`](https://8098-24-22-245-250.ngrok.io).

Now head back to the Discord Developer Dashboard, and update the `Interactions Endpoint URL` for your app:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677602192109/0116550d-623c-4740-8a5c-a65839048fd0.png align="center")