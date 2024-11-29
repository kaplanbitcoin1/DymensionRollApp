
* Service'i durduralım

```
roller rollapp services stop  
roller relayer services stop  
roller eibc services stop 
```

* Github'tan son sürümü çekelim

```
curl https://raw.githubusercontent.com/dymensionxyz/roller/main/install.sh | bash 
```
  
* Service tekrar başlatma

```
roller rollapp services start  
roller relayer services start 
roller eibc services start  
```

* Version kontrol (1.9.0-alpha-rc14-hotfix1)

```
roller version
```

* Celestia Update

```
roller da-light-client update
```
