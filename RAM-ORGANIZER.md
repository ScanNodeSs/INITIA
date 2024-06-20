GEREĞİNDEN FAZLA RAM KULLANIMI DÜZELTMEK İÇİN AŞAĞIDAKİ İŞLEMLERİ SIRASIYLA YAPALIM

```shell
nano ~/.initia/config/config.toml
```

İNDEXER DÜZENLEME 

config toml dosyasına girdikten sonra bilgisayarınızda ctrl w basın ve  arama kısmına 'index' yazın ve enter basın


indexer='kv' yazan yeri indexer='null' olarak düzeltin ve aşağıdaki kodlarla resart atın

```shell
sudo systemctl daemon-reload
sudo systemctl enable initiad.service
```


Log kontrolü yapın

```shell
sudo journalctl -u initiad.service -f --no-hostname -o cat
```

ram kullanımını kontrol edin
```shell
htop
```
