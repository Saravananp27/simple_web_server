# EX01 Developing a Simple Webserver

# Date:24/05/2025
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
from http.server import HTTPServer,BaseHTTPRequestHandler
content='''
<html>
<title>top software Industries</title>
<body>
<table border ="6" cellspacing="10" cellpadding="8">
<caption>TOP 5 Revenue Generating Software Companies </caption>
<tr>
<th>s.no</th>
<th>companies</th>
<th>Revenue</th>
</tr>
<tr>
<th>1</th>
<th>Microsoft</th>
<th>65 billon</th>
</tr>
<tr>
<th>2</th>
<th>orcale</th>
<th>29.6 billon</th>
</tr>
<tr>
<th>3</th>
<th>IMB</th>
<th>29.1 billion</th>
</tr>
<tr>
<th>4</th>
<th>SAP</th>
<th>6.4billion</th>
</tr>
<tr>
<th>5</th>
<th>symentec</th>
<th>5.6billion</th>    
</tr>
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

# OUTPUT:
![alt text](image-1.png)
![alt text](image.png)
# RESULT:
The program for implementing simple webserver is executed successfully.
