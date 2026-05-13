PACKETS AND FRAMES

Packets and frames are small pieces of data that, when forming together, make a larger piece of information or message. However, they are two different things in the OSI model. 

A packet is a piece of data from Layer 3 (Network Layer) of the OSI model, containing information such as an IP header and payload. 
A frame, however, is used at Layer 2 (Data Link) of the OSI model, which, encapsulates the packet and adds additional information such as MAC addresses.

You can think of this process as similar to mailing a letter through the post. The envelope is a frame, which, is used to move the contents (in this analogy, the packet) of the envelope to another place. 
Once the recepient opens the envelop (frame), they will know how to forward the letter (packet) itself.

This process is called encapsulation .At this stage, it's safe to assume that when we are talking about anything IP addresses, we are talking about packets.
When the encapsulating information is stripped away, we're talking about the frame itself.

Packets are an efficient way of communicating data across networked devices. Because this data is exchanged in small pieces, 
there is less chance of bottlenecking occurring across a network than large messages being sent at once.

For example, when loading an image from a website, this image is not sent to your computer as a whole, but rather small pieces where it is reconstructed on your computer. 
Take the image below as an illustration of this process. The cat's picture is divided into three packets, where it is reconstructed when it reaches the computer to form the final image.

Packets have different structures that are dependant upon the type of packet that is being sent.
As we'll come on to discuss, networking is full of standards and protocols that act as a set of rules for how the packet is handled on a device.
With billions of devices connected on the internet, things can quickly break down if there is no standardisation.

