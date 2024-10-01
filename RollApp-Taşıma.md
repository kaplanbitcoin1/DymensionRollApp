# Riskli İşlem 🧨 🧨 🧨 🧨


### Bu anlatım sadece HetznerCloud için geçerlidir. Üst sunucuya geçmek isteyenler olabilir. (Denendi) ✅


### RollApp service'lerinin hepsini durdurun.

```
roller rollapp services stop
roller relayer services stop
roller eibc services stop
```


### Mevcut sunucuya Cloud üzerinden Snapshot atın.


### Yeni bir sunucu siparişi verirken Image kısmında Snapshot dosyanızı seçin ve kurulumun bitmesini bekleyin.


### Yeni sunucuda eski Telebit dosyalarını silelim.


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


### Telebiti tekrar kuralım ve Mail ile doğrulayalım.

### Bu işlemler sonrası RPC-Değiştirme bölümündeki işlemleri yapmamız yeterli.

### Yeşil yakması 2-3 saati buluyor, sabredelim. 🐅 

