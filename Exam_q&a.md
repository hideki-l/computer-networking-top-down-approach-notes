# Exam questions and answers

## Chapter 1: Computer Networks and the Internet

## Chapter 2: Application Layer

## Chapter 3: Transport Layer

### What are ACKs and NAKs ?

In networking, ACKs (Acknowledgements) and NAKs (Negative Acknowledgements) are control messages used in communication protocols to manage the reliability of data transmission between devices. These messages help ensure data is transmitted correctly and reliably, allowing the sender and receiver to confirm the successful receipt (ACK) or detect errors (NAK). 
An ACK is a signal sent by the receiver to the sender to indicate that a packet of data has been successfully received without errors. A NAK is a signal sent by the receiver to the sender indicating that a packet was not successfully received, either due to errors or loss, and needs to be resent.

  - When a receiver successfully receives a data packet, it sends an ACK message back to the sender. The ACK typically contains the sequence number of the last successfully received packet, so the sender knows which data has been correctly received.
  - When a receiver detects an error (e.g., checksum failure, missing packet, etc.) or a lost packet, it sends a NAK message back to the sender. The sender then retransmits the specific data that was not received correctly.

### What's the difference between flow control and congestion control ?

Flow control is controlled by the receiving side. It ensures that the sender only sends what the receiver can handle. Think of a situation where someone with a fast fiber connection might be sending to someone on dialup or something similar. The sender would have the ability to send packets very quickly, but that would be useless to the receiver on dialup, so they would need a way to throttle what the sending side can send. Flow control deals with the mechanisms available to ensure that this communication goes smoothly.

Congestion control is a method of ensuring that everyone across a network has a "fair" amount of access to network resources, at any given time. In a mixed-network environment, everyone needs to be able to assume the same general level of performance. A common scenario to help understand this is an office LAN. You have a number of LAN segments in an office all doing their thing within the LAN, but then they may all need to go out over a WAN link that is slower than the constituent LAN segments. Picture having 100mb connections within the LAN that ultimately go out through a 5mb WAN link. Some kind of congestion control would need to be in place there to ensure there are no issues across the greater network.
