**Question 1:What does the 3-letter acronym FTP stand for?**

Avswer: File Transfer Protocol

**Question 2:Which port does the FTP service listen on usually?**

Avswer: 21

**Question 3:FTP sends data in the clear, without any encryption. What acronym is used for a later protocol designed to provide similar functionality to FTP but securely, as an extension of the SSH protocol?**

Avswer: SFTP

**Question 4:What is the command we can use to send an ICMP echo request to test our connection to the target?**

Avswer: ping

**Question 5:From your scans, what version is FTP running on the target?**

- Ta dùng lệnh dưới để kiểm tra phiên bản cuat FTP
``` bash
ftp <ip>
```
Avswer: vsftpd 3.0.3

**Question 6:From your scans, what OS type is running on the target?**

- Ta dùng ping 128(Window),64(Linux,Unix), 255(Cisco)

Avswer: Unix

**Question 7:What is the command we need to run in order to display the 'ftp' client help menu?**

Avswer: ftp -?

**Question 8:What is username that is used over FTP when you want to log in without having an account?**

Avswer: anonymous

**Question 9:What is the response code we get for the FTP message 'Login successful'?**

Avswer: 230

**Question 10:There are a couple of commands we can use to list the files and directories available on the FTP server. One is dir. What is the other that is a common way to list files on a Linux system.**

Avswer: ls

**Question 11:What is the command used to download the file we found on the FTP server?**

Avswer: get

**Submit the flag located on the FTP server**

- Ta truy cập vào ftp bằng tài khoản anonymous rồi get file flag.txt về .

![alt text](image.png)

```text
Flag: 035db21c881520061c53e0536e44f815
```

