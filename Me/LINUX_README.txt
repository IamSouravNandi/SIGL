# README

Administrators can use Endpoint Central to manage computers running Linux operating system. This document will explain you on the following:

	- Supported Linux OS
	- Installing Endpoint Central Agents
	- Installing Endpoint Central Agent Remotely
	- Uninstalling Endpoint Central Agents

# Supported Linux OS
--------------------
    Endpoint Central currently supports the following Linux versions:

	- Ubuntu 10.04 and later versions
	- RedHat Enterprise Linux 6 and later versions
	- CentOS 6 and later versions
	- Fedora  19 and later versions
	- Mandriva 2010  and later versions
	- Debian 7 and later versions
	- Linux Mint 13 and later versions
	- OpenSuSE 11 and later
	- SuSE Enterprise Linux 11 and later

# Installing Endpoint Central Agents
-----------------------------------

    Linux agents can be installed manually in the computers that need to be managed.  Agents should be downloaded on the Linux computer manually before initiating the installation process. Follow the steps mentioned below.

	1. Go to the terminal as a root user. If you do not login as a root user, open the terminal and use sudo command to perform each operation mentioned below and enter password whenever prompted. This 		   provides you the root privilege.
	2. Move to the Directory where you have downloaded the Agent, and verify "UEMS_LinuxAgent.bin" and serverinfo.json" are there.
	3. Execute the Command, "chmod +x UEMS_LinuxAgent.bin" as a root user. This prepares the executable for installation.
	4. Run the Installer using "./UEMS_LinuxAgent.bin". Agent will be installed by default in "/usr/local/desktopcentralagent" directory.
	5. If you wanted to change the installation location of the agent, use this command "./UEMS_LinuxAgent.bin -d <new_location>" .

    You can see that the Endpoint Central agent is successfully installed on the Linux computer. You need to install the agents manually on the computers, which needs to be managed using Endpoint Central. Once the agent installation is completed, the computer will be scanned automatically and the following details will be updated to the Endpoint Central server:

	~ System Details : All details about the comptuer, like Users, Groups and Services. This does not include details on the network shares mapped to the computer.
	~ Hardware  Details : All hardware details of the computer like, BIOS, Disk Drives, Physical Memory, Processors, Network Adapters etc. This does not include details on Printers and Ports.
	~ Software Details : All details on the software that is installed on the managed computer, with the version of the application and installation date etc.

# Installing Endpoint Central Agent Remotely
-------------------------------------------

    When you wanted to install Endpoint Central agent remotely on  Linux computers,  you can install  them using SSH. Follow the steps mentioned below to install Endpoint Central agent using SSH:

	- Copy the downloaded Endpoint Central agent to the remote computer on which the agent needs to be installed
		1. Go to terminal as root user
		2. Navigate to the location where the agent is being copied/downloaded
		3. Type "scp DCLinuxAgent.zip username@hostname:<Path_To_Storage_Directory_If_Needed>" to copy the agent to the target computer, enter password if prompted
		   where username refers to the root user name of the target computer
		   hostname refers to the local host name of the target computer
		   If no path is specified, then the agent will be copied to "/home/username" in the target computer

	- Install the agent by following the steps mentioned below:
		1. Go to the terminal and Type "ssh rootusername@hostname"  to login to the target computer
		2. Login as a root user. If you do not login as rootuser, open the terminal and use sudo command to perform each operation mentioned below and enter password whenever prompted. This 			   provides you the root privilege.
		3. Navigate to the location, where the agent is downloaded/copied, if the downloaded agent is a remote office agent, then extract <Remote_Office_Name>.zip  and navigate to Unzip the 			   DCLinuxAgent.zip by using the command "unzip -e DCLinuxAgent.zip".
		4. Verify if,  "UEMS_LinuxAgent.bin" & "serverinfo.json" are located in the same path
		5. Execute the Command, "chmod +x UEMS_LinuxAgent.bin" as a root user. This prepares the executable for installation.
		6. Run the Installer using "./UEMS_LinuxAgent.bin".  Ensure that the Property File "severinfo.json" exists in the Same Directory as "UEMS_LinuxAgent.bin".  Agent will 			   be installed by default in "/usr/local/desktopcentralagent" directory.
		7. If you wanted to change the installation location of the agent, use this command "./UEMS_LinuxAgent.bin -d <new_location>" .

	You have successfully installed the Endpoint Central agent on a remote computer using SSH.

# Uninstalling Endpoint Central Agents
-------------------------------------

	If you do not want to manage a computer, you can follow the steps mentioned below to uninstall the Endpoint Central agent. Once Endpoint Central agent is uninstalled, all the details related to 	the computer will be removed from Endpoint Central server. If you wanted to manage this computer again, then you will have to re-install Endpoint Central agent in it. However the previous details 	related to the computer will not be available. To uninstall the agents from the computers, follow the steps mentioned below:

	1. Go to the terminal as a root user. If you do not login as root user, open the terminal and use sudo command to perform each operation mentioned below and enter password whenever prompted. 		   		   This provides you the root privilege.
	2. Navigate to the location, where the agent is installed, (default Location : /usr/local/desktopcentralagent) execute this command to "chmod +x RemoveDCAgent.sh" to initiate the uninstaller. 	   		   You need to have root privilege to uninstall the agent.
	3. Execute this command "./RemoveDCAgent.sh"  to uninstall the agent.

	You can see that the Endpoint Central agent has been uninstalled successfully from the computer.

 

 