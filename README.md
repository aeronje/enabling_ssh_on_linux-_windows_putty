# enabling_ssh_on_linux_windows_putty
Basic SSH walkthrough for Windows users connecting to Linux.  This setup enables secure communication between your Windows host and Linux system over SSH (non-GUI/Purely terminal).


Download putty here and install to your Windows computer then proceed with steps 1 to 8 in your Linux machine: 

👉 https://www.putty.org/

1. Update your package list

👉 sudo apt update

2. Install the OpenSSH server

👉 sudo apt install openssh-server

3. Enable the SSH service to start on boot

👉 sudo systemctl enable ssh

4. Start the SSH service

👉 sudo systemctl start ssh


5. Allow SSH through the firewall

👉 sudo ufw allow ssh

6. Check firewall status

👉 sudo ufw status

/*
Expected output:
Status: inactive
(If it’s active, just make sure OpenSSH is allowed.)
*/

7. Verify that the SSH service is running

👉 sudo netstat -tulnp | grep ssh

/*
tcp        0      0 0.0.0.0:22            0.0.0.0:*               LISTEN      3398/sshd: /usr/sbin
tcp6       0      0 :::22                 :::*                    LISTEN      3398/sshd: /usr/sbin
The 0.0.0.0:22 and :::22 entries confirm that SSH is actively listening.
*/


8. Reboot the machine

👉 sudo reboot


9. From your Windows machine, open PuTTY

/*
Enter the hostname or IP address of your Linux machine.

Use port 22.

Choose SSH as the connection type.
*/

10. First-time connection notice

/*
You will get a prompt asking to accept the SSH key — click 'Accept'.
*/
