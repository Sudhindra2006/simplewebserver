# EX01 Developing a Simple Webserver
## Date:

## AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

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
'''
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<HTML>
    <CENTER>
    <H1>LAPTOP CONFIGURATION</H1>
</CENTER>
    <BODY>
        <CENTER>
        <TABLE border="2" CELLPADDING="10">
 <TR>
    <TD>LAPTOP NAME:</TD><TD>LENOVO THINKPAD</TD>
 </TR>           
<TR>
    <TD>DEVICE NAME:</TD><TD>SUDHINDRA</TD>
</TR>
<TR>
    <TD>OPERATIN SYSTEM:</TD><TD>WINDOWS 11 HOME</TD>
</TR>
<TR>
    <TD>PROCESSOR:</TD><TD>13th Gen Intel(R) Core(TM) i5-1335U   1.30 GHz </TD>
</TR>
<TR>
    <TD>CLOCK SPEED:</TD><TD>1.30 GHz</TD>
</TR>
<TR>
    <TD>INSTALLED RAM:</TD><TD>16GB RAM </TD>

</TR>
<TR>
    <TD>GRAPHIC PROCESSOR:</TD><TD>NVIDIA GeForce GTX 1650</TD>
</TR>
<TR>
    <TD>SSD CAPACITY</TD><TD>512GB</TD>
</TR>
<TR>
    <TD>POWER SUPPLY</TD><TD>65W</TD>
</TR>
</CENTER>
    </BODY>
</TABLE>
</HTML>
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
'''


## OUTPUT:
![Screenshot (7)](https://github.com/user-attachments/assets/850a4b29-2c0c-46e2-91e8-72d7e51f1214)
![Screenshot (8)](https://github.com/user-attachments/assets/053f73e6-261f-430f-aa02-1fc350db6c2c)



## RESULT:
The program for implementing simple webserver is executed successfully.
