# Install Tomcat Steps
The steps below are for installing Apache Tomcat on Debian but they can be adapted to Ubuntu as well since Ubuntu is from the Debian family of distros.

## List available tarballs on Oracle download mirrors
=> curl -s http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html | grep "otn-pub" | cut -d \" -f12


http://download.oracle.com/otn-pub/java/jdk/8u144-b01/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-linux-arm32-vfp-hflt.tar.gz
http://download.oracle.com/otn-pub/java/jdk/8u144-b01/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-linux-arm64-vfp-hflt.tar.gz
http://download.oracle.com/otn-pub/java/jdk/8u144-b01/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-linux-i586.rpm
http://download.oracle.com/otn-pub/java/jdk/8u144-b01/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-linux-i586.tar.gz
http://download.oracle.com/otn-pub/java/jdk/8u144-b01/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-linux-x64.rpm
http://download.oracle.com/otn-pub/java/jdk/8u144-b01/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-linux-x64.tar.gz
http://download.oracle.com/otn-pub/java/jdk/8u144-b01/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-macosx-x64.dmg
http://download.oracle.com/otn-pub/java/jdk/8u144-b01/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-solaris-sparcv9.tar.Z
http://download.oracle.com/otn-pub/java/jdk/8u144-b01/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-solaris-sparcv9.tar.gz
http://download.oracle.com/otn-pub/java/jdk/8u144-b01/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-solaris-x64.tar.Z
http://download.oracle.com/otn-pub/java/jdk/8u144-b01/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-solaris-x64.tar.gz
http://download.oracle.com/otn-pub/java/jdk/8u144-b01/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-windows-i586.exe
http://download.oracle.com/otn-pub/java/jdk/8u144-b01/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-windows-x64.exe
http://download.oracle.com/otn-pub/java/jdk/8u144-b01-demos/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-linux-arm32-vfp-hflt-demos.tar.gz
http://download.oracle.com/otn-pub/java/jdk/8u144-b01-demos/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-linux-arm64-vfp-hflt-demos.tar.gz
http://download.oracle.com/otn-pub/java/jdk/8u144-b01-demos/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-linux-i586-demos.rpm
http://download.oracle.com/otn-pub/java/jdk/8u144-b01-demos/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-linux-i586-demos.tar.gz
http://download.oracle.com/otn-pub/java/jdk/8u144-b01-demos/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-linux-x64-demos.rpm
http://download.oracle.com/otn-pub/java/jdk/8u144-b01-demos/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-linux-x64-demos.tar.gz
http://download.oracle.com/otn-pub/java/jdk/8u144-b01-demos/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-macosx-x86_64-demos.zip
http://download.oracle.com/otn-pub/java/jdk/8u144-b01-demos/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-solaris-amd64-demos.tar.Z
http://download.oracle.com/otn-pub/java/jdk/8u144-b01-demos/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-solaris-amd64-demos.tar.gz
http://download.oracle.com/otn-pub/java/jdk/8u144-b01-demos/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-solaris-sparcv9-demos.tar.Z
http://download.oracle.com/otn-pub/java/jdk/8u144-b01-demos/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-solaris-sparcv9-demos.tar.gz
http://download.oracle.com/otn-pub/java/jdk/8u144-b01-demos/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-windows-i586-demos.zip
http://download.oracle.com/otn-pub/java/jdk/8u144-b01-demos/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-windows-x64-demos.zip

## Pick the x64 Linux tarball
curl -LOb "oraclelicense=a" http://download.oracle.com/otn-pub/java/jdk/8u144-b01/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-linux-x64.tar.gz

## Make a folder for java-jdk HOME and untar jdk there
mkdir /opt/java-jdk
tar -C /opt/java-jdk -xvzf jdk-8u131-linux-x64.tar.gz


## Set Oracle Java JDK as default on your system
=> update-alternatives --install /usr/bin/java java /opt/java-jdk/jdk1.8.0_144/bin/java 1
 update-alternatives --install /usr/bin/javac javac /opt/java-jdk/jdk1.8.0_144/bin/javac 1

