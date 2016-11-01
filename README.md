# Craft CMS Basic Template

## Development

Terkadang saat membuat template, kita menginginkan Craft tidak membuat cache. Berhubung masih baru dengan CMS ini, saya membuat file `craft/storage/runtime/clean.sh` dan menjalankannya setiap kali ingin runtime storage bersih.

```
#! /bin/sh

folders=("./cache" "./compiled_templates" "./HTML" "./logs" "./state")

for folder in "${folders[@]}"
do
   rm -rf $folder
   mkdir $folder
done
```

File `craft/config/general.php` di bawah adalah konfigurasi dasar saat tahap development. Jika sudah production, entri devMode harus disetel false.

```
return array(
    'devMode' => true,
    'omitScriptNameInUrls' => true,
);
```

## Tags

Template ini mengasumsikan kita sudah membuat route untuk tags.

![alt text][route]

## Single

Semua entry dalam section bertipe single menggunakan template static.html.

![alt text][static]

## Article

Saat pertama kali memasang Craft, maka terdapat section bernama News. Ubah namanya menjadi Article dan sesuaikan Format URL dan template yang digunakan.

![alt text][section]

[route]: https://github.com/ceceprawiro/Craft-Basic-Template/raw/master/route.png "Route"
[static]: https://github.com/ceceprawiro/Craft-Basic-Template/raw/master/static.png "Static"
[section]: https://github.com/ceceprawiro/Craft-Basic-Template/raw/master/section.png "Section"