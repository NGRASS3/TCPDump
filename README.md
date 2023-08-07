<p align="center">
<img src="https://github.com/NGRASS3/TCPDump/assets/111653930/f7624d3a-8319-4b8f-a905-71da934eeb79"/>
</p>

<h1>Analyze Network Traffic with TCPDump</h1>
<p>
TCPDump is a command-line packet analyzer tool used in computer networking to capture and analyze network traffic in real-time. It allows you to inspect the packets being transmitted over a network interface, which can be incredibly useful for diagnosing network issues, monitoring network activity, and troubleshooting various network-related problems.
</p>

<p>
With tcpdump, you can capture packets based on a variety of filters, such as source and destination IP addresses, port numbers, protocols, packet sizes, and more. This helps you focus on the specific types of traffic you're interested in. Once the packets are captured, tcpdump can display their contents in a human-readable format, providing information about the headers, payload, and other relevant details.
</p>

In this project I will create shell scripts to capture and analyze packets to a particular website. I will then create a script to monitor traffic on our SSH port. 

<h2>Environments and Technologies Used</h2>

- Cloud Desktop with Ubuntu
- TCPDump
- Wireshark
- VSCode

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
<p>
<img src="https://github.com/NGRASS3/TCPDump/assets/111653930/a73855c2-3282-46f8-86a4-60f9b4762008"/>
</p>

We then run the script and get the following results:
<p>
<img src="https://github.com/NGRASS3/TCPDump/assets/111653930/7ab8151b-715b-46f7-8ebd-a9a8b08204a6"/>
</p>

As you can see our script successfully captured data in the format we requested. It has captured 10 packets (-c 10) in a numbered, readable format (-#XXtttt). It also includes source and destination IP and the actual packet contents. 
<br>
</br>
<h2>Analyzing SSH Traffic</h2>

<p>
For this next task we are going to assume someone is potentially trying to open SSH sessions into our workstation. To remedy this we will create a custom script to monitor any TCP traffic coming through SSH. 
</p>
Our script will look as follows:

<strong>sudo tcpdump port 22 -#XXtttt -w proof.pcap -G 600 -C 2</strong>
</p>

<p>
<img src="https://github.com/NGRASS3/TCPDump/assets/111653930/bc44fedf-ed8e-4a60-b3a9-7cc8e868c2f7"/>

</p>
<br />

