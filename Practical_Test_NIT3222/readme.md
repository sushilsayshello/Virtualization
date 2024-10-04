# VM Network Environment Setup for ArmitaTech Marketing Department

## Overview
This project sets up a virtual network environment for ArmitaTech's Marketing Department. The setup includes two virtual machines (VMs): one for Marketing Strategists (`ARMSushilMS`) and one for Document Storage (`ARMSushilDOC`). The VMs are connected to an internal network switch and assigned specific IP addresses within the `192.30.0.0/24` subnet. Network connectivity is verified through ping tests between the VMs and the host.

## Requirements
- Microsoft Hyper-V enabled host environment
- PowerShell with administrative privileges
- Windows 10 Pro, Enterprise, or Windows Server edition that supports Hyper-V

## Network Configuration
- **Internal Network Segment**: `192.30.0.0/24`
- **Gateway**: `192.30.0.1` (Host IP)
- **ARMSushilMS VM IP**: `192.30.0.59`
- **ARMSushilDOC VM IP**: `192.30.0.89`

## VM Specifications
- **ARMSushilMS VM**: 
  - 4 GB Memory, 4 vCPUs
  - MAC Address: `00-15-5D-00-04-10`
- **ARMSushilDOC VM**: 
  - 4 GB Memory, 4 vCPUs
  - MAC Address: `00-15-5D-00-04-20`

## Steps to Set Up the Environment

1. **Create and Configure the Internal Virtual Switch**:
   - The script checks if an internal switch called `ARMMarketingSwitch` exists; if not, it creates one.
   - Assigns an IP address to the host on this switch.

2. **Create and Configure VMs**:
   - Two VMs are created and connected to the internal switch. Each VM is assigned a static IP within the specified subnet and configured with a unique MAC address.

3. **Enable ICMP (Ping) Traffic**:
   - ICMP traffic is allowed on both the host and VMs to facilitate ping testing.

4. **Verify Connectivity**:
   - Pings are sent from the host to both VMs to confirm network connectivity.

## Usage

1. **Run the Setup Script**:
   - Open PowerShell with administrative privileges.
   - Run the provided setup script, which will automatically create the network environment, configure VMs, and enable ICMP traffic.

2. **Test Network Connectivity**:
   - After running the script, verify that the host can successfully ping both VMs.
   - You should see replies from both `192.30.0.59` (ARMSushilMS) and `192.30.0.89` (ARMSushilDOC), indicating successful connectivity.

## Example Commands

To manually test ping connectivity:
```powershell
# Ping from host to ARMSushilMS VM
ping 192.30.0.59

# Ping from host to ARMSushilDOC VM
ping 192.30.0.89
