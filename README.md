# Algorave İzmir — Live Sets

Sahnede canlı yazdığımız kodlar.

Algorave İzmir; canlı kodlama ve disiplinlerarası sanatı bir araya getirerek İzmir'de
algoritma kültürü inşa eden bir topluluktur. Uluslararası [TOPLAP](https://toplap.org/) ağının üyesiyiz.

🌐 [algoraveizmir.org](https://algoraveizmir.org) · 📷 [@algoraveizmir](https://instagram.com/algoraveizmir) · ▶️ [YouTube](https://www.youtube.com/@izmiralgorave)

---

## Bu depo ne içeriyor?

Etkinliklerimizde sahnede gerçek zamanlı yazdığımız performans kodları. Her klasör bir geceye ait;
o gece hangi kodun çalıştığını, hangi enstrümanlarla birleştiğini burada bulabilirsiniz.

Manifestomuzun beşinci maddesi:

> **Biz açık paylaşırız.** Kodumuz herkesindir. Yazdığımızı saklamayız, üstüne inşa edilsin diye
> bırakırız. Bir sonraki sanatçıya kapıyı, bizden öncekilerin araladığı gibi aralarız.

Bu depo o cümlenin karşılığıdır. Alın, çalıştırın, bozun, kendinize göre değiştirin.

---

## Klasör yapısı

```
sets/
  2026-08-01-lansman/          # etkinlik tarihi + adı
    aybike-ozsoyke/
      set.tidal                # sahnede çalışan kod
      README.md                # ne kullanıldı, nasıl çalıştırılır
    berken-eren-usar/
    hasan-metehan-ucar/
  2026-xx-xx-sonraki-etkinlik/

tools/                         # ortak yardımcı dosyalar, sample listeleri
docs/                          # kurulum notları, atölye materyalleri
```

Yeni bir gece eklerken `sets/` altında `YYYY-AA-GG-etkinlik-adi` biçiminde bir klasör açın.
Tarihi başa yazmak dosyaların kronolojik sıralanmasını sağlar.

---

## Kullandığımız araçlar

Setlerimiz **[TidalCycles](https://tidalcycles.org/)** ile yazılıyor. Tidal ses üretmez;
pattern'leri **[SuperCollider](https://supercollider.github.io/)** üzerinde çalışan
**SuperDirt**'e gönderir, sesi o çıkarır. Yani ikisi birlikte çalışmak zorunda.

| Bileşen | Ne yapar |
|---|---|
| TidalCycles | Pattern dilini yazdığınız katman — `.tidal` dosyaları |
| SuperCollider | Ses motoru |
| SuperDirt | Tidal'ın konuştuğu sample çalar (SuperCollider quark'ı) |
| sc3-plugins | Bazı efektler için gereken ek UGen'ler |

Kurulum adımları için: **[docs/kurulum.md](docs/kurulum.md)**

Her sanatçının klasöründeki `README.md` dosyasında o set için gereken özel kurulum
adımları ve kullanılan sample'lar yazılıdır.

## Çalıştırma sırası

1. SuperCollider'ı açın, `SuperDirt.start` komutunu çalıştırın
2. Editörünüzde Tidal'ı başlatın (boot)
3. `.tidal` dosyasındaki satırları tek tek değerlendirin (`Ctrl/Cmd + Enter`)
4. Durdurmak için `hush`

Setler doğaçlama yazıldığı için dosyalar baştan sona çalıştırılmak üzere değil,
satır satır denenmek üzere hazırlanmıştır.

---

## Katkı

Topluluk üyesiyseniz kendi setinizi doğrudan ekleyebilirsiniz. Dışarıdansanız
[issue açın](../../issues) ya da pull request gönderin.

Katkı verirken lütfen:

- Setinizi kendi klasörünüze koyun, başkasının dosyasını değiştirmeyin
- Klasörünüze kısa bir `README.md` ekleyin: hangi araç, hangi sürüm, özel bir kurulum var mı
- Büyük ses dosyalarını (`.wav`, `.mp4`) repoya koymayın — bağlantı verin

Tüm etkileşimlerde [Davranış Kurallarımız](CODE_OF_CONDUCT.md) geçerlidir.

---

## Lisans

Kod **[GNU GPL v3.0](LICENSE)** ile paylaşılmıştır.

Bu ne demek:

- **Yapabilirsiniz** — indirin, çalıştırın, değiştirin, kendi setinizde çalın,
  atölyenizde öğretin, sahnede kullanın. Performans yapmak için hiçbir şart yok.
- **Şart** — değiştirdiğiniz hâli *yayınlarsanız*, onu da GPL ile açmanız gerekir.
  Yani bu kodun üstüne inşa edilen her şey açık kalır.

Copyright © 2026 Algorave İzmir

Bu depodaki ses ve görsel kayıtlar (varsa) **CC BY-SA 4.0** ile paylaşılır.

---

## İletişim

izmiralgorave@gmail.com

<br>

---
<br>

# Algorave İzmir — Live Sets

*The code we write live on stage.*

Algorave İzmir is a community building algorithmic culture in İzmir by bringing together
live coding and interdisciplinary art. We are a member of the international
[TOPLAP](https://toplap.org/) network.

## What's in here

Performance code written in real time on stage at our events. Each folder belongs to one
night — you'll find what ran that evening and which instruments it played alongside.

The fifth article of our manifesto:

> **We share openly.** Our code belongs to everyone. We do not keep what we write; we leave
> it so others can build on it. We hold the door open for the next artist, just as those
> before us held it open for us.

This repository is that sentence in practice. Take it, run it, break it, make it yours.

## Tools

Our sets are written in **[TidalCycles](https://tidalcycles.org/)**. Tidal produces no sound
itself — it sends patterns to **SuperDirt**, running on
**[SuperCollider](https://supercollider.github.io/)**, which does the actual synthesis.
Setup instructions (in Turkish): [docs/kurulum.md](docs/kurulum.md)

## Structure

Sets live under `sets/YYYY-MM-DD-event-name/artist-name/`. Each artist folder has its own
README with the tools, versions and setup notes for that set.

Because these sets were improvised, the files are not meant to be run top to bottom —
evaluate them line by line.

## Contributing

Community members can add their own sets directly. Everyone else: open an issue or send a
pull request. Please keep to your own folder, include a short README, and link to large
audio files rather than committing them.

Our [Code of Conduct](CODE_OF_CONDUCT.md) applies to all interactions here.

## License

Code is released under the **[GNU GPL v3.0](LICENSE)**.

You are free to download, run, modify, perform and teach this code — performing carries no
conditions at all. The one requirement: if you *publish* a modified version, it must also
be released under the GPL. Whatever is built on this stays open.

Copyright © 2026 Algorave İzmir

Audio and visual recordings in this repository (if any) are shared under **CC BY-SA 4.0**.

## Contact

izmiralgorave@gmail.com
