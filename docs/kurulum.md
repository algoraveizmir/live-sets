# Kurulum Notları

Bu depodaki setleri çalıştırmak için TidalCycles ve SuperCollider gerekiyor.

> Komutlar sürümden sürüme değişebildiği için burada adımların **mantığını** anlatıyoruz.
> Güncel ve tam komutlar için her zaman resmî kaynağa bakın:
> **[tidalcycles.org/docs/getting-started/installation](https://tidalcycles.org/docs/getting-started/installation)**

---

## Neyin neye bağlı olduğu

Tidal tek başına ses çıkarmaz. Zincir şöyle işler:

```
Editörünüz  →  TidalCycles  →  (OSC mesajları)  →  SuperDirt  →  SuperCollider  →  hoparlör
   (kod)        (Haskell)                          (quark)      (ses motoru)
```

Bu yüzden dört şey kurmanız gerekiyor:

1. **SuperCollider** — ses motoru
2. **sc3-plugins** — bazı efektlerin ihtiyaç duyduğu ek UGen'ler
3. **SuperDirt** — SuperCollider içine kurulan quark; sample'ları çalar
4. **TidalCycles** — Haskell kütüphanesi (GHC ve cabal ile gelir)

Ayrıca kod yazacağınız bir **editör eklentisi** lazım.

---

## Kurulum sırası

Sıra önemli — SuperCollider olmadan SuperDirt kurulamaz.

### 1. SuperCollider

[supercollider.github.io/downloads](https://supercollider.github.io/downloads) adresinden
işletim sisteminize uygun sürümü indirin.

### 2. sc3-plugins

[supercollider.github.io/sc3-plugins](https://supercollider.github.io/sc3-plugins/)
sayfasındaki yönergeleri izleyin. SuperCollider'ın eklenti klasörüne kopyalanır.

### 3. SuperDirt

SuperCollider'ı açın ve şu satırı çalıştırın (satırın üzerindeyken `Cmd/Ctrl + Enter`):

```supercollider
Quarks.checkForUpdates({Quarks.install("SuperDirt", "v1.7.3")});
```

Kurulum birkaç dakika sürebilir; bittiğinde SuperCollider'ı yeniden başlatın.

> Sürüm numarası zamanla değişir. Güncel sürüm için
> [SuperDirt deposuna](https://github.com/musikinformatik/SuperDirt) bakın.

### 4. TidalCycles

Tidal bir Haskell kütüphanesi, yani önce **GHCup** (Haskell araç zinciri) gerekiyor.
Resmî kurulum sayfasındaki adımları izleyin — orada macOS, Linux ve Windows için
ayrı ayrı anlatılıyor.

### 5. Editör

Atom artık geliştirilmiyor. Güncel seçenekler:

- **[Pulsar](https://pulsar-edit.dev/)** — Atom'un devamı, `tidalcycles` paketi ile
- **[VS Code](https://code.visualstudio.com/)** — `vscode-tidalcycles` eklentisi ile
- **Vim / Neovim** — `vim-tidal`
- **Emacs** — `tidal.el`

---

## Çalıştırma

Her oturumda:

1. **SuperCollider'ı açın**, şu satırı çalıştırın:
   ```supercollider
   SuperDirt.start
   ```
   Konsolda hata yoksa ses motoru hazır demektir.

2. **Editörünüzde Tidal'ı başlatın** (boot). Eklentiye göre komut değişir; genelde
   komut paletinden "Tidal: Boot" gibi bir seçenek.

3. **Pattern satırlarını tek tek çalıştırın** — `Cmd/Ctrl + Enter`.

4. **Susturmak için:**
   ```haskell
   hush
   ```

---

## Sample'lar

SuperDirt varsayılan bir sample kütüphanesiyle gelir (`bd`, `sn`, `hh` gibi).
Setlerimizde kendi eklediğimiz sample'lar varsa, ilgili sanatçının klasöründeki
`README.md` dosyasında nereden indirileceği yazar.

Büyük ses dosyalarını bu depoya koymuyoruz — bağlantı veriyoruz.

---

## Sık karşılaşılan sorunlar

**Ses gelmiyor, hata da yok**
SuperCollider'da `SuperDirt.start` çalıştırıldı mı? Sistem ses çıkışı doğru cihazda mı?

**`Command not found: ghc` / `cabal`**
Haskell araç zinciri PATH'e eklenmemiş. Terminali kapatıp yeniden açın; sorun sürerse
GHCup kurulumunu tekrar gözden geçirin.

**Editör "Tidal: boot failed" diyor**
Tidal kütüphanesi kurulu değil ya da editör eklentisi GHC'yi bulamıyor. Eklenti
ayarlarında `ghci` yolunu elle vermeniz gerekebilir.

**`SuperDirt` bulunamıyor**
Quark kurulduktan sonra SuperCollider yeniden başlatılmadı.

---

<!-- Buraya kendi yaşadığınız sorunları ve çözümlerini ekleyin —
     bir sonraki katılan için en değerli kısım burası olacak. -->
