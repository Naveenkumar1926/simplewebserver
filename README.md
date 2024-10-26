# EX01 Developing a Simple Webserver
## Date:24/10/2024


## AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<html>
<head>
<title> My Web Server</title>
</head>
<body>
    <center><table border="10" cellpadding="30">
        <caption><h3>My system information</caption></h3>
        <tr bgcolor="grey" style="color:black;">
          <th bgcolor="antiquewhite">S.no</th><th>hardwares</th><th>specs</th>
        </tr>
        <tr bgcolor="antiquewhite" style="color:rgb(236, 18, 18);">
          <th bgcolor="grey" style="color:rgb(2, 247, 35);"> 1</td><th>model</th><th>thinkpad</th>
        </tr>
        <tr bgcolor="antiquewhite" style="color:rgb(245, 10, 10);">
            <th bgcolor="grey" style="color:rgb(2, 247, 35);">2</th><th>system manufacturer</th><th>LENOVO</th>
          </tr>
          <tr bgcolor="antiquewhite" style="color:rgb(244, 17, 17);">
            <th bgcolor="grey" style="color:rgb(2, 247, 35);">3</th><th>operating system</th><th>windows 11</th>
          </tr>
          <tr bgcolor="antiquewhite" style="color:rgb(250, 9, 9);">
            <th bgcolor="grey" style="color:rgb(2, 247, 35);">4</th><th>Ram</th><th>4gb</th>
          </tr>
          <tr bgcolor="antiquewhite" style="color:rgb(250, 12, 12);">
            <th bgcolor="grey" style="color:rgb(2, 247, 35);">5</th><th>Processor</th><th>intel</th>
          </tr>
          <tr bgcolor="antiquewhite" style="color:rgb(248, 9, 9);">
            <th bgcolor="grey" style="color:rgb(2, 247, 35);">6</th><th>SSD</th><th>512 GB</th>
          </tr>
        </center>

</body>
</html>

'''


class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()  
## OUTPUT:
![alt text](<Screenshot (29).png>)


## RESULT:
The program for implementing simple webserver is executed successfully.
