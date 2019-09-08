## Verify the Prerequisites for Installation

### Confirm the Specifications for Small Workgroups and Departments 
Ensure that your company meets the following criteria: 
* Number of users: Up to 150
* Storage size: 100 GB to 10TB
* High availability level
   * Zero-downtime backups via Btrfs snapshots 
   * Component failures lead to interruption of service 
   * Alternate backup scheme on other filesystems, including nightly backups with service interruption. For more information about backups, see **Backup** in [Scenario 1: Small Workgroups and Departments](https://doc.owncloud.org/server/10.2/admin_manual/installation/deployment_recommendations.html).

### Verify the System Requirements
Here is a list of requirements for a standard ownCloud installation. For more information, see [ownCloud Server Administration Manual](https://doc.owncloud.org/server/10.2/admin_manual/). 
* Operating system: RedHat Enterprise Linux 7.5 and 8 or SUSE Linux Enterprise Server 12
* Web server: Apache 2.4
* Database: MySQL or MariaDB with InnoDB storage engine (MyISAM is not supported)
* PHP 5.6 or higher
* Hosts that allow the administrator to have command line or Cron access

### Additional System Recommendations
It is recommended that you have one server running the ownCloud application, web server, and database server, as well as local storage. Below is a list of additional recommendations:
* Components: One server with at least 2 CPU cores, 16GB RAM, and local storage as needed.
* SSL Configuration:  The SSL termination is done in Apache. A standard SSL certificate is required to be installed according to the official Apache documentation.
* Authentication: User authentication using LDAP or Active Directory. For more information, see [User Authentication with LDAP](https://doc.owncloud.org/server/10.2/admin_manual/configuration/user/user_auth_ldap.html).
* Session Management: Local session management on the application server. PHP sessions are stored in a temporary filesystem, mounted at the operating system-specific session storage location.
You can find out where that is by running `grep -R ‘session.save_path’ /etc/php5` and then add it to the **/etc/fstab** file, for example:

    echo "tmpfs /var/lib/php5/pool-www tmpfs defaults,noatime,mode=1777 0 0" >> /etc/fstab``
* Memory Caching: A memory cache speeds up server performance, and ownCloud supports four of them. For more information, see [Configuring Memory Caching](https://doc.owncloud.org/server/10.2/admin_manual/configuration/server/caching_configuration.html).
* Storage: Local storage options.
* ownCloud Edition: Standard edition. For more information, see [Which Edition is Right for Me?](https://owncloud.com/standard-or-enterprise/). 

Step 2: [Install the ownCloud Server](./install.html)
