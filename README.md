# EX01 Developing a Simple Webserver

# Date:28:11:2024
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
```
1.views.py

from django.shortcuts import render,HttpResponse
from http.server import HTTPServer,BaseHTTPRequestHandler

content = '''
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lenovo ThinkPad E16 Specifications</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: rgb(244, 244, 249); 
            padding: 20px;
        }

        .container {
            max-width: 900px;
            margin: 0 auto;
            padding: 20px;
            background: rgb(255, 255, 255); /* White */
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
            border-radius: 12px;
        }
        .title {
            text-align: center;
            font-size: 28px;
            font-weight: bold;
            color: rgb(13, 255, 0); 
            background-color: rgb(255, 255, 255);
            margin-bottom: 20px;
            padding: 15px;
            text-transform: uppercase;
            letter-spacing: 1px;
            border-radius: 8px; 
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 10px;
        }

        th, td {
            padding: 15px;
            font-size: 16px;
        }

        th {
            background-color: aqua; 
            color: rgb(255, 255, 255); 
            font-weight: bold;
            text-transform: uppercase;
            text-align: left;
        }

        tr:nth-child(even) {
            background-color: rgb(224, 255, 255); 
        }

        tr:nth-child(odd) {
            background-color: rgb(240, 255, 255); 
        }

        tr:hover {
            background-color: rgb(200, 240, 240); 
        }

        td {
            border-bottom: 1px solid rgb(200, 200, 200); 
            text-align: left;
        }
      
    </style>
</head>
<body>
    <div class="container">
        <div class="title">💻Lenovo ThinkPad E16 Specifications💻</div>
        <hr border="2" >
        <table>
            <thead>
                <tr>
                    <th st>Feature</th>
                    <th>Specification</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>Processor</td>
                    <td>Intel Core i5-1340P / AMD Ryzen 7 7730U</td>
                </tr>
                <tr>
                    <td>Display</td>
                    <td>16.0" WUXGA (1920 x 1200), IPS, Anti-Glare</td>
                </tr>
                <tr>
                    <td>Integrated Graphics</td>
                    <td>Intel Iris Xe / AMD Radeon Graphics</td>
                </tr>
                <tr>
                    <td>Discrete Graphics</td>
                    <td>Optional NVIDIA GeForce RTX 2050</td>
                </tr>
                <tr>
                    <td>Memory</td>
                    <td>Up to 32GB DDR4</td>
                </tr>
                <tr>
                    <td>Storage</td>
                    <td>Up to 1TB SSD</td>
                </tr>
                <tr>
                    <td>Operating System</td>
                    <td>Windows 11 Pro</td>
                </tr>
                <tr>
                    <td>Weight</td>
                    <td>Starting at 1.78kg (3.92 lbs)</td>
                </tr>
                <tr>
                    <td>Battery Life</td>
                    <td>Up to 10 hours </td>
                </tr>
                <tr>
                    <td>Ports</td>
                    <td>USB-C, USB 3.2, HDMI, Ethernet, Audio Jack</td>
                </tr>
            </tbody>
        </table>
    </div>
</body>
</html>

'''
class Myserver(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200)
        self.send_header("content-type","text/html")
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver")
server_address = ('',8000)
httpd = HTTPServer(server_address,Myserver)
httpd.serve_forever()

2.urls.py

from django.contrib import admin
from django.urls import path
from app1 import views

urlpatterns = [
    path('admin/', admin.site.urls),
]

```
# OUTPUT:


  ![Screenshot (160)](https://github.com/user-attachments/assets/a9fe901d-fbf6-4780-a116-620abe082967)
      
  ![{25F38CAA-8ACD-4612-8F9C-8A170342B57A}](https://github.com/user-attachments/assets/701563e4-f44e-4d5c-8805-7c1b906b7567)


# RESULT:
The program for implementing simple webserver is executed successfully.
