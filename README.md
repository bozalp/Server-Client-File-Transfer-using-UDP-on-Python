# Server-Client-File-Transfer-using-UDP-on-Python
### Basit şekilde FTP protokolünü UDP üzerinden gerçekleştiren sunucu(server) servisi ve istemcisi(client)

* Hem **Windows** hem de **Linux tabanlı** işletim sistemlerinde çalışmaktadır.
* Sunucu 42. portu dinlemektedir.
* İstemci sunucu bağlantısı için sunucunun IP adresini yazarak bağlanabilmektedir.
* Bağlantı gerçekleştikten sonra **LIST SERVER** yazarak server klasöründeki dosyaları listeleyebilir.
* Bağlantı gerçekleştikten sonra **LIST CLIENT** yazarak client klasöründeki dosyaları listeleyebilir.
* Bağlantı gerçekleştikten sonra **GET dosya_adi.uzanti** şeklinde yazarak server klasöründeki istenen dosya client_dosyalarina gönderilir.
* Bağlantı gerçekleştikten sonra **PUT dosya_adi.uzanti** şeklinde yazarak client klasöründeki istenen dosya server_dosyalarina gönderilir.
* Bağlantı gerçekleştikten sonra **CLOSE** yazarak server ve client arasındaki bağlantısını kesebilirsiniz.

**1. LIST SERVER** >>
Bu kısımda client tarafından servera **listele** mesajı gönderilir. Server gelen mesaja karşılık olarak server_dosyalari isimli klasördeki dosya isimlerini diziye ekler. Daha sonra diziyi client tarafına mesaj olarak iletir. 

**2. LIST CLIENT** >>
Bu kısım client_dosyalari isimli klasördeki dosya isimlerini diziye ekler. Daha sonra diziyi client ekranında gösterir.

**GET dosya_adi.uzanti** >>
Server kısmında bulunan bir dosyayı kendinize göndermek için bu komut kullanılır. Server tarafında **get** mesajı iletilir. Server gelen mesaja karşılık eğer o dosya server_klasorunde yer almıyorsa **dosyayok** mesajını client tarafına gönderir ve server klasöründe de dosyanın bulunmadığı yazdırılır. Eğer dosya ismi ve uzantısı uyuşuyorsa dosya adı, dosya boyutu ve son olarak da dosyanın verilerini client tarafına yollar. Aktarım bittikten sonra serverdan gelen dosya boyutu bilgisi ile client_klasorune yerleşen dosyanın boyutları karşılaştırılır ve birbirlerini tutması halinde **basarili** mesajını servera yollar ve iki tarafın ekranına da **Dosya basariyla alindi :D** bastırır. Diğer durumda ise **basarisiz** şeklinde mesaj servera yollanır ve iki tarafın ekranına da **Dosya eksik sekilde alindi ya da hic alinmadi** yazdırılır.
