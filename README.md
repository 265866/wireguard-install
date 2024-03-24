# WireGuard installer

**This project is a bash script that aims to setup a [WireGuard](https://www.wireguard.com/) VPN on a Linux server, as easily as possible!**

WireGuard is a point-to-point VPN that can be used in different ways. Here, we mean a VPN as in: the client will forward all its traffic through an encrypted tunnel to the server.
The server will apply NAT to the client's traffic so it will appear as if the client is browsing the web with the server's IP.

The script supports both IPv4 and IPv6. Please check the [issues](https://github.com/265866/wireguard-install/issues) for ongoing development, bugs and planned features! You might also want to check the [discussions](https://github.com/265866/wireguard-install/discussions) for help.

## Requirements

Supported distributions:

- AlmaLinux >= 8
- Arch Linux
- CentOS Stream >= 8
- Debian >= 10
- Fedora >= 32
- Oracle Linux
- Rocky Linux >= 8
- Ubuntu >= 18.04

## Usage

Download and execute the script.

```bash
curl -O https://raw.githubusercontent.com/265866/wireguard-install/master/wireguard-install.sh
chmod +x wireguard-install.sh
./wireguard-install.sh
```

It will install WireGuard (kernel module and tools) on the server, configure it, create a systemd service and a client configuration file.

Then to add, remove, and list users, run:

```bash
./wireguard-install.sh -a add -n (name)
./wireguard-install.sh -a remove -n (name)
./wireguard-install.sh -a list
```

The add arg will output the files
wg0-client-(name).conf  wg0-client-(name).png
In the root directory. The .conf file will be the client configuration file, and the .png file will be the client configuration QR code.

(The remove arg will remove these files, should the user exist.)
