# EX01 Developing a Simple Webserver

# Date:12/0/25
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
```from http.server import HTTPServer, BaseHTTPRequestHandler

content = """
<!DOCTYPE html>
<html>
<head>
    <title>Device Specifications</title>
    <style>
        body {
            font-family:'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
            margin: 20px;
            background-color:darkolivegreen;
        }
        table {
            width: 60%;
            border-collapse: collapse;
            margin: 20px auto;
            background: #fff;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        th, td {
            text-align: left;
            padding: 12px;
            border: 1px solid #ddd;
        }
        th {
            background-color: #0078D7;
            color: white;
        }
        tr:nth-child(even) {
            background-color:aqua;
        }
        tr:hover {
            background-color:cornsilk;
        }
        caption {
            font-size: 20px;
            font-weight: bold;
            padding: 10px;
            text-align: center;
        }
    </style>
</head>
<body>
    <table>
        <caption>Device Specifications</caption>
        <tr>
            <th>Specification</th>
            <th>Details</th>
        </tr>
        <tr>
            <td>Device Name</td>
            <td>LAPTOP-OK438C1K</td>
        </tr>
        <tr>
            <td>Processor</td>
            <td>12th Gen Intel(R) Core(TM) i3-1215U 1.20 GHz</td>
        </tr>
        <tr>
            <td>Installed RAM</td>
            <td>8.00 GB (7.68 GB usable)</td>
        </tr>
        <tr>
            <td>Device ID</td>
            <td>FED1B711-7C21-464A-9BAA-30A98F1765ED</td>
        </tr>
        <tr>
            <td>Product ID</td>
            <td>00356-24754-57891-AAOEM</td>
        </tr>
        <tr>
            <td>System Type</td>
            <td>64-bit operating system, x64-based processor</td>
        </tr>
        <tr>
            <td>Pen and Touch</td>
            <td>No pen or touch input is available for this display</td>
        </tr>
    </table>
</body>
</html>
"""

class MyHandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Request received")
        self.send_response(200)
        self.send_header('Content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())

server_address = ('', 8000)
httpd = HTTPServer(server_address, MyHandler)
print("My webserver is running...")
httpd.serve_forever()
```

# OUTPUT:
![Screenshot 2025-04-29 100704](https://github.com/user-attachments/assets/7e1e286c-6538-44c0-9c73-9236692ae0b4)
![Screenshot 2025-04-29 101000](https://github.com/user-attachments/assets/d122917e-dc5a-400a-8c8a-bd22a5542302)
# RESULT:
The program for implementing simple webserver is executed successfully.
