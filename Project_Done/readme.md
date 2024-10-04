# Hyper-V Virtual Machines Setup and Network Configuration

## Project Overview

This project involves creating and configuring two virtual machines, **D_miaoAccounting** and **D_miaoLegaldoc**, on a Hyper-V host. The virtual machines are connected via a virtual switch, and each VM is assigned a static IP address for communication.

## Prerequisites

- Windows Server or Windows OS with **Hyper-V** enabled.
- PowerShell with admin privileges.
- Pre-configured **VHDX** files for the virtual machines.
- Familiarity with PowerShell and Hyper-V Manager.

## Steps Involved

### 1. Create a Virtual Switch

Create a virtual switch in Hyper-V to allow network communication between the VMs. An internal virtual switch is recommended for internal communication between VMs and the host.

### 2. Create Virtual Machines on the Host Machine

Two VMs are created:
- **D_miaoAccounting**: This VM is assigned a static MAC address and is set up with 7 vCPUs and 8 GB of RAM.
- **D_miaoLegaldoc**: This VM is set up with dynamic memory (2 GB min, 8 GB max) and 4 vCPUs.

Both VMs are connected to the virtual switch created earlier.

### 3. Configure Network Settings Inside the VMs

After creating the VMs, log into each VM and configure network settings:
- Assign static IP addresses.
- Set the default gateway and DNS server.
- Ensure the correct MAC addresses are used.

### 4. Enable ICMP (Ping) in Firewall

To allow the VMs to respond to ping requests, configure the Windows Firewall to allow ICMP (ping) traffic. This helps with testing connectivity between the VMs.

### 5. Testing Connectivity

You can test the configuration by:
- Pinging the **D_miaoAccounting** VM from the **D_miaoLegaldoc** VM.
- Pinging the **D_miaoLegaldoc** VM from the **D_miaoAccounting** VM.
- Pinging the VMs from the host machine.

This ensures that the network setup is working as expected.

## Tools Used

- **Hyper-V Manager**: To create and manage virtual machines.
- **PowerShell**: To automate the creation of VMs, configure network adapters, and set IP addresses.

## Conclusion

This project demonstrates the process of setting up Hyper-V virtual machines, configuring network adapters with static IP addresses, and testing connectivity using simple network tools like ping.



