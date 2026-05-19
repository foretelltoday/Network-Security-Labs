# 🔥 Palo Alto Firewall Lab

## Quraşdırma

### Tələblər
- VMware Workstation / Player
- Palo Alto VM image (OVA/OVF)

### Şəbəkə interfeysləri

**Management interface konfiqurasiyası:**
configure;
set deviceconfig system type static
set deviceconfig system ip-address <IP_ADDRESS> netmask <NETMASK> default-gateway <GATEWAY_IP>
commit;
exit;

text

### Zonalar
- inside
- outside
- DMZ

## Traffic Management

### NAT
Policies → NAT bölməsində NAT qaydaları yaradın

### URL Filtering
1. Objects → URL Category → Custom URL kateqoriyası yaradın
2. Objects → URL Filtering → Profile yaradın

### External Dynamic Lists (EDL)
1. Objects → External Dynamic Lists
2. Ubuntu-da EDL faylı olan veb səhifə yaradın
3. EDL-i policylərdə istifadə edin

## Tapşırıqlar
- Client maşınından chat, storage, shopping, VPN tətbiqlərini blok edin
- Custom EDL ilə malicious IP-ləri avtomatik blok edin
