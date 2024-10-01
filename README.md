<img width="1517" alt="Dymension" src="https://github.com/user-attachments/assets/b057fe61-7f3a-471e-ac24-796ff52cc480">



[Website](https://dymension.xyz/)<br>
[Discord](https://discord.com/invite/dymension)<br>
[Docs](https://docs.dymension.xyz/)<br>
[Explorer](https://pg.dym.fyi/)<br>

[YeniTopluluk-Kanalım](https://t.me/tigernode)<br>
[Hetzner 20€ cloud kredisi almak için](https://hetzner.cloud/?ref=jKRRgwoTGnE8)<br>


# Sistem Gereksinimleri
| Bileşenler	 | Tavsiye Gereksinimler | 
| ------------ | ------------ |
| CPU | 8 Core |
| RAM | 16 GB RAM |
| Storage | 160 GB Nvme |

* NOT: Sistem özellikleriniz ne kadar yüksek olursa o kadar iyidir diye düşünüyorum. Sunucunuz Dedicated olursa tadından yenmez.
* Etkinlik sonunda performansa bakılabilir, -öne geçmek için- RollApp'i iyi bir sunucuda çalıştırmanızı öneririm.


### Öncelikle [Platform'u](https://playground.dymension.xyz/) kullanabilmek için siteye gidip Mainnet ağında en az 5 DYM stake ediyoruz.
### (DYM ağında EVM adresinize deposit edeceksiniz) - Keplr cüzdan kullanabilirsiniz.


### Siteye giriş sağladıktan sonra Dymension [Discord](https://discord.com/invite/dymension)<br> kanalına giriş yapıpi PlayGround Faucet kısmından cüzdanınıza test tokenları almalısınız.

### İşlemlerde yaklaşık 40 adet token kullanacağız. Haftalık 60 token talep etme hakkınız var.



# Sunucu güncelleyelim

```
sudo apt update && sudo apt upgrade -y
```

# Gerekli paketleri yükleyelim

```
sudo apt install -y build-essential clang curl aria2 wget tar jq libssl-dev pkg-config make
```

# Docker sürüm

```
export DOCKER_API_VERSION=1.41
```


# Docker kuralım

```
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
```

# Repoyu Apt kaynaklarını ekleyip güncelleme yapalım

```
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

# Docker paketleri

```
sudo apt-get -y install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

# Kullanım izni

```
sudo usermod -aG docker ${USER}
```

# Sürekli sudo kullanmamak için

```
newgrp docker
```

# Şimdi GO kuruyoruz


```
cd $HOME
wget "https://golang.org/dl/go$ver.linux-amd64.tar.gz"
sudo rm -rf /usr/local/go
sudo tar -C /usr/local -xzf "go$ver.linux-amd64.tar.gz"
rm "go$ver.linux-amd64.tar.gz"
```

```
echo 'export GOPATH=$HOME/go' >> ~/.bashrc
echo 'export PATH=$PATH:/usr/local/go/bin:$GOPATH/bin' >> ~/.bashrc
source ~/.bashrc
```

# Version 1.23.0 olmalı

```
go version
```



# Roller kuralım


