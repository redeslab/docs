### Download files using Curl

Curl can be used to transfer data over a number of protocols. It supports many protocols including HTTP, HTTPS, FTP, TFTP, TELNET, SCP, etc. using Curl, you can download any remote files. It supports pause and resumes function as well.

To get started with, first, you need to install the curl.
Install curl

Launch command line application in Ubuntu that is Terminal by pressing the Ctrl+Alt+T key combinations. Then enter the below command to install curl with sudo.

$ sudo apt install curl

When prompted for a password, enter sudo password.


### Download and save the file using the source file name

To save the file with the same name as the original source file on the remote server, use –O (uppercase O) followed by curl as below:

$ curl –O [URL]