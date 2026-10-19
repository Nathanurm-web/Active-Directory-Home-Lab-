# Active Directory Home Lab

## Project Overview

Built a virtualized Active Directory home lab using Ubuntu Server, Samba Active Directory, and Windows 11 Pro on an Apple Silicon Mac using UTM.

The purpose of this project was to gain hands-on experience with Active Directory administration, Windows domain environments, DNS troubleshooting, and common IT help-desk tasks.

## Technologies Used

* Ubuntu Server
* Samba Active Directory Domain Controller
* Windows 11 Pro
* UTM Virtualization
* DNS, LDAP, Kerberos, and SMB
* Linux command-line administration

## Lab Environment

| Component            | Configuration        |
| -------------------- | -------------------- |
| Domain               | ad.lab               |
| Domain Controller    | adserver.ad.lab      |
| Domain Controller IP | 192.168.64.3         |
| Windows Client       | Windows 11 Pro       |
| Virtualization       | UTM on Apple Silicon |

## Tasks Completed

### 1. Active Directory Configuration

* Provisioned a Samba Active Directory domain.
* Configured internal DNS.
* Joined a Windows 11 client to the domain.
* Created domain users and a Helpdesk security group.

### 2. User Account Administration

* Created test accounts using `samba-tool`.
* Reset a domain user's password.
* Verified the new password by signing into Windows.
* Disabled and re-enabled a domain user account.

### 3. Network File Sharing

* Created a shared directory on Ubuntu.
* Configured an SMB network share.
* Accessed the share from Windows File Explorer.
* Successfully created a file on the network share.

### 4. Troubleshooting

* Investigated failed Windows domain-controller discovery.
* Tested DNS records and domain connectivity.
* Identified an incorrect IPv6 DNS resolver being used by Windows.
* Corrected the client configuration and verified successful domain-controller discovery.

## Key Commands

```bash
sudo samba-tool user list
sudo samba-tool user setpassword testuser
sudo samba-tool user disable helpdesk1
sudo samba-tool user enable helpdesk1
sudo samba-tool group listmembers Helpdesk
```

Windows troubleshooting commands:

```powershell
nslookup adserver.ad.lab
nltest /dsgetdc:ad.lab /force
```

## Skills Demonstrated

* Active Directory user and group administration
* Password resets and account lifecycle management
* Windows domain authentication
* DNS troubleshooting
* SMB file sharing
* Linux server administration
* Network connectivity troubleshooting

## Lessons Learned

This project provided practical experience troubleshooting an Active Directory environment. One major challenge was diagnosing why Windows could resolve domain-controller records through direct DNS queries but could not discover the domain controller automatically.

The issue was traced to Windows using an incorrect IPv6 DNS resolver. After correcting the client-side configuration, domain-controller discovery and authentication worked successfully.

## Future Improvements

* Test different access permissions for domain users.
* Explore remote administration tools.
* Practice additional account troubleshooting scenarios.
* Add more documentation and screenshots.
