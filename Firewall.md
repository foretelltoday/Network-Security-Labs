# Firewall

## Installtion requirements for all softwares/systems

## Palo VM installation

- Import VM file

### Configure network interfaces

- Configure network adapters like that ( uncheck DHCP )
    
    ![image.png](Firewall/image.png)
    
- Remove previous network interfaces form VM and add following:
    
    ![image.png](Firewall/image%201.png)
    
- Start VM and configure management interface
- Initial password admin:admin ( wait 5-6 min after login prompt appear)
- Run these commands to assign IP to management interface
    
    ```bash
    configure;
    set deviceconfig system type static
    set deviceconfig system ip-address <IP_ADDRESS> netmask <NETMASK> default-gateway <GATEWAY_IP> dns-setting servers primary <DNS_IP>
    commit;
    exit;
    show interface management;
    ```
    
- Open browser and login
- Add other network adapters like that
    
    ![image.png](Firewall/image%202.png)
    
- Start VM login web UI and go to Device —> Interfaces tab to see management interface configs
- Go to Device —> Management —> General Settings tab and change time zone and
- verify MAC address with VMware “Virtual Machine Settings” and with “debug show vm-series interface all”  command
- Edit interface ( For vmnet 8 select DHCP client , its WAN interface )

![image.png](Firewall/image%203.png)

![image.png](Firewall/image%204.png)

- Create Zones with name inside, outside and DMZ

## Initial configs

- Administrative users
    - create new administrative user with implicit username (not admin, administrator and etc)
    - create custom role
- Setup services
    
    ![image.png](Firewall/image%205.png)
    

## Traffic management

### Nat configs

- Configure NAT like this form Policies —> NAT
    
    ![image.png](Firewall/image%206.png)
    

### Static route

- Configure static route like that
    
    ![image.png](Firewall/image%207.png)
    
    ![image.png](Firewall/image%208.png)
    

### Default security rule

- create security rule via any-any access

## Tests via Ubuntu VM

- Create two Ubuntu VM one for clients network and one for servers network
- Then ping [google.com](http://google.com) and 8.8.8.8 to see logs in Palo Alto

## External Dynamic Lists

- Go to Objects —> External Dynamic Lists section and create EDL
- Create web page in  order host text EDL file in ubuntu
- Use this EDL in policies
- Change service route configuration via Device —> Setup —> Serices

## URL Filtering

- Go to Objects —> URL filtering
- Usage:
    
    ![image.png](Firewall/image%209.png)
    
- Test a site: https://urlfiltering.paloaltonetworks.com/
- Add Custom URL category in order block custom sites
    - Go to Objects —> URL Category and create custom URL category (NOTE: create it with wildcard)
- Create profile
    - Go to Objects —> URL Filtering and add new profile with newly created category

## Tasks

- Block, chat, storage, shopping, vpn applications from your client machine while allowing the internet
- Create or integrate custom EDL to block malicious IPs automatically (Public intelligence sources like AbuseIPDB can be used)

**Notes**:
User ID in Palo Alto