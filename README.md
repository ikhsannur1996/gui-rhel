### Install GNOME Desktop on RHEL 8.4:

1. *Update Repository:**
   Update Repository:

   ```bash
   sudo dnf repolist
   sudo dnf update
   dnf group list
   ```

2. **Install GNOME Desktop:**
   Install the GNOME desktop environment and X Window System:

   ```bash
   sudo dnf groupinstall "Server with GUI"
   ```

3. **Set Default Target:**
   Set the default target to graphical:

   ```bash
   sudo systemctl set-default graphical
   ```

4. **Reboot:**
   Reboot the system to apply the changes:

   ```bash
   sudo reboot
   ```

### Install and Configure XRDP:
1. **Enable EPEL Repository:**
   Enable the EPEL repository, which contains additional packages including XRDP:

   ```bash
   sudo dnf install https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm
   sudo dnf repolist
   sudo dnf update
   ```

2. **Install XRDP and EPEL Package:**
   Install the xrdp package along with the `tigervnc-server` package from EPEL:

   ```bash
   sudo dnf install xrdp
   ```

3. **Start and Enable XRDP Service:**
   Start and enable the xrdp service:

   ```bash
   sudo systemctl start xrdp
   sudo systemctl enable xrdp
   ```

4. **Configure Firewall:**
   If you are using the default firewall (firewalld), open the RDP port (default is 3389) to allow incoming connections:

   ```bash
   sudo firewall-cmd --add-port=3389/tcp --permanent
   sudo firewall-cmd --reload
   ```

### Connect to RHEL using XRDP:

1. **Connect using XRDP:**
   Use an RDP client on your local machine to connect to the RHEL server. You can use Microsoft's Remote Desktop Connection on Windows or a client like Remmina on Linux.

   Connect to the RHEL system using its IP address or hostname.

2. **Login:**
   Enter the username and password of an existing user on the RHEL system.

3. **Access GNOME Desktop:**
   After a successful connection, you should see the GNOME desktop environment on your RHEL server.

Now, with the EPEL repository enabled, you can install XRDP and related packages. Adjust the firewall settings and other configurations based on your specific requirements, and consider security best practices when configuring remote access.

![image](https://github.com/ikhsannur1996/gui-rhel/assets/32507742/df5416c0-1fe1-482a-83b4-0de42b82d22c)

![image](https://github.com/ikhsannur1996/gui-rhel/assets/32507742/6ef5e82e-df6a-49d8-96b7-243666929a92)

