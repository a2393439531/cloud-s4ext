---
title: "Week 1, Unit 6: Getting Started: SAP S/4HANA System Setup"
permalink: /week-1/unit-6/
excerpt: "In this unit you will install and setup the required development tools to implement all the S/4HANA Extensions of the Business Scenario described in this course."
header:
  overlay_color: "#333"
layout: single
sidebar:
  nav: "week-1"
---

<a name="step-1-1-top"/><a name="step-1-2-top"/><a name="step-1-3-top"/><a name="step-2-1-top"/><a name="step-2-2-top"/><a name="step-2-3-top"/><a name="step-2-4-top"/><a name="step-2-5-top"/><a name="step-3-1-top"/><a name="step-3-2-top"/><a name="step-3-3-top"/><a name="step-4-1-top"/><a name="step-4-2-top"/><a name="step-4-3-top"/><a name="step-4-4-top"/><a name="step-5-top"/><a name="step-6-1-top"/><a name="step-6-2-top"/><a name="step-6-3-top"/><a name="step-6-4-1-top"/><a name="step-6-4-2-top"/><a name="step-6-5-1-top"/><a name="step-6-5-2-top"/>

{% include toc %}

**Overview:**

<img src="./images/overview.png" alt="" />

**Role:**

-   IT administrator
-   SAP Basis administrator

**Systems, Tools, Services:**

-   Oracle VM VirtualBox (VirtualBox)
-   openSUSE Leap 42.1 Linux OS (VM OS)
-   SAP NetWeaver AS ABAP 7.50 SP02 (NetWeaver AS ABAP)
-   SAP GUI client

## Step 1: Preparation Steps

The _SAP NetWeaver AS ABAP_ system which is used in this course has to be installed on a 64 bit Linux Operating System (OS).
To enable also users working with Windows or Mac OS X operation system to install the needed ABAP system, we describe here how to make use of VirtualBox, where the ABAP system then is installed and run on a Linux Virtual Machine (VM).

> **Hint:** If you have already a 64 bit Linux OS then you can skip the described downloads and installation of VirtualBox (1.1 and 2.1) and Linux (1.2 and 2.3) and just download the ABAP installation files (1.3).

**System Requirements:**

Make sure that you have on your PC/Laptop or Macbook:

1.  At least **8 GB of RAM** (better 16 GB).
2.  At least **100 GB of free disk space**.

The tutorial has been tested to work for _Windows_ and _OS X_. Most of the written tutorial including the screenshots has been made on Windows, whereas the video presentation was done on an OS X (Macbook).

As the tools installation files are partly very large (> several GB) first download them.

#### 1.1 Download Oracle VM VirtualBox

1.  Download the latest released version of Oracle VM VirtualBox (in short VirtualBox) from [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads) for your host operating system (host OS).
2.  On the opened download page click e.g. **x86/amd64** link to start the download of VirtualBox for Windows OS.

