# active-directory-lab

<img width="614" alt="Image" src="https://github.com/user-attachments/assets/7d494d49-ce7f-4cd9-9deb-d7cae6022c08" />

## Project Overview

As shown in the diagram, this project simulates a **Windows network environment** using **VirtualBox** to demonstrate how **Active Directory (AD)** works. The setup involves creating two virtual machines: one for the **Active Directory Server** (Domain Controller) and another for the **UserPC** (Windows 10). 

## Project Goals:
- Create and configure a **Windows domain environment** using **Server 2019** and **Windows 10**.
- Set up **Active Directory** on the AD Server and create a domain (**mytechdomain.local**).
- Configure networking so the **UserPC** can access the internet through the **AD Server**.
- Enable **DHCP** on the AD Server to automatically assign IP addresses to the **UserPC**.
- Join the **UserPC** to the domain and log in with domain accounts.
- Explore and troubleshoot different Active Directory tasks to demonstrate my understanding of AD concepts.

This project is designed to showcase my skills in **Active Directory**, **network configuration**, and **Windows Server management**.


---

## Implementation Steps

### VirtualBox Setup and Networking Configuration
<details>
  <summary>VirtualBox Setup: Ethernet Configuration</summary>
  
  In this section, I demonstrate how I configured both Ethernet adapters for internal and external networking in VirtualBox. The external adapter connects to my college network for   internet access, while the internal adapter is used for communication between the Domain Controller and the UserPC.

  #### Screenshot 1: VirtualBox Setup for AD Server
  This screenshot shows how I configured the **AD Server** in VirtualBox. I have set the system specifications, including memory, boot order, and network adapters.

  <img width="520" alt="Image" src="https://github.com/user-attachments/assets/b82a2ac5-af04-4342-a89a-6d2c150d31fa" />

  #### Screenshot 2: Internal Ethernet Adapter Configuration
  In this screenshot, you can see the configuration for the **internal Ethernet adapter**. The internal network is used to allow communication between the **AD Server** and the **UserPC**. Since this is a private network, it’s safe to leave the details as shown without blurring.

  <img width="557" alt="Image" src="https://github.com/user-attachments/assets/2a7a9406-effe-48ad-9e7f-08e9496c8c14" />

  #### Screenshot 3: External Ethernet Adapter Configuration
  This screenshot shows the configuration for the **external Ethernet adapter**. The external adapter connects the **AD Server** to my home network, which allows internet access for the **UserPC**. Please note that some information has been blurred for security reasons.

  <img width="552" alt="Image" src="https://github.com/user-attachments/assets/ddd773cc-fd66-40cd-91d3-b7c4e96de6f8" />

  *Note: The IP address in the screenshot has been blurred to maintain privacy and security.*
</details>

---

### Configuring Network Services: NAT and DHCP
<details>
  <summary>Setting Up NAT and DHCP for Network Communication</summary>

  In this section, I demonstrate how I configured **NAT (Network Address Translation)** and **DHCP (Dynamic Host Configuration Protocol)** on the **AD Server** to allow the **UserPC** to access the internet and automatically receive an IP address.

  #### Screenshot 1: Setting Up NAT for Internet Access
  I configured NAT on the **AD Server** to allow the **UserPC** to access the internet. This setup ensures that the **UserPC** routes internet traffic through the **AD Server**.

  <img width="318" alt="Image" src="https://github.com/user-attachments/assets/0d0cf1b9-e2e3-4809-83c0-54cee7a345c8" />

  #### Screenshot 2: Creating a DHCP Scope
  I set up a **DHCP scope** to define a range of IP addresses that can be assigned dynamically to clients within the network.

  <img width="627" alt="Image" src="https://github.com/user-attachments/assets/a7ed0b87-6af7-438b-8b9e-34a9010382f2" />

  #### Screenshot 3: Defining IP Address Range for DHCP
  This configuration sets up the **IP address range** (192.168.1.100 - 192.168.1.200) that the DHCP server will use to assign addresses to connected devices.

  <img width="632" alt="Image" src="https://github.com/user-attachments/assets/372d778b-f869-415f-8ecb-de983de68c43" />

  #### Screenshot 4: Setting the Default Gateway
  I configured the **default gateway (192.168.1.1)** so that all network traffic from the **UserPC** is properly routed through the **AD Server**.

 <img width="626" alt="Image" src="https://github.com/user-attachments/assets/1003eb44-6bb4-4979-b367-d1529d9a554d" />

  These steps successfully configure **NAT and DHCP** to ensure that the **UserPC** can connect to the **Active Directory** network and access the internet via the **AD Server**.
</details>

---

### UserPC Integration into the Active Directory Domain
<details>
  <summary>Connecting UserPC to the AD Domain and Verifying Network Access</summary>

  In this section, I set up a **Windows 10 VM (UserPC)** on VirtualBox and configured its network adapter to be **internal** so that it can only access the internet through the **AD Server**.

  #### Screenshot 1: UserPC Obtains an IP Address via DHCP
  After installing the Windows 10 VM, the **DHCP server** automatically assigned it an IP address from the configured scope.

  <img width="601" alt="Image" src="https://github.com/user-attachments/assets/120b257d-484e-4d2d-95ea-e721a681fece" />

  #### Screenshot 2: Adding UserPC to the AD Domain
  I joined **UserPC** to the **mytechdomain.local** domain, allowing it to authenticate using Active Directory credentials.

  <img width="400" alt="Image" src="https://github.com/user-attachments/assets/09a00f60-b2c2-4782-939c-22395fd9ea48" />

  #### Screenshot 3: UserPC Appears in Active Directory
  After adding **UserPC** to the domain, it is now listed as a recognized computer in **Active Directory Users and Computers**.

  <img width="536" alt="Image" src="https://github.com/user-attachments/assets/f9466306-5e98-4e68-8798-d6280b983de6" />

  #### Screenshot 4: Verifying Network Configuration and Internet Access
  I created a **HelpDesk account** with administrative privileges and logged into **UserPC** using this account. Running the `ipconfig` command confirmed that **UserPC**:
  - Received an IP address from the **DHCP scope**.
  - Uses the **default gateway (192.168.1.1)** set up on the **AD Server**.
  - Successfully pings `google.com`, verifying that it can access the internet through the **AD Server**.

<img width="483" alt="Image" src="https://github.com/user-attachments/assets/9068612f-ccd2-479b-aae5-d381a32df6ec" />

  This successfully achieves one of the primary project goals: ensuring that **UserPC** is in an internal network but can still reach the internet through the **AD Server**.
</details>

