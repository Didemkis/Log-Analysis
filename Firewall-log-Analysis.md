## FİREWALL LOG ANALİZ

### FİREWALL Log Nedir?

Firewall logları, bir güvenlik duvarı tarafından oluşturulan ve çeşitli ağ etkinliklerinin kayıtlarını tutan dosyalardır. Bu loglar, ağ trafiğini izlemek, analiz etmek ve güvenlik ihlallerini tespit etmek amacıyla kullanılır.

### Firewall Loglarının İçeriği

Firewall logları, genellikle aşağıdaki bilgileri içerir:
*  Kaynak IP Adresi: Trafiğin başladığı cihazın IP adresi.
*  Hedef IP Adresi: Trafiğin yönlendirildiği cihazın IP adresi.
*  Kaynak Port Numarası: Trafiğin başladığı port numarası.
*  Hedef Port Numarası: Trafiğin yönlendirildiği port numarası.
*  Protokol: Kullanılan ağ protokolü (örneğin, TCP, UDP, ICMP).
*  Zaman Damgası: Trafik olayının gerçekleştiği tarih ve saat.
*  Eylem: Güvenlik duvarının trafiği izin verip vermediği veya engellediği bilgisi.
*  Kural: Hangi güvenlik duvarı kuralının trafiğe uygulandığı bilgisi.

** Örnek log formatı:**
1.ÖRNEK: 
```
2024-08-02T14:45:30Z, 10.0.0.5, 198.51.100.7, 12345, 443, TCP, DENIED, Block External HTTPS Traffic, Port Scan Detected

```

Analiz 

```
Timestamp (Zaman Damgası): 2024-08-02T14:45:30Z  <!-- Olayın kaydedildiği tarih ve saat.  -->
Source IP (Kaynak IP): 10.0.0.5 <!-- Trafiğin başladığı cihazın IP adresi.  -->
Destination IP (Hedef IP): 198.51.100.7 <!--  Trafiğin yönlendirildiği cihazın IP adresi. -->
Source Port (Kaynak Port): 12345  <!--  Trafiğin başladığı port numarası. -->
Destination Port (Hedef Port): 443  <!-- Trafiğin yönlendirildiği port numarası. 443 portu genellikle HTTPS trafiği için kullanılır. -->
Protocol (Protokol): TCP  <!--  Kullanılan ağ protokolü. -->
Action (Eylem): DENIED  <!--  Trafiğin güvenlik duvarı tarafından engellendiğini belirtir. -->
Rule (Kural): Block External HTTPS Traffic  <!--  Hangi güvenlik duvarı kuralının uygulandığını belirtir.  -->
Additional Info (Ek Bilgi): Port Scan Detected  

```
2.ÖRNEK: 
```
date=2023-07-25 time=09:23:35 logid="0002000035" type="traffic" subtype="local" level="notice" vd="vdom2" eventtime=1688555012345678912 srcip=10.0.0.1 srcport=54321 srcintf="port22" srcintfrole="undefined" dstip=10.0.0.2 dstport=8443 dstintf="vdom2" dstintfrole="undefined" sessionid=204856 proto=6 action="server-rst" policyid=1 policytype="local-in-policy" service="HTTPS" dstcountry="Reserved" srccountry="Reserved" trandisp="noop" app="Web Management(HTTPS)" duration=8 sentbyte=2345 rcvdbyte=3456 sentpkt=7 rcvdpkt=8 appcat="unscanned"

```

Analiz 

```
Timestamp (Zaman Damgası):  25.07.2023 time: 09:23:35
Source IP (Kaynak IP): 10.0.0.1
Destination IP (Hedef IP): 10.0.0.2
Source Port (Kaynak Port): 54321  
Destination Port (Hedef Port):8443 
Hizmet: service="HTTPS"

```