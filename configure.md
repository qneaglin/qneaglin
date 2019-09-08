## Configure the ownCloud Server Environment
### Configure the Apache Web Server
In order for your users to connect to the ownCloud server, you must configure Apache, which will enable users to connect to the ownCloud server. Complete the following steps:
1. Enable the mod_rewrite module:
```
    a2enmod rewrite
```
2. Enable the following recommend modules:
```
    a2enmod headers
    a2enmod env
    a2enmod dir
    a2enmod mime
```
   **NOTE:** If you want to use the OAuth2 app, then mod_headers must be installed and enabled.
   
3. Disable any server-configured authentication for ownCloud, as it uses Basic authentication internally for DAV services. If you have turned on authentication on a parent folder (for example, an AuthType Basic directive), you can disable the authentication specifically for the ownCloud entry. In the Apache configuration file, add the following line in the section:
```
    Satisfy Any
```
4. Restart Apache:
```
    service apache2 restart
```
5. If you run ownCloud in a subdirectory and want to use CalDAV or CardDAV clients, make sure you have configured the correct Service discovery URLs.
6. Multi-Processing Module (MPM) Apache prefork must be used. Do not use a threaded MPM like event or worker with mod_php, because PHP is currently [not thread safe](https://secure.php.net/manual/en/install.unix.apache2.php).

### Enable SSL/TLS 
You can use HTTP to access the ownCloud server. You can configure your system to use a secure HTTP connection, HTTPS. By doing so, SSL/TLS is used to encrypt all your server traffic and to protect user’s logins and data in motion. To enable security, see [SSL/TLS Strong Encryption: How-To](https://httpd.apache.org/docs/2.4/ssl/ssl_howto.html).

### Run the Installation Wizard
**NOTE:** It is strongly recommended that you protect the installation wizard by using [password authentication](https://cwiki.apache.org/confluence/display/httpd/PasswordBasicAuth) or [access control](https://httpd.apache.org/docs/2.4/howto/access.html). If the installer is unprotected, a malicious actor could interfere with your installation and block you out. Ensure that only you can access the web installer by securing it.

To run the installation wizard, complete the following steps:
1. Open a web browser from the machine that is hosting the Apache server and access the following URL:
```
   http://localhost/owncloud
```
2. Enter the adminstrator's user name and password.
3. Click **Finish setup**.

### Add Users
By default, the ownCloud web client is installed on the ownCloud server machine. When you log in to the web client with your administrator credentials, you can perform tasks such as creating user accounts. You can also use the ownCloud command line interface to perform administration tasks. For more information, see [Using the occ Command](https://doc.owncloud.com/server/10.2/admin_manual/configuration/server/occ_command.html).

To add user accounts to the ownCloud server, complete the following steps from the **default view** in the ownCloud web client:
1. Open a web browser and navigate to the ownCloud server HTTP address (for example, http://*hostname*/owncloud).
2. When prompted, enter the administrator's user name and password.
3. Navigate to the User Management page.
4. Enter the user name in the **Login Name** field.
5. Enter the user’s email address in the **E-mail** field.
6. Using the drop-down list, you can optionally assign the user to a group by selecting the group to which you want to add the user.
7. Click **Create**.
8. Optionally, you can enter the user’s full name in the **Full Name** field. 
   
   **NOTE:** The user can complete this step later. 

***Congratulations!*** You are now finished configuring your ownCloud server. There are additional steps you can perform for better performance and security. For more information, see [Manual Installation on Linux](https://doc.owncloud.org/server/10.2/admin_manual/installation/manual_installation.html). 

**Provide your users with the following information:**
* The Web address of the ownCloud server.
* Their user name and password for the ownCloud Server.
* A link to the Quickstart for Users (link to that section). 
