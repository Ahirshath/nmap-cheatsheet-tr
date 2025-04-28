
# 🛰️ Nmap Kılavuz Projesi

Bu proje, Nmap aracının en yaygın kullanılan komutlarının açıklamalarıyla birlikte düzenlenmiş bir kılavuzudur. Siber güvenlik uzmanları, penetrasyon testçileri ve bilgi güvenliği meraklıları için referans kaynağı olarak tasarlanmıştır.

## 📁 İçerik

- `Nmap_Klavuz.md`: Nmap komutlarının açıklamaları ve kullanım örnekleriyle detaylı bir markdown dokümanı.

## 🇹🇷 Nmap Komutları ve Açıklamaları (Türkçe Rehber)

📌 Hedef Belirtme ve Temel Seçenekler

| Komut | Açıklama |
|-------|----------|
| `-iL <dosya>` | Belirtilen dosyadaki IP adreslerini hedef olarak alır. |
| `--exclude <ip>` | Belirtilen IP adreslerini tarama dışında bırakır. |
| `-Pn` | Ping atmadan tarama yapar. Cihaz çevrimdışı gibi görünse bile tarama yapılır. |
| `-A` | Agresif tarama: OS tanımlama, servis versiyonları, script taraması ve traceroute içerir. |
| `--traceroute` | Hedefe ulaşan ağ yolunu (hop'ları) görüntüler. |
| `-R` | IP'den ters DNS çözümlemesi yapar. |

---

## ⚙️ Tarama Teknikleri

| Komut | Açıklama |
|-------|----------|
| `-sS` | TCP SYN (stealth) taraması. Firewall'lar tarafından daha zor tespit edilir. |
| `-sT` | TCP connect taraması. Root izni gerekmez, daha belirgin izler bırakır. |
| `-sU` | UDP port taraması yapar. |
| `-sN` | TCP Null taraması. Güvenlik duvarlarını atlatmaya yönelik pasif bir yöntemdir. |
| `-sF` | TCP FIN taraması. Genellikle açık portları belirlemede kullanılır. |
| `-sA` | ACK taraması. Firewall varlığını tespit etmek için kullanılır. |
| `-sO` | IP protokol taraması. Hangi protokollerin açık olduğunu kontrol eder. |

---

## 🧠 Servis ve Sürüm Tespiti

| Komut | Açıklama |
|-------|----------|
| `-sV` | Servis sürüm bilgilerini belirlemeye çalışır. |
| `--version-trace` | Daha fazla detay için sürüm tespiti sürecini gösterir. |
| `-O` | İşletim sistemi tanımlama (OS detection) yapar. |
| `--osscan-guess` | OS tespiti yapılamadığında tahmin yürütür. |

---

## 🔥 Zamanlama ve Performans Ayarları

| Komut | Açıklama |
|-------|----------|
| `-T<0-5>` | Zamanlama modu (0 = en yavaş, 5 = en hızlı). |
| `--min-rate <sayı>` | Minimum gönderim hızı (paket/saniye). |
| `--max-retries <sayı>` | Paket yeniden gönderme sınırı. |
| `--host-timeout <süre>` | Bir host için tarama zaman aşımı süresi. |
| `--min-parallelism <sayı>` | Minimum paralel iş parçası sayısı. |

---

## 🛡️ Güvenlik Duvarı Atlama Teknikleri

| Komut | Açıklama |
|-------|----------|
| `-f` | Paketleri parçalara ayırarak gönderir (fragmentation). |
| `--mtu <değer>` | Paket boyutunu belirli byte'lara sabitler. |
| `-D RND:10` | 10 farklı sahte IP ile decoy tarama yapar. |
| `-sI <zombi> <hedef>` | Idle tarama (zombi sistemi üzerinden). |
| `--source-port <port>` | Kaynak portu belirler (örneğin 53 ile DNS trafiği gibi görünür). |
| `--spoof-mac 0` | Rastgele bir MAC adresi kullanarak spoofing yapar. |

---

## 💾 Çıktı Formatları

| Komut | Açıklama |
|-------|----------|
| `-oN <dosya>` | Normal metin formatında çıktı kaydeder. |
| `-oX <dosya>` | XML formatında çıktı verir. |
| `-oG <dosya>` | Grep için uygun formatta çıktı sağlar. |
| `-oA <ad>` | Tüm formatları tek seferde üretir (N, X, G). |
| `--stats-every 5s` | Tarama ilerleme bilgisini her 5 saniyede gösterir. |

---

## 📜 NSE Script Örnekleri

| Komut | Açıklama |
|-------|----------|
| `--script whois-domain.nse` | Domain WHOIS bilgilerini getirir. |
| `--script whois-ip.nse` | IP adresi WHOIS bilgisi çeker. |
| `--script vuln` | Zafiyet taraması yapar. |

---

## 🧪 Faydalı Komutlar

| Komut | Açıklama |
|-------|----------|
| `-h` | Yardım menüsünü gösterir. |
| `-v`, `-vv` | Detaylı çıktı verir. Çoklu kullanımı detay seviyesini artırır. |
| `-d` | Hata ayıklama modunu etkinleştirir. |
| `--reason` | Port durumlarının nedenini açıklar. |
| `--open` | Sadece açık portları gösterir. |
| `--packet-trace` | Gönderilen ve alınan paketleri gösterir. |

---

## 🐚 Örnek Kullanım

```bash
sudo nmap -sS -sV -O -Pn --script vuln <hedef_ip>
```

---

## ✅ Özellikler

- Ping ve port tarama parametreleri
- Firewall atlatma yöntemleri
- OS ve servis tespiti

## ⚠️ Uyarı

Bu rehber yalnızca **eğitimsel ve izinli test ortamlarında** kullanılmak üzere hazırlanmıştır. İzinsiz tarama ve saldırı girişimleri yasalara aykırıdır ve cezai yaptırımları olabilir.

## 📌 Lisans

MIT Lisansı altında paylaşılmıştır. Dilediğiniz gibi kullanabilir, geliştirebilir ve paylaşabilirsiniz.

---

Hazırlayan: [burakcanbalta](https://github.com/burakcanbalta)
