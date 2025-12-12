# Yedekli Kampüs Ağ Tasarımı (Redundant Triangle Topology)

Bu proje, kurumsal ağlarda kesintisiz iletişim sağlamak amacıyla tasarlanmış, yedekli bir ağ mimarisini simüle eder.
Projede **Layer 3 Switch** kullanılarak VLAN'lar arası yönlendirme yapılmış ve **EtherChannel** teknolojisi ile bant genişliği artırılmıştır.

## Projede Kullanılan Teknolojiler
* **Inter-VLAN Routing:** Router-on-a-stick yerine daha performanslı olan Layer 3 Switch (SVI) yöntemi kullanıldı.
* **EtherChannel (LACP):** Switchler arası çift kablo kullanılarak hat yedekliliği sağlandı ve hız artırıldı.
* **(STP):** Ağdaki döngüleri (Loop) engellemek için Spanning Tree protokolü yapılandırıldı.
* **Ağ Güvenliği:** Varsayılan (Native) VLAN değiştirilerek (VLAN 666) VLAN Hopping saldırılarına karşı önlem alındı.

##  Topoloji Detayları
* **CORE Switch:** Ağın beyni olarak çalışır, tüm yönlendirme  görevini üstlenir.
* **ACCESS Switchler:** Son kullanıcıların bağlandığı kenar cihazlardır.
* **VLAN Yapısı:**
    * VLAN 10: Personel
    * VLAN 20: Customer
    * VLAN 99: Management
    * VLAN 666: Native (Güvenlik)

##  Nasıl Çalıştırılır?
1.  `.pkt` uzantılı dosyayı indirin.
2.  Cisco Packet Tracer ile açın.
3.  VLAN'lar arası ping testi yaparak yedekliliği test edebilirsiniz.
