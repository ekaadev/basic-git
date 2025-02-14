# Git

## Workflow Git

3 Stage git
- Modified: (menambah, mengedit, menghapus) namun belum disimpan permanen ke repository
- Staged: menandai modified file untuk disimpan secara permanen ke repository
- Commited: sudah disimpan di repository

3 Section git
- Working Directory, modifikasi file dilakukan pada state ini
- Staging Area, section dimana file sudah disiapkan untuk disimpan secara permanen
- Repository, tempat dimana semua file dan riwayatnya disimpan

## Diagram Three tree
1. Working
```bash
git add {file name}
```
2. Staging
```bash
git commit -m {message commit}
```
3. Repository

## Snapshot
Snapshoot, kumpulan perubahan yang terjadi di semua file yang kita commit
Snapshoot akan menghasilkan hash

## HEAD
HEAD, pointer menuju paling akhir atau snapshot yang paling akhir

## Commit Log
Log / History dapat digunakan untuk mentracking riwayat file yang telah diubah/ditambahkan/dihapus
Untuk melihat commit log dapat menggunakan peritah:
```bash
git log
```
Untuk melihat commit log dalam satu line
```bash
git log --oneline
```
Untuk melihat commit log dalam bentuk graph
```bash
git log --oneline --graph
```
Untuk melihat commit log yang dilakukan dengan detail
```bash
git show {hash}
```

## Compare Commit
Jika ingin membandingkan hasil commit dapat menggunakan perintah:
```bash
git diff {hash1} {hash2}
```
Jika ingin membandingkan hasil commit dengan style tool yang digunakan dapat menggunakan menggunakan perintah:
### Requirement
1. Set configuration in your git ```git config --global diftool```
```bash
git difftool {hash1} {hash2}
```

## Ignore File
Jika tidak mengingkan file tertentu untuk masuk ke repository dapat menggunakan fitur ignore.

## Blame
Jika ingin tahu yang melalakukan penambahan atau melakukan perubahan dengan nama commitnya dapat menggunakan fitur blame

Untuk menggunakan fitur blame dapat menggunakan perintah:
```bash
git blame {file name}
```

## Alias
Dengan alias, dapat digunakan untuk menambahkan perintah lain

```bash
git config --global alias.{alias name} {command git}
```

Ignore dapat membuat file dengan nama ```.gitignore```

## In Working Directory

### Canceling Adding File 
Jika ingin membatalkan penambahan file di working stage dapat menggunakan command:
```bash
git clean -f
```

### Canceling Updating or Removing File
Jika ingin membatalkan perubahan atau penghapusan file di working stage dapat menggunakan command:
```bash
git restore {file name}
```

## In Staging Index

### Canceling from Staging Index
Jika ingin membatalkan penambahan file di staging index dengan mengembalikan ke working directory dapat menggunakan command
```bash
git restore --staged {file name}
```

## In Commit

### Reset Commit
Tidak ada cara untuk mengembalikan perubahan yang telah dicommit tetapi dapat menggunakan ```git reset```, mekanisme riset commit sebetulnya hanya menggeser HEAD ke hash lainnya.
Terdapat 3 mode dalam reset
1. --soft, memindahkan HEAD pointer, namun tidak melakukan perubahan apapun di staging index dan working directory
2. --mixed, memindahkan HEAD pointer, mengubah staging index menjadi sama seperti repository, namun tidak mengubah apapun di working directory
3. --hard, memindahkan HEAD pointer, dan mengubah staging index dan working directory sehingga sama dengan repository

Untuk melakukan reset commit dapat menggunakan perintah:
```bash
git reset <mode> hash
```

### Amend Commit
Jika ingin menjadikan satu commit dapat menggunakan amend commit

Untuk melakukan ammend commit dapat menggunakan perintah:
```bash
git commit --amend
```

### Melihat versi sebelumnya
Untuk melihat versi sebelumnya dapat menggunakan perintah:

```bash
git checkout {hash} -- {file name}
```

### Kembali ke snapshot sebelumnya
Untuk kembali ke snapshot sebelumnya, dapat menggunakan perintah:
```bash
git checkout {hash}
```
Untuk kembali ke paling awal, dapat menggunakan perintah:
```bash
git checkout {branch name}
```

### Membatalkan commit yang telah dilakukan
Untuk membatalkan commit yang sudah dilakukan dapat menggunakan perintah:
```bash
git revert {hash}
```
