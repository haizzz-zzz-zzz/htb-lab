**Question 1: In cybersecurity, isolated environments—like Pwnbox or the vulnerable target machines—are often VMs. What does VM stand for?**

Answer: Virtual Machine

**Question 2 : What tool do we use to interact with the operating system in order to issue commands via the command line, such as the one to start our VPN connection? It's also known as a console or shell.**

Answer: terminal
**Question 3 : What service do we use to form our VPN connection into HTB labs?**

Answer : openvpn

**Question 4: What tool do we use to test our connection to the target with an ICMP echo request?**

Answer : ping

**Question 5 : What is the name of the most common tool for finding open ports on a target?**

Answer : nmap

**Question 6 : What service do we identify on port 23/tcp during our scans?**

- Ta dùng lệnh 
```bash 
nmap -sC <ip>
```

Answer : telnet


**Question 7 : What username is able to log into the target over telnet with a blank password?**

Answer : root

**Submit the flag located in root's home directory.**

- Ta dùng lệnh dưới đấy để truy cập vào dịch vụ telnet
``` bash
telnet -l root <ip>
```
![alt text](image/1.png)

- Việc còn lại là tìm flag
![alt text](image/2.png)

```text
Flag: b40abdfe23665f766f9c61ecba8a4c19
```



