# Flarial GUI (LeviLauncher mod)

ClickGUI ala Flarial buat LeviLauncher (Android, ARM64).

- Layar awal: tombol **Mods** + **pensil** (edit HUD) di atas, **Cosmetics** (merah) di bawah.
- Mods dan Cosmetics masih kosong.
- Pensil = mode edit HUD: seret kotak buat mindahin, tarik titik pojok kanan bawah buat resize.
- Buka GUI lewat tombol melayang **F** dari Mod Menu LeviLauncher.

## Build (tanpa PC)
1. Upload semua file repo ini ke GitHub (repo public).
2. Tab **Actions** > workflow **build** > Run workflow.
3. Download artifact **flarial_gui** > isinya `flarial_gui.levipack` dan folder `flarial_gui`.
4. Import `.levipack` di LeviLauncher > Mods, aktifkan, lalu jalankan Minecraft.

Kalau folder `.github` nggak ikut ke-upload, buat manual: Add file > Create new file > nama `.github/workflows/build.yml`, lalu paste isinya.

## Yang belum dites (jujur)
- Ukuran layar: `kScreenW` / `kScreenH` di `src/main.cpp` (default 2436x1080). Kalau posisi meleset, ubah angkanya.
- Overlay HUD cuma muncul pas layar HUD kebuka (bukan di chat/menu).
- Format `.levipack`: kalau gagal diimport, pakai folder `flarial_gui` hasil artifact.
