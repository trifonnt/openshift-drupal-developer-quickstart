To install this quickstart, use the following command:
	
	rhc app create drupal php-5.4 mysql-5.5 --from-code=https://github.com/openshift-quickstart/openshift-drupal-developer-quickstart.git
	
Then visit http://app-domain.rhcloud.com/install.php to finish the installation.

**WARNING!!!**  
_If you are running this as a scaled application..._

Before you can run the installation script, you will need to ssh into your application and edit the ~/haproxy/conf/haproxy.cfg file  

    # Change this line
    option httpchk GET /
    # To this
    option httpchk GET /install.php  
	
and then restart your application, then you can proceed with the install by visiting http://app-domain.rhcloud.com/install.php 
After you have finished the install, you should swap it back to 

    option httpchk GET / 
