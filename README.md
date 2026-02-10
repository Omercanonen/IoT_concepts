## Domainler:

### SCADA:
Üretimde bulunan makinelerin izlenmesinde, veri toplanmasında kullanılır. Makinede bulunan PLC ve sensörlerden veri toplar (Makine sıcaklığı, makine durumu gibi bilgiler).
Nasıl çalışıyor sorusuna odaklanır.

#### Bileşenleri:
RTU: Sensör ve aktüatörlerle iletişim kurar ve veri toplar.

PLC: Sensörden gelen veriyi otomatize eden endüstriyel bilgisayar.
Master Station: Verilerin toplandığı, işlendiği ve görselleştirdiği merkez birim.

#### Çalışma Mantığı:
Sensörlerden okunan veriler (temp, pressure, flow rate, vs.) rtu ve plc'lere aktarılır.
RTU ve PLC'ler okudukları verileri Master Station'a gönderir.
Master Station'da gelen veri analiz edilir ve veri tabanında saklanır.
Operatörler Master Station'dan gelen datayı, alarmları ve akışı görüntüleyebilir ve kontrol edebilir.

------------------------------------------------------
### Mes:
Üretim aşamasınndaki problemlerin izlenmesi, çözüm bulunması ve performans takibi için kullanılır.
Kalite sorunlarına, üretim hattındaki beklenmedik duruşlara, kapasite yetersizliğine, ve üretimdeki performans düşüşüne çözümler bulur.
Ne kadar üretildi sorusuna odaklanır.

#### Çalışma Mantığı:
- SCADA sistemleri ve operatör girişleri aracılığıyla veri elde eder.
- Toplanan veriler ile üretim bandının hangi aşamada olduğunu, hangi makinenin çalıştığını, ve üretilen ürünün kalitesini anlık olarak izler.
- Sistem tespit edilen problemleri (kalite problemleri, kapasite yetersizliği, beklenmeyen duruşlar, takip yetersizliği, düşük performans vb.) önceliklendirir.
	- Elde edilen analizler ve veriler ile problemlere karşı çözümler üretilir.

-----------------------------------
### MOM:
İşletmede bulunan makinaların yaşam döngüsüne, bakım süreçlerine ve sağlığına odaklanır.
MES sistemleri üretime odaklanırken MOM sistemleri ürünü üreten makinaların sağlığına odaklanır.

#### Çalışma Mantığı:
SCADA ve cihazlardan gelen anlık verileri sisteme aktarır.
Gelen veri makinenin çalışma aralıkları ile karşılaştırılır.
Eğer veriler normal dışına çıkma eğilimindeyse olası arıza tespit edilir.
Olası arıza için bir kayıt oluşturulur ve bildirilir.


## Örnek Sistem:

Bir fabrikada üretim hattında bulunan montaj makinelerinden alınan veri ile:

SCADA makineden sıcaklık verisini alır.

		PLC aracılığı ile master station'a veriyi iletir ve görselleştirilir.
		Örnek: Sicaklik:110;Durum:1
MES, SCADA'dan gelen bu veri ile ne kadar ürün üretildiğini tespit eder.

		Makinenin her başarılı hareketini 1 üretilmiş parça olarak kabul eder.
		
		Toplam üretim sayısını analiz eder ve hedef sayı ile karşılaştırır.
		Örnek: Uretim:200;Hata:2;Verimlilik:85
MOM, SCADA'dan gelen veriyi analiz eder olası bir arıza tespit ettiyse arıza kaydı açılır. 

		Makinenin sıcaklık aralığı bellidir, eğer aralığın dışında bir veri gelirse sorunun kaynağını analiz eder.
		
		Arıza kaydı oluşturur

-----------------------------------------------
### ERP:
İşletme içerisindeki organizasyonu yönetmek, izlemek ve iş akışını otomatize etmek için kullanılan sistemdir.
3 farklı yapısı bulunur.
##### Onsite ERP:
İşletme içerisindeki organizasyonun yönetimini kendi içerisinde yapmak isterse kullanılır. Bu seçenekte şirket içerisinde kendi IT ekibi olması gerekir, bütün geliştirme ve bakım süreçlerini bu ekip yönetir.

##### Cloud-Based ERP:
Yazılımın 3.parti bir servis sağlayıcı ile çalıştığı yöntemdir. Onsite yönteme göre daha düşük maliyetlidir, otomatik güncellenir ve her yerden erişim sağlanır.

##### Hibrit ERP:
Hem onsite hem cloud sistemleri içeren yöntemdir. Şirket için kritik veriler onsite, operasyonel işlemler cloud'da tutulur.

