<p align="center">
<img src="https://github.com/NGRASS3/TCPDump/assets/111653930/f7624d3a-8319-4b8f-a905-71da934eeb79"/>
</p>

<h1>Analyze Network Traffic with TCPDump</h1>
TCPDump is a command-line packet analyzer tool used in computer networking to capture and analyze network traffic in real-time. It allows you to inspect the packets being transmitted over a network interface, which can be incredibly useful for diagnosing network issues, monitoring network activity, and troubleshooting various network-related problems.

With tcpdump, you can capture packets based on a variety of filters, such as source and destination IP addresses, port numbers, protocols, packet sizes, and more. This helps you focus on the specific types of traffic you're interested in. Once the packets are captured, tcpdump can display their contents in a human-readable format, providing information about the headers, payload, and other relevant details.

In this project I will create shell scripts to capture and analyze packets to a particular website. I will then create a script to monitor traffic on our SSH port. 

<h2>Environments and Technologies Used</h2>

- Cloud Desktop with Ubuntu
- TCPDump
- Wireshark
- -VSCode

<h2>Basic TCPDump Commands used</h2>

- sudo = to run TCPDump with admin priveleges.
- tcpdump = run the tool to capture and analyze network packets.
- -D = shows available network interfaces
- i any = analyze traffic from all available network interfaces.
- -c 10 = capture 10 packets.
- -tttt = show packets in human readable format.
- -# = Add a number to each packet.
- -w test.pcap = write the data to the test.pcap file.
- -C 1 = specify maximum size in megabytes of each capture file.
- -G 60 = sets time intervale (ex: 1minute)

<h2>Capturing Website Traffic</h2>

To start we will create our first script in VSCode with the following input:
<br>
<strong> sudo tcpdump -#XXtttt host skyroute66.com -c 10</strong>

<img src="https://github.com/NGRASS3/TCPDump/assets/111653930/a73855c2-3282-46f8-86a4-60f9b4762008"/>

Once this script is running we can refresh our browser to get some network activity going and see our results in the VSCode 
