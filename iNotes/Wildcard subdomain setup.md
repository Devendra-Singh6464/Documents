- Simpal apache2 configuration but alias map this`ServerAlias saas.com *.saas.com`

1. Install dnsmasq.
```bash
sudo apt-get install dnsmasq
```
2. `/etc/dnsmasq.d` create a domain file like if your domain is `saas.com` so create.
```bash
cd /etc/dnsmasq.d/
```
then.
```bash
vi saas.com
```
add this in `saas.com`  file and save file.
```bash
address=/saas.com/127.0.0.1
```
3. `vi /etc/dnsmasq.conf` and add this in file last and save file.
```bash
address=/saas.com/127.0.0.1
```
and change localdns port and save file.
```bash
port=5353
```
4. Go this directory `/etc/NetworkManager/dnsmasq.d` and create same `saas.com-wildcard.conf` file and this line.
```bash
vi saas.com-wildcard.conf
```
add line and save file.
```bash
saas.com-wildcard.conf
```
5. host entry.
```bash
vi /etc/hosts
```
and add this line.
```bash
127.0.0.1 saas.com #domain
127.0.0.1 *.saas.com   #wildcard subdomain
```
 6. Restart apache, dnsmasq and network-manager service.
```bash
sudo systemctl reload NetworkManager
sudo systemctl restart dnsmasq
sudo systemctl restart apache2
```
