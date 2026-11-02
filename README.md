# EX01 Developing a Simple Webserver
## Date: 27.09.2026

## AIM:
To develop a simple webserver to serve html pages and display the Windows Specifications of your Laptop.

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
```
sera.py
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
    <head>
        <title>Laptop specifications</title>
    </head>
    <body bgcolor="white">
        <table border="4" cellspacing="5" cellpading="11" align="center" width="600" height="700">
            <caption><h1>Laptop specifications</h1></caption>
            <caption><h2>V.Sera aakash(26018101)</h2></caption>
            <tr bg color="lightblue">
                <th>s.no</th>
                <th>Device type</th>
                <th>Device info</th>
            </tr>
            <tr>
                <td>1</td>
                <td>Device name</td>
                <td>TL15-53M-G2-SERAAAKASHVELU</td>
            </tr>
            <tr>
                <td>2</td>
                <td>Processor</td>
                <td>Intel(R) Core(TM) 5 210H (2.20 GHz)</td>
            </tr>
            <tr>
                <td>3</td>
                <td>Installed RAM</td>
                <td>16.0 GB (15.7 GB usable)</td>
            </tr>
            <tr>
                <td>4</td>
                <td>Graphics card</td>
                <td>Intel(R) Graphics (128 MB)</td>
            </tr>
            <tr>
                <td>5</td>
                <td>Storage</td>
                <td>135 GB of 477 GB used</td>
            </tr> 
            <tr>
                <td>6</td>
                <td>Device ID</td>
                <td>71874527-0DF8-4C54-ADE6-2697D31742A5</td>
            </tr>
            <tr>
                <td>7</td>
                <td>Product ID</td>
                <td>00342-42945-49032-AAOEM</td>   
            </tr>
            <tr>
                <td>8</td>
                <td>System Type</td>
                <td>64-bit operating system, x64-based processor</td>
            </tr>
            <tr>
                <td>9</td>
                <td>Pen and touch</td>
                <td>No pen or touch input is available for this display</td>
            </tr>    
         </table>           
        </body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Client request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my own webserver is running successfully...")
httpd.serve_forever()
```

## OUTPUT:
webpage
![alt text](<Screenshot (18).png>)
server page
![alt text](image.png)
## RESULT:
The program for implementing simple webserver is executed successfully.
