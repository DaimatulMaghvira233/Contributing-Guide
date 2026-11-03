cat > CONTRIBUTING.md << 'EOF'
# Contributing Guide

Panduan ini wajib dibaca setiap anggota tim sebelum mengirim kode ke repository.

## 🧰 Tentang Proyek

- **Nama proyek:** TW FOOD
- **Deskripsi singkat:** Website dan aplikasi mobile pemesanan produk plant-based dengan akun, keranjang, dan pembayaran
- **Stack/teknologi:** Laravel, Bootstrap 5, MySQL, Git & GitHub
- **Branch utama:** `main` (selalu stabil, tidak boleh di-push langsung)

## 📌 Branch Convention

Format: `<type>/<nomor-tiket-opsional>-<deskripsi-singkat>`

| Type | Kegunaan | Contoh |
|------|----------|--------|
| `feature/` | Fitur baru | `feature/123-user-login` |
| `fix/` | Perbaikan bug | `fix/cart-total` |
| `hotfix/` | Perbaikan darurat di production | `hotfix/payment-down` |
| `refactor/` | Merapikan kode tanpa mengubah fungsi | `refactor/order-service` |
| `docs/` | Dokumentasi | `docs/api-reference` |
| `test/` | Penambahan atau perbaikan test | `test/checkout-flow` |
| `chore/` | Maintenance | `chore/update-deps` |

**Aturan:**
- Huruf kecil semua
- Gunakan tanda hubung (`-`), bukan spasi atau underscore
- Sertakan nomor tiket bila ada
- Maksimal 50 karakter

**Contoh benar dan salah:**

| ✅ Benar | ❌ Salah | Alasan |
|---------|---------|--------|
| `feature/201-product-search` | `Fitur Pencarian` | Tidak ada type, huruf besar, ada spasi |
| `fix/cart-total` | `fix_cart_total` | Memakai underscore |
| `docs/api-reference` | `perbaikan-baru` | Tidak ada type dan tidak jelas isinya |

## 📝 Commit Convention

Format: `<type>(<scope>): <description>`

**Type:** `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `revert`

**Contoh benar:**

```text
feat(auth): add JWT refresh token
fix(cart): correct total when discount applied
docs(readme): update installation steps
```

**Contoh salah:**

| ❌ Salah | Masalah | ✅ Perbaikan |
|---------|---------|-------------|
| `wip` | Tidak menjelaskan apa pun | `feat(cart): add quantity input` |
| `Fix bug.` | Tanpa scope, huruf besar, diakhiri titik | `fix(login): handle empty password` |
| `Update README` | Tanpa type | `docs(readme): update installation steps` |
| `feat(auth): added login` | Bukan imperative mood | `feat(auth): add login` |

**Aturan:**
- Subject huruf kecil, imperative mood ("add", bukan "added"), tanpa titik di akhir
- Maksimal 50 karakter untuk subject
- Body dipisah satu baris kosong dari subject
- Referensi issue di bagian akhir, misalnya `Closes #123`
- Satu commit = satu perubahan logis (commit atomik)

## 🔀 Pull Request

- Judul PR mengikuti format commit message
- Ukuran PR sebaiknya kurang dari 400 baris perubahan
- Wajib 1 approval dari reviewer
- Wajib lolos CI bila tersedia
- Gunakan **Squash Merge**
- Isi deskripsi PR: apa yang diubah, kenapa, dan cara mengujinya

**Contoh judul PR:**
- ✅ `feat(order): add checkout page`
- ❌ `update kode`

## 👀 Code Review

Awali komentar dengan label berikut:

| Label | Arti |
|-------|------|
| `blocking:` | Harus diperbaiki sebelum merge |
| `nit:` | Saran kecil, opsional |
| `question:` | Butuh klarifikasi |
| `praise:` | Apresiasi untuk kode yang bagus |

**Contoh:**
- `blocking: password belum di-hash sebelum disimpan`
- `nit: nama variabel $d sebaiknya $discount`

## ⚙️ Workflow

1. `git checkout main && git pull origin main`
2. `git checkout -b feature/xxx`
3. Kerjakan fitur, commit secara atomik
4. `git push -u origin feature/xxx`
5. Buat Pull Request di GitHub
6. Tunggu review dan CI
7. Squash merge setelah disetujui
8. Hapus branch yang sudah di-merge

## 🚫 Yang Dilarang

- Push langsung ke `main`
- Commit message tidak jelas (`wip`, `test`, `asdf`)
- Commit file `.env`, `node_modules/`, `vendor/`, atau credentials
- Rebase branch yang sudah di-push dan dipakai orang lain
EOF