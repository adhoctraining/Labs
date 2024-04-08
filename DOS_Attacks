## Lab: DoS/DDoS Attacks

 

Objective: The objective of this lab is to demonstrate various types of Denial of Service (DoS) and Distributed Denial of Service (DDoS) attacks using Linux tools like hping3, and to understand the impact of these attacks on a network.

Pre-lab:

    Download and set up a Linux VM (e.g., Ubuntu, MXLinux, Debian, or Kali).
    Install required packages: wireshark, hping3, htop, and nmap.
    Clone the Linux VM twice in VirtualBox, naming them "Server 1" and "Server 2". Set the network adapter for each VM to internal network.
    Log in to the Linux VM using the credentials provided.
    Open a terminal and perform package installation and VM cloning.

Lab Steps:

Step 1: Understanding DoS Attacks

    Explanation of DoS Attack:
        Provide an overview of Denial of Service (DoS) attacks, emphasizing their purpose, which is to disrupt normal network services by overwhelming the target system with a flood of illegitimate traffic.
        Discuss the impact of DoS attacks on network availability and performance.

    Demonstration of Ping:
        Open a terminal on Server 2 and note its IP address using the command ip address.
        Ping Server 2 from Server 1 using the command ping [Server 2 IP].
        Capture and analyze packets exchanged during the ping using Wireshark on Server 1.
        Explain the ICMP Echo Request and Echo Reply packets observed in Wireshark, highlighting the normal communication between the two servers.

Step 2: Ping Flood DoS Attack

    Explanation of Ping Flood Attack:
        Discuss the concept of a Ping Flood attack, where an attacker sends an overwhelming number of ICMP Echo Request packets to the target system, consuming its resources and causing network congestion.
        Highlight the simplicity and effectiveness of this attack in disrupting network services.

    Demonstration of Ping Flood Attack:
        Clear the terminal and start Wireshark packet capture.
        Execute a ping flood attack from Server 1 to Server 2 using hping3 with the command hping3 -1 --flood -c 1000 [Server 2 IP].
            -1: Indicates ICMP protocol.
            --flood: Sends packets as fast as possible.
            -c 1000: Sends 1000 ICMP Echo Request packets.
        Observe the flood of ICMP Echo Request packets in Wireshark.
        Discuss the impact of the attack on Server 2's resources, such as increased CPU and network utilization.

    Variations of Ping Flood Attack:
        Repeat the attack with different options of hping3 (--fast, --faster, --rand-source) to demonstrate varying intensities of the attack.
        Explain the significance of each option in terms of packet transmission rate and attack severity.
        Discuss the implications of spoofing the source IP address using the --spoof option in hping3 for evading detection.

Step 3: SYN Flood DoS Attack

    Explanation of SYN Flood Attack:
        Provide an overview of SYN Flood attacks, which exploit the TCP Three-Way Handshake process to exhaust the target system's resources by inundating it with SYN packets without completing the handshake.
        Discuss the impact of SYN Flood attacks on network services, such as denial of access to legitimate users.

    Demonstration of SYN Flood Attack:
        Explain the TCP Three-Way Handshake process, emphasizing the SYN, SYN-ACK, and ACK packets exchanged between client and server.
        Demonstrate a SYN flood attack on port 80 of Server 2 using hping3 with the command hping3 -S --flood -p 80 [Server 2 IP].
            -S: Indicates SYN packet.
            --flood: Sends packets as fast as possible.
            -p 80: Specifies port 80 as the target port.
        Observe the flood of SYN packets in Wireshark and discuss the impact on Server 2's resources, such as increased memory and connection table utilization.

    Additional Resources for Understanding SYN Flood Attacks:
        Provide references or links to external resources, such as videos or articles, for further exploration of SYN Flood attacks and mitigation strategies.
        Encourage students to conduct additional research to deepen their understanding of this type of DoS attack.

Conclusion: In this lab, you learned about various types of Denial of Service (DoS) attacks, including Ping Flood and SYN Flood attacks, and their impact on network availability and performance. By using Linux tools like hping3 and Wireshark, you were able to simulate and observe the effects of these attacks on network traffic and server resources. Understanding these attack techniques is essential for network administrators to implement effective defense mechanisms and mitigate the risk of DoS attacks.
