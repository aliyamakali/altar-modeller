# EMA Lightning — lisans ve sorumluluk bölümleri

Kaynak: https://github.com/canberk7/ema-lightning README.md, 2026-11-21
Kaynak (model kartı): https://huggingface.co/canberkkkkkk/ema-lightning README.md, 2026-11-21
Model deposunda ayrı `LICENSE` / `NOTICE` dosyası YOK. Türkçe README'nin ilgili bölümleri aşağıda
değiştirilmeden alınmıştır (Apache-2.0, ağırlıklar ve kod).

## Training data

An internal corpus of about 1,000 hours of single-speaker Turkish speech, all synthetic, generated with [VoxCPM2](https://huggingface.co/openbmb/VoxCPM2) (OpenBMB, Apache 2.0). The voice is not a real person's: it was designed in VoxCPM2 from a short text description, with no recording of anyone as a reference.

## Responsible use

EMA Lightning makes synthetic speech, and people who hear it should know that. Tell listeners they are hearing an AI-generated voice, for example at the start of a call ("Bu görüşmede yapay zekâ ile üretilmiş bir ses kullanılmaktadır."), and label the audio you publish the same way ("Bu ses yapay zekâ ile üretilmiştir."); laws in many places, including the EU AI Act, require this disclosure. Do not present it as a real person's voice, use it in scams or impersonation, or make it say things a real person did not say. Numbers, dates and abbreviations are read through automatic text normalization, which can misread unusual input, so for banking, health, legal or emergency messages, have a person check the text and the audio before it reaches anyone.

## Disclaimer

EMA Lightning is provided "as is", without warranty of any kind, under the Apache License 2.0. The authors are not liable for how it is used or for any damage arising from its use. Whoever deploys it is responsible for using it lawfully, including the disclosure and consent rules that apply where it is used. This section is not legal advice.

## License

Apache 2.0, for the weights and the code. Commercial use included.

## Acknowledgements

Special thanks to **[Erdem Tuna](https://github.com/erdemtuna)**, who built [normalizer-tr](https://github.com/erdemtuna/normalizer-tr), the Turkish text normalizer behind EMA Lightning. Every number, date, amount and symbol you hear read aloud goes through his work.

Thanks also to **Freya** for the Freya-TR-Eval benchmark, and to **the Anka TTS authors** for the published baselines marked †.
