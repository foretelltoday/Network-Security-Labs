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
configure;
set deviceconfig system type static
set deviceconfig system ip-address <IP_ADDRESS> netmask <NETMASK> default-gateway <GATEWAY_IP>
commit;
exit;
show interface management;

text

### 6. Brauzerdə daxil olun

### 7. Digər şəbəkə adapterlərini əlavə edin

![Additional Adapters](images/image2.png)

### 8. Web UI-da **Device → Interfaces** bölməsini yoxlayın

### 9. **Device → Management → General Settings** - zaman zonasını dəyişin

### 10. Zonalar yaradın
- inside
- outside
- DMZ

---

## ⚙️ İlkin konfiqurasiyalar

### Administrativ istifadəçilər
- Yeni istifadəçi yaradın (admin istifadə etməyin)
- Custom rol yaradın

### Xidmətlər

![Services](images/image3.png)

---

## 🚦 Trafik idarəsi

### NAT konfiqurasiyası

![NAT Configuration](images/image4.png)

### Static Route

![Static Route 1](images/image5.png)
![Static Route 2](images/image6.png)

---

## 🔗 URL Filtering

### URL Filtering profile

![URL Filtering](images/image7.png)

### Custom URL kateqoriyası

![Custom URL Category](images/image8.png)

### Test saytı:
[https://urlfiltering.paloaltonetworks.com/](https://urlfiltering.paloaltonetworks.com/)

---

## 📋 External Dynamic Lists (EDL)

![EDL Configuration](images/image9.png)

---

## 📝 Tapşırıqlar

1. Client maşınından chat, storage, shopping, VPN tətbiqlərini blok edin
2. Custom EDL ilə malicious IP-ləri avtomatik blok edin

---

## 📌 Qeydlər

- VM quraşdırması zamanı 5-6 dəqiqə gözləmək lazımdır
- İlkin şifrə: admin / admin
- Management interfeysi üçün statik IP verin
- WAN interfeysi üçün DHCP client seçin

---

## 🔗 Faydalı linklər

- [Palo Alto Documentation](https://docs.paloaltonetworks.com)
- [URL Filtering Test](https://urlfiltering.paloaltonetworks.com)

---

*Bu qeydlər real laboratoriya təcrübələri əsasında hazırlanmışdır.*
