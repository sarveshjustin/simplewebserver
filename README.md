# Developing a Simple Webserver
## AIM:
To Develop a webserver to display about top five web application development frameworks.

## DESIGN STEPS:
### Step 1: 
HTML content creation
### Step 2:
Design of webserver workflow
### Step 3:
Implementation using Python code
### Step 4:
Serving the HTML pages.
### Step 5:
Testing the webserver

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1>The Top Five Web Application Development Frameworks Are:</h1>
<h1>Express</h1>
<h1>Django</h1>
<h1>Rails</h1>
<h1>Laravel</h1>
<h1>Spring</h1>

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
server_address = ('',786)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
 
```

## OUTPUT:
![output](output.png)
Running image:
 ![output](running%20code.png)



## RESULT:

Thus a webserver is developed to display about top five web application development frameworks.
