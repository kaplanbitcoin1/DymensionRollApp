<img width="1517" alt="Dymension" src="https://github.com/user-attachments/assets/b057fe61-7f3a-471e-ac24-796ff52cc480">



[Website](https://dymension.xyz/)<br>
[Discord](https://discord.com/invite/dymension)<br>
[Docs](https://docs.dymension.xyz/)<br>
[Explorer](https://pg.dym.fyi/)<br>
[Celestia](https://discord.com/invite/YsnTPcSfWQ)<br>

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



### Dymension RoolApp'in kullandığı portlar bu şekilde. Önerim yeni bir sunucuya kurulum yapmanız yönünde.

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

```
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
ver="1.23.0"
```


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

```
wget https://raw.githubusercontent.com/dymensionxyz/roller/main/install.sh 
```

# install.sh içerisine girelim ve içerisindeki her şeyi silelim.

```
nano install.sh
```

### Aşağıdaki komutu install.sh içerisine yapıştırıp CommandXCommandYEnter diyelim.

```shell
#!/bin/bash

set -e
OS=$(uname -s)
ARCH=$(uname -m)

if [[ "$ARCH" == "x86_64" ]]; then
    ARCH="amd64"
elif [[ "$ARCH" == "arm64" ]] || [[ "$ARCH" == "aarch64" ]]; then
    ARCH="arm64"
fi

# Doğrudan URL'yi ayarlayın
TGZ_URL="https://github.com/dymensionxyz/roller/releases/download/v1.6.4-alpha-rc08/roller_${OS}_${ARCH}.tar.gz"
ROLLER_BIN_PATH="/usr/local/bin/roller"
if [ -f "$ROLLER_BIN_PATH" ]; then
    sudo rm -f "$ROLLER_BIN_PATH"
fi
sudo mkdir -p "/tmp/roller_tmp"
echo "💈 Downloading roller..."
sudo curl -L "$TGZ_URL" --progress-bar | sudo tar -xz -C "/tmp/roller_tmp"
echo "💈 Installing roller..."
sudo mv "/tmp/roller_tmp/roller" "$ROLLER_BIN_PATH"
sudo chmod +x "$ROLLER_BIN_PATH"
sudo rm -rf "/tmp/roller_tmp"
echo "💈 Installation complete! You can now use roller from your terminal."
```

# Script'i çalıştıralım
```
bash install.sh
```


# RollApp'i başlatalım ve Playground'u seçelim.

```
roller rollapp init
```

### Çıkan soruya görseldekine benzer kendi RollApp id'nizi yazıyorsunuz.

<img width="594" alt="7" src="https://github.com/user-attachments/assets/34e67398-d20f-410f-976c-09a7090ae089">

### Uzun bir kurulum sürecinin ardından başardın ✅ Keyleri kaydedelim. 

<img width="1166" alt="8" src="https://github.com/user-attachments/assets/8fcf8813-5d3b-4533-b129-b4e834fbad55">



# Şimdi Rpc, Api ve Evm iletişimi için Telebit kuracağız.
### Mail adresi yazdıktan sonra size bir şifre verilecek.
### Maili kontrol edelim ve VPN ile linke giriş yapalım. Ardından bize verilen şifreyi yazalım ve onaylayalım. 
### Sunucuya geri dönüp Enter diyelim. 

```
curl https://get.telebit.io/ | bash
```

<img width="762" alt="9" src="https://github.com/user-attachments/assets/70403eaf-16b9-4451-b0bf-614633e09988">

# Endpoint'leri oluşturmak için: 

```
~/telebit http 1317 rest
~/telebit http 8545 evm
~/telebit http 26657 rpc
```

# Sisteminize kaydetmek için:

```
~/telebit save
```

# Verilen bilgiler sizin adreslerinizdir. Görseldeki gibi düzenlemenizi öneririm. Bu adresleri bir süre sonra kullanacağız. 

<img width="466" alt="10" src="https://github.com/user-attachments/assets/ff714ce7-98e1-46a5-950d-59de04f4a29a">


# Şimdi Sequencer kurulumuna geçiyoruz. Bu işlemler çok önemli. Hata yaparsanız bir daha RollApp hiç çalışmayabilir.

### Öncelikle her zaman y/n soruları sorulacak. 
### Bu sorularda sadece verilen tuşları kullanın. Enter'a tıklarsanız. 🧨🧨 (Denendi) 😏

### Önemli: Cüzdan adreslerinize asla sizden istenmeden token göndermeyin. Yine 🧨🧨 😁


# Kurulumu başlatıp `Sequencer` seçiyoruz ve token adedi gösterecek. 
# 1 defa Enter'a basıyoruz ve size Sequencer adresinizi verecek. 
# Buraya 11 adet Dym gönderin ve Explorer üzerinden gelip gelmediğini kontrol edin. 
# Token geldiyse sunucuya dönüp sadece `Y` tuşuna basın.

```
roller rollapp setup
```


<img width="1161" alt="11" src="https://github.com/user-attachments/assets/bfa5079c-c003-4ecc-a742-6b8049599078">



# Bu kısımda Telebit bilgilerimizi gireceğiz.
# Boşluk olmamalı yoksa hata verir. (Denendi) 😁
# Bilgileri girip onay aldıktan sonra görseldeki gibi `N` tuşuna basıyoruz


<img width="852" alt="12" src="https://github.com/user-attachments/assets/9f740106-e3da-470b-9cfd-efe71d0f5359">


# 10 Adet Dym Bond edilecek diyor, `Y` tuşuna tıklıyoruz.

<img width="1065" alt="13" src="https://github.com/user-attachments/assets/bbc43f86-40d4-46a5-83e6-a584678e2f65">


### Son olarak verilen Tia adresinize token gönderin ve Mocha [Explorer](https://mocha.celenium.io/) üzerinden gelip gelmediğini kontrol edin.
### Kontrol sağladıktan sonra eğer token gelmişse Y tuşuna tıklayın. Bu kısmı da hallettik 😏


<img width="1446" alt="14" src="https://github.com/user-attachments/assets/41eb3137-ad6d-4470-acfd-598a97c4a42b">


# Şimdi RollApp'i çalıştırmaya başlayabiliriz. Sırasıyla:


```
roller rollapp services load
```

```
roller rollapp services start
```

# Status kontrol için

```
roller rollapp status
```

* Çıktınız bu şekilde olmalı

<img width="1086" alt="15" src="https://github.com/user-attachments/assets/be7ba2dc-f86c-4c30-ad65-41dcb819ba08">


# Relayer kurulum


```
roller relayer setup
```


# Bize Relayer adreslerimiz verildi. Bunları kaydetmeyi unutmayın.
### Relayer Hub Key adresinize 21 adet DYM gönderin ve Explorer üzerinden gelip gelmediğini kontrol edin.
### Eğer token geldiyse `Y` tuşuna basın. 

<img width="1221" alt="16" src="https://github.com/user-attachments/assets/d82781ab-907e-443f-82b3-4ff9ddbc368a">


### Kanal bulunamadı uyarısı verecektir. IBC kanalı oluşturmak için `Y` tuşuna tıklayın. Bu bölüm de tamamdır 🐅

<img width="970" alt="17" src="https://github.com/user-attachments/assets/1842650f-dc3e-45a3-8d0f-84929870dc3a">


# Relayer service başlatalım

```
roller relayer services load
```

```
roller relayer services start
```


# Kurulum aşamasında sona geldik. Şimdi eIBC kuralım.

```
roller eibc init
```


# Cüzdan kelimelerini kaydedin ve adresinize 2 adet DYM gönderin. Explorer ile check edin


<img width="1168" alt="18" src="https://github.com/user-attachments/assets/2a6ff9b3-11d7-47f3-b32b-ff1774afd3ed">


# Şimdi sırasıyla

### ROLLAPPID kısmını kendi bilginizle değiştirin 

```
roller eibc fulfill rollapps set SENİNROLLAPPID 0.01
```

# TOKENSEMBOL bölümünü kendi bilginizle değiştirin.
# Hatırlarsanız ben kurulum aşamasında `BER` olarak belirlemiştim.


```
roller eibc fulfill denoms set TOKENSEMBOL 0.01
```

# eIBC'yi service ile çalıştıralım

```
roller eibc services load
```

```
roller eibc services start
```

# eIBC bakiye kontrolü için

```
roller eibc funds
```
# Sanırım artık yeşil yakıyor olmalısın 🐅 😁

<img width="1536" alt="19" src="https://github.com/user-attachments/assets/22e07c6c-8900-4ed0-a73b-0d317d6e80b0">



# Henüz bitmedi 😁

### Transfer bölümüne tıklayıp kendi ağınızdan DYM ağına bastığınız token'ları göndermeniz gerekiyor. 
### Ben 1000000 token köprüledim, karar sizin.
### Bu işlem 1-1.5 saat kadar sürmektedir, haberiniz olsun.

<img width="1518" alt="20" src="https://github.com/user-attachments/assets/8439333f-794b-493e-8a62-b768c0579ebb">


