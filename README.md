**Ansible Playbook Documentation**

**Overview**

This documentation outlines the Ansible playbooks created for automating different system administration tasks. Each playbook corresponds to a specific exercise aimed at automating various aspects of server management such as web server setup, user creation, database configuration, static website deployment, system updates, and scheduling tasks.

**Exercise 1: Install and Configure a Web Server**

**Objective:**

Automate the installation and configuration of a web server (Apache or Nginx), set up a custom homepage, and ensure the service is running.

**Requirements:**

- Install Apache or Nginx on the target machine.
- Create a file /var/www/html/index.html with the content:
  - "Welcome to \[Your Name\]'s server, managed by Ansible!"
- Ensure the web server service is started and enabled on boot.

**Playbook Tasks:**

1. Install Apache or Nginx using the apt or yum module.
2. Use the copy module to create the custom homepage (/var/www/html/index.html).
3. Ensure the web server service is running and enabled using the service module.
4. Verify that the web server is running and accessible.

**Commands Used:**

- apt/yum: Install Apache or Nginx.
- copy: Copy the index.html file.
- service: Ensure the web server is started and enabled.

**Results:**

- Apache or Nginx is installed.
- A custom homepage is deployed.
- The web server is running and accessible.

**Exercise 2: Create a User**

**Objective:**

Automate the creation of a user with SSH key-based login.

**Requirements:**

- Create a user named ansible_user.
- Set an encrypted password for the user.

**Playbook Tasks:**

1. Use the user module to create the ansible_user account.
2. Use the password option to set the encrypted password.

**Commands Used:**

- user: Creates the user and assigns the password.

**Results:**

- The ansible_user account is created with a password set using an encrypted hash.

**Exercise 3: Install and Configure a Database Server**

**Objective:**

Automate the setup of a MySQL or PostgreSQL server, create a database, and set up a user with access permissions.

**Requirements:**

- Install MySQL or PostgreSQL.
- Ensure the database service is running and enabled on boot.
- Create a database named ansible_db.
- Create a database user with permissions to access ansible_db.

**Playbook Tasks:**

1. Install MySQL or PostgreSQL using the apt or yum module.
2. Use the mysql_db or postgresql_db module to create the database.
3. Use the mysql_user or postgresql_user module to create a user and grant permissions.
4. Ensure the database service is running and enabled using the service module.

**Commands Used:**

- apt/yum: Install the database server.
- mysql_db/postgresql_db: Create the database.
- mysql_user/postgresql_user: Create the user and grant permissions.
- service: Ensure the database service is started and enabled.

**Results:**

- MySQL or PostgreSQL is installed.
- The ansible_db database is created.
- A user is created and granted access to the database.
- The database service is running and enabled on boot.

**Exercise 4: Deploy a Static Website**

**Objective:**

Automate the deployment of a static website.

**Requirements:**

- Install Apache or Nginx.
- Copy the website files from a local directory to /var/www/html/.
- Set correct file permissions on the website files.
- Restart the web server to apply the changes.
- Verify that the website is accessible.

**Playbook Tasks:**

1. Install Apache or Nginx using the apt or yum module.
2. Use the copy or unarchive module to copy the website files to /var/www/html/.
3. Use the file module to set the correct permissions on the website files.
4. Restart the web server using the service module.

**Commands Used:**

- apt/yum: Install Apache or Nginx.
- copy/unarchive: Deploy website files.
- file: Set file permissions.
- service: Restart the web server.

**Results:**

- Apache or Nginx is installed.
- Website files are deployed.
- The website is accessible via the web server.

**Exercise 5: System Update and Cleanup**

**Objective:**

Automate system maintenance tasks including updating packages, cleaning up unused packages, and ensuring adequate free disk space.

**Requirements:**

- Update all system packages.
- Clean up unused packages and old kernels.
- Ensure at least 1GB of free disk space.

**Playbook Tasks:**

1. Use the apt or yum module to update all system packages.
2. Use the shell or command module to remove unused packages and old kernels.
3. Verify the free disk space using the shell module and ensure it is greater than 1GB.

**Commands Used:**

- apt/yum: Update system packages.
- shell/command: Clean up unused packages and check disk space.

**Results:**

- The system is updated with the latest packages.
- Unused packages and old kernels are cleaned up.
- The system has at least 1GB of free disk space.

**Exercise 6: Set Up a Cron Job**

**Objective:**

Automate the scheduling of a periodic backup task.

**Requirements:**

- Create a cron job that runs /usr/local/bin/backup.sh every day at midnight.
- Ensure the script logs output to /var/log/backup.log.
- Verify the cron job is correctly configured.

**Playbook Tasks:**

1. Create the /usr/local/bin/backup.sh script using the copy module and ensure it is executable.
2. Use the cron module to schedule the cron job to run daily at midnight.
3. Use the shell module to verify that the cron job is correctly configured.

**Commands Used:**

- copy: Create the backup script.
- cron: Schedule the backup job.
- shell: Verify the cron job configuration.

**Results:**

- A cron job is scheduled to run the backup script daily at midnight.
- The script's output is logged to /var/log/backup.log.
- The cron job is correctly configured.

**Conclusion**

This documentation outlines the six key playbooks created for automating various system administration tasks using Ansible. These playbooks cover tasks ranging from web server configuration to periodic backups, ensuring efficient system management and maintenance across multiple servers.