Confirm as follows :
root@ ~ () $  
=> update-alternatives --list java
/opt/java-jdk/jdk1.8.0_144/bin/java
root@ ~ () $  
=> update-alternatives --list javac
/opt/java-jdk/jdk1.8.0_144/bin/javac

## Check Java version
=> java -version
java version "1.8.0_144"
Java(TM) SE Runtime Environment (build 1.8.0_144-b01)
Java HotSpot(TM) 64-Bit Server VM (build 25.144-b01, mixed mode)

## Download Tomcat tarball
=> wget http://apache.mirror.globo.tech/tomcat/tomcat-9/v9.0.0.M26/bin/apache-tomcat-9.0.0.M26.tar.gz

## List files
=> ls -rlt
total 259416
-rw-r--r--  1 root root   9376594 Aug  2 21:01 apache-tomcat-9.0.0.M26.tar.gz
-rw-r--r--  1 root root 185515842 Sep 25 22:32 jdk-8u144-linux-x64.tar.gz

## Make a dedicated tomcat user to run tomcat server
=> useradd -rs /bin/false tomcat

## Make folder for tomcat HOME, i.e. CATALINA_HOME
mkdir /opt/tomcat

## Extract tarball to CATALINA_HOME

=> tar -C /opt/tomcat/ -xvzf apache-tomcat-9.0.0.M26.tar.gz

## Make a symlink from tomcat-latest

=> ln -s /opt/tomcat/apache-tomcat-9.0.0.M26/ /opt/tomcat/tomcat-latest

## Make tomcat user the owner of the entire directories
=> chown -R tomcat.tomcat /opt/tomcat/tomcat-latest /opt/tomcat/apache-tomcat-9.0.0.M26

## Create startup script

Next, create systemd startup script /etc/systemd/system/tomcat.service pointing to our new /opt/java-jdk and /opt/tomcat/tomcat-latest.

Below you can find the content of new /etc/systemd/system/tomcat.service systemd file:
[Unit]
Description=Tomcat9
After=network.target

[Service]
Type=forking
User=tomcat
Group=tomcat

Environment=CATALINA_PID=/opt/tomcat/tomcat-latest/tomcat8.pid
Environment=TOMCAT_JAVA_HOME=/usr/bin/java
Environment=CATALINA_HOME=/opt/tomcat/tomcat-latest
Environment=CATALINA_BASE=/opt/tomcat/tomcat-latest
Environment=CATALINA_OPTS=
Environment="JAVA_OPTS=-Dfile.encoding=UTF-8 -Dnet.sf.ehcache.skipUpdateCheck=true -XX:+UseConcMarkSweepGC -XX:+CMSClassUnloadingEnabled -XX:+UseParNewGC -XX:MaxPermSize=128m -Xms512m -Xmx512m"

ExecStart=/opt/tomcat/tomcat-latest/bin/startup.sh
ExecStop=/bin/kill -15 $MAINPID

[Install]
WantedBy=multi-user.target

##  Reload Tomcat
Lastly, reload systemd, start and enable tomcat to start after reboot:
=> systemctl daemon-reload
=> systemctl start tomcat
=> systemctl enable tomcat

## Access Tomcat
The last step is to confirm that Tomcat is up and running. Tomcat should be now listening on port 8080:
=> ss -ant | grep 8080
LISTEN     0      100         :::8080
To access tomcat navigate your browser to an IP address of you new Tomcat server. Example http://10.1.1.125:8080/

## Set the following user and role in $CATALINA_HOME/conf/tomcat-users.xml
<role rolename="manager-gui"/>
<user username="admin" password="admin" roles="manager-gui"/>

# Gotchas
https://stackoverflow.com/questions/36566401/severe-could-not-contact-localhost8005-tomcat-may-not-be-running-error-while
https://stackoverflow.com/questions/14271828/cannot-start-tomcat-7-server-java-net-bindexception-address-already-in-use/14271856

# Links
https://linuxconfig.org/how-to-install-tomcat-9-on-debian-9-stretch-linux