[Top](#step-1-1-top)

#### 1.2 Download Linux OS openSUSE

1.  Download Linux OS openSUSE Leap 42.1 (DVD installation medium, 64bit, released version) to your local machine from [https://software.opensuse.org/421/en](https://software.opensuse.org/421/en)

    > **Warning:** For this tutorial you must use Linux OS openSUSE Leap **42.1** that is not the latest openSUSE release. Make sure to download and install the **42.1** version.

2.  On the opened download page click **Direct Link** link to start the download.

[Top](#step-1-2-top)

#### 1.3 Download NetWeaver AS ABAP

1.  Open [https://tools.hana.ondemand.com/#abap](https://tools.hana.ondemand.com/#abap)
2.  Scroll down to section **SAP NetWeaver AS ABAP Developer Edition**
3.  Download all eight files `sap_netweaver_as_abap_750_sp02_ase_dev_edition.part<n>.rar` _(&lt;n> == 1,2,3,4,5,6,7,8)_ to your local machine.
4.  Use any unarchiver tool (e.g. WinRAR for Windows or Unarchiver for OS X) to extract the NetWeaver ABAP installation files somewhere to your local machine.

> **Warning:** Please check the file size of all the parts what you have downloaded. The file size is listed next to part rar files in [https://tools.hana.ondemand.com/#abap](https://tools.hana.ondemand.com/#abap). Each part file is around 1.5 GB.
>
> Please check that you have unarchived the rar files correctly. The total size of the extracted folder of the Netweaver AS ABAP Installation files is around 12+ GB.
> If you have partially downloaded or partially extracted the ABAP files and if you continue the installation, you will run into installation errors.

[Top](#step-1-3-top)

## Step 2: Install Linux VM in VirtualBox

#### 2.1 Install VirtualBox

1.  Use the VirtualBox installer you downloaded before (Step 1 - 1.1).
2.  You can keep all default settings of the installation wizard.
3.  After installation, you can start the VirtualBox Manager as follows:

    -   On a Windows host:  Open the standard **Programs** menu and click on the item in the **VirtualBox** group.
    -   On a Mac OS X host: In the **Finder**, double-click on the **VirtualBox** item in the **Applications** folder (You may want to drag this item onto your Dock).

    <img src="./images/w1-u6-s2/pic01--virtualbox.png" alt="" width="640px" />

[Top](#step-2-1-top)

#### 2.2 Create new Linux VM in VirtualBox

1.  Open **VirtualBox** Manager application
2.  Click **New** button to create a new Linux virtual machine (VM) image with the following settings:

      - Name: **SAP NetWeaver 7.50 SP02**
      - Type: **Linux** (Operating System)
      - Version: **openSUSE (64-bit)**
      - Click **Next**

      <img src="./images/w1-u6-s2/pic02--new-vm.png" alt="" width="640px" />

3.  On the next displayed wizard page

      - Change _Memory size_ to **6 GB** (6144 MB).
      - Click **Next**

      <img src="./images/w1-u6-s2/pic03--new-vm.png" alt="" width="640px" />

4.  On the next displayed wizard page

      - Make sure that **Create a virtual hard disk now** is selected.
      - Click **Create**

      <img src="./images/w1-u6-s2/pic04--new-vm.png" alt="" width="640px" />

5.  On the next opened wizard page

      - Make sure that **VDI** (Default) is selected as _Hard disk file type_.
      - Click **Next**

      <img src="./images/w1-u6-s2/pic05--new-vm.png" alt="" width="640px" />

6.  On the next displayed wizard page

    - Make sure that **Dynamically allocated** (Default) is selected as _Storage on physical hard disk_.
    - Click **Next**

      <img src="./images/w1-u6-s2/pic06--new-vm.png" alt="" width="640px" />

7.  On the next displayed wizard page

    - Change _File size_ to **80 GB** and keep the _File location_
    - Click **Create** to create **a new VM entry** with the specified settings.

      <img src="./images/w1-u6-s2/pic07--new-vm.png" alt="" width="640px" />

> **Result:** A new VM entry with Name _SAP NetWeaver 7.50 SP02_ is created on the left side of the VirtualBox Manager.
>
>    <img src="./images/w1-u6-s2/pic08--new-vm.png" alt="" width="640px" />

[Top](#step-2-2-top)

#### 2.3 Set boot installation file for Linux VM

1.  Right-click on the before created VM entry **SAP NetWeaver 7.50 SP02** to open context menu.
2.  Choose **Settings...** to open a settings dialog.
3.  Select the **Storage** item.
4.  In the Storage Tree section select the **Empty** node of _Controller:IDE_.

    <img src="./images/w1-u6-s2/pic09--boot-file.png" alt="" width="640px" />

5.  In the _Attributes_ section on the right side click on the **disk icon** to open a menu.
6.  Click on option **Choose Virtual Optical Disk File...** to open a file browser.

    <img src="./images/w1-u6-s2/pic10--boot-file.png" alt="" width="640px" />

7.  Select the openSUSE Linux OS .iso file that you downloaded in above Step 1 - 1.2.

    <img src="./images/w1-u6-s2/pic11--boot-file.png" alt="" width="640px" />

8.  Back on the _Settings_ dialog click **OK** to save settings.

    <img src="./images/w1-u6-s2/pic12--boot-file.png" alt="" width="640px" />

> **Result:** The VM has been prepared to boot from the specified _openSUSE DVD Image_ file as soon as it is started as described in the next section.

[Top](#step-2-3-top)

#### 2.4 Install openSUSE Linux OS on the VM

1.  In **VirtualBox Manager** select _SAP NetWeaver 7.50 SP02_ VM node and click **Start** button to start the new VM. It opens a new window **Oracle VM VirtualBox** and starts the virtual machine.

    <img src="./images/w1-u6-s2/pic13--install-linux.png" alt="" width="640px" />

2.  Quickly use your keyboard **DOWN key** to select the **Installation** menu item.

    <img src="./images/w1-u6-s2/pic14--install-linux.png" alt="" width="640px" />

3.  Enter **RETURN** key to start the VM OS installation of openSUSE Linux.
4.  During initialization:

5.  Click the icon of the **mouse pointer integration** message so that this message is never displayed again.

      <img src="./images/w1-u6-s2/pic15--install-linux.png" alt="" width="640px" />

6.  During installation:

7.  Set Keyboard and Language as desired - Course used **English** Language (and check your keyboard layout by typing some keys in **Keyboard Test** area).

      <img src="./images/w1-u6-s2/pic16--install-linux.png" alt="" width="640px" />

8.  Click **Next** to accept license and press **Next** in the screen with **Installation Options** by leaving the defaults.

      <img src="./images/w1-u6-s2/pic17--install-linux.png" alt="" width="640px" />

9.  In the next screen with _Suggested Partitioning_ click on **Edit Proposal Settings**.

      <img src="./images/w1-u6-s2/pic18--install-linux.png" alt="" width="640px" />

    -   For the field **File System for Root partitioning** , choose **Ext4** from the drop-down box.
    -   Uncheck **Propose Separate Home Partition**. This option is needed so that openSUSE Linux OS installation creates only one drive but does not 2 drives (Home and Extension) where Home has less space to continue the ABAP installation.
    -   Choose **Ok** to save settings.

10. Click **Next**.

    <img src="./images/w1-u6-s2/pic19--install-linux.png" alt="" width="640px" />

11. Select **Region** and **Timezone** and press **Next**.

    <img src="./images/w1-u6-s2/pic20--install-linux.png" alt="" width="640px" />

12. In Desktop Selection, choose Desktop of choice - Course used **KDE**.

    <img src="./images/w1-u6-s2/pic21--install-linux.png" alt="" width="640px" />

13. Click on **Next**.
14. Give User's full name, User name and Master password and click **Next**.

    <img src="./images/w1-u6-s2/pic22--install-linux.png" alt="" width="640px" />

15. In the _Installation Settings_ page , scroll down to find **Firewall and SSH** settings:

    -   Find the **disable** link to disable Firewall.
    -   Click on **enable** link to Enable SSH service.

    <img src="./images/w1-u6-s2/pic23--install-linux.png" alt="" width="640px" />

16. Click on **Install**.

    <img src="./images/w1-u6-s2/pic24--install-linux.png" alt="" width="640px" />

17. Click again **Install** on the opened _Confirm Installation_ dialog to really start the operating system installation.

    <img src="./images/w1-u6-s2/pic24b--install-linux.png" alt="" width="640px" />

18. After the installation finished (will take about 15-20 minutes) the system will reboot automatically.

19. The VM will come up with default start option **Boot from hard Disk**. If you do nothing it will
    automatically use this option after 60 seconds (you can also hit RETURN key to immediately boot).

      <img src="./images/w1-u6-s2/pic25--reboot-linux.png" alt="" width="640px" />

20. Next the **openSUSE Leap &lt;version>** is displayed as default option and after a few seconds automatically used.

    <img src="./images/w1-u6-s2/pic26--reboot-linux.png" alt="" width="640px" />

21. OpenSUSE might want to install quite some updates. It is up to you if you want to install them.
22. Finally there might be a logon page for the user you specified during the installation (the logon page will also come up after certain time of not working with the running VM). Enter your **password** and click **Unlock** to enter the KDE desktop of your installed Linux OS.

    > **Note:** This password is also the root password of the root user, which you have to enter frequently later in this unit.

    <img src="./images/w1-u6-s2/pic27--reboot-linux.png" alt="" width="640px" />

23. On the opened KDE desktop you can close the **Desktop Folder** window. Hover over the window and click the **X** icon (with tooltip _Remove_) in the lower right corner of the window.

    <img src="./images/w1-u6-s2/pic28--reboot-linux.png" alt="" width="640px" />

24. **For Laptop Users:** To keep the Linux VM session alive when not connected to a power supply you must change the default _Energy Saving_ system settings.

    > **Warning:** The default power setting is that the server will suspend your session after 10 minutes of inactivity when your laptop is on battery. This stops any access to the SAP system and also shuts down the network connection making the VM inaccessible.

25. On the KDE desktop open the Application menu in the bottom left corner. In the search field enter query string **power** and click result item  **Energy Saving**.

    <img src="./images/w1-u6-s2/pic31--install-linux-power.png" alt="" width="640px" />

26. In the _Energy Saving_ dialog select tab **On Battery**. Disable the checkbox **Suspend session**.
    Select tab **On Low Battery**. Again disable the checkbox **Suspend session**. Click on **Apply** and close the dialog with **Ok**.

      <img src="./images/w1-u6-s2/pic32--install-linux-power.png" alt="" width="640px" />

[Top](#step-2-4-top)

#### 2.5 Create VM Snapshot

After the Linux installation successfully finished you should create a snapshot to preserve this initial state. You can then always step back to this Snapshot VM state if your VM image gets spoiled for whatever reason.

1.  In the running **Oracle VM VirtualBox** window menu: Choose **Machine > Take Snapshot...**.

    <img src="./images/w1-u6-s2/pic29--snapshot.png" alt="" width="640px" />

2.  In the opened window enter **Initial Installation Snapshot** and click _OK_.

    <img src="./images/w1-u6-s2/pic30--snapshot.png" alt="" width="640px" />

> **Result:** Initial installation snapshot has been created.

[Top](#step-2-5-top)

## Step 3: VM Configurations - Proxy, Internet, shared Clipboard

#### 3.1 Configure Internet Proxy

If you are working behind a firewall with a proxy then you have to configure it as following, otherwise you skip this section 3.1.

##### 3.1.1 VM VirtualBox Setting

1.  In the running **Oracle VM VirtualBox** window menu: Choose **Input > Keyboard > Keyboard Settings...**.

    <img src="./images/w1-u6-s3/pic01--proxy-config.png" alt="" width="640px" />

2.  In the opened _Preferences_ window select _Proxy_ item.

    <img src="./images/w1-u6-s3/pic02--proxy-config.png" alt="" width="640px" />

3.  On _Proxy_ page

4.  Select **Manual Proxy Configuration** option.
5.  Enter your **Host** and **Port** to the corresponding input fields (e.g. **proxy.mycompany.com** and **8080**).
6.  Click **OK** to save the proxy settings.

##### 3.1.2 YaST Proxy Setting

1.  In the running **Oracle VM VirtualBox** click in the lower left corner of the window frame the **wheel with K** icon to open the KDE **Application Menu**.

    <img src="./images/w1-u6-s3/pic03--proxy-config.png" alt="" width="640px" />

2.  Navigate to **System > YaST** and click the YaST item.
3.  Enter your **root password** to open _YaST Control Center_ window.

    <img src="./images/w1-u6-s3/pic04--proxy-config.png" alt="" width="640px" />

4.  Enter **proxy** string into the search field.

    <img src="./images/w1-u6-s3/pic05--proxy-config.png" alt="" width="640px" />

5.  On the right side select the **Proxy** item of the found _Network Services_.
6.  On opened _Proxy Configuration_ page

7.  Select **Enable Proxy** checkbox
8.  Enter **HTTP Proxy URL** value, e.g. http://proxy.mycompany.corp:8080
9.  Select **Use the Same Proxy for All Protocols** checkbox
10. Click **Test Proxy Settings** to save the proxy settings.

    <img src="./images/w1-u6-s3/pic06a--proxy-config.png" alt="" width="640px" />

11. A **Proxy settings work successfully** popup should appear. Confirm it with **OK**.

    <img src="./images/w1-u6-s3/pic06b--proxy-config.png" alt="" width="640px" />

12. Click **OK** to save the proxy settings.

    <img src="./images/w1-u6-s3/pic06c--proxy-config.png" alt="" width="640px" />

13. Confirm the Successfully saved dialog with **OK**.

[Top](#step-3-1-top)

#### 3.2 Test Internet Connection

##### 3.2.1 Test Internet without Proxy

1.  Open again the KDE **Application Menu** (_wheel with K_ icon in lower left corner).

    <img src="./images/w1-u6-s3/pic07--test-proxy.png" alt="" width="640px" />

2.  Navigate to **Internet > Firefox** and click item to open the Firefox Web browser.

> **Note:** If you are accessing the Internet via a **proxy** then you will not see a Web page in Firefox before you executed the next [section 3.2.2](#test-internet-with-proxy)
> If you are not working with a **proxy** then you should already see a working opensuse default Web page which ensures that your Linux VM image can access the internet.
>
> **Warning:** Make sure that internet in Firefox is working, otherwise later steps will fail.

  <img src="./images/w1-u6-s3/pic08--test-proxy.png" alt="" width="640px" />

If you are working with a proxy, you have to configure Firefox to use this proxy as follows:

##### 3.2.2 Test Internet with Proxy

1.  Open **Firefox menu** in the upper right corner and click on **Preferences**.

    <img src="./images/w1-u6-s3/pic09--test-proxy.png" alt="" width="640px" />

2.  On the opened _Preferences_ page

3.  Choose **Advanced** item from left side icon bar.
4.  On the _Advanced_ page click **Network** tab.
5.  Click **Settings...** button

    <img src="./images/w1-u6-s3/pic10--test-proxy.png" alt="" width="640px" />

6.  On the opened **Connection Settings** dialog:

7.  Select **Manual Proxy configuration** option
8.  Enter your **HTTP Proxy** and **Port** value (e.g. _proxy_ and _8080_)
9.  Select **Use this proxy server for all protocols** option
10. Click **OK** to save the proxy settings.

    <img src="./images/w1-u6-s3/pic11--test-proxy.png" alt="" width="640px" />

After this you should see a working opensuse default Web page that works through your proxy.

[Top](#step-3-2-top)

#### 3.3 Enable bi-directional shared clipboard

Before you continue with the ABAP installation specific steps you should enable the bi-directional shared clipboard as follows.

1.  In the running **Oracle VM VirtualBox** window menu: Open **Devices > Shared Clipboard > Bidirectional**.

    <img src="./images/w1-u6-s3/pic12--clipboard.png" alt="" width="640px" />

2.  Click on the **Bidirectional** item so that it is enabled.

> **Hint:** With this enabled _bi-directional_ option you can now copy and paste from your host operating system to the VM image window and vice versa. This is very helpful as you can copy e.g. needed command lines from the tutorial description (web page on your host OS) into a bash window of your VM window.

[Top](#step-3-3-top)

## Step 4: VM Preparations for ABAP Installation

#### 4.1 Enable Network Access to Linux VM

1.  In **VirtualBox** Manager right-click on **SAP NetWeaver 7.50 SP02 VM** item to open context menu.

    <img src="./images/w1-u6-s4/pic01--vm-net-config.png" alt="" width="640px" />

2.  Choose **Settings...** to open a settings dialog.
3.  Select the **Network** item and do for selected **Adapter 1** tab the following:

4.  Enable Network Adapter: is **selected** (Default)
5.  Attached to: **NAT** (Default) is selected

    <img src="./images/w1-u6-s4/pic02--vm-net-config.png" alt="" width="640px" />

6.  Open **Advanced** node
7.  Click **Port Forwarding**

    <img src="./images/w1-u6-s4/pic03--vm-net-config.png" alt="" width="640px" />

8.  On the opened _Port Forwarding Rules_ dialog

    -   Click 6 times the **green plus** icon to create 6 rows of roles.
    -   Then enter the following values for the created roles.

    > **Hint:** Copy each value entry (e.g. 1. each Name, 2. Protocol, etc.) then double-click into the table field to get the edit focus and then paste the copied value. This is a tedious work to do but unfortunately there is no way to import these value from file.

    | Name         |Protocol    |Host-IP        |Host Port   |Guest IP     |Guest Port    |
    |--------------|------------|---------------|------------|-------------|--------------|
    | HTTP         |TCP         |127.0.0.1      |8000        |10.0.2.15    |8000          |
    | HTTPS        |TCP         |127.0.0.1      |44300       |10.0.2.15    |44300         |
    | SCC          |TCP         |127.0.0.1      |8443        |10.0.2.15    |8443          |
    | SAPGUI       |TCP         |127.0.0.1      |3200        |10.0.2.15    |3200          |
    | AiE          |TCP         |127.0.0.1      |3300        |10.0.2.15    |3300          |
    | SSH          |TCP         |127.0.0.1      |22          |10.0.2.15    |22            |

9.  Click **OK** to save the entered values.

    <img src="./images/w1-u6-s4/pic04--vm-net-config.png" alt="" width="640px" />

10. Click **OK** to save Network settings.

    <img src="./images/w1-u6-s4/pic05--vm-net-config.png" alt="" width="640px" />

[Top](#step-4-1-top)

#### 4.2 Prepare UUIDD Service

> **Hint:** UUIDD Installation will only work if VM has internet access as you tested successfully before in above Step 3 > 3.2.

##### 4.2.1 Install UUIDD

1.  In the running **Oracle VM VirtualBox** open the KDE **Application Menu**.

    <img src="./images/w1-u6-s4/pic06--uuidd.png" alt="" width="640px" />

2.  Navigate to **System > YaST** and click the YaST item.
3.  Enter your **root password** to open _YaST Control Center_ window.

    <img src="./images/w1-u6-s4/pic07--uuidd.png" alt="" width="640px" />

4.  The first list item **Software** is selected by default.
5.  On the right side click on **Software Management** from the items list.
6.  On the newly opened _YaST2_ page do the following

7.  Enter **uuidd** string into the search field and click **Search**.
8.  On the right side select the found **uuidd** Pack
9.  Click **Accept** to install _uuid daemon helper_ in YaST.

    <img src="./images/w1-u6-s4/pic08--uuidd.png" alt="" width="640px" />

10. On the **Installation Successfully Finished** page click **Finish** to get back to the YaST Control Center window.

##### 4.2.2 Start UUIDD

The installed UUIDD service will now be started by a command window, called _Konsole_, as follows.

1.  Open the KDE **Application Menu**.
2.  Navigate to **System > Konsole** and click on it to open a new bash window.

    <img src="./images/w1-u6-s4/pic09--uuidd.png" alt="" width="640px" />

    > **Hint:** If you right-click on the Konsole item you can choose **Add to Favorite** to create a shortcut icon in the KDE Application Menu.

3.  In the bash window execute **sudo service uuidd status** to check if the service is running
4.  All commands starting with 'sudo' will ask for root password (sudo means that the command is executed as root user)
5.  UUIDD status output should be **inactive (dead)** as you just installed the service.

    <img src="./images/w1-u6-s4/pic10--uuidd.png" alt="" width="640px" />

6.  Execute **sudo service uuidd start** to start the service (Will ask again for root password).

    <img src="./images/w1-u6-s4/pic11--uuidd.png" alt="" width="640px" />

7.  Execute **sudo service uuidd status** to check if the service is running

    > **Hint:** If you press UP and DOWN keys you receive the commands history you already executed in the Konsole window before.

8.  Status should now be active

[Top](#step-4-2-top)

#### 4.3 Prepare Network Setup

The ABAP installation later requires the hostname _vhcalnplci_. Due to that you will change now the existing hostname to that one.

1.  Change hostname

2.  Use the already opened **Konsole** and execute command **sudo vi /etc/hostname** (will ask for root password) to open the hostname file with the _vi_ editor, a screen-oriented text editor for Unix operating systems.

    <img src="./images/w1-u6-s4/pic12--hostname.png" alt="" width="640px" />

3.  Press **Esc** and **i** to switch the vi editor to _insert_ mode, i.e. change file content.

    <img src="./images/w1-u6-s4/pic13--hostname.png" alt="" width="640px" />

4.  Replace the existing hostname _linux-n1wt.suse_, i.e. delete the first line, with **vhcalnplci**.

    > **Hint:** Navigate in the _vi_ editor with **arrow keys** and then use **back DEL** key to delete the characters.

    <img src="./images/w1-u6-s4/pic14--hostname.png" alt="" width="640px" />

5.  Press **Esc** and **:wq** to save the changed file.

    <img src="./images/w1-u6-s4/pic15--hostname.png" alt="" width="640px" />

6.  Hit **ENTER** key to execute this _vi_ editor command and go back to the _Konsole_ bash window.

    <img src="./images/w1-u6-s4/pic16--hostname.png" alt="" width="640px" />

    > **Hint:** After pressing the _Esc_ the cursor will go to the bottom of the screen at a colon prompt. Write your file by entering **:w** and quit by entering **:q**. You can combine these to save and exit by entering **:wq**.

7.  Restart network to reload the new hostname and test it
8.  Execute **sudo rcnetwork restart**
9.  Execute **hostname** and see that the hostname output is **vhcalnplci**.

    <img src="./images/w1-u6-s4/pic17--hostname.png" alt="" width="640px" />

10. Define hosts
11. In the opened _Konsole_ execute command **sudo vi /etc/hosts** to open the vi editor for _hosts_ file.
12. Press **Esc** and **i** to switch again to _insert_ mode.
13. After the existing **127.0.0.1** entry add a the following new line entry

    -   **10.0.2.15 vhcalnplci vhcalnplci.dummy.nodomain**

        > **Hint:** Navigate in the _vi_ editor with **arrow keys** to the place where you want to paste the added entry.

    <img src="./images/w1-u6-s4/pic18--hostname.png" alt="" width="640px" />

14. Press **Esc** and **:wq** and hit **ENTER** key to save the changed file.
15. Restart network to set settings and test it
16. Execute **sudo rcnetwork restart**
17. Test setup with **ping vhcalnplci**
18. The ping output should look like
    -   **64 bytes from vhcalnplci (10.0.2.15): icmp_seq=1 ttl=64 time=0.041 ms**
19. Stop the ping output with **CRTL** and **C**.

    <img src="./images/w1-u6-s4/pic19--hostname.png" alt="" width="640px" />

[Top](#step-4-3-top)

#### 4.4 Mount _netweaver_ Installation Folder in Linux VM

Before you can start with the actual ABAP installation in next Step 5 the running _SAP NetWeaver 7.50 SP02 VM_ needs to get access to extracted ABAP installation files. For that you mount a _netweaver_ folder as follows:

##### 4.4.1 Setup a Shared Folder

1.  In **VirtualBox** Manager right-click on **SAP NetWeaver 7.50 SP02 VM** item to open context menu.

    <img src="./images/w1-u6-s4/pic20--shared.png" alt="" width="640px" />

2.  Choose **Settings...** to open a settings dialog.
3.  Select the **Shared Folders** item.

    <img src="./images/w1-u6-s4/pic21--shared.png" alt="" width="640px" />

4.  Click on the **folder icon with green plus** (with tooltip _Adds new shared folder_) to open _Add Share_ dialog.
5.  _Add Share_ Settings:
6.  Folder Path: Click dropdown list > Others... > navigate to location where you unrared the NetWeaver ABAP archives.
7.  Folder Name: **netweaver**
8.  Read-only: **not selected** (default)
9.  Auto-Mount: **not selected** (default)
10. Make Permanent: **not selected** (default)
11. Click **OK**

    <img src="./images/w1-u6-s4/pic22--shared.png" alt="" width="640px" />

12. Click on **OK**.

    <img src="./images/w1-u6-s4/pic23--shared.png" alt="" width="640px" />

##### 4.4.2 Mount _netweaver_ folder to the Shared Folder

1.  Use already opened **Konsole** or open a new one (KDE **Application Menu** and navigate to **System > Konsole**).
2.  Execute command **mkdir netweaver** to create a new _netweaver_ folder

    > **Hint:** Execute **pwd** (print working directory) so that you know at which location you created this folder

    <img src="./images/w1-u6-s4/pic24--shared.png" alt="" width="640px" />

3.  Execute command **sudo mount -t vboxsf netweaver netweaver** (will ask for root password) to mount the created _netweaver_ folder on the VM with the before setup _Shared Folder_ (also named netweaver).

    <img src="./images/w1-u6-s4/pic25--shared.png" alt="" width="640px" />

4.  Execute command **cd netweaver** to navigate into the netweaver folder.
5.  Execute command **ls -l** to list the contents of the mounted folder. The contents are the extracted ABAB installation files to which you running VM has now access to.

Now you have everything prepared for the actual NetWeaver ABAP installation which you will do in the following Step 5.

[Top](#step-4-4-top)

## Step 5: Install SAP NetWeaver AS ABAP on Linux VM

1.  Use already opened **Konsole** or open a new one (KDE **Application Menu** and navigate to **System > Konsole**).
2.  Inside the mounted **netweaver** folder execute command **ls -l** to see that amoungst other files and folders the **install.sh** is available.
3.  Execute **chmod +x install.sh** to enable the execution of the installer.

    <img src="./images/w1-u6-s5/pic01--install.png" alt="" width="640px" />

4.  Execute **sudo ./install.sh** (will ask for root password) to start installation with
5.  Hit **Enter** key when _Hit enter to continue_ message appears.
6.  Hit **Space** key until _Do you agree to the above license_ message comes up.
7.  Read and accept the license agreement and confirm with **yes**, if you agree to the terms of condition.
8.  When prompted for the OS users password, choose a strong password for your ABAP OS users (Users like _npladm_). The password should be minimum length 8 characters with a combination of Camel case alphabets, numbers and special characters.
9.  Installation will start and take about 20 minutes.

    > **Note:** The install script can fail if you choose a very simple password. So please choose a stronger password with a combination of Camel case alphabets, numbers and special characters for the install script.

      <img src="./images/w1-u6-s5/pic02--install.png" alt="" width="640px" />

10. If the installation was successful, you should see the following message:

        Instance on host vhcalnplci started
        Installation of NPL successful

    <img src="./images/w1-u6-s5/pic03--install.png" alt="" width="640px" />

[Top](#step-5-top)

## Step 6: Run and Test SAP NetWeaver AS ABAP

#### 6.1 Start NetWeaver AS ABAP

With the following steps you make sure that the AS ABAP is up and running.

##### 6.1.1 Startup ABAP

1.  Use already opened **Konsole** or open a new one (KDE **Application Menu** and navigate to **System > Konsole**).
2.  Execute the following three commands to start and check the installed NetWeaver AS ABAP
3.  Execute **su -l npladm** (will ask for _NetWeaver AS ABAP_ **system password**) to switch to _NetWeaver Admin_ user, so that you act in this Konsole as this user and its permissions.

    > **Hint:** This user has been created during the ABAP installation in above Step 5 and only this user has the permissions to start, stop and check the status of the installed ABAP on the VM.
    >
    > **Note:** The `-` (or `-l`) parameter for the **su** (_substitue user_) command creates a shell environment the same as if you had logged in with that different user.  Without the `-l` parameter, you're running the **sapcontrol** command in the shell environment of the current user.

4.  Execute **startsap ALL** to start the ABAP server (if not already).
5.  Execute **sapcontrol -nr 00 -function GetProcessList** to check that the processes are running and are all **GREEN**

    > **Note:** As 'startsap ALL' can take some time repeat the command execution a few times until all four prosseses (IGS Watchdog, Dispatcher, Gateway, ICM) are GREEN

    The result should look as follows:

        GetProcessList
        OK
        name, description, dispstatus, textstatus, starttime, elapsedtime, pid
        igswd_mt, IGS Watchdog, GREEN, Running, 2017 ... , ... , ...
        disp+work, Dispatcher, GREEN, Running, 2017 ... , ... , ...
        gwrd, Gateway, GREEN, Running, 2017 ... , ... , ...
        icman, ICM, GREEN, Running, 2017 ... , ... , ...

    <img src="./images/w1-u6-s6/pic01--start-abap.png" alt="" width="640px" />

##### 6.1.2 Create a new VM Snapshot

After the ABAP installation successfully finished you should create a snapshot to preserve this state as you already did after the Linux installation. You can then always step back to this Snapshot VM state if your VM image gets spoiled for whatever reason.

1.  In the running **Oracle VM VirtualBox** window menu: Choose **Machine > Take Snapshot...**.

    <img src="./images/w1-u6-s6/pic02--snapshot-abap.png" alt="" width="640px" />

2.  In the opened window enter **ABAP Installation Snapshot** and click _OK_.

    <img src="./images/w1-u6-s6/pic03--snapshot-abap.png" alt="" width="640px" />

> **Result:** ABAP installation snapshot has been created.

[Top](#step-6-1-top)

#### 6.2 Install SAP GUI Client

The SAP GUI Client is the front-end application to connect to SAP Back-End systems like the NetWeaver ABAP you install before on a Linux VM on your local PC (Windows or OS X).

> **Hint:** If you have already a SAP GUI Client installed on your computer, you can use it and skip the installation. Continue then with _Add and open new System_.

##### 6.2.1 Install SAP GUI Client

1.  On your PC or notebook (Windows or OS X) go to the location where you unarchived the NetWeaver ABAP installation files and find the folder **client**

**For Windows:**

1.  Go to folder /client/**SAPGUI4Windows**
2.  Right-click on `SAP_GUI_7.40_PL1_20150108_1618.exe` and choose **Run as administrator** from context menu to launch the installation wizard.

    <img src="./images/w1-u6-s6/pic04--gui.png" alt="" width="640px" />

3.  Confirm _User Account Control_ dialog with **OK**
4.  Click through the installation wizard and keep the defaults but make sure that **SAPGUI 7.40 PL1** checkbox is selected.
5.  The wizard should finish with a success message which you confirm with **Close**.

    <img src="./images/w1-u6-s6/pic05--gui.png" alt="" width="640px" />

    > **Result:** The **/SAP/FrontEnd/SAPgui/saplogon.exe** file inside windows program files folder has been created to launch **SAP GUI** application.

**For Mac OS X:**

1.  Go to folder /client/**JavaGUI**
2.  Double-click on `PlatinGUI740_8-OSX.JAR` file to run it with _JAR Launcher.app_ so that the SAP GUI installer opens.

    <img src="./images/w1-u6-s6/pic06--gui-mac.png" alt="" width="640px" />

3.  Click **Next** to open _Readme_ page.
4.  Click again **Next** to open _Installation Options_ page.
5.  Keep the defaults and click **Install** to start the installation.
6.  The wizard should finish with a success message which you confirm with **Close**.

    <img src="./images/w1-u6-s6/pic07--gui-mac.png" alt="" width="640px" />

##### 6.2.2 Add and open new System

**For Windows:**

1.  Open the **SAP Logon** application (also known as _SAP GUI_) from Windows Start menu.

    <img src="./images/w1-u6-s6/pic08--gui-sys.png" alt="" width="640px" />

2.  Add your local NetWeaver ABAP installation as new system:
3.  Click **New** icon from the _SAP GUI_ toolbar to open **Create New System Entry** wizard.

    <img src="./images/w1-u6-s6/pic09--gui-sys.png" alt="" width="640px" />

4.  Select **User Specified System** entry and click **Next**.

    <img src="./images/w1-u6-s6/pic10--gui-sys.png" alt="" width="640px" />

5.  On the next page enter the following

    -   Description : **Local NetWeaver**
    -   Application Server: **127.0.0.1**
    -   Instance Number : **00**
    -   System ID: **NPL**

        <img src="./images/w1-u6-s6/pic11--gui-sys.png" alt="" width="640px" />

6.  Click **Finish** to create a new system entry.

    <img src="./images/w1-u6-s6/pic12--gui-sys.png" alt="" width="640px" />

7.  Logon to the new system
8.  Right-click on the newly created entry **Local NetWeaver** and click on **Log on** option of the context menu.

    <img src="./images/w1-u6-s6/pic13a--gui-sys.png" alt="" width="640px" />

9.  To log in to the system for the first time, use the following credentials:
10. Client: **001**
11. User: **Developer**
12. Password: **Appl1ance**
13. Language: **EN**

    <img src="./images/w1-u6-s6/pic13b--gui-sys.png" alt="" width="640px" />

14. Click green **Accept** icon to log into the system with the specified credentials.
15. Click also green **Accept** icon on the opened **Copyright** dialog so that the **SAP Easy Access** entry page of the local NetWeaver system is displayed.

    <img src="./images/w1-u6-s6/pic13c--gui-sys.png" alt="" width="640px" />

    > **Hint (optional):** As the **Favorites links** of the _SAP Easy Access_ page are not used directly in the tutorial this information is only added as hint:
    >
    > The _Favorites_ links like **Launchpad** as you can see in the before opened _SAP Easy Access_ page will only work if you add the following IP address to host name mapping to _C:\\Windows\\System32\\drivers\\etc\\hosts_ on your host OS.
    >
    > -   **127.0.0.1 vhcalnplci vhcalnplci.dummy.nodomain**

**For Mac OS X:**

1.  Open **SAP GUI** application by double-clicking **/Applications/SAP Clients/SAPGUI/SAPGUI.app** file.

    <img src="./images/w1-u6-s6/pic14--gui-mac-sys.png" alt="" width="640px" />

2.  **New** icon to open **Connection Properties** dialog
3.  Enter _Description_: **Local NetWeaver**
4.  Click **Advanced** tab

    <img src="./images/w1-u6-s6/pic15--gui-mac-sys.png" alt="" width="640px" />

5.  On _Advanced_ tab select **Expert mode** option.
6.  In the text area field enter **conn=/H/127.0.0.1/S/3200**

    <img src="./images/w1-u6-s6/pic16--gui-mac-sys.png" alt="" width="640px" />

7.  Click **SAVE** to create a new System entry.

    <img src="./images/w1-u6-s6/pic17--gui-mac-sys.png" alt="" width="640px" />

8.  Logon to the new System
9.  Right-click on the newly created entry **Local NetWeaver** and click on **Connect** option of the context menu.

    <img src="./images/w1-u6-s6/pic18--gui-mac-sys.png" alt="" width="640px" />

10. To log in to the system for the first time, use the following credentials:
11. Client: **001**
12. User: **Developer**
13. Password: **Appl1ance**
14. Language: **EN**

    <img src="./images/w1-u6-s6/pic19--gui-mac-sys.png" alt="" width="640px" />

15. Click green **Accept** icon to log into the system with the specified credentials.
16. Click also green **Accept** icon on the opened **Copyright** dialog so that the **SAP Easy Access** entry page of the local NetWeaver system is displayed.

    <img src="./images/w1-u6-s6/pic21--gui-mac-sys.png" alt="" width="640px" />

    > **Hint (optional):** As the **Favorites links** of the _SAP Easy Access_ page are not used directly in the tutorial this information is only added as hint:
    >
    > The _Favorites_ links like **Launchpad** as you can see in the before opened _SAP Easy Access_ page will only work if you add the following IP address to host name mapping to _\\etc\\hosts_ on your host OS.
    >
    > -   **127.0.0.1 vhcalnplci vhcalnplci.dummy.nodomain**

[Top](#step-6-2-top)

#### 6.3 Install SAP System License

To work with the installed local NetWeaver AS ABAP system you have to request a Demo license for free as described in the following steps.

##### 6.3.1 Install License

1.  Use the before opened **SAP GUI** where you logged in with the **Developer** user.
2.  Enter **SLICENSE** in the transaction field in the upper right corner

    <img src="./images/w1-u6-s6/pic22--license.png" alt="" width="640px" />

3.  Click green **Enter** icon to launch the _SLICENSE_ transaction.
4.  Copy & paste Hardware Key from the opened transaction page.

    <img src="./images/w1-u6-s6/pic23--license.png" alt="" width="640px" />

5.  To get a license
6.  Open [http://www.sap.com/minisap](http://www.sap.com/minisap)
7.  Fill in your **HCP trial User ID** as _SCN User id_ and fill in the other requested information.
8.  Agree to the license.
9.  Choose system ID **NPL - SAP NetWeaver 7.x (Sybase ASE)**.
10. Enter the **Hardware key** value which you copied from SLICENSE transaction before.
11. Click **Submit**.

    <img src="./images/w1-u6-s6/pic24--license.png" alt="" width="640px" />

12. You will receive a mail to the provided email address with an attachment called **NPL.txt**

    > **Note:** The mail might take 5-10 minutes or even longer.

13. Save the attachment to disk.
14. Switch to the still open SAP GUI window.
15. On the transaction SLICENSE page click the button **Install**.

    > **Note:** If the Install button is not visible scroll down the scroll bar on the right side.

    <img src="./images/w1-u6-s6/pic25--license.png" alt="" width="640px" />

16. In the opened file browser navigate to the license file **NPL.TXT** and open it.
17. On the **SAP GUI Security** window click **Allow** to grant access to the file.
18. Then a successfully installed window should appear on which you click the green **Continue** icon.
19. Finally a new **Valid License Entry** is added to the table on the _Digital Signed Licenses_ tab.

    <img src="./images/w1-u6-s6/pic27--license.png" alt="" width="640px" />

20. **Close** the window where the transaction _SLICENSE_ has been opened.

##### 6.3.2 Create a new VM Snapshot

After you added the license successfully to you NetWeaver AS ABAP system you should again preserve this state.

1.  In the running **Oracle VM VirtualBox** window menu: Choose **Machine > Take Snapshot...**.
2.  In the opened window enter **ABAP with License Snapshot** and click **OK**.

> **Result:** _ABAP with License_ snapshot has been created.

[Top](#step-6-3-top)

#### 6.4 Shutdown VM with NetWeaver AS ABAP

When you are not working on the course, like probably now as week 1 almost finished, it is recommended to shutdown the VM where the NetWeaver AS ABAP is running on.

> Note: First reason for this is the ABAP Demo System might take a lot of system resources. The second reason is that the shutdown and restart with snapshot procedure of the VM with the ABAP system is sometimes the only way to get out of certain ABAP related problems (e.g. _ABAP processes does not result in GREEN status after executing 'startup ALL'_).

Shutdown of the NetWeaver ABAP VM should be done in two steps, first stopping the ABAP and then closing the VM.

##### 6.4.1 Stopping NetWeaver AS ABAP

1.  In the running **Oracle VM VirtualBox** open KDE **Application Menu**.
2.  Open a **Konsole** (**System > Konsole**) and execute the following three commands:
3.  Execute **su -l npladm** (will ask for _NetWeaver AS ABAP_ **system password**) to switch to _NetWeaver Admin_ user, so that you act in this Konsole as this user and its permissions.
4.  Execute **stopsap ALL** to stop the ABAP server.

    <img src="./images/w1-u6-s6/pic28--abap-stop.png" alt="" width="640px" />

[Top](#step-6-4-1-top)

##### 6.4.2 Closing VM

1.  In the running **Oracle VM VirtualBox** window menu: Open **File > Close...**.

    <img src="./images/w1-u6-s6/pic29--abap-stop.png" alt="" width="640px" />

2.  In the opened _Close Virtual Machine_ window select **Power off the machine** option.

    > **Hint:** With this option the current state will not be preserved and if VM is restarted the last saved snapshot will be taken as system state.

    <img src="./images/w1-u6-s6/pic30--abap-stop.png" alt="" width="640px" />

3.  Click **OK** so that the VM window is closed.

[Top](#step-6-4-2-top)

#### 6.5 Starting VM with NetWeaver AS ABAP

After you have stopped the ABAP and closed the VM as described in above [section 6.4](#shutdown-vm-with-netweaver-as-abap) we now describe how you launch the VM, start the ABAP there and verify that the ABAP processes are running fine.

We will describe this startup of the VM from the latest existing snapshot you created.

> **Hint:** Keep in mind that in later weeks of this course you will be pointed to this _How to start a VM_ section. Then you might already have another latest snapshot that the one after described below.

##### 6.5.1 Starting up VM from latest Snapshot

1.  In **VirtualBox Manager** restore the latest snapshot:
2.  Select **Snapshots** button in the upper right corner
3.  Open the snapshot tree nodes and select the latest node **before Current State** node (at the end of week 1, unit 6 this is **ABAP with License Snapshot**)
4.  Open context menu on selected  node and chose **Restore Snapshot**

    <img src="./images/w1-u6-s6/pic31--abap-start.png" alt="" width="640px" />

5.  If the _Virtual Box - Question_ window pops up then

    -   **Deselect checkbox** _Create a snapshot of current machine state option_.
    -   Click **Restore**

    <img src="./images/w1-u6-s6/pic31b--abap-start.png" alt="" width="640px" />

    > **Result:** The state of the selected VM is restored to this snapshot and can be started now.

6.  Select _SAP NetWeaver 7.50 SP02_ VM node and click **Start** button to start the new VM. It opens a new window **Oracle VM VirtualBox** and starts the virtual machine.

    > **Hint:** Hit RETURN key to accept the default menu entries (first _Boot from Harddisk_ and second _openSUSE_) so that you do not have to wait a few seconds for auto-start.

      <img src="./images/w1-u6-s6/pic32--abap-start.png" alt="" width="640px" />

[Top](#step-6-5-1-top)

##### 6.5.2 Starting up NetWeaver AS ABAP on running VM

1.  In the running **Oracle VM VirtualBox** open KDE **Application Menu**.
2.  Open a **Konsole** (**System > Konsole**)
3.  Check Network connection:
4.  Execute **sudo ifconfig** (will ask for root password).
5.  Make sure, that you find **inet addr:10.0.2.15** as part of the output result.

    > **Note:** If you don't get this **inet addr**, then try to execute **sudo rcnetwork restart** and check again.

    <img src="./images/w1-u6-s6/pic33--abap-start.png" alt="" width="640px" />

6.  Start NetWeaver AS ABAP:
7.  Execute **su -l npladm** (will ask for _NetWeaver AS ABAP_ **system password**) to switch to _NetWeaver Admin_ user, so that you act in this Konsole as this user and its permissions.
8.  Execute **startsap ALL** to start the ABAP server.
9.  Execute **sapcontrol -nr 00 -function GetProcessList** to check that the processes are running and are all **GREEN**

    > **Note:** As 'startsap ALL' can take some time repeat the command execution a few times until all four prosseses (IGS Watchdog, Dispatcher, Gateway, ICM) are GREEN

    <img src="./images/w1-u6-s6/pic34--abap-start.png" alt="" width="640px" />

    The result should look as follows:

        GetProcessList
        OK
        name, description, dispstatus, textstatus, starttime, elapsedtime, pid
        igswd_mt, IGS Watchdog, GREEN, Running, 2017 ... , ... , ...
        disp+work, Dispatcher, GREEN, Running, 2017 ... , ... , ...
        gwrd, Gateway, GREEN, Running, 2017 ... , ... , ...
        icman, ICM, GREEN, Running, 2017 ... , ... , ...

[Top](#step-6-5-2-top)

[**&lt; Previous** Unit 4](../unit-4/) | [**Up ^** Week 1](../) | [**Next >** Overview Week 2](../../week-2/)