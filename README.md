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


