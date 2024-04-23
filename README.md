# intel-smi
A wrapper to create `nvidia-smi` style output of `xpumcli`/`xpu-smi`. 

Outputs from `xpumcli` discovery is too little, while outputs from `xpumcli discovery -d0` or `xpumcli stats -d0` are too much to be useful. 
It's even so hard to browse basic info like how much memory is used or which tile is active. 

So this script extracts key info that most commonly matters to users, and form an `nvidia-smi` style output. 

Intel, thanks for making your tools work like crap. 


