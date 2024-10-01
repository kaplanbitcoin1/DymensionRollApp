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


### Öncelikle [Platform'u](https://playground.dymension.xyz/) kullanabilmek için siteye gidip Mainnet ağında en az 5 DYM stake edelim.
### (DYM ağında EVM adresinize deposit edeceksiniz) - Keplr cüzdan kullanabilirsiniz.


### Siteye giriş yaptıktan sonra Dymension [Discord](https://discord.com/invite/dymension) kanalına katılalım. 

# (Bekleme bölümünü kendinizi tanıtarak geçmeniz gerekir.) 

### PlayGround Faucet kısmından cüzdanınıza DYM uzantılı adresinizi yazarak test tokenları alabilirsiniz.

### İşlemlerde yaklaşık 35 adet token kullanacağız. Haftalık 60 token talep etme hakkınız var.


# Token bulduysak eğer hadi öyleyse başlayalım. 

### Deploy a RollApp kısmına tıklayıp ilgili bölümleri dolduralım. X, Website vb. gibi.

* Domain'i uzun tutalım yoksa 20 DYM isteyecektir. RollApp id kısmına dokunmayın, Domain yazınca otomatik oluşacaktır.
* Diğer bilgierinizi de doldurduktan sonra Register edelim. 

<img width="1536" alt="1" src="https://github.com/user-attachments/assets/a746c225-6940-40f2-821f-5622b4716e84">

# Bir sonraki aşamada Token Symbol kısmını 3 harf olacak şekilde doldurun.

### Diğer parametreleri değiştirmiyoruz.

<img width="1536" alt="2" src="https://github.com/user-attachments/assets/47fbd610-ab67-4249-aa78-a00bcb5da976">


# Add/Edit Accounts kısmına tıklayalım

<img width="1536" alt="3" src="https://github.com/user-attachments/assets/7884d740-a8cc-469b-a1f1-8f53bb7c8f53">


# Add Account diyerek stake ettiğiniz 0x uzantılı Dym adresini yazalım ve Remaining Supply kısmına tıklayıp kaydedelim. 

<img width="1273" alt="4" src="https://github.com/user-attachments/assets/b8720080-6337-4186-850e-24b97e977cee">


# Gerenate ettikten sonra son olarak Permissionless bölümü aktif olacak şekilde Set edelim.

<img width="1504" alt="5" src="https://github.com/user-attachments/assets/8bffce1a-cbe7-4ed2-aee7-085dde4f298f">

# Sonunda RollApp profilimiz oluştu 😁

<img width="1536" alt="6" src="https://github.com/user-attachments/assets/ed0ab1f1-90e4-4773-a82a-d14ee796550e">



# Dymension RoolApp'in kullandığı portlar bu şekilde.
# Önerim yeni bir sunucuya kurulum yapmanız yönünde.

<img width="734" alt="Ekran Resmi 2024-09-30 18 17 55" src="https://github.com/user-attachments/assets/193446f9-1e0c-4de5-a798-204d2aadad71">


### Çayınızı, kahvenizi aldıysanız artık kuruluma başlayabiliriz 🧨


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


