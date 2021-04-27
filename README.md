![Repo Image](https://github.com/lalantham/xrdp-on-linux/blob/main/img.png)
# Desktop Environment on CentOS & Debian {xRDP}

>On Centos Server

## 01 - Install Desktop

	1.1 - dnf update

	1.2 - sudo yum groupinstall "Server with GUI" 

	1.3 - sudo yum install epel-release

	1.4 - sudo yum install xrdp -y 

## 02 - Start Service

	2.1 - sudo systemctl enable xrdp
	
	2.2 - sudo systemctl start xrdp
	
	2.3 - sudo systemctl status xrdp
	
	2.4 - sudo nano /etc/xrdp/xrdp.ini > exec gnome-session
	
	2.5 - sudo systemctl restart xrdp

## 03 - Firewall Configuration

	3.1 - sudo firewall-cmd --new-zone=xrdp --permanent

	3.2 - sudo firewall-cmd --zone=xrdp --add-port=3389/tcp --permanent

	3.3 - sudo firewall-cmd --zone=xrdp --add-source=192.168.1.0/24 --permanent

	3.4 - sudo firewall-cmd --reload

  
>On Debian Server

## 01 - Install Desktop

	1.1 - sudo apt update

	1.2 - sudo apt install xfce4 xfce4-goodies xorg dbus-x11 x11-xserver-utils 

	1.3 - sudo apt install xrdp 

## 02 - Start Service

	2.1 - sudo systemctl enable xrdp
	
	2.2 - sudo systemctl start xrdp
	
	2.3 - sudo systemctl status xrdp
	
	2.4 - sudo adduser xrdp ssl-cert

	2.5 - sudo nano /etc/xrdp/xrdp.ini > exec startxfce4
	
	2.6 - sudo systemctl restart xrdp

## 03 - Firewall Configuration

	3.1 - sudo ufw allow from 192.168.1.0/24 to any port 3389

	3.2 - sudo ufw allow 3389
