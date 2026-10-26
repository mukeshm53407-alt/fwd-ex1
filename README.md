# EX01 Developing a Simple Webserver
## Date:
15-10-2026
## REG NO:
26002429

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
content = """
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Web Development Protocols</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      max-width: 900px;
      margin: 40px auto;
      padding: 0 20px;
      color: #222;
    }

    h1 {
      color: #174ea6;
      text-align: center;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 24px;
    }

    th, td {
      border: 1px solid #ccc;
      padding: 12px;
      text-align: left;
    }

    th {
      background-color: #174ea6;
      color: white;
    }

    tr:nth-child(even) {
      background-color: #f2f6fc;
    }

    caption {
      margin-bottom: 10px;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <h1>Protocols Used in Web Development</h1>

  <table>
    <caption>Common web protocols and their purposes</caption>
    <thead>
      <tr>
        <th>Protocol</th>
        <th>Full Name</th>
        <th>Purpose</th>
        <th>Common Port</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>HTTP</td>
        <td>Hypertext Transfer Protocol</td>
        <td>Transfers web pages and other resources between browsers and servers.</td>
        <td>80</td>
      </tr>
      <tr>
        <td>HTTPS</td>
        <td>Hypertext Transfer Protocol Secure</td>
        <td>Securely transfers web data using encryption with TLS.</td>
        <td>443</td>
      </tr>
      <tr>
        <td>DNS</td>
        <td>Domain Name System</td>
        <td>Finds the IP address associated with a domain name.</td>
        <td>53</td>
      </tr>
      <tr>
        <td>TCP</td>
        <td>Transmission Control Protocol</td>
        <td>Provides reliable, ordered delivery of data between networked devices.</td>
        <td>Varies</td>
      </tr>
      <tr>
        <td>IP</td>
        <td>Internet Protocol</td>
        <td>Addresses and routes packets between devices across networks.</td>
        <td>Not applicable</td>
      </tr>
      <tr>
        <td>WebSocket</td>
        <td>WebSocket Protocol</td>
        <td>Enables two-way, real-time communication between a browser and server.</td>
        <td>80 / 443</td>
      </tr>
      <tr>
        <td>FTP / SFTP</td>
        <td>File Transfer Protocol / Secure File Transfer Protocol</td>
        <td>Transfers files between systems; SFTP encrypts the connection.</td>
        <td>21 / 22</td>
      </tr>
      <tr>
        <td>SMTP</td>
        <td>Simple Mail Transfer Protocol</td>
        <td>Sends email, often for website notifications and account messages.</td>
        <td>25, 465, or 587</td>
      </tr>
    </tbody>
  </table>
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
server_address = ('',880)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()

~~~


## OUTPUT:
![alt text](<../Screenshot 2026-10-24 143055.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.

