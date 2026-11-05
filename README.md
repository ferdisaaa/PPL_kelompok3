# SauceDemo Automation (Selenium + pytest + POM)

Otomasi pengujian UI untuk https://www.saucedemo.com/ dengan Page Object Model.

## Anggota Kelompok
| Nama | NIM |
|------|-----|
| (isi) | (isi) |

## Struktur
- `pages/`  : Page Object (locator Relative XPath + aksi)
- `tests/`  : Skrip uji + assertions
- `conftest.py` : fixture browser

## Cara menjalankan
```bash
python -m venv venv
# Windows: .\venv\Scripts\Activate.ps1   |   Linux/macOS: source venv/bin/activate
pip install -r requirements.txt
pytest -v
```
