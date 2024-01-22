# AssessableActivityWAD2023-24
	1.	sudo apt-get update
	2.	sudo apt-get install apache2
	3.	sudo apt-get install mysql-server php libapache2-mod-php php-mysql
	4.	sudo service mysql start
	5.	sudo mysql
		a.	mysql> USE mysql
		b.	mysql> UPDATE user SET plugin='mysql_native_password' WHERE User='root';
		c.	mysql> FLUSH PRIVILEGES;
		d.	mysql> exit
	6.	sudo service mysql restart
	7.	sudo apt-get install firefox
	8.	sudo apt-get install unzip
	9.	wget -U "Firefox" https://phpgurukul.com/?sdm_process_download=1&download_id=7210" -O download.zip
	10.	unzip download.zip
	11.	sudo mv 'Hostel management System Project'/ /var/
	12.	cd /var/'Hostel management System Project'/
	13.	sudo mv hostel/ /var/www/html/
	14.	sudo chown -R www-data /var/www/html/hostel/
	15.	sudo mysql
		a.	mysql> CREATE DATABASE hostel;
		b.	mysql> USE hostel;
		c.	mysql> source /var/'Hostel management System Project'/SQL File/hostel.sql
		d.	mysql> exit
	16.	cd /etc/apache2/sites-available/
	17.	sudo cp 000-default.conf 001-defaul.conf
	18.	cd ../sites-enabled/
	19.	sudo a2dissite 000-default.conf
	20.	sudo a2ensite 001-defaul.conf
	21.	sudo nano 001-defaul.conf
	
	001-default.conf content:
	
	<VirtualHost *:80>
        	# The ServerName directive sets the request scheme, hostname and port that
        	# the server uses to identify itself. This is used when creating
        	# redirection URLs. In the context of virtual hosts, the ServerName
        	# specifies what hostname must appear in the request's Host: header to
       		# match this virtual host. For the default virtual host (this file) this
        	# value is not decisive as it is used as a last resort host regardless.
	        # However, you must set it for any further virtual host explicitly.
		ServerName 44.219.58.19

	        ServerAdmin webmaster@localhost
		DocumentRoot /var/www/html/hostel/

        	# Available loglevels: trace8, ..., trace1, debug, info, notice, warn,
        	# error, crit, alert, emerg.
        	# It is also possible to configure the loglevel for particular
        	# modules, e.g.
        	#LogLevel info ssl:warn

        	ErrorLog ${APACHE_LOG_DIR}/error.log
        	CustomLog ${APACHE_LOG_DIR}/access.log combined

        	# For most configuration files from conf-available/, which are
        	# enabled or disabled at a global level, it is possible to
        	# include a line for only one particular virtual host. For example the
        	# following line enables the CGI configuration for this host only
        	# after it has been globally disabled with "a2disconf".
	        #Include conf-available/serve-cgi-bin.conf
	</VirtualHost>

	# vim: syntax=apache ts=4 sw=4 sts=4 sr noet
	
	
	22.	sudo service apache2 restart

	In browser we use the Static IP addres, which in my case is: 4.219.58.19 

