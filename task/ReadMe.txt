1) I have to install logrotate, vim, zip, unzip, python-dev, python-pip, virtualenv, uwsgi.
2) I can do that by writing down this command in terminal " iptables -A INPUT -p tcp --dport 80 -j ACCEPT" this coomand will expose TCP port 80 on my host os.
3) nginx problem is error 504 "bad gateway" it appears because of issue in nginx.conf;
4) Phrase "Hello from MacPaw" is placed in /app/main.py. That's why i have to spin up a uswgi server which can execute this file, role of the nginx will be as reverse-proxy. Additionally i have to make connection between uwsgi and nginx.
5) In order to do that i have to put in "127.0.0.1 internship.macpaw.io" in hosts and change server_name in nginx.conf because of uwsgi server uses ip 127.0.0.1 and port 8080. 
6) 
a) The most common non-200 response code at your old website is 401;
b) Number of requests from 8.8.8.8 is 790;
c) "HTTP/1.1 304 Not Modified
x-amz-id-2: Z55O1pkHJ6RFBwZudzLtqFYrZiXW9Fc3wEMw4gkNVjQq4tdHrvzkoj2k5y5hq3hd69LdjbLP3SU=
x-amz-request-id: C88ADA8320C99CD7
Date: Tue, 01 May 2018 17:40:58 GMT
Last-Modified: Sun, 08 Apr 2018 10:01:55 GMT
ETag: "51f33b1cd666a77916ca18d3a913ff58"
Server: AmazonS3." 
The two first symbols from ETag header of a file stored in your s3 bucket are 51;
The password of the file "/tmp/additional.zip" is 401+790+51=1242;
In order to get this file i have to write down the command unzip /tmp/additional.zip and put in the password.
