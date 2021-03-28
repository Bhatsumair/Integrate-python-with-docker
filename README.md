# Integrate-python-with-docker#!/usr/bin/python3

print("content-type: text/html")
print()

import subprocess
import cgi

form = cgi.FieldStorage()

#osname = input("Enter ur os name : ")
osname = form.getvalue(" x")

cmd = "docker run -dit --name {0} centos:7".format(osname)

output = subprocess.getstatusoutput(cmd)

status = output[0]
out = output[1]

if status == 0:
   print("os launched name {} ..".format(osname))
else:
   print("some eror : {}".format(out))
