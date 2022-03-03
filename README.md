# Network Analyzer

<img src="res/network.gif" alt="NETWORK" width="400px">

This PowerShell script provides a robust tool for network discovery and SNMP querying within a Windows environment. The tool is designed to scan a specified IP address or a range of addresses within a subnet and gather data using SNMP protocol.

## Features

- **Network Discovery:** Discovers active devices within a specified IP range or a single IP address.
- **SNMP Data Retrieval:** Gathers SNMP data from devices for additional insights.

## Prerequisites

- Windows operating system with PowerShell 5.1 or higher.
- SNMP PowerShell module installed on the system.
- Devices configured to respond to SNMP requests with the correct community string.

## Installation

To install the SNMP PowerShell module, run the following command in an elevated PowerShell prompt:

```powershell
Install-Module -Name SNMP -Scope CurrentUser
```

## Usage

To use the tool, import the script into your PowerShell session and call the `discover_network` function with the required parameters.

```powershell
# Import the script
. .\path_to_script\network_analyzer.ps1

# Run network discovery on a specific IP
discover_network -specific_ip "192.168.1.100"

# Run network discovery on an entire subnet
discover_network -subnet "192.168.1.0/24"
```

## Functions

- `get_snmp_data`: Queries a device for SNMP data.
- `discover_network`: Scans for active devices and collects data within a subnet or from a specific IP.

## Output

The script will output a list of devices with the following information for each:

- IP Address
- Host Name (if resolvable)
- SNMP Data (if retrievable)

## Troubleshooting

If you encounter a warning about untrusted repositories or issues with the SNMP query, ensure that:

- The SNMP module is correctly installed and available.
- The target devices are configured to accept SNMP requests from your host.
- There are no firewalls blocking SNMP traffic (usually on UDP port 161).
- The SNMP service is active on the devices you're querying.

## Contributing

Contributions to enhance the functionality or efficiency of this tool are welcome. Please feel free to fork the repository and submit pull requests.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
