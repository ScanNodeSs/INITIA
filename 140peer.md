peer bulamama sorunu ve peer artırma yolu 



nano /root/.initia/config/config.toml





ctrl +w  max_num_inbound_peers yazın 

# Maximum number of inbound peers
max_num_inbound_peers = 140

# Maximum number of outbound peers to connect to, excluding persistent peers
max_num_outbound_peers = 10

Bunlar yazacak ve max_num_inbound_peers = 40 yazacak orda biz 140 yapicaz 

max_num_inbound_peers = 140 şeklinde olucak


ctrl xy enterla kaydet



systemctl daemon-reload && systemctl restart initiad && journalctl -u initiad -fo cat




core node rehberden derlenmiştir
