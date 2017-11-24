# WIFI Hacking #
---
1.这个直接使用wireshark中wireless中wifi traffic，然后找出beacons frame存在的SSID

![](3/1.png)

2.使用tshark命令
找出ssid==a101-guest 并且是probe respond，然后目的地址为所求

![](3/2.png)

3.第三题我做的时候比较困难，一开始在wirshark的wireless->wifi traffic中筛出probe request-beacons frame-probe respond 找出三个GGBWG-G	Chu-Sushi	Apple Setup提交一直不对，然后手工在wireshark里找所有SSID，发现漏了sharkAP，而这个SSID，只有probe request 类型，符合条件，然后就把这个加进去了

![](3/3.1.PNG)

![](3/3.2.PNG)

4.我在wireshark->wireless->wifitraffic中发现有一个地址发过很多probe request包，但是这个地址没有收到回应，所以这个地址为乱入的手机,然后把这个地址作为过滤条件得结果,将乱码的解出来是“神州专车”

![](3/4.PNG)

![](3/4.2/PNG)

6.这道题在wireshark里找到过滤条件怎么写，然后用tshark命令得出结果

![](3/6.1.PNG)

![](3/6.png)

7.在wireshark->wireless->wifitraffic中发现有两bssid 没有beacons frame 但是却有responde

![](3/7.PNG)


5.这道题Group和Pairwise 的Cipher Suite type要一致，我一开始只pairwise cipher suite type找出的是错的，然后看到上面有个group cipher suite type,就把这个作为与过滤条件，得出结果

![](3/5.PNG)

8.隐藏SSID
我抓的包里只找到两个

![](3/SSID.png)