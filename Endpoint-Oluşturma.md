### Öncelikle Telebit'in fişini çekelim 🧨 😁


```
sudo systemctl stop telebit
```

```
sudo rm -rf /opt/telebit/
```

```
rm -rf ~/telebit/
```

```
sudo rm /etc/systemd/system/telebit.service
```

```
sudo systemctl daemon-reload
```


### Güncellemeleri yapalım

```
sudo apt -q update
sudo apt -qy install curl git jq lz4 build-essential
sudo apt -qy install curl git jq lz4 build-essential snapd unzip
sudo apt -qy upgrade
```

### Nginx kurulum

```
sudo apt -qy install nginx
```


### Çalışıyor mu diye kontrol etmek için

```
sudo systemctl status nginx
```

### Başlatmak için

```
sudo systemctl start nginx
```


### FreeDns sitesine gidip üye olalım ve mail doğrulaması yapalım

https://freedns.afraid.org/subdomain/

* Api, Rpc ve Evm adreslerini oluşturuyoruz
* Destination bölümüne sunucu IP adresini yazıyoruz

* Bu şekilde 3 adet endpoint adresiniz olmalı <img width="781" alt="Ekran Resmi 2024-10-08 11 19 48" src="https://github.com/user-attachments/assets/e3323e9e-7e18-4a54-a900-bbb9c70616e2">

### Konfigürasyon dosyasını oluşturalım

```
sudo nano /etc/nginx/sites-enabled/dym
```


### Aşağıdaki komutu içerisine yapıştırıp: Api, Rpc ve Evm adreslerini yazalım. (Kendi bilgilerinle değiştir)

`dym-rest.domainAdresiniz.com` `dym-rpc.domainAdresiniz.com` `dym-evm.domainAdresiniz.com` 🧨

```
server {
    listen 80;
    server_name dym-rest.domainAdresiniz.com;

    location / {
        add_header Access-Control-Allow-Origin *;
        add_header Access-Control-Max-Age 3600;
        add_header Access-Control-Expose-Headers Content-Length;
        proxy_pass http://0.0.0.0:1317;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }
}

server {
    listen 80;
    server_name dym-rpc.domainAdresiniz.com;

    location / {
        proxy_pass http://0.0.0.0:26657;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }
}

server {
    listen 80;
    server_name dym-evm.domainAdresiniz.com;

    location / {
        proxy_pass http://0.0.0.0:8545;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }
}
```


### Nginx yapılandırmasını test etmek için

```
sudo nginx -t
```

### Her şey doğruysa yeniden başlatmak için
```
sudo systemctl reload nginx
```

### Certbot kuralım
```
sudo snap install --classic certbot
```

### Bağlantı oluşturalım

```
sudo ln -s /snap/bin/certbot /usr/bin/certbot
```

### Güvenlik ayarı için

```
sudo snap set certbot trust-plugin-with-root=ok
```

### SSL Sertifikası alalım. Yes diyelim ve Enter. (Biraz bekletiyor, çıkış yapmayın)

```
sudo certbot --nginx --register-unsafely-without-email
```


### RPC'yi kontrol etmek istiyorsak

```
curl https://dym-rpc.domainAdresiniz.com/health
```

* Son olarak `Metadata` dosyasının içerisindeki bilgilerimizi değiştirip kaydedelim

* Adresleri bu şekilde doldurmanız gerekir `https://SENİNRPCADRESİN.COM`


```
nano /root/.roller/rollapp/init/sequencer-metadata.json
```

### Güncelleme isteği gönderelim

```
roller rollapp sequencer metadata update
```



### Bütün service'lere restart atıp bekleyelim. Bir süre sonra kendi Endpointlerimiz aktif olacaktır.

```
roller rollapp services restart
roller relayer services restart
roller eibc services restart
```

* Mission Completed 🐅
