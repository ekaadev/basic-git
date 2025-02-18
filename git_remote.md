# Git Remote

## Git Server Repository
Git server dapat dibuat menggunakan beberapa platform  salah satunya yaitu github.

Cara membuat repository di github:
1. Buka [github](https://github.com/)
2. Login atau buat akun baru
3. Tekan tombol new repository
4. Isi data data repository

## SSH (Secure Socket Shell)
SSH, protokol jaringan yang memudahkan pertukaran data dengan aman melalui internet.

### SSH Key
Untuk generate SSH key, dapat menggunakan perintah:
```bash
ssh-keygen
```

Setelah menjalankan perintah akan muncul 2 file yaitu:
1. id_rsa (private key)
2. id_rsa.pub (public key)

## Remote Repository
Remote repository berguna agar dapat terhubung dengan server repository.

Terdapat beberapa cara untuk menambahkan remote repository yang sudah dibuat:
1. Masuk ke repository lokal
2. Gunakan perintah:
```bash
git remote add {remote name / origin(default)} {url repository}
```

### Show List Remote Repository
Untuk melihat list remote repository, dapat menggunakan perintah:
```bash
git remote
```

### Show Detail Remote Repository
Untuk mengetahui remote repository menuju kemana dapat ditambahkan dengan perintah:
```bash
git remote get-url {remote name}
```

### Delete Remote Repository
Untuk menghapus remote repository, dapat menggunakan perintah:
```bash
git remote rm {remote name}
```

## Push
Jika ingin mengirim perubahan yang terdapat di local repositroy, ada perlunya untuk mengirimkan juga secara manual ke remote repository.

### Push Branch / Push to Remote Repository
Untuk mengirim perubahan ke remote repository, dapat menggunakan perintah:
```bash
git push {remote name} {branch name}
```
atau jika ingin mengirim ke branch yang berbeda, dapat menggunakan perintah:
```bash
git push {remote name} {branch name}:{remote branch name}
```

### Push All Branch
Untuk mengirim ke semua branch, dapat menggunakan perintah:
```bash
git push {remote name} --all
```

### Delete Branch Remote Repository
Untuk menghapus branch di remote repository, dapat menggunakan perintah:
```bash
git push --delete {remote name} {branch name}
```

## Clone
Clone aadalah fitur yang digunakan untuk mengunduh project yang sudah ada di remote repository

### Clone Remote Repository
Untuk mengunduh project yang sudah ada di remote repository, dapat menggunakan perintah:
```bash
git clone {url repository}
```

### Show List Branch Remote Repository
Untuk melihat semua branch di remote repostory, dapat menggunakan perintah:
```bash
git branch -r
```

atau jika ingin melihat semua branch, dapat menggunakan pertintah:
```bash
git branch -a
```

### Create Branch from Remote Repository
Untuk membuat branch dari remote repository, dapat menggunakan perintah:
```bash
git checkout -b {local branch name} {remote name}/{remote branch name}
```

## Fetch
Fetch adalah fitur yang digunakan untuk mendapatkan perubaahan terakhir dari remote repository.

### Fetch Remote Repository
Untuk melakukan fetching dari remote repository, dapat menggunakan perintah:
```bash
git fetch {remote name}
```
atau jika ingin melihat di branch tertentu, dapat mengggunakan perintah:
```bash
git fetch {remote name} {branch name}
```

note: Perubahan pada fitur a hanya masuk ke local repository tapi tidak menimpa branch yang sedang digunakan. Sederhananya update data.

## Pull
Pull akan melakukan 2 aktivitas sekaligus yaitu fetching data dan di simpan ke dalam branch yang sedang digunakan.

### Pull Remote Repository
Untuk melakukan pull dari remote repository, dapat menggunakan perintah:
```bash
git pull {remote origin} {branch name}
```

## Tag
Jika ingin mengirim tag ke remote repository, dapat menggunakan perintah:
```bash
git push {remote name} --tags
```
note: untuk mengambil semua data tag dari remote repository, dapat menggunakan perintah ```git fetch {remote name}```

Untuk menghapus tag di remote repository, dapat menggunakan perintah:
```bash
git push --delete {remote name} :refs/tags/{tag name}
```

## Pull Request
Platform git server mendukung fitur pull request, fitur ini digunakan untuk meminta pemilik repository untuk menggabungkan perubahan yang sudah dilakukan.

## Merge Conflict
Ketika terjadi konflik saat melakukan merge, kita harus memperbaiki konflik tersaebut terlebih dahulu.

### Solve Merge Conflict - Manual
Untuk memperbaiki konflik di local repository, dapat menggunakan perintah:
```bash
git merge {remote name}/{remote branch name}
```

## Submodule
Submodule adalah fitur yang digunakan untuk menghubungkan repository yang satu dengan repository yang lain.

### Add Submodule
Untuk menambahkan submodule, dapat menggunakan perintah:
```bash
git submodule add {url repository} {folder name}
```

note: submodule hanya boleh digunakan untuk duplikasi repository yang sudah ada jika ada perubahan dari misal librarynya, maka pull dari branch utama jangan di submodulenya karena otomatis akan terupdate.

### Update Submodule
Untuk update submodule, dapat menggunakan perintah:
```bash
git submodule update --remote
```

### Initialize Submodule
Untuk memberitahu adanya perubahan pada submodule, dapat menggunakan perintah:
```bash
git submodule init
```

### Set Branch SUbmodule
Untuk mengubah branch pada submodule, dapat menggunakan perintah:
```bash
git submodule set-branch {branch name} {folder name}
```

### Delete Submodule
Untuk menghapus submodule, dapat menggunakan perintah:
- Hapus folder submodule & hapus .gitmodules

## Fork
Beberapa platform git server seperti github mendukung adanya forking repository, fitur ini digunakan untuk membuat salinan repository yang sudah ada.