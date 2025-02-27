POC 20:
Drive link for the video:

--> Set Up a Virtual Network:

Step 1: Go to Azure Portal → Virtual Networks → Create a Vnet.

Step 2: Define two subnets:

a. Public Subnet (e.g., 10.0.1.0/24) – for the Bastion Host.

b. Private Subnet (e.g., 10.0.2.0/24) – for internal instances.

_______________________________________________________________________________________________________________________________________________________________________________________________________________________


---> Deploy Azure Bastion

Step 1: Navigate to Azure Bastion → Create a Bastion Host.

Step 2: Select:

a. Virtual Network: The VNet created in Step 1.

b. Subnet: Choose AzureBastionSubnet (must be named exactly this).

c. Public IP: Create a new one.

Step 3: Click Create and wait for deployment.

_______________________________________________________________________________________________________________________________________________________________________________________________________________________

---> Deploy Private Virtual Machines

Step 1: Go to Virtual Machines → Create a new VM.

Step 2: Place it inside the private subnet.

Step 3: Disable public IP (to ensure it's private).

Step 4: Configure NSG (Network Security Group):

Step 5: Allow RDP (3389) or SSH (22) only from the Bastion Host.

____________________________________________________________________________________________________________________________________________________________________________________________________________________

---> Securely Access the Private VM via Bastion

Step 1: Go to Virtual Machines → Select the private VM.

Step 2: Click Connect → Bastion.

Step 3: Enter the username and password (or SSH key).

Step 4: Click Connect – this securely logs you into the private VM without exposing it to the internet.

_____________________________________________________________________________________________________________________________________________________________________________________________________________________
