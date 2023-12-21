ssh config:
/etc/ssh/sshd_config <- edit what's required
Port 4242 <- this is also for -> /etc/ssh/ssh_config
PermitRootLogin no
Then: sudo service ssh restart


UFW
sudo ufw enable (if not installed, sudo apt install ufw)
sudo ufw allow 4242
sudo ufw status


sudo permissions:
sudo config: /etc/sudoers.d/sudoconfig | if not existing, touch
sudo logs: /var/log/sudo/sudo.log | if not existing, mkdir and touch

password requirements:
/etc/login.defs
PASS_MAX_DAYS 30
PASS_MIN_DAYS 2
PASS_WARN_AGE 7

sudo apt install libpam-pwquality
/etc/pam.d/common-password
(write there the password rules: minlen, ucredit, dcredit, lcredit maxrepeat,
reject_username, difok, enforce_for_root)


Cron schedules command executions in the background. To edit the script:

sudo contrab -u root -e (-e is to edit current user's cron jobs)



Useful commands: 

Super User mode: su -

Create user: sudo adduser <user>
Create group: sudo addgroup <group>

Add user to an existing group: sudo adduser <user> <group> or sudo usermod -aG <group> <user>

Know the users in the group and if it exists: getent group <group>

Know which groups exist: cat /etc/group
	recommended: cat /etc/group > file_to_read_easier.txt

Reboot: sudo systemctl reboot
Shutdown: sudo shutdowh -h now




ssh install and test:
sudo apt install openssh-server
sudo service ssh status

