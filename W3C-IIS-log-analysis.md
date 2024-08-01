## W3C ISS LOG ANALİZ

### W3C ISS Log Nedir?

W3C ISS (Internet Security Systems) logları, bir ağ veya sistem üzerinde güvenlik olaylarını ve faaliyetlerini izlemek, analiz etmek ve yönetmek için kullanılan log kayıtlarıdır. Bu loglar, ISS çözümlerinin sağladığı güvenlik verilerini içeren bir formatta düzenlenmiştir. W3C formatı, web standartları organizasyonu tarafından belirlenen ve veri paylaşımı ve işlenebilirliği açısından tutarlı bir biçim sağlar.

W3C günlük dosyasındaki her giriş, günlük aracının istekleri birbirinden ayırt etmesine olanak tanıyan benzersiz bir tanımlayıcı içerir. Bu tanımlayıcı, istek satırı ve gövde metni gibi isteğin farklı bölümlerini ayırmak için de kullanılabilir.


Örneğin, bir istemci statik bir dosyada saklanan bir web sayfasına erişim istediğinde, cs-uri-stem alanı istemci tarafından talep edilen dosyanın ne olduğunu belirtir. Bu alanlar, sunucu günlüklerinde kötü amaçlı kodların veya diğer anormalliklerin tespit edilmesinde çok değerlidir.

Ayrıca, cs-uri-stem alanı kullanıcının hangi tarayıcıyı kullandığını belirtirken, cs-kullanıcı adı alanı web sunucusuna kimlik doğrulaması yapan kişinin bilgilerini sağlar. Bu bilgiler, sunucu güvenliğini izlemek ve olası tehditleri tespit etmek için kritik öneme sahiptir.

** Örnek log formatı:**

```
#Version: 1.0
#Date: 12-Jan-1996 00:00:00
#Fields: time cs-method cs-uri
00:34:23 GET /foo/bar.html
```

Çeşitli logları analiz yapalım : 
```
#Fields: date time s-ip cs-method cs-uri-stem cs-uri-query s-port cs-username c-ip cs(User-Agent) cs(Referer) sc-status sc-substatus sc-win32-status time-taken
```

1. LOG : 

```
#Software: Microsoft Internet Information Services 10.0
#Version: 1.0
#Date: 2024-08-01 15:45:00
#Fields: date time s-ip cs-method cs-uri-stem cs-uri-query s-port cs-username c-ip cs(User-Agent) cs(Referer) sc-status sc-substatus sc-win32-status time-taken
2024-08-01 15:45:00 fe80::abcd:1234:efgh:5678%1 RPC_IN_DATA /rpc/rpcproxy.dll 2e5038fc-7891-45cd-93fe-gh90j21k030h@test.com:7001&CorrelationID=<empty>;&RequestId=22e7b89b-8d45-5g54-9511-be34d215bb73&cafeReqId=22e7b89b-8d45-5g54-9511-be34d215bb73; 443 TEST\HealthMailbox1234567 fe80::abcd:1234:efgh:5678%1 MSRPC - 503 1 1 9123

```

ANALİZ: 

```
    Yazılım: Microsoft Internet Information Services 10.0
    Sürüm: 1.0
    Tarih: 2024-08-01
    Alanlar:
        date: 01.08.2024
        time: 15:45:00
        s-ip: Sunucu IP adresi
        cs-method: RPC_IN_DATA
        cs-uri-stem: /rpc/rpcproxy.dll
        cs-uri-query: 2e5038fc-7891-45cd-93fe-gh90j21k030h@test.com:7001&CorrelationID=<empty>;&RequestId=22e7b89b-8d45-5g54-9511-be34d215bb73&cafeReqId=22e7b89b-8d45-5g54-9511-be34d215bb73;
        s-port: 443
        cs-username: TEST\HealthMailbox1234567
        c-ip: fe80::abcd:1234:efgh:5678%1
        cs(User-Agent): MSRPC
        cs(Referer): -
        sc-status: 503

```
2. LOG : 

```
2023-01-15 12:34:56 172.16.0.1 PATCH /api/update - 8080 - 172.16.3.1 Mozilla/5.0+(Windows+NT+10.0;+Win64;+x64)+AppleWebKit/537.36+(KHTML,+like+Gecko)+Chrome/91.0.4472.124+Safari/537.36 - 201 1 0 1234

```
ANALİZ: 

```
Alanlar:
        date: 15.01.2023
        time: 12:34:56
        s-ip: 172.16.0.1
        cs-method: PATCH
        cs-uri-stem: /api/update
        s-port: 8080
        cs-username: -
        c-ip: 172.16.3.1
        cs(User-Agent): Mozilla/5.0+(Windows+NT+10.0;+Win64;+x64)+AppleWebKit/537.36+(KHTML,+like+Gecko)+Chrome/91.0.4472.124+Safari/537.36
        cs(Referer): -
        sc-status: -
        time-taken: 1234

```