# Jenkins Docs

 ##  How To Install Jenkins on Ubuntu 20.04 

 ### **Prerequisites**

To follow this tutorial, you will need Oracle JDK 11 installed , <a href="https://www.digitalocean.com/community/tutorials/how-to-install-java-with-apt-on-ubuntu-20-04" target="_blank"> Java 11 installation . </a>
    
    P.S : Oracle jdk 14 is not supported right now by Jenkins .

### **Step 1 — Installing Jenkins**  :

 * First, add the repository key to the system:

    ```bash
    wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
    ```
    After the key is added the system will return with OK.


 *  Next, let’s append the Debian package repository address to the server’s sources.list:

    ```bash
    sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'

    ```
 * After both commands have been entered, we’ll run update so that apt will use the new repository :
    
    ```bash
    sudo apt update
    ```
 * Finally, we’ll install Jenkins and its dependencies:
    
      ```bash
    sudo apt install jenkins
    ```

### **Step 2 —Starting Jenkins :**

 * Let’s start Jenkins by using systemctl:
    
    ```bash
    sudo systemctl start jenkins
    ```
 * Since systemctl doesn’t display status output, we’ll use the status command to verify that Jenkins started successfully:

    ```bash
    sudo systemctl status jenkins
    ```
 * If everything went well, the beginning of the status output shows that the service is active and configured to start at boot:
  
   Output
    
    ```bash
    ● jenkins.service - LSB: Start Jenkins at boot time
    Loaded: loaded (/etc/init.d/jenkins; generated)
    Active: active (exited) since Fri 2020-06-05 21:21:46 UTC; 45s ago
    Docs: man:systemd-sysv-generator(8)
    Tasks: 0 (limit: 1137)
    CGroup: /system.slice/jenkins.service
    ```

### **Step 3  —Setting Up Jenkins :**
   
* To set up your installation, visit Jenkins on its default port, 8080, using your server domain name or IP address: http://**your_server_ip_or_domain**:8080
 
    You should receive the Unlock Jenkins screen, which displays the location of the initial password:

    ![Unlock Jenkins](https://assets.digitalocean.com/articles/jenkins-install-ubuntu-1604/unlock-jenkins.png)

* In the terminal window, use the cat command to display the password: 
 
    ```bash
    sudo cat /var/lib/jenkins/secrets/initialAdminPassword
    ```

    Copy the 32-character alphanumeric password from the terminal and paste it into the Administrator password field, then click Continue.

* The next screen presents the option of installing suggested plugins or selecting specific plugins:

    ![Plugins installation1.1](https://assets.digitalocean.com/articles/jenkins-install-ubuntu-1804/customize_jenkins_screen_two.png)
 

* We’ll click the Install suggested plugins option, which will immediately begin the installation process :

    ![Plugins installation1.2](https://assets.digitalocean.com/articles/jenkins-install-ubuntu-1804/jenkins_plugin_install_two.png)

* When the installation is complete, you’ll be prompted to set up the first administrative user :

     ![Admin Setup ](https://assets.digitalocean.com/articles/jenkins-install-ubuntu-1804/jenkins_create_user.png)

* You’ll receive an Instance Configuration page that will ask you to confirm the preferred URL for your Jenkins instance. Confirm either the domain name for your server or your server’s IP address (http://localhost:8080/  in case if you're working locally ):

     ![Instance configuration ](https://assets.digitalocean.com/articles/jenkins-install-ubuntu-1804/instance_confirmation.png)

* After confirming the appropriate information, click Save and Finish. You’ll receive a confirmation page confirming that “Jenkins is Ready!”: 

     ![Jenkins is ready ](https://assets.digitalocean.com/articles/jenkins-install-ubuntu-1804/jenkins_ready_page_two.png)

* Click Start using Jenkins to visit the main Jenkins dashboard ,  At this point, you have completed a successful installation of Jenkins.

