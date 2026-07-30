# Turkey Postal Codes Database (Türkiye Posta Kodları)

Türkiye posta kodları veritabanı. 81 il, 2,771 posta kodu. Turkey postal codes for all 81 provinces with district names.

## What is this?

This repository provides a **ready-to-use database** of turkey postal codes database (türkiye posta kodları) with **2,771 records**. Available as SQLite database and SQL dumps — ideal for developers, data analysts, and fintech applications.

## Downloads

| Format | Description | Link |
|---|---|---|
| **SQLite** | Single database file, ready to query | [Releases](../../releases) |
| **SQL** | SQL dump, import into MySQL/PostgreSQL/etc. | [Releases](../../releases) |
| **Excel / CSV / PDF** | Formatted spreadsheets | [listbase.org](https://listbase.org/tr/geography/) |

## Database Schema

```sql
CREATE TABLE postal_codes (
  postal_code TEXT NOT NULL,
  city_code TEXT,
  city_name TEXT NOT NULL,
  district_name TEXT,
  neighbourhood_count INTEGER
);
CREATE INDEX idx_postal_codes_postal_code ON postal_codes (postal_code);
CREATE INDEX idx_postal_codes_city_name ON postal_codes (city_name);
CREATE INDEX idx_postal_codes_city_code ON postal_codes (city_code);
```

## Stats

- **2,771** records
- **1** datasets
- Updated: **2026-07-30**

## Preview

| postal_code | city_code | city_name | district_name | neighbourhood_count |
| --- | --- | --- | --- | --- |
| 01010 | 01 | Adana | Seyhan | 4 |
| 01020 | 01 | Adana | Seyhan | 7 |
| 01030 | 01 | Adana | Seyhan | 6 |
| 01040 | 01 | Adana | Seyhan | 2 |
| 01050 | 01 | Adana | Seyhan | 1 |
| 01060 | 01 | Adana | Seyhan | 7 |
| 01070 | 01 | Adana | Seyhan | 5 |
| 01080 | 01 | Adana | Seyhan | 4 |
| 01100 | 01 | Adana | Seyhan | 2 |
| 01110 | 01 | Adana | Seyhan | 2 |
| 01120 | 01 | Adana | Seyhan | 2 |
| 01130 | 01 | Adana | Seyhan | 5 |
| 01140 | 01 | Adana | Seyhan | 4 |
| 01150 | 01 | Adana | Seyhan | 2 |
| 01160 | 01 | Adana | Seyhan | 3 |
| ... | ... | ... | ... | ... |

*Showing 15 of 2,771 records*

## Release Files

| File | Records | Description |
|---|---|---|
| `postal-codes-turkey.db` | 2,771 | SQLite database (all data) |
| `postal-codes-turkey.sql` | 1-2,771 | SQL dump |


## Usage

### SQLite
```bash
sqlite3 postal-codes-turkey.db "SELECT postal_code, district_name FROM postal_codes WHERE city_name = 'İstanbul' ORDER BY postal_code;"
```

### Import SQL (MySQL)
```bash
mysql -u root -p your_database < postal-codes-turkey.sql
```

### Import SQL (PostgreSQL)
```bash
psql -U postgres -d your_database -f postal-codes-turkey.sql
```

## Use Cases

- **Kargo ve teslimat** — Posta koduna göre adres doğrulama
- **E-ticaret** — Posta kodundan il ve ilçe otomatik tamamlama
- **Adres formu** — Kullanıcının girdiği posta kodunu doğrulama
- **Veri zenginleştirme** — Posta kodundan il/ilçe bilgisi ekleme
- **Logistics** — Map delivery zones by postal code area in Turkey

## FAQ

### Türkiye&#39;de kaç posta kodu var?
Bu veritabanı 81 ili kapsayan 2.771 posta kodu içermektedir. Türk posta kodları 5 haneli rakamlardan oluşur.

### How are Turkish postal codes structured?
Turkish postal codes are 5-digit numbers. The first 2 digits represent the city (il) code (e.g., 34 = İstanbul, 06 = Ankara). This database covers 2,771 postal codes across all 81 provinces.

### How often is this data updated?
The database is updated monthly. Check the [Releases](../../releases) page for the latest version.

### Belirli bir ilin posta kodlarını nasıl bulurum?
```sql
SELECT postal_code, district_name FROM postal_codes WHERE city_name = 'Ankara' ORDER BY postal_code;
```

### How do I search by postal code?
```sql
SELECT * FROM postal_codes WHERE postal_code = '34000';
```


## Browse by City (İl) (81)

| City (İl) | Records | Details |
|---|---|---|
| İstanbul | 266 | [View](cities/-stanbul/) |
| İzmir | 106 | [View](cities/-zmir/) |
| Ankara | 84 | [View](cities/Ankara/) |
| Afyonkarahisar | 82 | [View](cities/Afyonkarahisar/) |
| Konya | 75 | [View](cities/Konya/) |
| Manisa | 69 | [View](cities/Manisa/) |
| Adana | 65 | [View](cities/Adana/) |
| Mersin | 63 | [View](cities/Mersin/) |
| Balıkesir | 61 | [View](cities/Bal-kesir/) |
| Antalya | 59 | [View](cities/Antalya/) |
| Bursa | 59 | [View](cities/Bursa/) |
| Tokat | 51 | [View](cities/Tokat/) |
| Yozgat | 50 | [View](cities/Yozgat/) |
| Sivas | 48 | [View](cities/Sivas/) |
| Kütahya | 43 | [View](cities/K-tahya/) |
| Kastamonu | 42 | [View](cities/Kastamonu/) |
| Giresun | 40 | [View](cities/Giresun/) |
| Elazığ | 39 | [View](cities/Elaz-/) |
| Eskişehir | 39 | [View](cities/Eski-ehir/) |
| Kayseri | 39 | [View](cities/Kayseri/) |
| Isparta | 38 | [View](cities/Isparta/) |
| Çanakkale | 37 | [View](cities/-anakkale/) |
| Niğde | 36 | [View](cities/Ni-de/) |
| Adıyaman | 35 | [View](cities/Ad-yaman/) |
| Zonguldak | 34 | [View](cities/Zonguldak/) |
| Çorum | 33 | [View](cities/-orum/) |
| Muş | 33 | [View](cities/Mu-/) |
| Kocaeli | 32 | [View](cities/Kocaeli/) |
| Nevşehir | 32 | [View](cities/Nev-ehir/) |
| Edirne | 31 | [View](cities/Edirne/) |
| Kırklareli | 31 | [View](cities/K-rklareli/) |
| Malatya | 31 | [View](cities/Malatya/) |
| Rize | 31 | [View](cities/Rize/) |
| Aksaray | 31 | [View](cities/Aksaray/) |
| Burdur | 29 | [View](cities/Burdur/) |
| Samsun | 29 | [View](cities/Samsun/) |
| Çankırı | 28 | [View](cities/-ank-r-/) |
| Denizli | 28 | [View](cities/Denizli/) |
| Erzincan | 27 | [View](cities/Erzincan/) |
| Gaziantep | 26 | [View](cities/Gaziantep/) |
| Şırnak | 26 | [View](cities/-rnak/) |
| Bitlis | 24 | [View](cities/Bitlis/) |
| Aydın | 23 | [View](cities/Ayd-n/) |
| Bolu | 23 | [View](cities/Bolu/) |
| Erzurum | 23 | [View](cities/Erzurum/) |
| Hatay | 23 | [View](cities/Hatay/) |
| Siirt | 23 | [View](cities/Siirt/) |
| Kırıkkale | 23 | [View](cities/K-r-kkale/) |
| Düzce | 23 | [View](cities/D-zce/) |
| Ağrı | 22 | [View](cities/A-r-/) |
| Diyarbakır | 22 | [View](cities/Diyarbak-r/) |
| Trabzon | 22 | [View](cities/Trabzon/) |
| Osmaniye | 22 | [View](cities/Osmaniye/) |
| Ordu | 21 | [View](cities/Ordu/) |
| Bingöl | 20 | [View](cities/Bing-l/) |
| Gümüşhane | 20 | [View](cities/G-m-hane/) |
| Batman | 20 | [View](cities/Batman/) |
| Yalova | 20 | [View](cities/Yalova/) |
| Bilecik | 19 | [View](cities/Bilecik/) |
| Artvin | 18 | [View](cities/Artvin/) |
| Kırşehir | 18 | [View](cities/K-r-ehir/) |
| Sakarya | 18 | [View](cities/Sakarya/) |
| Sinop | 18 | [View](cities/Sinop/) |
| Şanlıurfa | 18 | [View](cities/-anl-urfa/) |
| Karaman | 18 | [View](cities/Karaman/) |
| Amasya | 17 | [View](cities/Amasya/) |
| Kars | 17 | [View](cities/Kars/) |
| Kahramanmaraş | 17 | [View](cities/Kahramanmara-/) |
| Tunceli | 17 | [View](cities/Tunceli/) |
| Uşak | 17 | [View](cities/U-ak/) |
| Karabük | 17 | [View](cities/Karab-k/) |
| Tekirdağ | 16 | [View](cities/Tekirda-/) |
| Van | 16 | [View](cities/Van/) |
| Mardin | 15 | [View](cities/Mardin/) |
| Ardahan | 15 | [View](cities/Ardahan/) |
| Hakkari | 14 | [View](cities/Hakkari/) |
| Muğla | 13 | [View](cities/Mu-la/) |
| Bartın | 13 | [View](cities/Bart-n/) |
| Iğdır | 11 | [View](cities/I-d-r/) |
| Bayburt | 9 | [View](cities/Bayburt/) |
| Kilis | 8 | [View](cities/Kilis/) |


## Browse Online

Explore and download individual datasets at **[listbase.org](https://listbase.org/tr/geography/)**.

## License

[MIT](LICENSE) — Free to use for any purpose.

## Source

PTT (Posta ve Telgraf Teşkilatı)

---

Made with data from [ListBase.org](https://listbase.org/tr/geography/) — Free Reference Tables & Lists
