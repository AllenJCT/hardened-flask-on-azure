#  Hardened Web Server on Microsoft Azure

This project demonstrates how to deploy, secure, and maintain a Linux-based web server using a Flask app hosted on an Azure virtual machine (VM). The server was hardened following best practices for system services, firewalls, SSH security, automatic updates, and application uptime.



## Project Summary

- **Cloud Provider:** Microsoft Azure
- **OS:** Ubuntu 22.04 LTS
- **App Stack:** Python 3, Flask, Gunicorn
- **Security Stack:** UFW, Fail2Ban, Unattended Upgrades
- **Web Server Exposure:** Port 5000 (via Gunicorn)
  

## Tools & Technologies Used

| Category         | Tools / Services                  |
|------------------|-----------------------------------|
| Cloud Platform   | Azure Virtual Machines (B1s)      |
| Web Framework    | Flask + Gunicorn                  |
| Firewall         | UFW (Uncomplicated Firewall)      |
| Intrusion Prevention | Fail2Ban                    |
| Auto Updates     | `unattended-upgrades`             |
| SSH Management   | OpenBSD Secure Shell (sshd)       |
| Service Control  | systemd services for Flask        |



## Screenshots & Explanation

### Azure VM Configuration  
Shows resource group, size, public IP, OS, and networking setup.

![Azure VM](./Azure%20VM.PNG)



### SSH Hardening  
Secure shell is fully enabled and actively monitored, ensuring secure remote access to the VM.

![SSH Status](./SSH%20Hardening.PNG)



### Firewall Rules via UFW  
Only ports 22 (SSH) and 5000 (Flask app) are open to the public.

![UFW](./UFW%20Status.PNG)



### Fail2Ban & Unattended Security Updates  
Fail2Ban monitors auth logs and blocks brute-force SSH attempts. Automatic security patches are installed via `unattended-upgrades`.

![Fail2ban](./Fail2ban%20%26%20Unattended%20Upgrades.PNG)



### Flask App Deployed as a Persistent Service  
The Flask app is deployed with Gunicorn and managed via `systemd` to survive restarts and shutdowns.

![FlaskApp Service](./FlaskApp%20Live.PNG)



### Public Web Access to Flask App  
Your Flask app is successfully running and accessible via the VM’s public IP on port 5000.

![Flask Live](./FlaskApp%20Live%20in%20browser.PNG)



## Security Practices Implemented

- Disabled unused ports via UFW
- Fail2Ban bans repeated failed SSH attempts
- Automatic security updates configured
- Flask deployed as a background system service
- Secure SSH key-based authentication (public key)
- Gunicorn for production-grade app serving



## Key Learnings

- How to launch and manage Linux VMs in Azure
- End-to-end web app deployment and hardening
- Configuring and validating firewall and service status
- Creating resilient infrastructure via systemd services
- Security-first approach for public-facing web servers



## Live Access (While VM Is Running)

**[http://172.200.57.142:5000](http://172.200.57.142:5000)**  
> (Note: this link only works if the Azure VM is running and port 5000 is open)

