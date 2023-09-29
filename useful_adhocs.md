# Ping remote hosts 
ansible all -m ping
# check hosts uptime 
ansible (specific host or group) -m shell -a "uptime"

# update the cache 
ansible all -m apt -a update_cache=true --become --ask-become-pass

#  install ubuntu 
ansible all -m apt -a name=tmux --become --ask-become-pass
ansible all -m apt -a name=vim-nox --become --ask-become-pass

# package install CentOS
ansible all -m yum -a "name=python3-pip" --become --ask-become-pass

# update the package 
ansible all -m apt -a "name=python3 state=latest" --become --ask-become-pass

# Upgrade all servers 
ansible all -m apt -a "upgrade=dist" --become --ask-become-pass

# install through playbook 
ansible-playbook --ask-become-pass install_apache.yml

# start the service
ansible (specific host or group)  -m service -a "name=service-name state=started"
# stop the service
ansible (specific host or group)  -m service -a "name=service-name state=stopped"

# Restart the service 
 ansible (specific host or group) -m systemd -a "name=service-name state=restarted"

# Check the disk space 
 ansible (specific host or group) -m command -a "df -h"

# check the memory 
 ansible (specific host or group) -m command -a "free -m"

# create user 
 ansible (specific host or group) -m user -a "name=newuser password=encrypted-password"

# Add user in to group 
 ansible (specific host or group) -m user -a "name=newuser groups=newgroup"

# remote the user 
 ansible (specific host or group) -m user -a "name=newuser groups=newgroup"

# set the file permission 
 ansible (specific host or group) -m file -a "path=/path/to/file mode=0644"

# Fetch Remote Logs
 ansible (specific host or group) -m fetch -a "src=/var/log/application.log dest=/local/destination/"
Retrieves a log file from a remote host.

#  Nginx with a Custom Site:
 ansible (specific host or group) -m shell -a "echo 'server { ... }' > /etc/nginx/sites-available/custom-site"
Explanation: Creates a custom Nginx site configuration.

# Rotate Log Files:
 ansible (specific host or group) -m shell -a "logrotate -f /etc/logrotate.d/application"
Explanation: Forces log file rotation.

# Deploy a Web Application:
 ansible (specific host or group) -m shell -a "git clone repo-url /var/www/app && chown -R www-data:www-data /var/www/app"
Explanation: Deploys a web application from a Git repository.

# Database Backup:
 ansible (specific host or group) -m shell -a "mysqldump -u username -p'password' dbname > /backup/db.sql"
Explanation: Creates a MySQL database backup.

# Apply Security Updates (APT):
 ansible (specific host or group) -m shell -a "unattended-upgrade"
Explanation: Automates the application of security updates on Debian-based systems.

# Manage Firewall Rules:
 ansible (specific host or group) -m shell -a "ufw allow 80/tcp"
Explanation: Adds a firewall rule to allow incoming HTTP traffic.

# Database User Management:
 ansible (specific host or group) -m shell -a "mysql -e 'CREATE USER ...;'"
Explanation: Manages database users and privileges.


# Docker Container Deployment:
 ansible (specific host or group) -m shell -a "docker run ..."
Explanation: Deploys a Docker container.

# Load Balancer Configuration:
 ansible (specific host or group) -m shell -a "configure-load-balancer.sh"
Explanation: Configures a load balancer.


