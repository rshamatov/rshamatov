# TCP Offloading

## GSO

Network devices and networks accept packet sizes up to a maximum segment size (MSS) that
may be as small as 1500 bytes. To avoid the network stack overheads of sending many small
packets, Linux uses **generic segmentation offload (GSO)** to send packets up to 64 Kbytes in size (“super packets”), which are split into MSS-sized segments just before delivery to the network device. If the NIC and driver support TCP **segmentation offload (TSO)**, GSO leaves splitting to the device, improving network stack throughput. There is also a **generic receive offload (GRO)** complement to GSO.6 GRO and GSO are implemented in kernel software, and TSO is implemented by NIC hardware.
