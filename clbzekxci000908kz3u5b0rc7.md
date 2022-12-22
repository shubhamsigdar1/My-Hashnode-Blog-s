# Lets Install And Get Started With Node.JS

## Installation Process

1.  Search on Google: install node
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671730374924/a36fbd5b-01d1-4c60-97ab-96cf4b577c8c.png align="center")
    
2.  Click on Link [https://nodejs.org/en/download/](https://nodejs.org/en/download/)
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671730482354/5771ff55-74cd-49b0-b56d-a0235f11b7fa.png align="center")
    
3.  Choose either LTS or Current depending on you i.e. you want the latest features by choosing the Current one or old features that already worked and reviewed.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671730497855/478d2488-7719-47e4-baab-538e151fb9a9.png align="center")
    
4.  After clicking on window Installer you see its started downloading
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671730690718/f4a508aa-af90-48fd-8a26-af83b661c365.png align="center")
    
5.  Click on next
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671730769256/3de0af8e-02b6-42ce-829b-9a6d6aa4d2ce.png align="center")
    
6.  Read and Accept term in the license Agreement and click next
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671730799000/32f2b9d5-3881-4730-aee1-e0f41b81438c.png align="center")
    
7.  Click next
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671730848229/08551e83-3f1c-4def-ac57-7cf72db1bca6.png align="center")
    
8.  Click next
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671730863082/ad0eeb8d-d0bb-41a0-b830-fd4e0241dd3d.png align="center")
    
9.  Choose checkBox and click next
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671730903404/de2d707b-f4c2-470e-b44a-99dd791df014.png align="center")
    
10.  Installation started and after installation click finish
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671730915558/22846c08-51be-40e6-a475-4676218db1cd.png align="center")

11.  After clicking on finish one terminal popup to install chocolatey please press any Key from Keyboard to continue
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671730954719/e6c24068-e4f1-4912-874a-7bacf6ce18b8.png align="center")

12.  After clicking any key from keyboard, PowerShell opened and waits for 5minute until options come TYPE ENTER to exit
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671730963565/d2a634ba-459f-4975-b6fb-fb000110d573.png align="center")

13.  Type Enter and you are done
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671730986501/f2bc14e7-c4d7-44cc-858c-eaacbf0353dc.png align="center")

## How to Check Whether node.JS is installed or not in your system?

### **Follows Steps**

1.  Open VS code and then create index.html file and nodetesting.js file and then write this code below
    

```xml
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
  </head>
  <body>
    <h1>Hello, world!</h1>
  </body>
</html>const http = require('http')
```

```javascript
const fs = require('fs')
http.createServer((req, res) => {
  fs.readFile('index.html', (err, data) => {
    res.writeHead(200, {'Content-Type': 'text/html'})
    res.write(data)
    res.end()
  })
}).listen(8000)
```

2.  Open Terminal of vs code and write on terminal `node nodetesting.js` and Hit Enter
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671732262355/ad4069ea-d942-433e-88fc-0fa9d6e95909.png align="center")
    
3.  Open chrome browser using open with Live server extension and you can see a similar
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671732389442/89a53273-dc75-4d51-a584-0d2d778c4b9f.png align="center")
    
4.  Finally, You are done with server-side programming. Congrats!