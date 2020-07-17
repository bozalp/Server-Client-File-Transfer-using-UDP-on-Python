# Server-Client-File-Transfer-using-UDP-on-Python
### FTP protokolünü UDP üzerinden gerçekleştiren sunucu(server) servisi ve istemcisi(client)

* Hem **Windows** hem de **Linux tabanlı** işletim sistemlerinde çalışmaktadır.
* Sunucu 42. portu dinlemektedir.
* İstemci sunucu bağlantısı için sunucunun IP adresini yazarak bağlanabilmektedir.
* Bağlantı gerçekleştikten sonra **LIST SERVER** yazarak server klasöründeki dosyaları listeleyebilir.
* Bağlantı gerçekleştikten sonra **LIST CLIENT** yazarak client klasöründeki dosyaları listeleyebilir.
* Bağlantı gerçekleştikten sonra **GET dosya_adi.uzanti** şeklinde yazarak server klasöründeki istenen dosya client klasörüne gönderilir.
* Bağlantı gerçekleştikten sonra **PUT dosya_adi.uzanti** şeklinde yazarak client klasöründeki istenen dosya server klasörlerine gönderilir.
* Bağlantı gerçekleştikten sonra **CLOSE** yazarak server ve client arasındaki bağlantısını kesebilirsiniz.
