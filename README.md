# EX01 Developing a Simple Webserver
## Date: 15-04-2025

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
~~~
from http.server import HTTPServer, BaseHTTPRequestHandler
content="""

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Laptop Specs</title>
</head>
<body>
    <center>
        <h1>LAPTOP SPECIFICATION</h1>
        <img src="Laptop.webp" alt="">
        <table border ="12" style="margin-bottom: 30px;">
            <tr>
               <th>PROCESSOR</th>
               <td>AMD Ryzen™ R7-7435HS</td>
            </tr>
            <tr>
                <th>OPERATING SYSTEM</th>
                <td>Windows 11 Pro</td>
            </tr>
            <tr>
                <th>GRAPHICS</th>
                <td>NVIDIA® GeForce RTX™ 4060 Laptop GPU 8GB GDDR6 (115W ) 2370MHz Boost Clock (VR ready, G-SYNC support) <br>
                    40 Series NVIDIA Supported Technologies: <br>
                    NVIDIA DLSS 3 <br>
                        i) NVIDIA Ada Lovelace Architecture <br>
                       ii) NVIDIA Max-Q Technologies <br>
                      iii) Advanced Optimus <br>
                       iv) Optimal Playable Settings <br>
                        v) Rapid Core Scaling <br>
                       vi) CPU Optimizer <br>
                      vii) Dynamicboost <br>
                     viii) DLSS <br>
                       ix) Resizable BAR <br>
                </td>
            </tr>
            <tr>
                <th>MEMORY</th>
                <td>Up to 24GB (2x12GB) 4800MHz DDR5 <br>
                    2 x SO-DIMM</td>
            </tr>
            <tr>
                <th>STORAGE</th>
                <td>Up to 1TB M.2 2242 PCIe SSD (Gen4) (The slots support M.2 2280 and 2242) <br>

                    2 x PCIE-Gen4-SSD-Slot (2280/2242 capable design, 1 occupied by default SSD installed; the other is reserve for customer upgrade.)</td>
            </tr>
            <tr>
                <th>BATTERY</th>
                <TD>4-cell 60Whr <br>

                    Support Super Rapid Charge Pro (10min charge 0-40% capacity, 30min charge 0-80% capacity, 60min charge 0-100% capacity) </TD>
            </tr>
            <tr>
                <th>AUDIO</th>
                <td>2 x 2 watt speakers with Nahimic Audio</td>
            </tr>
            <tr>
                <th>CAMERA</th>
                <td>Built-in Webcam (720p) with E-Shutter</td>
            </tr>
        </table>
    </center>
</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd= HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
~~~

## OUTPUT:

![Screenshot 2025-04-24 083547](https://github.com/user-attachments/assets/ba3325b4-92fb-4918-9fc1-da1ed18654a3)


![Screenshot 2024-12-07 155829](https://github.com/user-attachments/assets/8de20157-a9db-4d8b-b8c7-5149b24093a8)

## RESULT:
The program for implementing simple webserver is executed successfully.
