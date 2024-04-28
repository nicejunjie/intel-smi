# intel-smi
A wrapper to create `nvidia-smi` style output of `xpumcli`/`xpu-smi`. 
*** 

Outputs from `xpumcli` discovery is too little, while outputs from `xpumcli discovery -d0` or `xpumcli stats -d0` are too much to be useful. 
It's even so hard to browse basic info like how much memory is used or which tile is active. 

So this script extracts key info that most commonly matters to users, and form an `nvidia-smi` style output. 

Intel, thanks for making those crappy tools.  


**Usage:** <br>
  `intel-smi` will prints info of all devices. <br>
  `intel-smi -d DEVICE_ID` will show info of a particular device, multiple devices can be specified as a comma-separated list (e.g., -d0,2,3). <br>
  `intel-smi -h` prints help message. <br>
  `intel-smi -u` prints some useful commands or environmental variables for Intel GPU. <br>


**Example:** <br>
```
junjieli@c552-008.stampede3:>intel-smi
Sun Apr 28 03:13:32 PM EDT 2024
+-------------------------------------------------------------------v0.4.23-+
|  Driver Version: I915_23.10.32_PSB_231129.32                              |
|  Kernel Version: 5.14.0-284.30.1.el9_2.x86_64                             |
|  GFX Firmware Version: PVC2_1.23263                                       |
|  GFX PSC Firmware Version: 0x1012ca9.0x20220803                           |
|  AMC Firmware Version: 6.7.0.0                                            |
+-------------------------------------+--------------------------+----------+
| Device            GPU-Name          |       PCI-BDF-Addr       |   ECC    |
|   Tile      Temp     Pwr:Usage/Cap  |        Mem-Usage         | GPU-Util |
|=====================================+==========================+==========|
| 0         Data Center GPU Max 1550  |             0000:4b:00.0 |     on   |
|  0.0        33C        52W/300W     |       64MiB/65536MiB(0%) |     0%   |
|  0.1        29C         3W/300W     |       61MiB/65536MiB(0%) |     0%   |
|-------------------------------------+--------------------------+----------|
| 1         Data Center GPU Max 1550  |             0000:5c:00.0 |     on   |
|  1.0        31C        68W/300W     |       63MiB/65536MiB(0%) |     0%   |
|  1.1        30C        67W/300W     |       61MiB/65536MiB(0%) |     0%   |
|-------------------------------------+--------------------------+----------|
| 2         Data Center GPU Max 1550  |             0000:9a:00.0 |     on   |
|  2.0        30C        70W/300W     |       63MiB/65536MiB(0%) |     0%   |
|  2.1        30C        68W/300W     |       61MiB/65536MiB(0%) |     0%   |
|-------------------------------------+--------------------------+----------|
| 3         Data Center GPU Max 1550  |             0000:ca:00.0 |     on   |
|  3.0        31C        68W/300W     |       63MiB/65536MiB(0%) |     0%   |
|  3.1        31C        70W/300W     |       61MiB/65536MiB(0%) |     0%   |
+-------------------------------------+--------------------------+----------+
+---------------------------------------------------------------------------+
|PID       Command           DeviceID        SHR              MEM           |
|===========================================================================|
|2317833   xhpl_intel64_dy     0              0              18415          |
|2317769   xhpl_intel64_dy     0              0              6881           |
|2317833   xhpl_intel64_dy     1              0              18415          |
|2317769   xhpl_intel64_dy     1              0              6881           |
|2317833   xhpl_intel64_dy     2              0              6881           |
|2317769   xhpl_intel64_dy     2              0              18415          |
|2317833   xhpl_intel64_dy     3              0              6881           |
|2317769   xhpl_intel64_dy     3              0              18415          |
+---------------------------------------------------------------------------+
intel-smi runtime: 0.285s 
```
