# EX01 Developing a Simple Webserver
## Date:21-04-2025

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<head>
    <title>saveetha engineering collage</title>
    
</head>
<body >
    <style>
        table,th,td{    
        border : 2px solid yellow;
        }
        body{
            background-color: black;
            color: white;
        }
    </style>
<center>
   <table>
    <tr>
        <th>APPLICATION LAYER</th>
        <TH>TRANSPORT LAYER</TH>
        <TH>INTERNET LAYER</TH>
        <TH>NETWORK ACCESS LAYER</TH>
    </tr>
    <tr>
        <td>HTTP <br> FTP<br> DNS<br> TELNET <br></td>
        <td>TCP<br>
            UDP</td>
        <TD>IPv4<br>IPv6</TD>
        <td>ETHERNET</td>
    </tr>
   </table>
</center>
</body>
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
![WhatsApp Image 2025-04-21 at 21 26 51_912651c6](https://github.com/user-attachments/assets/dc03f424-3e74-4c4a-8fb1-978ca2048bcb)
![WhatsApp Image 2025-04-21 at 21 28 35_a14e74a2](https://github.com/user-attachments/assets/44382225-dcc7-45b2-9ee4-b4a46e2f1771)




## RESULT:
The program for implementing simple webserver is executed successfully.
