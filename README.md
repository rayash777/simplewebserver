# EX01 Developing a Simple Webserver

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
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
<head>
<title>Top five software companies in revenue</title>
</head>
<body>
<h1 align="center">
TOP FIVE SOFTWARE COMPANIES IN REVENUE</h1>
<table align="center" border="2" cellspacing="5" cellpadding="5" width="800" height="500">
<tr>
<th>RANK</th>
<th>COMPANY NAME</th>
<th>REVENUE</th>
</tr>
<tr>
<td>1</td>
<td>Apple(AAPL)</td>
<td>$385.70 B </td>
</tr>
<tr>
<td>2</td>
<td>Alphabet(Google)</td>
<td>$307.39 B</td>
</tr>
<tr>
<td>3</td>
<td>Microsoft</td>
<td>$227.58 B</td>
</tr>
<tr>
<td>4</td>
<td>Ibm</td>
<td>$61.85 B</td>
</tr>
<tr>
<td>5</td>
<td>Oracle</td>
<td>$51.62 B</td>
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
![alt text](<Screenshot (430).png>)

![alt text](<Screenshot (431).png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
