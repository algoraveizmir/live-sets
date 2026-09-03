# Başlangıç

Hiç kod yazmamış biri için ilk adımlar. Kurulum gerekmez —
**[strudel.cc](https://strudel.cc)** adresini açın, örnekleri yapıştırın,
`Ctrl + Enter` ile çalıştırın.

Anlamadığınız bir terim çıkarsa: [`../sozluk.md`](../sozluk.md)

---

## 1 — İlk ses

```javascript
sound("bd")
```

`bd` = bass drum. Çalıştırın, bir davul vuruşu duyacaksınız — döngü başına bir kez.

Susturmak için `hush` yazıp çalıştırın.

## 2 — Örüntü

```javascript
sound("bd hh sd hh")
```

Boşlukla ayrılan her ses döngüyü eşit bölüyor. Dört ses → her biri çeyrek döngü.

`hh` = hi-hat, `sd` = snare drum.

## 3 — Hız

```javascript
sound("bd hh sd hh").fast(2)
```

Aynı örüntü, iki kat hızlı. `.slow(2)` deneyin.

## 4 — Katman

```javascript
stack(
  sound("bd ~ bd ~"),
  sound("~ hh ~ hh")
)
```

`~` sessizlik demek. `stack` iki örüntüyü aynı anda çalar.

## 5 — Öklidyen ritim

```javascript
sound("bd").euclid(3, 8)
```

Sekiz adıma üç vuruş, olabildiğince eşit dağıtılmış. Sayıları değiştirin:
`euclid(5,8)`, `euclid(7,16)`. Bu formül dünya müziğindeki pek çok geleneksel ritmi verir.

## 6 — Nota

```javascript
note("c e g c5").sound("piano")
```

Artık davul değil, melodi. `c5` bir oktav üstteki do.

## 7 — Ses işleme

```javascript
note("c e g c5").sound("piano").lpf(800).room(0.5)
```

`lpf` tizleri kesiyor, `room` yankı ekliyor. Sayıları değiştirip dinleyin.

---

## Nasıl çalışılır

Bu örnekleri sırayla okumak yerine **bozarak** ilerleyin. Sayıyı değiştirin, bir sesi
silin, iki örneği birleştirin. Canlı kodlamada öğrenme yolu budur — kod çalışırken
değiştirip ne olduğunu duymak.

Yanlış bir şey yazarsanız ses durur ya da hata çıkar; `hush` yazıp baştan başlayın.
Hiçbir şey kırılmaz.

---

## Sonraki adım

- Strudel'in kendi öğreticisi: [strudel.cc/workshop/getting-started](https://strudel.cc/workshop/getting-started/)
- Görsel eklemek isterseniz: [hydra.ojack.xyz](https://hydra.ojack.xyz)
- Atölye materyallerimiz: [`../atolyeler/`](../atolyeler/)
