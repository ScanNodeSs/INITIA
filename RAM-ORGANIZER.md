GEREĞİNDEN FAZLA RAM KULLANIMI DÜZELTMEK İÇİN AŞAĞIDAKİ İŞLEMLERİ SIRASIYLA YAPALIM

toml dosyasına girelim

```shell
nano ~/.initia/config/config.toml
```

İNDEXER DÜZENLEME 

config toml dosyasına girdikten sonra bilgisayarınızda ctrl w basın ve aşağıda gösterildiği gibi  arama kısmına 'index' yazın ve enter basın

![image](https://github.com/ScanNodeSs/INITIA/assets/172748611/275947eb-79f8-4d55-88e8-2db397fdd081)

indexer='kv' yazan yeri indexer='null' olarak düzeltin ctrl xy basın ve enter basın kaydedecek ve dosyadan çıkacaktır. Aşağıdaki kodlarla resart atın

```shell
sudo systemctl daemon-reload
sudo systemctl enable initiad.service
```
![image](https://github.com/ScanNodeSs/INITIA/assets/172748611/49c1c8c0-418e-47b8-8f30-56c468cff9f2)


Log kontrolü yapın

```shell
sudo journalctl -u initiad.service -f --no-hostname -o cat
```

ram kullanımını kontrol edin
```shell
htop
```