#### Temel ERP Modülleri:
- **Finans ve Muhasebe:** İşletmenin mali durumunu, nakit akışını ve bütçeleme süreçlerini yönetir.
- **Tedarik Zinciri:** Hammadde tedariği, lojistik, tedarikçi süreçlerini yönetir.
- **İnsan Kaynakları:** Personel yönetimi, işe alım ve eğitim süreçlerini yönetir.
- **Satış ve Pazarlama:** Müşteri ilişkileri, satış siparişleri gibi işlemleri yönetir.
- **Üretim Yönetimi:** İş emirlerini, malzeme planlamasını, üretim gibi işlemleri yönetir.

------------------------------------------------
### IIoT:
Endüstriyel üretim süreçlerinde verilerin toplanarak, analiz edilmesine olanak sağlar.
Daha güvenli çalışmayı, öngörülü bakım ve durdurma işlemleri yaparak üretim zamanını arttırmayı, operasyonel verimliliği sağlar.

#### IIoT ve IoT Farkı:
- IoT evlerde ve ofislerde kullanılan akıllı cihazları (akıllı ev sistemleri, kamera vs.) kapsar.
- IIoT ise endüstriyel alanda (üretim, madeni, lojistik, liman vs.), üretimde kullanılan makinelere ve cihazları kapsar.

------------------------------------
## Haberleşme Protokolleri:

### OPC UA:
Üretimde yer alan makinelerin iletişimini sağlayan haberleşme protokolüdür. Windows, linux gibi birden fazla platformu destekler OPC DA'ya göre daha gelişmiş bir protokoldür.
- Servis odaklı mimari ile geliştirilmiştir.,
- Platform odaklı bir yapıda değildir, her platformda çalışır.
- Authentication, authorization ve encryption ile güvenli ve ölçeklenebilir yapıdadır.

##### Avantajları:
- Bir platforma bağlı çalışmaz birden fazla platformu destekler.
- Yüksek güvenlikli veri iletimini sağlar.
##### Dezavantajları:
- Yüksek işlem gücü gerekir, implementasyon ve geliştirme maliyeti yüksektir.


### ModBus TCP:
Üretimde yer alan makinelerin iletişimini sağlayan haberleşme protokolüdür. TCP/IP katmanı üzerinde çalışan en yaygın ve kullanımı basit olan protokoldür. Master-Slave yapısıyla çalışır 

#### Veri Yapısı:
- PDU(Protocol Data Unit): Fonksiyonları ve veriyi tutar.
- ADU(Application Data Unit): PDU'ya ek olarak cihaz adreslerini, request ve response bilgilerini tutar.
##### Avantajları:
- Kurulumu kolaydır.
- Tüm PLC'ler tarafından desteklenir.
- Ölçeklenebilir.
##### Dezavantajları:
- Güvenlik zayıftır, veri manipulasyonuna açıktır. 
- Büyük veri paketlerinde iletim hızı düşer.

### Fanuc FOCAS:
Fanuc marka cnc makinelerinden veri (parça sayısı, alarm, devir, vs.) iletmek için kullanılan protokoldür.
Haberleşme genellikle ethernet kartı ya da fiber optik kart üzerinde yapılır.

### Mitsubishi MC:
Mitsubishi marka PLC ve CNC makinelerden veri iletmek için kullanılan protokoldür. Request-Response yapısıyla çalışır. 
Basit komutlar ile makine hafızasındaki register'lara erişim sağlanır.

### Siemens S7:
Siemens marka PLC'lerden veri iletmek için kullanılan protokoldür. Ethernet üzerinden iletim sağlanır. PLC üzerindeki Data Block'lara ve Merker alanlarına doğrudan erişim sağlanabilir.

-------------
## Metrikler:

### OEE (Overall equipment effectiveness):
Üretim işleminin performansını ve verimliliğini ölçen birim.

- **Availability:** Planlanan üretim zamanında ne kadar üretim yaptığını belirten faktör.
- **Performance:** Ekipmanın maksimum potansiyeline oranla ne kadar üretim yaptığını belirtir
- **Quality:** Üzerinde yeniden işlem yapmayı gerektirmeyen iyi kalitede üretilen ürünleri belirtir
  
OEE = Availability x Performance x Quality

OEE iyileştirmenin faydaları:
- Verimliliği arttırır.
- Ürün kalitesini arttırır.
- Daha iyi karar vermeyi sağlar.
- Üretim ekipmanlarının sürdürülebilirliğini arttırır.
- Maliyet düşürür.



