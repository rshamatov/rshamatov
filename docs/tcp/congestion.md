# TCP Congestion Control

Congestion control algorithms have been developed to maintain performance on congested
networks. Some operating systems (including Linux-based) allow the algorithm to be selected as
part of system tuning. These algorithms include:

* **Reno**: Triple duplicate ACKs trigger: halving of the congestion window, halving of the
slow-start threshold, fast retransmit, and fast recovery.
* **Tahoe**: Triple duplicate ACKs trigger: fast retransmit, halving the slow-start threshold,
congestion window set to one maximum segment size (MSS), and slow-start state. (Along
with Reno, Tahoe was first developed for 4.3BSD.)
* **CUBIC**: Uses a cubic function (hence the name) to scale the window, and a “hybrid start”
function to exit slow start. CUBIC tends to be more aggressive than Reno, and is the
default in Linux.
* **BBR**: Instead of window-based, BBR builds an explicit model of the network path characteristics
(RTT and bandwidth) using probing phases. BBR can provide dramatically better
performance on some network paths, while hurting performance on others. BBRv2 is
currently in development and promises to fix some of the deficiencies of v1.
* **DCTCP**: DataCenter TCP relies on switches configured to emit Explicit Congestion
Notification (ECN) marks at a very shallow queue occupancy to rapidly ramp up to the
available bandwidth (RFC 8257) [Bensley 17]. This makes DCTCP unsuitable for deployment
across the Internet, but in a suitably configured controlled environment it can
improve performance significantly

There're also: Vegas, New Reno, and Hybla.
