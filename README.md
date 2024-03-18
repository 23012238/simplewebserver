# EX01 Developing a Simple Webserver
## Date:25.02.24

## AIM:
To develop a simple webserver to serve html pages.

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
```c
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
    <head>
        <title> simple webserver </title>
    </head>
    <body>
       <table border="2" cellspacing="12" cellpadding="12" height="25" width="50">
       <h1> TOP FIVE SOFTWARE COMPANIES </h1>
            <tr>
                <th>Rank</th>
                <th>Company</th>
                <th>Revenue</th>
            </tr>
            <tr>
                <th>1</th>
                <th>Micro Soft</th>
                <th>$86.6</th>
            </tr>
            <tr>
                <th>2</th>
                <th>Oracle</th>
                <th>$37.1</th>
            </tr>
            <tr>
                <th>3</th>
                <th>SAP</th>
                <th>$20.9</th>
            </tr>
            <tr>
                <th>4</th>
                <th>Symantec</th>
                <th>$6.8</th>
            </tr>
            <tr>
                <th>5</th>
                <th>VMware</th>
                <th>$5.2</th>
            </tr>
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
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()

```


## OUTPUT:

![alt text](<Screenshot 2024-03-18 105108-1.png>)
![alt text](<Screenshot 2024-03-18 105125.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
