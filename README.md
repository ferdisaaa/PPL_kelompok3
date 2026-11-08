# SauceDemo Automation (Selenium + pytest + POM)

Otomasi pengujian UI untuk https://www.saucedemo.com/ dengan Page Object Model.
Tugas Praktikum Pertemuan 7, mata kuliah Pengujian Perangkat Lunak (TI505).

## Anggota Kelompok
| Nama | NIM |
|------|-----|
| Vina Maulidah | 24090014 |
| Nayla Zalfa Zahiyah | 24090017 |
| Ferdi Saputra | 24090075 |
| Rafa Intinanzah Wibisono | 24090095 |

## Struktur
- `pages/`  : Page Object (locator Relative XPath + aksi)
  - `base_page.py` : class induk, explicit wait dan aksi dasar Selenium
  - `login_page.py` : halaman login
  - `inventory_page.py` : halaman inventory
- `tests/`  : Skrip uji + assertions
  - `test_login.py` : 3 test login
  - `test_inventory.py` : test add to cart dan logout
- `conftest.py` : fixture browser

## Test Case
| No | Test | Yang dicek |
|----|------|------------|
| 1 | test_login_positive_valid_user | Login valid, URL pindah ke inventory dan logo tampil |
| 2 | test_login_negative_locked_out_user | Pesan error untuk akun yang diblokir |
| 3 | test_login_negative_empty_password | Pesan error saat password kosong |
| 4 | test_add_backpack_to_cart | Badge keranjang jadi 1 setelah Add to cart |
| 5 | test_logout | Kembali ke halaman login dan tombol login tampil |

## Cara menjalankan
Butuh Python 3.10+ dan Google Chrome.

```bash
python -m venv venv
# Windows: .\venv\Scripts\Activate.ps1   |   Linux/macOS: source venv/bin/activate
pip install -r requirements.txt
pytest -v
```

Hasil yang diharapkan: 5 passed.

## Catatan
- Tidak memakai absolute XPath dan tidak memakai `time.sleep()`, waktu tunggu pakai explicit wait di `BasePage`.
- Semua locator ada di folder `pages/`, tidak ada locator di file test.