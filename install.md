---
title: Install the ownCloud Server
layout: default
---

## Install the ownCloud Server	
As an administrator, you can install the ownCloud server by completing the following steps:
1. Ensure that your system meets the minimum system requirements. For a list of these requirements, see [Verify the Prerequisites for Installation](./prereq.html). 

2. Download the [tarball](https://owncloud.org/download/#owncloud-server-tar-ball). 
   The file name is owncloud-x.y.z.tar.bz2, where x.y.z is the version number (for example, ownCloud-10.2.1.tar.bz2).

3. Download the corresponding checksum file (for example, owncloud-x.y.z.tar.bz2.md5 or
owncloud-x.y.z.tar.bz2.sha256).

4. Verify the MD5 or SHA256 sum, by running the following commands for your archive type:
```
    md5sum -c owncloud-x.y.z.tar.bz2.md5 < owncloud-x.y.z.tar.bz2
    
    sha256sum -c owncloud-x.y.z.tar.bz2.sha256 < owncloud-x.y.z.tar.bz2
    
    md5sum -c owncloud-x.y.z.zip.md5 < owncloud-x.y.z.zip
    
    sha256sum -c owncloud-x.y.z.zip.sha256 < owncloud-x.y.z.zip
```


5. Extract the archive contents. Run the appropriate unpacking command for your archive type to unpack to a single ownCloud directory:
```
    tar -xjf owncloud-x.y.z.tar.bz2
    
    unzip owncloud-x.y.z.zip 
```    


6. Copy the ownCloud directory to its destination:
```
    cp -r owncloud /var/www
```    

Step 3: [Configure the ownCloud Server Environment](./configure.html)
