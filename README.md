
Git clone do Repositorio

```bash
cd /opt
git clone https://github.com/networkautomationbr/netbox-nginx.git
```

O NetBox estará disponível em:
👉 http://localhost:8000

## 🌐 Nginx (HTTPS Proxy) [EXTRA]

Crie a pasta para os certificados:
```bash
mkdir -p /opt/netbox-nginx/certs
```

```bash
openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
  -keyout /opt/netbox-nginx/certs/privkey.pem \
  -out /opt/netbox-nginx/certs/fullchain.pem \
  -subj "/CN=localhost"
```

Alterar IP Address em /opt/netbox-nginx/conf.d/default.conf

```bash
nano /opt/netbox-nginx/conf.d/default.conf
```

Subindo o container do NGINX
```bash
cd  /opt/netbox-nginx/
docker compose up ou docker compose up -d
```
