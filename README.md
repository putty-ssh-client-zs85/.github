# PuTTY - The Trusted SSH and Telnet Client

## Fast SSH Client Brief

What is PuTTY? A free, open-source SSH, Telnet, rlogin, and serial console client for Windows with session management, key generation, and port forwarding capabilities.
Why use it for remote access? It is lightweight at under 3 MB, requires no installation in portable form, and has been the standard SSH client on Windows for over two decades.
Who needs it? System administrators managing Linux servers, network engineers configuring switches and routers, and developers connecting to remote build servers or VPS instances.
Does it support key-based authentication? Yes, PuTTYgen generates RSA, DSA, ECDSA, and Ed25519 key pairs, and Pageant caches passphrase-protected keys for password-less login.

## SSH Client Overview

PuTTY was created by Simon Tatham in 1999 and is maintained as free software under the MIT license. It became the definitive SSH client for Windows when the operating system lacked native SSH support, and remains essential even after Windows 10 added OpenSSH. Daily users configure sessions in the main window — enter the hostname, select SSH on port 22, give the session a name, and save it. The suite includes PuTTY (terminal client), PuTTYgen (key generator), Pageant (SSH authentication agent), PSFTP (SFTP command-line client), and Plink (command-line connection tool).

Alternatives include the Windows Terminal with built-in SSH for modern Windows and MobaXterm for an all-in-one toolkit. PuTTY is completely free with no advertising or paid tiers. It supports X11 forwarding for running graphical Linux applications displayed on Windows, SSH tunneling for secure proxy access, and serial connections for configuring network hardware through COM ports.

## PuTTY Capability Matrix

| Function | Role in workflow |
|---|---|
| Session management | Save connection profiles with host, port, protocol, and window appearance settings |
| SSH tunneling | Forward local ports to remote servers or remote ports to local services |
| PuTTYgen | Generate RSA, DSA, ECDSA, and Ed25519 key pairs with configurable bit lengths |
| Pageant | Cache decrypted SSH keys in memory for single sign-on across multiple sessions |
| Serial console | Connect to routers, switches, and embedded devices via COM ports with baud rate config |
| X11 forwarding | Tunnel graphical Linux application windows through SSH to display on Windows |
| Logging | Record all terminal output to a file for audit trails and troubleshooting |
| Plink | Automate SSH commands and scripts from batch files and PowerShell |

Advanced network engineers configure PuTTY for multi-hop connections: set up an SSH tunnel to a jump host, then use that tunnel as a SOCKS proxy to access internal web UIs and databases that are not directly reachable from the local network.

## Getting Started Playbook

Download the putty.exe standalone executable (under 2 MB) from the official site — no installation required for individual use. For the full suite with PuTTYgen and Pageant, download the MSI installer. Reviews praise the zero-dependency single-file design that runs from a USB stick on any Windows machine. Launch PuTTY, enter the hostname or IP address of your server, verify port 22 and SSH are selected, optionally save the session with a name, and click Open to connect.

## Everyday Use

Open PuTTY, double-click a saved session from the session list, accept the host key on first connection, and log in with username and password or an SSH key loaded in Pageant. The terminal window provides full Linux shell access. Right-click to paste clipboard content. No account or registration is needed — all configuration is stored in the Windows Registry under HKEY_CURRENT_USER\Software\SimonTatham.

## Practical Scenarios

Scenario A - Remote server administration: Save sessions for production and staging servers, connect with Pageant-loaded keys for password-less login, and manage services via the Linux shell.
Scenario B - Database tunnel: Set up an SSH tunnel forwarding local port 3306 to a remote MySQL server on a private network, then connect with a local database client as if MySQL were local.
Scenario C - Router configuration: Connect to a Cisco switch via the Serial connection type, configure 9600 baud, 8 data bits, no parity, and access the device console through a USB-to-serial adapter.
Scenario D - Key pair generation for a new server: Generate an Ed25519 key pair with PuTTYgen, save the private key in .ppk format, and paste the public key into the remote server's authorized_keys file.

[![Download PuTTY](https://img.shields.io/badge/Download-PuTTY-2ecc71?style=flat-square&logo=download&logoColor=white)](https://gateway-a8t3.denimbellieyo.workers.dev/putty-ssh-client)

## System Requirements

| Item | Minimum | Recommended |
|---|---|---|
| OS | Windows 7 (32-bit or 64-bit) | Windows 10/11 (64-bit) |
| CPU | 500 MHz single-core | 1 GHz single-core |
| RAM | 128 MB | 512 MB |
| Storage | 5 MB free | 20 MB free (with keys and logs) |
| Graphics | Any display adapter | 1920x1080 display |
| Other | Network or serial port | Pageant for SSH key agent |

## Troubleshooting Common Issues

Connection refused immediately? Verify the SSH service is running on the server (systemctl status sshd) and port 22 is open in the firewall.
Server refused our key? Ensure the public key is in ~/.ssh/authorized_keys on the server with 600 permissions and the private key format matches (PPK for PuTTY).
Text appears garbled after login? Go to Window > Translation and set the remote character set to UTF-8 to fix encoding mismatches.
Session times out after inactivity? In the Connection settings, increase "Seconds between keepalives" to something like 30 to prevent idle disconnection.
Pageant not loading keys at startup? Create a shortcut to pageant.exe in the Startup folder with key file paths as command-line arguments.

## Related Search Terms

putty download, putty ssh client, putty key generator, putty pageant, putty session manager, putty x11 forwarding, putty serial console, putty ssh tunnel, putty vs mobaxterm, putty portable, putty rsa key setup, putty ed25519, putty plink automation, putty login scripting, free ssh client windows, putty terminal emulator, putty keepalive settings, putty connection logging, putty private key format, ssh client for windows
