# ROAD TO WIRESHARK

<video src="C:\Users\noble\Desktop\PROJECTS\road-to-wireshark\videos\001 Capturingpackets.mp4" width="320" height="240" controls></video>

## Introduction

Welcome to the "Road to Wireshark" repository! This repository will document my learning journey as I dive deep into Wireshark, guided by the Udemy course **[Getting Started with Wireshark: The Ultimate Hands-On Course](https://www.udemy.com/course/wireshark-ultimate-hands-on-course/?couponCode=KEEPLEARNING)** by Chris Greer. This course is designed to make the intimidating world of packet analysis approachable and actionable, helping IT engineers and cybersecurity professionals enhance their network troubleshooting and analysis skills.
This repo is dedicated to documenting my journey in learning Wireshark, a powerful network protocol analyzer. Below you'll find an outline of the topics I'll be covering, along with some initial resources and notes.

## Course Overview

### Course Title:
**Getting Started with Wireshark: The Ultimate Hands-On Course**

### Instructor:
Chris Greer, Wireshark University instructor and packet analysis consultant.

### Duration:
7 hours

### Description:
Wireshark can be overwhelming with the vast amount of data it captures. This course aims to demystify the tool, showing you practical ways to use Wireshark to solve network issues and isolate cybersecurity incidents. Real-world examples, assignments, and hands-on exercises will help you become comfortable with the interface, understand core protocols, and develop the skills to interpret packets and find actionable data quickly.

### What You’ll Learn:
- Capture and interpret network traffic with Wireshark
- Understand core networking protocols: DHCP, DNS, TCP/IP
- Troubleshoot the top five network problems with Wireshark
- Analyze cybersecurity attacks with Wireshark

### Prerequisites:
- Basic understanding of networking (switching, routing)

### Target Audience:
- Network Engineers and Cybersecurity professionals
- Threat hunters looking to delve into protocol analysis

## Goals and Objectives

Through this course, my primary objectives are to:
1. **Gain Proficiency in Wireshark:** Learn to navigate the Wireshark interface, customize it, and utilize its features effectively.
2. **Understand Network Protocols:** Develop a solid understanding of core networking protocols and how to analyze them using Wireshark.
3. **Troubleshoot Network Issues:** Acquire the skills to identify and troubleshoot common network problems.
4. **Analyze Cybersecurity Incidents:** Learn to capture and interpret traffic related to cybersecurity attacks.

## Learning Roadmap

This section will be updated as I progress through the course, documenting my notes and key learnings from each module. The roadmap will be structured according to the course curriculum and include:

1. **Introduction to Wireshark**
   - Installation and initial setup
   - Overview of the Wireshark interface
2. **Capturing Traffic**
   - Selecting interfaces
   - Starting and stopping captures
3. **Display and Capture Filters**
   - Basic and advanced filter usage
4. **Analyzing Packets**
   - Packet details and bytes pane
   - Common protocols and their analysis
5. **Real-World Examples**
   - Troubleshooting network issues
   - Analyzing security incidents


## What is Wireshark?

Wireshark is an open-source packet analyzer used for network troubleshooting, analysis, software and protocol development, and education. It captures and interactively browses the traffic running on a computer network.

### Key Features:
- Live capture and offline analysis
- Deep inspection of hundreds of protocols
- Standard three-pane packet browser**
- Multi-platform support (Windows, macOS, and UNIX)
- Rich VoIP analysis
- Read/write many different capture file formats
- Powerful display filters
- Decryption support for many protocols

## Section Five (5): Where and How to Capture Packets

#### Think BEFORE You Capture!

In the module "Think Before You Capture," I learned the importance of planning before diving into packet analysis with Wireshark. First, identify who is affected by the issue, whether it's isolated or widespread, and whether it's consistent or intermittent. Determine which applications and servers are impacted and if they are local or cloud-based. Understanding the network path the traffic traverses is essential for a clean capture. By considering these factors beforehand, I can capture data more effectively and resolve issues faster.

 #### How To Capture In a Switched Environment - Local Capture vs SPAN vs TAP

In this module, I learned the following key points about capturing traffic in a switched environment:

1. **Local Capture:** Installing Wireshark directly on an endpoint can be quick and easy but may strain the device's resources, especially on busy servers.
2. **SPAN/Mirror:** This method involves configuring network devices to forward packets to a monitor port. It's crucial to avoid overloading the SPAN port by sending too much traffic.
3. **Network TAP:** A TAP is a physical device inserted into the network path, providing a reliable way to capture traffic without burdening the network devices or endpoints.

Understanding these methods helps ensure effective packet capturing in switched environments.

### Capturing at Multiple Locations

When troubleshooting network issues, especially performance problems, it's beneficial to capture traffic from multiple network points. Here are the key points I learned:

1. **Client-Side Capture:** Capturing packets from the client can reveal local network conditions, broadcast activity, and the client's interactions with multiple servers.
2. **Server-Side Capture:** Capturing packets from the server can show interactions with other backend services, such as application or database servers, which might be causing the slowdown.
3. **Dual-Side Capture:** Capturing from both client and server sides helps in identifying issues like retransmissions and packet loss, offering a clearer picture of where the problem lies.

This multi-point capture approach provides a comprehensive view of the network issue, making troubleshooting more effective.

### Using Capture Filter?

- **Capture Filter**: Allows you to collect only specific traffic based on criteria you set (e.g., TCP packets, traffic to/from a specific IP address).

- **When to Use**:
  - If you know exactly what you need and want to limit the amount of captured data.
  - Useful in busy environments to focus on relevant traffic.

- **When to Avoid**:
  - If you are unsure of the issue or need to see all network activity, as capture filters might miss important traffic (e.g., backend server conversations).
  - Specific filters might exclude useful information from other protocols (e.g., ICMP messages for troubleshooting TCP issues).

- **Best Practice**:
  - Capture all traffic initially and then use display filters to analyze data. This approach provides a more comprehensive view and aids in thorough troubleshooting.
  
 ### Capturing traffic with Wireshark : User Interface

When I start Wireshark, it shows all the available interfaces, including Ethernet and Wi-Fi. To begin capturing, I select the relevant interface and click the blue shark fin icon. To stop the capture, I click the red square icon.
![All Interfaces](images/001_interfaces.png)

I learned to enable promiscuous mode in the capture options, which allows me to capture all traffic on the network, not just my own. I also discovered the snap length setting, which lets me capture only the headers (e.g., 64 bytes) to save space and avoid capturing sensitive payloads.

**Capturing Packets** 

<iframe width="560" height="315" src="https://github.com/user-attachments/assets/9afcfb8e-9be0-478d-9b32-d6ba09ac67ee" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media></iframe>

Customizing the interface list to show only the ones I use regularly is another valuable lesson. I can manage these interfaces in the capture options by unchecking those I don't need. After configuring these settings, I can start capturing traffic by clicking "Start."
![Snaplink_Capture](images/002_Snaplinks.png)

#### Long-Term Capture Configuration with Wireshark

Setting up long-term capture in Wireshark is essential for troubleshooting intermittent issues and monitoring for cybersecurity threats. By using the capture options in the Wireshark interface, I can start capturing traffic on a selected interface and configure it to save the data to a permanent file. Instead of capturing one massive file, I learned to use a **ring buffer,** which captures several smaller files and overwrites the oldest files when the buffer is full. 
![CapturesPcaps](images/004_longTermcaptures.png)
This setup helps manage disk space efficiently and makes it easier to pinpoint when an issue occurred. I also discovered that enabling promiscuous mode allows capturing all network traffic, not just traffic to and from my machine. Additionally, using the **pcapng** format over pcap provides more metadata, which is helpful for analysis. With these configurations, I can ensure continuous monitoring and have historical data available for when problems arise or if a security incident occurs. 

Video Below
<video controls src="videos/002 Longtermcapture.mp4" title="Capturing Packets in Ring Buffer"></video>

