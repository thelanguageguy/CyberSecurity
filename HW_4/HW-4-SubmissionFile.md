## Week 4 Homework Submission File: Linux Systems Administration


![PERMISSION REQUIRED](HW-4-Image/PERMISSION-REQUIRED.jpg)
### Step 1: Ensure/Double Check Permissions on Sensitive Files

1. Permissions on `/etc/shadow` should allow only `root` read and write access.

    - Command to inspect permissions: <ls -l /etc/shadow>

    - Command to set permissions (if needed): <chmod 600 /etc/shadow>

2. Permissions on `/etc/gshadow` should allow only `root` read and write access.

    - Command to inspect permissions: <ls -l /etc/gshadow>

    - Command to set permissions (if needed): <chmod 600 /etc/gshadow>

3. Permissions on `/etc/group` should allow `root` read and write access, and allow everyone else read access only.

    - Command to inspect permissions: <ls -l /etc/group>

    - Command to set permissions (if needed): <chmod 644 /etc/group>

4. Permissions on `/etc/passwd` should allow `root` read and write access, and allow everyone else read access only.

    - Command to inspect permissions: <ls -l /etc/passwd>

    - Command to set permissions (if needed): <chmod 644 /etc/passwd>

### Step 2: Create User Accounts

1. Add user accounts for `sam`, `joe`, `amy`, `sara`, and `admin`.

    - Command to add each user account (include all five users): sudo adduser sam joe amy sara admin 

2. Ensure that only the `admin` has general sudo access.

    - Command to add `admin` to the `sudo` group: <sudo usermod -aG sudo admin>

### Step 3: Create User Group and Collaborative Folder

1. Add an `engineers` group to the system.

    - Command to add group: sudo addgroup engineers

2. Add users `sam`, `joe`, `amy`, and `sara` to the managed group.

    - Command to add users to `engineers` group (include all four users): <sudo gpasswd -M sam,joe,amy,sara engineers>

3. Create a shared folder for this group at `/home/engineers`.

    - Command to create the shared folder: <sudo mkdir /home/engineers>

4. Change ownership on the new engineers' shared folder to the `engineers` group.

    - Command to change ownership of engineer's shared folder to engineer group: <sudo chown -R :engineers /home/engineers>

### Step 4: Lynis Auditing

1. Command to install Lynis: <sudo apt -y install lynis>

2. Command to see documentation and instructions: <lynis --help>

3. Command to run an audit: sudo lynis audit system

4. Provide a report from the Lynis output on what can be done to harden the system.

    - Screenshot of report output:


![WARNINGS](HW-4-Image/LynisAudit-WARNINGS.png)

![SUGGESTIONS](HW-4-Image/LynisAudit-SUGGESTIONS.png)

![SCAN DETAILS](HW-4-Image/LynisAudit-SCAN-DETAILS.png)

![SELF DESTRUCT](HW-4-Image/LynisAudit-SELF-DESTRUCT.jfif)

(gfycat.com)

### Bonus
1. Command to install chkrootkit: <sudo apt -y install chkrootkit>

2. Command to see documentation and instructions: <chkrootkit --help>

3. Command to run expert mode: <sudo chkrootkid -x>

4. Provide a report from the chrootkit output on what can be done to harden the system.
    - Screenshot of end of sample output:


![CHKROOTKIT REPORT](HW-4-Image/CHKROOTKIT-REPORT.gif)

![SUDO](HW-4-Image/SUDO.png)

(hackaday.com)
---
