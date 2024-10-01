# Bu anlatım sadece Hetzner Cloud için geçerlidir. Üst sunucuya geçmek isteyenler olabilir. 


### RollApp service'lerinin hepsini durdurun.


```
roller rollapp services stop
roller relayer services stop
roller eibc services stop
```

### Mevcut sunucuya Cloud üzerinden Snapshot alın.

### Yeni bir sunucu siparişi verirken Image kısmında Snapshot dosyanızı seçin ve kurulumun bitmesini bekleyin.
