# TCP Overview

Transport issues are the responsibility of the endpoints in question and thus should not be delegated to the core network.

Two issues falling under this category are data **corruption** and **congestion**. For the first, even
though essentially all links on the Internet have link-layer checksums to protect against data corruption, TCP still adds its own checksum (in part because of a history of data errors introduced *within* routers). For the latter,  TCP is today essentially the *only* layer  that addresses congestion management.
