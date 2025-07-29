# Route-Table-Blackhole
https://www.loom.com/share/793d609ee4e0445494121d9cf6176e6d


Step 1: Go to Route Tables
In the AWS Management Console, go to the VPC Dashboard.

On the left-hand menu, click Route Tables.

Step 2: Find the Route Table for Your EC2 Subnet
Find the route table attached to the subnet your EC2 instance is using.

You can do this by checking which subnet your instance is in (via the EC2 dashboard), then going back to the Subnets section in VPC and checking its associated Route Table.

Step 3: Edit the Route
Select the correct route table.

Click the “Routes” tab.

Click “Edit routes.”

Step 4: Break the Internet Route
Look for the route with the Destination 0.0.0.0/0 — this is the route that sends traffic to the internet.

Instead of the Internet Gateway (igw-xxxxxxxx), change the Target to something incorrect — for example, select the EC2 instance’s Elastic Network Interface (eni-xxxxxxxx) or a random local resource.
Step 5: Test the EC2 Instance
Try to connect to the EC2 instance via RDP (for Windows) or SSH (for Linux).
 Part 3: Fixing the Problem
Step 6: Go Back to Route Tables
Go back to the Route Tables section in the VPC console.

Select the same route table again.

Step 7: Restore the Internet Route
Click “Edit routes.”

Find the 0.0.0.0/0 route.

Change the Target back to the correct Internet Gateway (igw-xxxxxxxx).

Click “Save changes.”

✅ Step 8: Verify It’s Working
Try connecting to your instance again via RDP or SSH.

Try pinging or browsing from inside the instance.

Everything should now be working again — internet access is restored!

🎬 Outro (optional):
You’ll notice the connection fails — because there's no valid route to the internet.

Click “Save changes.”
![image](https://github.com/franklopez7554/Route-Table-Blackhole/blob/main/Screenshot%202025-07-29%20122730.png)
![image](https://github.com/franklopez7554/Route-Table-Blackhole/blob/main/Screenshot%202025-07-29%20122747.png)
![image](https://github.com/franklopez7554/Route-Table-Blackhole/blob/main/Screenshot%202025-07-29%20122820.png)
![image](https://github.com/franklopez7554/Route-Table-Blackhole/blob/main/Screenshot%202025-07-29%20122858.png)
![image](https://github.com/franklopez7554/Route-Table-Blackhole/blob/main/Screenshot%202025-07-29%20122947.png)
