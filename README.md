# **Upgrading thingsboard from 3.3.1PE to 3.3.2PE**

**Make a directory called tb-3.3.2PE and cd into it:**

```bash
mkdir tb-3.3.2PE && cd tb-3.3.2PE
```

**Download thingsboard 3.3.2PE Debian Package from the link below:**

```bash
wget https://dist.thingsboard.io/thingsboard-3.3.2pe.deb
```

**Stop Thingsboard service:**

```bash
sudo service thingsboard stop
```

**Install thingsboard-3.3.2pe:**

```bash
sudo dpkg -i thingsboard-3.3.2pe.deb
```

**Execute the upgrade script:**

```bash
sudo /usr/share/thingsboard/bin/install/upgrade.sh --fromVersion=3.3.1
```

**Start thingsboard service:**

```bash
sudo service thingsboard start
```

**P.S.: if you see message like below in the terminal you can just ignore it.**

```bash
Warning: The unit file, source configuration  file  or drop-ins of thingsboard.service changed on disk. Run 'systemctl daemon-reload' to reload units.
```

# **Upgrading thingsboard from 3.3.2PE to 3.3.3PE**

**Make a directory called tb-3.3.3PE and cd into it**

```bash
cd .. && mkdir tb-3.3.3PE && cd tb-3.3.3PE
```

**Download thingsboard 3.3.3PE Debian Package from the link below:**

```bash
wget https://dist.thingsboard.io/thingsboard-3.3.3pe.deb
```

**Stop Thingsboard service:**

```bash
sudo service thingsboard stop
```

**Install the Debian Package**

```bash
sudo dpkg -i thingsboard-3.3.3pe.deb
```

**You might encounter this message below while installing thingsboard-3.3.3pe**
![enter image description here](screenshots/upgrade-msg.png)

You can choose Y but it will replace old configuration with new configuration. So you need to backup your thingsboard.conf and thingsboard.yaml file.
**Also you can find the old configuration files in this folder**

```bash
/usr/share/thingsboard/conf
```

```bash
/usr/share/thingsboard/conf/thingsboard.conf.dpkg-old
/usr/share/thingsboard/conf/thingsboard.yml.dpkg-old
```

**Execute the upgrade script**

```bash
sudo /usr/share/thingsboard/bin/install/upgrade.sh --fromVersion=3.3.2
```

**Start thingsboard service**

```bash
sudo service thingsboard start
```

# **Upgrading thingsboard from 3.3.3PE to 3.3.4PE**

**Make a directory called tb-3.3.4PE and cd into it**

```bash
cd .. && mkdir tb-3.3.4PE && cd tb-3.3.4PE
```

**Download thingsboard 3.3.4PE Debian Package from the link below:**

```bash
wget https://dist.thingsboard.io/thingsboard-3.3.4pe.deb
```

**Stop Thingsboard service**

```bash
sudo service thingsboard stop
```

**Install the Debian Package**

```bash
sudo dpkg -i thingsboard-3.3.4pe.deb
```

**Execute the upgrade script**

```bash
sudo /usr/share/thingsboard/bin/install/upgrade.sh --fromVersion=3.3.3
```

**Start thingsboard service**

```bash
sudo service thingsboard start
```

# **Upgrading thingsboard from 3.3.4PE to 3.3.4.1PE**

**Make a directory called tb-3.3.4.1PE and cd into it**

```bash
cd .. && mkdir tb-3.3.4.1PE && cd tb-3.3.4.1PE
```

**Download Thingsboard 3.3.4.1PE Debian package:**

```bash
wget https://dist.thingsboard.io/thingsboard-3.3.4.1pe.deb
```

**Stop Thingsboard service**

```bash
sudo service thingsboard stop
```

**Install the Debian Package**

```bash
sudo dpkg -i thingsboard-3.3.4.1pe.deb
```

**Start thingsboard service**

```bash
sudo service thingsboard start
```

# **Upgrading thingsboard from version 3.3.4.1PE to 3.4PE**

**Make a directory called tb-3.3.4.1PE and cd into it**

```bash
cd .. && mkdir tb-3.4PE && cd tb-3.4PE
```

**Download Thingsboard 3.4PE Debian package:**

```bash
wget https://dist.thingsboard.io/thingsboard-3.4pe.deb
```

**Stop Thingsboard service**

```bash
sudo service thingsboard stop
```

**Install the Debian Package**

```bash
sudo dpkg -i thingsboard-3.4pe.deb
```

**Execute the upgrade script**

```bash
sudo /usr/share/thingsboard/bin/install/upgrade.sh --fromVersion=3.3.4
```

**Start thingsboard service**

```bash
sudo service thingsboard start
```

# Additional Logging

**To see thingsboard logs in realtime**

```bash
journalctl -fu thingsboard
```

# Place Jars and Lib Files

**Download the zip file from the link below:**

```bash
cd ..
```

```bash
wget https://raw.githubusercontent.com/mahbubul-alam-sabuj/tesenso.io-upgrade-guide/main/files.zip
```

![files inside files folder](screenshots/file-list.png)

**Install unzip:**

```bash
sudo apt install unzip
```

**Unzip files.zip:**

```bash
unzip files.zip
```

**You need to place files/extensions files to the folder below:**

```bash
/usr/share/thingsboard/extensions
```

```bash
sudo cp files/extensions/* /usr/share/thingsboard/extensions/
```

**And place libmbus.so file to /usr/share/thingsboard/bin/libs/ folder. For that you need to create a folder inside bin folder if libs folder does not exist in /bin folder.**

```bash
sudo mkdir /usr/share/thingsboard/bin/libs
```

**Then copy libmbus.so:**

```bash
sudo cp files/libmbus.so /usr/share/thingsboard/bin/libs
```

**Restart thingsboard service:**

```bash
sudo service thingsboard restart
```
