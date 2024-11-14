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

![Image 11-13-24 at 11 52 AM](https://github.com/user-attachments/assets/01da9e71-d99d-435f-a04c-57793f8c6e8b)
Let's disable the firewall by typing: <pre>netsh advfirewall set allprofiles state off</pre> into PowerShell

