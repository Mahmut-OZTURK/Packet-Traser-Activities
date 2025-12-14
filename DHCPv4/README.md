# Merkez-Şube DHCP Relay (IP Helper) Projesi

Bu proje, farklı coğrafi konumlardaki şubelerin (Ankara) IP adreslerini tek bir merkezden (İstanbul) almasını sağlayan **DHCP Relay Agent** yapısını simüle eder.

##  Projenin Amacı
Şubelerde ekstra sunucu maliyetinden kaçınmak ve IP yönetimini merkezileştirmek için Router'ların "Relay Agent" (Aracı) özelliğini kullanmak.

##  Kullanılan Teknolojiler
* **Cisco IOS DHCP Server:** Router üzerinde çoklu havuz (Pool) yapılandırması.
* **IP Helper-Address:** Broadcast DHCP isteklerini Unicast'e çevirerek WAN üzerinden taşıma.
* **Static Routing:** Merkez ve Şube arasındaki iletişimi sağlayan yönlendirme kuralları.

##  Karşılaşılan Zorluklar ve Çözümler
* **Sorun:** Merkez Router, gelen isteği alıp cevabı nereye döneceğini (Routing) bilmiyordu.
* **Çözüm:** Merkez Router'a şube ağı için statik rota (ip route) eklenerek dönüş yolu açıldı.
* **Sorun:** DHCP havuzu tanımlanırken yanlış ağ adresi girilmesi.
* **Çözüm:** Havuz komple silinip (no ip dhcp pool) temiz bir şekilde tekrar oluşturuldu.

##  Kurulum
1.  Dosyayı indirin ve Packet Tracer ile açın.
2.  Ankara tarafındaki PC'den DHCP isteği başlatın.
3.  İstanbul'dan IP aldığını doğrulayın.
