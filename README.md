# bWAPP Installation Guide

**Created by [Ahmed Hamdy](https://github.com/ahmedhamdy0x/) from [GenTiL Security](https://www.youtube.com/@gentil.security)**

## Installing bWAPP on Kali Linux & Ubuntu

### Download bWAPP from the Official Website
1. Go to [bWAPP download page](http://www.itsecgames.com/download.htm).
2. Click on "You can download bWAPP from here" to go to the download server.
3. Click on "Download Latest Version".

### Update Your System
```sh
sudo apt-get update -y
```

### Prepare the Environment
1. Go to the downloads directory:
    ```sh
    cd ~/Downloads
    ```
2. Create a new directory named `bwapp`:
    ```sh
    mkdir bwapp
    ```
3. List the downloads directory contents:
    ```sh
    ls
    ```
4. Move the bWAPP zip file to the `bwapp` directory:
    ```sh
    mv bWAPPv2.2.zip bwapp
    ```
5. Navigate to the `bwapp` directory:
    ```sh
    cd bwapp
    ```

### Extract bWAPP
1. Unzip the bWAPP zip file:
    ```sh
    unzip bWAPPv2.2.zip
    ```
2. Remove the bWAPP zip file:
    ```sh
    rm bWAPPv2.2.zip
    ```

### Install MySQL
1. Check if MySQL is installed:
    ```sh
    mysql -V
    ```
2. Update the system before installation:
    ```sh
    sudo apt-get update -y
    ```
3. Install MySQL if not installed:
    ```sh
    sudo apt install mysql-server
    ```
4. Start MySQL:
    ```sh
    sudo systemctl start mysql
    ```
5. Enable MySQL on startup:
    ```sh
    sudo systemctl enable mysql
    ```
6. Check MySQL status:
    ```sh
    sudo systemctl status mysql
    ```
    Press `Q` to exit.

### Install Apache2
1. Check if Apache2 is installed:
    ```sh
    apache2 -v
    ```
2. Update the system before installation:
    ```sh
    sudo apt-get update -y
    ```
3. Install Apache2 if not installed:
    ```sh
    sudo apt install apache2
    ```
4. Start Apache2:
    ```sh
    sudo systemctl start apache2
    ```
5. Enable Apache2 on startup:
    ```sh
    sudo systemctl enable apache2
    ```
6. Check Apache2 status:
    ```sh
    sudo systemctl status apache2
    ```
    Press `Q` to exit.

### Prepare bWAPP
1. Navigate to the bWAPP directory:
    ```sh
    cd bWAPP
    ```
2. Give all permissions to these directories:
    ```sh
    chmod 777 passwords/
    chmod 777 images/
    chmod 777 documents/
    ```

### Configure MySQL
1. Open MySQL to add a user and give privileges:
    ```sh
    sudo mysql
    ```
2. Create a user (replace `ahmed` and `pass123` with your desired username and password):
    ```sql
    CREATE USER 'ahmed'@'localhost' IDENTIFIED BY 'pass123';
    ```
3. Grant privileges to the user you created:
    ```sql
    GRANT ALL PRIVILEGES ON bWAPP.* TO 'ahmed'@'localhost';
    ```
4. Apply the changes immediately:
    ```sql
    FLUSH PRIVILEGES;
    ```
5. Exit MySQL:
    ```sh
    exit
    ```

### Edit bWAPP Database Credentials
1. Edit the `settings.php` file:
    ```sh
    mousepad admin/settings.php
    ```
2. Change `root` to the same username you created in MySQL:
    ```php
    $db_username = "ahmed";
    ```
3. Add the same password you created in MySQL:
    ```php
    $db_password = "pass123";
    ```
4. Save changes (Ctrl + S), and close the file.

### Important Step
1. Go to [this link](https://drive.google.com/file/d/1LaAB...) and copy the content (Ctrl + C).
2. Edit `install.php`:
    ```sh
    mousepad install.php
    ```
3. Select all (Ctrl + A), paste the copied content (Ctrl + V), save changes (Ctrl + S), and close the file.

### Move bWAPP Files to Local Server
1. Navigate to the parent directory:
    ```sh
    cd ../
    ```
2. Move all bWAPP files to the local server:
    ```sh
    sudo mv * /var/www/html/
    ```

### Install bWAPP Database
1. Open the following link in your browser and click to install the database:
    [http://localhost/bWAPP/install.php](http://localhost/bWAPP/install.php)

### Verify Database Installation
1. Open MySQL to check if the database has been added:
    ```sh
    sudo mysql
    ```
2. Show databases:
    ```sql
    SHOW DATABASES;
    ```
3. Exit MySQL:
    ```sh
    exit
    ```

### Login to bWAPP
1. Go to [http://localhost/bWAPP/](http://localhost/bWAPP/)
2. Login credentials:
    - Username: `bee`
    - Password: `bug`

---

## Installing bWAPP on Windows

### Download XAMPP
1. Go to the [XAMPP official website](https://www.apachefriends.org).
2. Click on "XAMPP for Windows" to download the latest version.
3. Follow the easy setup instructions.
4. Open XAMPP and enable Apache & MySQL services by pressing Start in front of each of them, then minimize it.

### Download bWAPP from the Official Website
1. Go to [bWAPP download page](http://www.itsecgames.com/download.htm).
2. Click on "You can download bWAPP from here" to go to the download server.
3. Click on "Download Latest Version".

### Prepare bWAPP
1. Create a new folder and move the bWAPP zip file to this folder.
2. Unzip the bWAPP file and remove the zip file.

### Move Files to Local Server
1. Select all files (Ctrl + A), and copy them (Ctrl + C).
2. Go to the local server path `C:\xampp\htdocs`.
3. Paste all files in this path (Ctrl + V).

### Edit install.php File (Important Step)
1. Right-click on the `install.php` file located in `C:\xampp\htdocs\bWAPP`.
2. Open with a text editor.
3. Go to [this link](https://drive.google.com/file/d/1LaAB...) and copy the content (Ctrl + C).
4. Back to the `install.php` file open with a text editor, select all (Ctrl + A), paste the copied content (Ctrl + V), save changes (Ctrl + S), and close the text editor.

### Install bWAPP Database
1. Open the following link in your browser and click to install the database:
    [http://localhost/bWAPP/install.php](http://localhost/bWAPP/install.php)

### Login to bWAPP
1. Go to [http://localhost/bWAPP/](http://localhost/bWAPP/)
2. Login credentials:
    - Username: `bee`
    - Password: `bug`

Congratulations! Go and have fun with more than 100 web vulnerabilities. Happy exploiting!
