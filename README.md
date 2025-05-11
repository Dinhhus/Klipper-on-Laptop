# Klipper-on-Laptop

https://www.youtube.com/watch?v=Ib1Dd3rIE2I

Activate Or Deactivate The SSH Server
Activate The SSH Server
The SSH server is deactivated by default in Bitnami virtual machines. However, some applications (like GitLab) require SSH access to import code repositories.

To activate the SSH server, execute the commands below at the server console:

Debian
sudo rm -f /etc/ssh/sshd_not_to_be_run
sudo systemctl enable ssh
sudo systemctl start ssh
Ubuntu
sudo mv /etc/init/ssh.conf.back /etc/init/ssh.conf
sudo start ssh
Once enabled, configure key-based authentication or password-based authentication and then connect to the virtual machine over SSH.

Deactivate The SSH Server
The SSH server is deactivated by default in the Bitnami virtual machines. If you have activated it as described here, you can deactivate it following the opposite steps:

Debian
sudo systemctl stop ssh
sudo systemctl disable ssh
Ubuntu
sudo stop ssh
sudo mv /etc/init/ssh.conf /etc/init/ssh.conf.back

# Lối không kết nối được với moon racker

vào moonracker.conf của printer tương ứng thêm 127.0.0.1 và mục trust_clients:

[server]

host: 0.0.0.0

port: 7125

klippy_uds_address: /home/dinh/printer_printer11_data/comms/klippy.sock

[authorization]

trusted_clients:

    127.0.0.1
    
    192.168.0.0/16
