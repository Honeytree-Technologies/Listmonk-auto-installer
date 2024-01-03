# Listmonk Deployment Script

This script simplifies and streamlines the deployment of Listmonk and its associated components using Docker and bash scripting. 

As an open-source tool, it simplifies the installation of Listmonk on both new and existing servers, ideal for users of varying expertise. It manages the full setup process, including the activation of the admin user, and bolsters security by modifying the SSH port, setting up a firewall, and implementing Fail2Ban with progressive blocking rules. 

This unencrypted Bash script is free for use and distribution, with credit to Honeytree Technologies.

## About the Script

- **Language**: Bash
- **Deployment**: Uses Docker images for deploying Listmonk containers.
- **Configuration**:
  - SSL certificate generation via Let's Encrypt for designated domains and Nginx setup.

## Pre-requisites

- Server or VPS with a minimum of 4GB Ram, 2 vCPU, and 65 GB storage.
- Ubuntu v20.04 LTS pre-installed.
- Open ports:  443, 80 and SSH (Which you will choose in the script).
- Machine should have internet access for fetching packages and Docker images.
- Pre-register the machine's IP with the domain for SSL certificate generation.
- An email delivery service or SMTP server.

## Deployment Steps

1. SSH into the machine and assume root privileges.
2. Create and navigate to a directory: `mkdir auto_script && cd auto_script`.
    You can also use own directory.
3. Run the following command to start the script.
    ```bash
    curl -lO https://code.honeytreetech.com/fediverse/listmonk/auto-installer/auto_script.sh && sudo chmod +x auto_script.sh && ./auto_script.sh
    ```
4. Input the requested details as per the following table.
    | Name | Description | Mandatory | Optional | Default Value | 
    |------|---------|-----------|----------|---------------|
    | `admin_user`|Admin username| &checkmark; | &#10006;| &#10006; | 
    | `admin_password`|Admin password| &checkmark; | &#10006;| &#10006; | 
    |`db_user` | Database user | &checkmark;|  &#10006;| postgres| 
    |`db_password` | Database password| &checkmark;| &#10006;| pass_XXXXXXXXX (whereX is Random character)|
    |`domain_name` | Domain name| &checkmark;| &#10006;| &#10006;|
    |`ssh_port` | SSH port | &checkmark;| &#10006;| &#10006;|

                                
5. Accept terms of service as prompted.
6. Create Admin user and password during installation of script.
7. Follow further on-screen instructions to complete the setup.

## Post Deployment

- Access Listmonk via the provided domain with the given admin credentials.
- SSH port defaults to new port (which you entered in the script).
- fail2ban is activated with progressive blocking.

## Post-Installation Security Recommendations

Once you have successfully deployed Listmonk using this script, it's crucial to take additional steps to secure and harden your environment. 

Consider the following actions:

- **Regular Updates**: Ensure that all system packages and software are regularly updated to patch potential vulnerabilities.
- **Firewall Configuration**: Fine-tune your firewall settings to allow only necessary traffic and block potential threats.
- **User Access**: Limit or disable root access. Use sudo for administrative tasks and avoid using the root account for daily tasks.
- **Secure Passwords**: Implement strong password policies, and consider using password managers.
- **Two-Factor Authentication**: Where possible, enable 2FA for critical services and accounts.
- **Backup**: Regularly back up critical data and ensure backups are stored securely.
- **Monitoring & Logging**: Set up monitoring and logging to detect and alert on suspicious activities.
- **Application-Specific Security**: Explore and implement security best practices specifically tailored to Listmonk and any other applications you might be running.
- **Review and Audit**: Periodically review and audit your security settings and practices to ensure they are up-to-date with the latest threats and vulnerabilities.

It's essential to recognize that the security landscape is dynamic. Stay informed, and be proactive in securing your digital assets.




## CREDITS

This script and deployment guide have been made possible by [Honeytree Technologies, LLC](https://honeytreetech.com).

Please follow [@jeff@honeytree.social](https://honeytree.social/@jeff).
