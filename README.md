# webclient
Basic web client program, written in python, that connects and retrieves data from a web server
Here's the code; Please review and feedback to me!

#!/usr/bin/python
# -*- coding: iso-8859-15 -*-


#Write a client program that connects and retrieves data from a web server

#NOTES:

#The pipe or socket is an endpoint of a bidirectional inter-process communication
#flow across an internet protocol based computer network, such as the Internet.
#1 import socket or library then your floating in the air anti-gravity
#2 create socket
#3 Make connection to server -use a tuple to connect to host and port number or ext
#4 Start talking send GET request for the desired page
#5 Write while loop; while statement is true - socket receiving 512 character bytes of data, is greater than 1 byte, print output and continue
#6 Continue reading page until data is equal to 0
#7 Close socket

##  Further reading can be found here http://docs.python.org/library/socket.html

import socket

mysock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
mysock.connect(('www.dsittraining.com', 80))
mysock.send('GET http://new.dsittraining.com/ HTTP/1.0\n\n')

while True:
    data = mysock.recv(512)
    if len(data) < 1:
        break
    print data
mysock.close()
