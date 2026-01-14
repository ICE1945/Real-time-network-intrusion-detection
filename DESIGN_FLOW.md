# IDS Design Flow

[ Start IDS Engine ]
        |
        v
[ Initialize Network Interface ]
        |
        v
[ Capture Live Network Packets ]
        |
        v
[ Parse Packet Headers ]
        |
        v
[ Apply Detection Rules ]
        |
        v
[ Suspicious Activity Detected? ]
        |
   +----+----+
   |         |
  Yes        No
   |         |
   v         v
[ Generate Alert ]   [ Continue Monitoring ]
        |
        v
[ Log Event ]
        |
        v
[ Real-Time Monitoring Continues ]
