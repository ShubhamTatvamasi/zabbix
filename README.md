# zabbix

https://www.zabbix.com/download

Default Credentials: \
Username: `Admin` \
Password: `zabbix`

CPU: 2 vCPUs \
Memory: 4 GB RAM \
Disk: 20 GB SSD

Update `zabbix_agentd.conf` for Active connection:
```
Server=zabbix.shubhamtatvamasi.com
ServerActive=zabbix.shubhamtatvamasi.com
Hostname=Server 1
```

### Encrypt Connection

Generate a PSK key for the Zabbix agent:
```bash
openssl rand -hex 64 > /etc/zabbix/secret.psk
```

Update `zabbix_agentd.conf` with the PSK key:
```
TLSConnect=psk
TLSAccept=psk
TLSPSKIdentity=Server 1
TLSPSKFile=/etc/zabbix/secret.psk
```
