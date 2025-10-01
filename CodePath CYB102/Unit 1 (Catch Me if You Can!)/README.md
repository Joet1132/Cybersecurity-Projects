This project introduces me to using Wireshark in order to inspect ``.pcap`` files and find the malicious actor's IP address, and subject lines of three different phishing emails that I've identified. I have also shown the body contents of three different ``.eml`` files all within the CLI via SSH on the virtual machine.  I tried to use Outlook on the Ubuntu RDP, but RDP was just too slow. I instead used the cat command to read these .eml files and screenshotted it from there. The command I used to download the .eml files was: ``tshark -r C.pcap -o tcp.desegment_tcp_streams:TRUE -o tcp.reassemble_out_of_order:TRUE -q --export-objects imf,phishing_emails`` (.eml files go into ``phishing_emails`` directory)

#### From the assignment, I was also required to give an explanation of how I went about finding the bad apple from just the .pcap files. My explanation is as follows:

1.) I installed Wireshark onto my Ubuntu WSL while it is connected to Azure Labs VM by SSH. 

2.) Then I figured out how to download the pcap.files.zip from the CodePath’s Unit 1 Project webpage. The command that I used was ``wget -O pcap_files.zip http://courses.codepath.org/course_files/cyb102/project_1/pcap_files.zip``

3.) I then unzipped the pcap_files.zip while in the directory, and it brought out 4 different .pcap files. I used the command: ``unzip -l pcap_files.zip``

4.) I proceeded to play around with using the tshark command to see what I can come up with. I looked through each of the four .pcap files one by one. Starting with : ``tshark -r A.pcap``

5.) I knew I needed to look for a pattern in order to narrow down and identify who the malicious actor is. I used ChatGPT as well as the Wireshark Display Filter Reference to help me get closer to writing the correct commands for tshark. I used filters like ``smtp`` as well as ``imf``

6.) Command that I used: ``tshark -r C.pcap -Y “smtp && imf”``

7.) This ultimately not only filtered out SMTP packets, but also having imf in there helped to filter only decoded information on the sender, their email, and what’s written in the subject header. 

8.) The C.pcap packet file contains information regarding a malicious actor sending out phishing emails to 2 employees. (the two victims here are 98.137.159.26 and 106.10.248.75).


