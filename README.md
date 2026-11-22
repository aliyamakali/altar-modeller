# Altar ses modelleri

Bu depo, [Altar](https://github.com/aliyamakali) kişisel asistanının internetsiz Türkçe ses modellerini
barındırır. Dosyalar **Releases** bölümündedir (`v-model-1`). Altar bu dosyaları kullanıcının cihazına
indirir ve SHA-256 ile doğrular.

Modellerin hiçbiri Altar'a ait değildir. Her biri kendi sahibinin **Apache License 2.0** lisansıyla
yayınlanmıştır. Altar bu projelerle bağlantılı değildir ve onlar tarafından onaylanmamıştır.

## Modeller ve sahipleri

| Dosyalar | Model | Sahibi | Lisans | Kaynak |
|---|---|---|---|---|
| `yazgi-*.onnx`, `yazgi-sesler.bin` | yazgı-tts-1 | © 2026 Erkam Kavak | Apache-2.0 | https://huggingface.co/erkamk/yazgi-tts-1 |
| `antalia-*.onnx` | Antalia-2 Mini | © 2026 PatientDesk AI | Apache-2.0 | https://huggingface.co/cloud0day3/antalia-mini |
| `ema-*.onnx` | EMA Lightning | Canberk Aslan | Apache-2.0 | https://huggingface.co/canberkkkkkk/ema-lightning |

Her modelin özgün `NOTICE` dosyası (varsa) değiştirilmeden `third_party/` klasöründedir; üçünün de lisansı aynı Apache-2.0 metnidir. yazgı-tts-1'in
eğitim verisi künyeleri `third_party/yazgi-tts-1/NOTICE` dosyasında; video bazında yükleyici künyeleri (YODAS2) özgün depodaki [ATTRIBUTION.md](https://huggingface.co/erkamk/yazgi-tts-1/blob/main/ATTRIBUTION.md) dosyasındadır. Apache License
2.0'ın tam metni `LICENSE` dosyasındadır.

## Yapılan değişiklikler (Apache-2.0 md. 4(b))

Model mimarisi ve eğitimi **değiştirilmemiştir**. Yalnız biçim ve sayısal hassasiyet değiştirilmiştir:

- **Tüm modeller:** Özgün PyTorch ağırlıkları ONNX biçimine çevrildi.
- **yazgı-tts-1, küçük set (`*-ds362.onnx`, toplam ~83 MB):** Telefon için sıkıştırıldı.
  - voice: fp16
  - prefix: int8 (kanal başına)
  - talker: int4 blok nicemleme (MatMulNBits, blok 32)
  - predictor: fp16
  - codec-dec: int8
  - 20 Türkçe kayıtta asıl modelle karşılaştırıldı: yazıya geri çevirme hata oranı artmadı, doğallık
    değişmedi, tekrar ya da takılma olmadı.
- **yazgı-tts-1, tam set (`yazgi-*.onnx`, ~330 MB):** Yalnız ONNX'e çevrildi (fp32).
- **Antalia-2 Mini:** ONNX'e çevrildi; vocoder fp16.
- **EMA Lightning:** ONNX'e çevrildi (fp32).

Antalia'nın özgün paketi çalışma anında GPL-3.0 lisanslı `cmudict` paketini kullanır. Bu paket bu depoda ve
Altar'da **yoktur**.

## Yapay zekâ sesi

Bu modellerin ürettiği sesler yapay zekâ ile üretilmiş sentetik seslerdir. Bu seslerle üretilen kayıtları
yayımlayanlar, yürürlükteki mevzuatın gerektirdiği yerde (ör. AB Yapay Zekâ Yasası) sesin yapay zekâ ile
üretildiğini belirtmelidir.

---

*English:* Offline Turkish TTS models used by the Altar assistant. Files are in Releases. All models belong to
their authors and are Apache-2.0 licensed. Original NOTICE files are in `third_party/`; the full Apache-2.0 text is in `LICENSE`. Changes:
converted to ONNX. The small yazgı-tts-1 set (~83 MB) is additionally quantized (fp16 / int8 / int4 block)
for phones. Architecture and training are unchanged. Not affiliated with or endorsed by the model authors.
