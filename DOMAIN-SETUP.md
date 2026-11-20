# İsviçre Rotam — Özel Alan Adı Kurulum Notları

Hedef web adresi: https://isvicrerotam.com

Bu dosya kurulum yönergesidir; `CNAME` şu anda tasarım dalında hazırdır. Canlı site `main` dalından yayınlandığı için bu dal birleştirilmeden ve GitHub Pages / DNS işlemleri yapılmadan alan adı aktif olmaz.

## 1. GitHub Pages

Depo: https://github.com/bulentimat-ai/isvicre-rotam-website

GitHub → Settings → Pages → Custom domain → `isvicrerotam.com` → Save.

Github Pages kaynağı `main` dalı kök dizinidir. Tasarım onaylandıktan sonra bu dalın birleştirilmesi gerekir. GitHub'ın eklediği veya güncellediği `CNAME` değerinin tam olarak `isvicrerotam.com` olduğundan emin olun.

## 2. Alan adı DNS kayıtları

Alan adı sağlayıcısının DNS panelinde aşağıdaki kayıtları kullanın (GitHub Pages resmî yönergesi):

| Tür | Ad/Host | Değer |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | bulentimat-ai.github.io |

Opsiyonel IPv6 kayıtları (A kayıtlarını değiştirmeden eklenebilir):

- AAAA @ → 2606:50c0:8000::153
- AAAA @ → 2606:50c0:8001::153
- AAAA @ → 2606:50c0:8002::153
- AAAA @ → 2606:50c0:8003::153

DNS üzerinde çakışan varsayılan/parked A kayıtlarını dikkatle kontrol edin. Wildcard (`*`) kullanmayın. `www` CNAME hedefini bir alt dizine veya `isvicrerotam.com` adresine değil, doğrudan `bulentimat-ai.github.io` adresine yönlendirin.

## 3. HTTPS ve doğrulama

- DNS kayıtları doğru çözümlendiğinde GitHub → Settings → Pages → Enforce HTTPS.
- `https://isvicrerotam.com/`, `/gizlilik/`, `/destek/`, `/hakkinda/` adreslerini ayrı ayrı test edin.
- `https://www.isvicrerotam.com` yönlendirmesini ve HTTPS sertifikasını test edin.
- Eski GitHub Pages bağlantıları çalışmaya devam ediyor / yönlendiriliyor mu kontrol edin.
- DNS değişikliklerinin yayılması 24 saate kadar sürebilir.

**Eski App Store Connect Privacy/Support URL'lerini yeni site çalıştığı doğrulanmadan değiştirmeyin.**

## 4. E-posta adresleri (webde yazılması, posta kutusu açmaz)

- Destek: `destek@isvicrerotam.com`
- Genel bilgi / gizlilik: `info@isvicrerotam.com`

E-posta altyapısı ayrıca sağlayıcı üzerinden kurulmalıdır. MX kayıtları ve gönderim güvenilirliği için SPF, DKIM ve DMARC değerleri seçilen e-posta sağlayıcısına göre yapılandırılmalıdır. GitHub Pages e-posta barındırma hizmeti vermez.

DNS üzerinde var olan ve e-posta için kullanılan MX/TXT kayıtlarını değiştirmeyin veya silmeyin. E-posta gönderme ve alma testleri tamamlanmadan adresleri aktif ve çalışıyor kabul etmeyin.

## Kaynaklar

- https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site
- https://docs.github.com/en/pages/getting-started-with-github-pages/securing-your-github-pages-site-with-https
