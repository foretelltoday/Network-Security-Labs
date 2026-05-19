# 🔥 Palo Alto Firewall Lab

## 📦 Quraşdırma tələbləri
- VMware Workstation / Player
- Palo Alto VM image (OVA/OVF)

---

## 🚀 Palo VM quraşdırılması

### 1. VM faylını import edin

### 2. Şəbəkə interfeyslərini konfiqurasiya edin

**Virtual Network Editor ayarları:**

![Virtual Network Editor](images/image.png)

### 3. Köhnə interfeysləri silin, yenilərini əlavə edin

![Network Adapters](images/image1.png)

### 4. VM-i başladın və management interfeysini konfiqurasiya edin

**İlkin giriş:**
- İstifadəçi: `admin`
- Şifrə: `admin` (5-6 dəqiqə gözləyin)

### 5. Management interfeysinə IP təyin etmək üçün komandalar:

```bash
configure;
set deviceconfig system type static
set deviceconfig system ip-address <IP_ADDRESS> netmask <NETMASK> default-gateway <GATEWAY_IP>
commit;
exit;
show interface management;
6. Brauzerdə daxil olun
7. Digər şəbəkə adapterlərini əlavə edin
https://images/image2.png

8. Web UI-da Device → Interfaces bölməsini yoxlayın
9. Device → Management → General Settings - zaman zonasını dəyişin
10. Zonalar yaradın
inside

outside

DMZ

⚙️ İlkin konfiqurasiyalar
Administrativ istifadəçilər
Yeni istifadəçi yaradın (admin istifadə etməyin)

Custom rol yaradın

Xidmətlər
https://images/image3.png

🚦 Trafik idarəsi
NAT konfiqurasiyası
https://images/image4.png

Static Route
https://images/image5.png
https://images/image6.png

🔗 URL Filtering
URL Filtering profile
https://images/image7.png

Custom URL kateqoriyası
https://images/image8.png

Test saytı:
https://urlfiltering.paloaltonetworks.com/

📋 External Dynamic Lists (EDL)
https://images/image9.png

📝 Tapşırıqlar
Client maşınından chat, storage, shopping, VPN tətbiqlərini blok edin

Custom EDL ilə malicious IP-ləri avtomatik blok edin

📌 Qeydlər
VM quraşdırması zamanı 5-6 dəqiqə gözləmək lazımdır

İlkin şifrə: admin / admin

Management interfeysi üçün statik IP verin

WAN interfeysi üçün DHCP client seçin

🔗 Faydalı linklər
Palo Alto Documentation

URL Filtering Test
