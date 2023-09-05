## Steps to Siulate 5G
> Resource : ![](https://www.youtube.com/watch?v=76sT_uP6Gck)
> Password for all the VMs is `ubuntu`
---
- Start all the three VMs : SNR-Core, gNB1, UE1
---
- Go in the SNR-Core VM and open terminal and enter : ```ifconfig```    to note the ip of this machine
- Then enter : ```sudo tcpdump -i any -w free5gc_core.pcap```
- In the same machine open another terminal and enter : ```cd 5Nr-Core/webconsole/```   ,then enter : ```go run server.go```    to start the server.
- Opne another terminal and enter : ```cd 5Nr-Core```   to go inside the folder and then enter ; ```./run.sh```

----

- Go in the 5NR-gNB VM
- Open terminal and run ```ifconfig```  to note down its ip.
- Then run : ```sudo tcpdump -i any -w free5gc_gnb.pcap```
- Then open another terminal and run : ```./start_gNB.sh```

---

- Go in the UE1 VM
- Opne terminal and enter : ```ifconfig```   to note down its ip
- Then run : ```sudo tcpdump -i any -w free5gc_ue.pcap```

---

-  On your Host machine open browser and go at the URL : 192.168.56.101:5000, that is the ip addrs of the SNR-Core VM.
- The username is 'admin' and password is 
- Here you will able to monitor users.
---
- Go back in theUE1 VM, opne another terminal.
- Then run : ```sudo ./start_UE1.sh```

---

- After running for a while and doing some activities in the UE VM, you will have some data, This will be generated in the .pcap files in all the three VMs since we ran tcpdump.
- Now from whichever machine you want either your Host Machine or any other, opne filezilla, enter IP of each VM one by one and donwload the pcap files generated to do the anylysis in wireshark.
