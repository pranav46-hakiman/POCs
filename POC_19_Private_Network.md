POC 19: 
The video link of the following process: 

Step 0: Open the Azure Portal - 

---> Create a Virtual Network (VNet)
Log in to Azure Portal - https://portal.azure.com.
Step 1:Search for "Virtual Networks" in the search bar.

Step 2: Click "Create" → "Virtual Network".
Step 3:Fill in the required details:
a.Subscription: Select your Azure subscription.
b.Resource Group: Create a new one or select an existing one.
c.VNet Name: Enter a name (e.g., MyPrivateVNet).
d.Region: Select your preferred Azure region.

Step 4: In networking,Set the IPv4 Address Space (e.g., 10.0.0.0/16).
Step 5: Click "Next: Security" and configure security settings as needed.
Step 6: Click "Review + Create" → Click "Create".


______________________________________________________________________________________________________________________________________________________________________

--> Create Subnets
Step 1: Go to your Virtual Network (VNet) in the Azure Portal.
Step 2: Click on the "Subnets" tab.
Step 3: Click "Add Subnet" and configure:
Step 4: Subnet Name: (e.g., PrivateSubnet1)
Step 5: Subnet Address Range: (e.g., 10.0.1.0/24)
Step 6: Network Security Group (NSG): (Optional) Create or select an NSG to control traffic.
Step 7: Service Endpoints: Enable if needed.
Step 8: Click "Save".
If needed, Repeat these steps to create multiple subnets (e.g., 10.0.2.0/24 for PrivateSubnet2).

____________________________________________________________________________________________________________________________________________________________________

---> Configure Routing for Internal Communication
Step 1: Go to the "Route Tables" section in Azure.
Step 2: Click "Create a Route Table".
Step 3: Select Subscription and Resource Group.
Step 4: Enter Name (e.g., PrivateRouteTable) and choose the same Region as the VNet.
Step 5: Click "Review + Create" → Click "Create".

____________________________________________________________________________________________________________________________________________________________________

--> Associate the Route Table with Subnets
Step 1: Open the Route Table you just created.
Step 2: Click "Subnets" → Click "Associate".
Step 3: Select your Virtual Network (VNet) and Choose the subnet.
Step 4: Click "OK".

____________________________________________________________________________________________________________________________________________________________________

---> Create a Route for Internal Communication
Step 1: Go to the Route Table you created.
Step 2: Click "Routes" → Click "Add".
Step 3: a.Enter Route Name (e.g., InternalRoute).
        b.Set Address Prefix (e.g., 10.0.0.0/16 for all internal traffic).
        c.Set Next Hop Type:
--"Virtual Network Gateway" (for VPN connections).
--"Virtual Appliance" (for custom routing).
--"None" if default Azure routing is used.
Step 4: Click "Save".

____________________________________________________________________________________________________________________________________________________________________

---> Test Internal Communication
Step 1: Deploy two Virtual Machines (VMs) in different subnets.
Step 2: Try Pinging each other using their private IPs.
step 3: If the ping fails:
--Check Network Security Groups (NSG) to allow ICMP traffic.
--Ensure the route table is correctly associated with the subnets.
