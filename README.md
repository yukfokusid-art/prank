# Website Suara Seru-seruan untuk Cloudflare Pages

Ini paket website static yang bisa langsung diupload ke Cloudflare Pages.

## Isi file

```txt
index.html
sounds/
  suara-kaget.wav
```

## Cara deploy ke Cloudflare Pages

1. Masuk Cloudflare Dashboard.
2. Buka **Workers & Pages**.
3. Klik **Create application**.
4. Pilih **Pages**.
5. Pilih **Upload assets** / **Direct Upload**.
6. Upload isi ZIP ini.
7. Klik **Deploy**.

## Cara ganti suara

1. Siapkan file suara kamu, misalnya:
   - `ketawa.mp3`
   - `jumpscare.mp3`
   - `suara-lucu.wav`

2. Masukkan file suara ke folder `sounds`.

3. Buka `index.html`.

4. Cari bagian ini:

```js
const soundConfig = {
  soundFile: "sounds/suara-kaget.wav",
  volume: 0.85,
  delay: 3000,
  playOnce: true,
  showVisualEffect: true,
  visualText: "BOO! 😆",
  visualDuration: 1200
};
```

5. Ganti `soundFile`.

Contoh:

```js
soundFile: "sounds/ketawa.mp3",
```

## Cara atur delay

```js
delay: 3000,
```

Keterangan:

- `1000` = 1 detik
- `3000` = 3 detik
- `5000` = 5 detik
- `10000` = 10 detik

## Cara atur volume

```js
volume: 0.85,
```

Keterangan:

- `0.2` = pelan
- `0.5` = sedang
- `1` = paling keras

## Kenapa suara tidak langsung otomatis pas halaman dibuka?

Browser modern biasanya memblokir autoplay audio sebelum pengunjung klik/tap halaman. Karena itu website ini memakai tombol dulu, lalu suara muncul setelah delay.
