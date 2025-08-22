**Automated VLAN Validation Tool**

**Overview**

This Python script automates VLAN configuration validation across multiple Cisco switches (tested on 188 devices). It connects to each switch, retrieves VLAN information, and saves the output to individual files for analysis. The tool helps identify missing or inconsistent VLAN configurations, ensuring compliance with network design standards.

**Features**

• Connects to multiple switches via SSH

• Retrieves and saves VLAN configurations

• Handles both standard and enable secret authentication

• Generates timestamped output files

• Provides success/failure status for each device

**Prerequisites**

• Python 3.13

• Required Python packages: netmiko, getpass, datetime

**Installation**

Install required packages:

pip install netmiko

**Configuration**

Create a switches.txt file in the same directory as the script

Add one IP address per line for all switches you want to check

**Example**
switches.txt 
content:

192.168.1.1

192.168.1.2

10.0.0.1

**Usage**

**Run the script:**

python list_vlans.py

Enter your credentials when prompted:

• SSH Username

• SSH Password

• Enable Secret (optional)

**Output**

The script creates individual text files for each switch with the naming format:

vlans_[hostname]_[timestamp].txt
Example: vlans_SWITCH01_20231201.txt

**Each file contains:**

• Switch hostname

• IP address

• Complete VLAN configuration from the show vlan brief command

**Results**

After execution, the script displays:

• Total number of switches processed

• Success count

• Individual connection status for each device

**Customization**

You can modify the command sent to switches by changing the vlans = connection.send_command("show vlan brief", delay_factor=2) line to use different show commands.
