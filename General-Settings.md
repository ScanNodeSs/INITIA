1) snap kullanırsanız kullandığınız kişinin pruning ayarlarını öncesinde yapmayı unutmayın

2)rpc açmanız gerekiyorsa

INITIA RPC sorgulama
RPC="$(wget -qO- eth0.me)$(grep -A 3 "\[rpc\]" ~/.initia/config/config.toml | egrep -o ":[0-9]+")" && echo $RPC
RpC çalışma sorgulama
curl $RPC/status
connection refused alırsan
düzelt
sed -i 's/^laddr = "tcp:\/\/127\.0\.0\.1:/laddr = "tcp:\/\/0.0.0.0:/' $HOME/.initia/config/config.toml
Yeniden başlat ve kontrol et
sudo systemctl restart initiad
curl $RPC/status

http://İP-ADRESİNİZ:15657

3) indexer null yapma tek komut

sed -i "s/^indexer *=.*/indexer = \"null\"/" $HOME/.initia/config/config.toml

sudo systemctl restart initiad

4)Gözden kaçmış olabilir genel bi yapılması gereken ayarları hatırlatayım
CTRL+W ile arabilirsiniz.

nano ~/.initia/config/config.toml 
Aşağıdaki parametreleri güncelleyin: 


timeout_propose = "3s" 
timeout_propose_delta = "500ms" 
timeout_prevote = "1s" 
timeout_prevote_delta = "500ms" 
timeout_precommit = "1s" 
timeout_precommit_delta = "500ms" 
timeout_commit = "1s" 
Dosyayı kaydedin ve kapatın. 

app.toml dosyasını güncelleme: 
Oracle kısmı (en alt)

app.toml dosyasını açın: 


nano ~/.initia/config/app.toml

Aşağıdaki parametreyi güncelleyin: 


client_timeout = "300ms" 
Dosyayı kaydedin ve kapatın. 



Node'u yeniden başlatın: 

sudo systemctl daemon-reload
sudo systemctl restart initiad

onur arkaşımıza teşekkür ederim...
