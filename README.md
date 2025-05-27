<h1>Creating Windows and Linux Virtual Machines in Microsoft Azure</h1>


This walkthrough will guide you through the process of creating Windows and Linux virtual machines in Microsoft Azure. It will walk through the entire process step-by-step, demonstrating how to set up and configure virtual machines for hands-on experience with cloud infrastructure.

<h2>🧰 Prerequisites</h2>

- A <a href="https://azure.microsoft.com/en-us/free/">Microsoft Azure account</a>
<h2>🖥️ Environments & Tools</h2>

- Microsoft Azure

<h2>🧑‍💻 Operating Systems</h2>

- macOS Sequoia (host system)
- Windows 10 Pro (22H2) (virtual machine)
- Ubuntu Server 22.04 (virtual machine)

<h2>🪜 Project Steps</h2>

- Create a Resource group in Azure  
- Create a Windows 10 Virtual Machine inside the Resource group  
- Create a Linux (Ubuntu) Virtual Machine inside the same Resource group
  
<h2>☁️ Step 1: Create a Resource Group in Microsoft Azure</h2>

- Log into the [Azure Portal](https://portal.azure.com/) by signing in with your Microsoft account.

- Locate the search bar at the top, type in **"Resource groups"** and select it from the dropdown options.

  <!-- Screenshot: Azure portal with "Resource Groups" being searched -->
  <p>
    <img width="1200" alt="Screenshot 2025-05-26 at 2 50 42 PM" src="https://github.com/user-attachments/assets/55e74439-9f71-4076-a787-6b6f7d3de6d2" />
</p>


- Once on the Resource Groups page, click **+ Create** to start the process of creating a new resource group.

  <!-- Screenshot: Click on Create button in Resource Groups -->
  <p>
    <img width="1200" alt="Screenshot 2025-05-26 at 2 55 16 PM" src="https://github.com/user-attachments/assets/81c025b9-18a0-4bb6-978c-65c392fc81a5" />
  </p>


- In the **Create Resource group** form:
  - Make sure you select the correct **Subscription** which should be from when you set up your Microsoft Azure account.
  - Enter a name to name your new Resource group (e.g., `VM-RG`). This Resource group is where our virtual machines will be stored in the Cloud.
  - Choose a **Region** (recommended: Select the same region every time going forward as it may prevent future complications and headaches).

  <!-- Screenshot: Resource Group creation form filled out -->
  <p>
    <img width="1200" alt="Screenshot 2025-05-26 at 3 01 48 PM" src="https://github.com/user-attachments/assets/8cce8869-b532-48f5-a693-435b42237925" />
  </p>

- After entering the required information, click **Review + Create**. Review the Resource group infomration. Once you are ready, click **Create** to deploy the resource group. It is recommended to take a note of the name and region of this Resource group for your future reference.

  <!-- Screenshot: Review + Create screen before final confirmation -->
  <p>
    <img width="1206" alt="Screenshot 2025-05-26 at 3 18 45 PM" src="https://github.com/user-attachments/assets/e58465e8-ed6b-4e02-8c3b-2e274a2d9b8c" />
  </p>

- After you click **Create** and the deployment is complete, you’ll be directed back to the Resource groups page. You have successfully created a new Resource group in the Cloud and you will see your newly created resource group listed on the Resource groups dashboard.

  <!-- Screenshot: Resource Group successfully created and visible -->
  <p>
    <img width="1200" alt="Screenshot 2025-05-26 at 3 28 32 PM" src="https://github.com/user-attachments/assets/a02e406b-ff77-425f-8c6f-8808e5452b93" />
  </p>


<h2>🪟 Step 2: Create a Windows 10 Virtual Machine inside the Resource Group</h2>

- Using the search bar at the top, type in **"Virtual machines"** and select it from the dropdown options.

  <!-- Screenshot: Azure Portal showing search for "Virtual machines" -->
  <p>
    <img width="1200" alt="Screenshot 2025-05-26 at 4 45 01 PM" src="https://github.com/user-attachments/assets/843e77cf-dffa-4ce1-bcd7-e3847bea0414" />
  </p>

- On the **Virtual machines** page, click **+ Create** and then click **Azure virtual machine** from the dropdown options.

  <!-- Screenshot: Virtual Machines page with "+ Create" button and dropdown -->
  <p>
    <img width="1200" alt="Screenshot 2025-05-26 at 4 47 12 PM" src="https://github.com/user-attachments/assets/14daa173-cf28-451a-80e1-8c3b2d081401" />
  </p>

- In the **Basics** tab of the **Create a virtual machine** form:
  - Select the same **Resource group** that you created earlier 
  - Enter a name for the new virtual machine in **Virtual machine name**
  - Select the same **Region** as your Resource group (Ours was East US)
  - For **Image**, select: **Windows 10 Pro, version 22H2**

  <!-- Screenshot: Basics tab with name, region, and image filled -->
  <p>
    <img width="1200" alt="Screenshot 2025-05-26 at 6 10 41 PM" src="https://github.com/user-attachments/assets/e5646081-586c-48c3-a0c6-e86cd1f2a72c" />
  </p>

- Scroll down. Under **Size**, select:
  - **Standard_D2s_v6** (2 vCPUs, 8 GiB memory)
  - If this size is not available, click **See all sizes** for other options and select another size with at least 2 vCPUs and 8 GiB of memory.

  <!-- Screenshot: VM size selection screen -->
  <p>
    <img width="1200" alt="Screenshot 2025-05-26 at 6 22 17 PM" src="https://github.com/user-attachments/assets/3568487e-a7d9-4a81-a2c1-dafb27929620" />
  </p>

- In the **Administrator Account** section:
  - Create a **Username** and **Password** and make a note of it or write it down somewhere. You will need it to log in to Remote Desktop later.
  - Check the box under **Licensing**. Click **Next: Disks >** to move on.

  <!-- Screenshot: Admin username/password fields and licensing checkbox -->
  <p>
    <img width="1200" alt="Screenshot 2025-05-26 at 6 26 54 PM" src="https://github.com/user-attachments/assets/d322aee3-24d5-40b9-a57e-0e5f44e79fef" />
  </p>

- Leave the Disk settings at default. 
- Click **Next: Networking** and configure the following:
  - Azure might auto-generate a **Virtual Network**. You can either use this one or create your own.
  - Leave the default **Subnet** and **Public IP** 
  - Make sure **RDP (3389)** is selected as an inbound port under **Select inbound ports** so you will be able to your virtual machine

  <!-- Screenshot: Networking tab with RDP selected and virtual network configured -->
  <p>
    <img width="1200" alt="Screenshot 2025-05-26 at 6 44 56 PM" src="https://github.com/user-attachments/assets/ed4f274e-ec8b-4f9d-8fb8-b91732af456a" />
  </p>

- Click **Review + Create** to move on and start reviewing your configuration.
- Look over Resource Group, Region, Virtual machine name, Image (operating system image), and Public inbound ports (for RDP access).

  <!-- Screenshot: Review + Create summary for Windows VM -->
  <p>
    <img width="1200" alt="Screenshot 2025-05-26 at 6 44 56 PM" src="https://github.com/user-attachments/assets/5c38c2b2-2bc5-4671-b3fc-f28943e064d7" />
  </p>

- Once deployment is complete, you'll see a message on your screen saying **Your deployment is complete**. Congrats! We just created our first virtual machine in the Cloud. Now let's create a Linux virtual machine.

  <!-- Screenshot: Deployment complete and VM overview screen -->
  <p>
    <img width="1200" alt="Screenshot 2025-05-26 at 7 18 31 PM" src="https://github.com/user-attachments/assets/f06f4065-93a4-44df-833a-c166cd95b610" />
  </p>


 <h2>🐧 Step 3: Create a Linux (Ubuntu) Virtual Machine inside the same Resource Group</h2>

- Time for the next virtual machine. Let's configure the Linux one now.

- In the **Basics** tab:
  - Select the same **Resource Group** used for the Windows virtual machine we just made 
  - In **Name** type in a name for the new virtual machine
  - Select the same **Region** we chose before (we chose East US)
  - Select **Ubuntu Server 22.04 LTS** for **Image**

  <!-- Screenshot: Basics tab filled for Linux VM -->
  <p>
    <img width="1200" alt="Screenshot 2025-05-26 at 7 24 40 PM" src="https://github.com/user-attachments/assets/2121b37d-b0a5-4921-a22b-94f8b5c7c4da" />
  </p>

- Under **Size**, select:
  - **Standard_D2s_v6** (2 vCPUs, 8 GiB memory) or a similar configuration from the dropdown options if this one isn't available

  <!-- Screenshot: VM size selected for Linux -->
  <p>
    <img width="1200" alt="Screenshot 2025-05-26 at 7 29 00 PM" src="https://github.com/user-attachments/assets/2491a946-c00a-4307-8964-7301a74d0934" />
  </p>

- In the **Administrator Account** section:
  - Change the **Authentication type** to **Password** instead of SSH
  - Set a **username** and **password**. To make it easy we can use the same credentials we used for the Windows virtual machine

  <!-- Screenshot: Linux admin account section with password authentication selected -->
  <p>
    <img width="1200" alt="Screenshot 2025-05-26 at 7 45 15 PM" src="https://github.com/user-attachments/assets/52543623-cdda-4ca9-a755-9a437a40b632" />
  </p>

- Click **Next: Disks** and leave the Disk settings at default
- Click **Next: Networking**, and configure:
  - **Virtual network**: Select the same one used by the Windows VM
  - Leave Subnet, Public IP, and other settings as default
  - Make sure **SSH (Port 22)** is selected in **Select inbound ports**

  <!-- Screenshot: Networking tab for Linux VM with SSH enabled -->
  <p>
    <img width="1200" alt="Screenshot 2025-05-26 at 7 51 46 PM" src="https://github.com/user-attachments/assets/1894d8c3-2173-4fb6-b0d7-166604ce0bd2" />
  </p>

- Click **Review + Create** and look over the:
  - Virtual machine name
  - Image is Ubuntu 22.04
  - SSH is enabled in Public Inbound Ports
  - Region and Resource Group are the same as the Windows virtual machine
  
  <!-- Screenshot: Review + Create screen for Linux VM -->
  <p>
    <img width="1200" alt="Screenshot 2025-05-26 at 7 53 30 PM" src="https://github.com/user-attachments/assets/7b71cda2-c3a8-45ae-bd16-65ff992a8755" />
  </p>

- Click **Create**. You will be taken to the **Overview** screen and you will see a message that says **Yout deployment is complete** once the virtual machine has successfully been deployed.

  <!-- Screenshot: Linux VM deployment complete -->
  <p>
    <img width="1200" alt="Screenshot 2025-05-26 at 8 09 50 PM" src="https://github.com/user-attachments/assets/6965ae0f-0c61-46c5-bb31-98188ec62844" />

  </p>
  <h2>✅ Conclusion</h2>

  This concludes the project. We successfully created a Resource Group, a Windows VM running Windows 10 Pro, and a Linux VM running Ubuntu in Microsoft Azure. 

Using just my MacBook, I was able to set up and access two additional virtual machines, each running a different operating system—without any need for extra hardware or physical space. This showcases the efficiency and cost-effectiveness of Cloud Service Providers (CSPs) like Azure, making powerful computing resources easily accessible for both individuals and organizations.

Remember to stop/turn off virtual machines when they are not being used to avoid unnecessary charges.  








