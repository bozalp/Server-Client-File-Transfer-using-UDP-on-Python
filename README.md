# Server-Client-File-Transfer-using-UDP-on-Python
### Basit şekilde FTP protokolünü UDP üzerinden gerçekleştiren sunucu(server) servisi ve istemcisi(client)
#### Yazar: Batuhan ÖZALP
#### Program dili: Python3
#### Çalışan platformlar: Windows-Linux tabanlı işletim sistemleri
* Sunucu 42. portu dinlemektedir.
* İstemci sunucu bağlantısı için sunucunun IP adresini yazarak bağlanabilmektedir.
#### Nasıl Çalışır?
CMD ya da terminal üzerinden önce server.py bulunduğu kısımda **python server.py** yazıp çalıştırılır. Daha sonra client tarafında client.py dosyasının bulunduğu yere gidip **python client.py** komutları çalıştırılır. Linux'ta **sudo python3 server.py-client.py** şeklinde yazılmalıdır. Daha sonra client kısmından server bilgisayarının ip adresi girilerek bağlantı sağlanır. Bağlantı kurulduktan sonra aşağıda listenen komutlar ile program üzerinde işlemler yapılabilir.
* Bağlantı gerçekleştikten sonra **LIST SERVER** yazarak server klasöründeki dosyaları listeleyebilir.
* Bağlantı gerçekleştikten sonra **LIST CLIENT** yazarak client klasöründeki dosyaları listeleyebilir.
* Bağlantı gerçekleştikten sonra **GET dosya_adi.uzanti** şeklinde yazarak server klasöründeki istenen dosya client_dosyalarina gönderilir.
* Bağlantı gerçekleştikten sonra **PUT dosya_adi.uzanti** şeklinde yazarak client klasöründeki istenen dosya server_dosyalarina gönderilir.
* Bağlantı gerçekleştikten sonra **CLOSE** yazarak server ve client arasındaki bağlantısını kesebilirsiniz.

#### Kodlar arkaplanda nasıl çalışır?

**1. LIST SERVER** >>
Bu kısımda client tarafından servera **listele** mesajı gönderilir. Server gelen mesaja karşılık olarak server_dosyalari isimli klasördeki dosya isimlerini diziye ekler. Daha sonra diziyi client tarafına mesaj olarak iletir. 

**2. LIST CLIENT** >>
Bu kısım client_dosyalari isimli klasördeki dosya isimlerini diziye ekler. Daha sonra diziyi client ekranında gösterir.

**3. GET dosya_adi.uzanti** >>
Server kısmında bulunan bir dosyayı kendinize almak için bu komut kullanılır. Server tarafına **get** mesajı iletilir. Server gelen mesaja karşılık eğer o dosya server_klasorunde yer almıyorsa **dosyayok** mesajını client tarafına gönderir ve server klasöründe de dosyanın bulunmadığı yazdırılır. Eğer dosya ismi ve uzantısı uyuşuyorsa dosya adı, dosya boyutu ve son olarak da dosyanın verilerini client tarafına yollar. Aktarım bittikten sonra serverdan gelen dosya boyutu bilgisi ile client_klasorune yerleşen dosyanın boyutları karşılaştırılır ve birbirlerini tutması halinde **basarili** mesajını servera yollar ve iki tarafın ekranına da **Dosya basariyla alindi :D** bastırır. Diğer durumda ise **basarisiz** şeklinde mesaj servera yollanır ve iki tarafın ekranına da **Dosya eksik sekilde alindi ya da hic alinmadi** yazdırılır.

**4. PUT dosya_adi.uzanti** >>
Client tarafındaki dosyayı server tarafına göndermek için kullanılır. **GET** kısmından tek farkı server ve client isimlerinin yerlerinin değişmesidir. Gönderim ve alım kısmı üst kısımda anlatıldığının tam tersi durumdadır. 

**5. CLOSE** >> 
Client tarafından bu komut yazılırsa servera **kapat** mesajı iletilir ve iki tarafın bağlantısı kesilir ve progrmadan çıkış yapılır. 
