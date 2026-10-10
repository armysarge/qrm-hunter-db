# QRM Hunter DB

A community library of identified HF interference (QRM) signatures, with spectrum screenshots, IQ snippets and confirmed sources. The [QRM Hunter](https://github.com/armysarge/qrm-hunter) app downloads this library and contributes to it.

> **Status: placeholder.** The entry format, validation CI and the app's upload and download support arrive with QRM Hunter sub-project 5. Until then, this repo holds no data.

## How it will work

- Each confirmed QRM report is one folder, `entries/<uuid>/`, containing:
  - `entry.json`: the feature fingerprint, confirmed source class, device make and model, bands, mains frequency, SDR model, how the source was found, and optionally a callsign and a 4-character Maidenhead grid.
  - `waterfall.png`: a waterfall and spectrum screenshot of the interference.
  - `clip.sigmf-meta` / `clip.sigmf-data` (optional): a short IQ recording in [SigMF](https://sigmf.org/) format.
- CI validates every entry and builds `index.json.gz`, which it publishes as a Release asset. The app downloads and caches that index, then matches new captures against it, e.g. "87% like 14 confirmed Huawei SUN2000 reports".
- Uploads are opt-in. The app shows exactly what will be sent, then opens a pull request or issue. A maintainer reviews every submission before it is merged.

## Privacy

Entries never contain exact locations. A callsign and a 4-character grid square (about 100 × 200 km) are optional. IQ clips are short and limited to the interference itself.

## Licence

All data in this repository is licensed under [CC BY 4.0](LICENSE). Contributors agree that their submissions are published under that licence. When you reuse the data, credit "QRM Hunter DB contributors".

## Maintainer

Shaun Scholtz, **ZS6SHZ**. 73!
