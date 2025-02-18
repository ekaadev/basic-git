# Git Branching

## When is branching used?
Branching digunakan ketika membuat fitur baru atau memperbaiki bug.

### Show Current Branch
Untuk menampilkan branching yang saat ini, dapat menggunakan perintah:
```bash
git branch --show-current
```

### Create new Branch
Untuk branch baru, dapat menggunakan perintah:
```bash
git branch {branch name}
```

### Show All Branch
Untuk menampilkan semua branch saat ini, dapat menggunakan perintah:
```bash
git branch
```

### Move Another Branch
Untuk berpindah branch dari branch yang saat ini digunakan, dapat menggunakan perintah:
```bash
git checkout {branch name}
```

### Rename Branch
Untuk mengubah nama branch dari branch yang saat ini digunakan, dapat menggunakan perintah:
```bash
git branch -M {new branch name}
```

### Delete Branch
Untuk menghapus branch yang ada, dapat menggunakan perintah:
```bash
git branch -d {branch name}
```

## Merge Branch
Merge adalah sebuah proses yang melakukan penggabungan dua buah branch. Studi kasusnya jika ingin menggabungkan fitur a dengan fitur b.

### How to Merge Branch
1. Masuk ke branch yang ingin menjadi lokasi merge
2. Gunakan perintah:
```bash
git merge {branch name}
```
3. Untuk menghapus branch yang sudah di merge, dapat menggunakan perintah:
```bash
git branch -d {branch name}
```

### Merge Conflict - Pembatalan Merge
Untuk membatalkan merge yang ingin dilakukan, dapat menggunakan perintah:
```bash
git merge --abort
```

Jika ingin menyelesaikan conflict saat merging, dapat dilakukan secara manual dengan mengedit file yang conflict. Setelah solving masalah conflict akan membuat commit baru.

### Cherry Pick
Jika ingin melakukan merge commit tertentu, dapat menggunakan perintah:
```bash
git cherry-pick {hash}
```

## Tag
HEAD adalah pointer yang menunjuk ke commit terakhir di branch yang sedang digunakan. Namun untuk Tag adalah pointer yang menunjuk ke commit tertentu.

Untuk membuat tag, dapat menggunakan perintah:
```bash
git tag {tag name} {commit ID or hash}
```

Note: Tag is unique

Untuk melihat tag yang sudah dibuat, dapat menggunakan perintah:
```bash
git tag -l
```

Untuk menghapus tag, dapat menggunakan perintah:
```bash
git tag -d {tag name}
```

## Stash
Stash adalah tempat penyimpanan sementara perubahan yang belum di commit. Stash digunakan ketika ingin berpindah branch atau melakukan perubahan yang lain.

Untuk menggunakan stash, dapat menggunakan perintah:
```bash
git stash push -m {message stash}
```

Untuk melihat semua stash, dapat menggunakan perintah:
```bash
git stash list
```

Untuk melihat stash secara detail, dapat menggunakan perintah:
```bash
git stash show {stash ID}
```

Untuk mengambil stash, dapat menggunakan perintah:
```bash
git stash apply {stash ID}
```

Untuk meghapus semua stash, dapat menggunakan perintah:
```bash
git stash clear
```

atau jika ingin menghapus stash tertentu, dapat menggunakan perintah:
```bash
git stash drop {stash ID}
```

## Rebase
Rebase teknik penggabungan branch dengan menjadikan branch yang akan di rebase sebagai branch utama dan commit yang akan di rebase sebagai commit terakhit. Sederhananya, jika merge yang tadinya bercabang akan dijadikan satu tetapi untuk rebase yang tadinya bercabang dijadikan satu history commit dengan branch yang di rebase.

Untuk melakukan rebase, dapat menggunakan perintah:
```bash
git rebase {branch name}
```

Jadi misal ```git rebase main``` artinya branch yang sedang digunakan sekarang akan menjadi commit terakhir atau lebih depan dari branch main secara penggambaran.

Dengan seperti ini branch main akan tetap sama commitnya sampai pada branch main menggunakan command ```git merge {branch name}```, setelah mengeksekusi commmand ini commit branch main akan fast forward ke commit branch yang di merge.

### Rebase secara visual
![rebase](https://github.com/user-attachments/assets/485dac7d-f7b1-4c7d-9499-fdade027f2db)

## Squash
Squash adalah teknik penggabungan commit yang dilakukan dengan menggabungkan beberapa commit menjadi satu commit.

Squash bisa dilakukan ketika ingin merge atau rebase branch yang sudah banyak commit.

Untuk melakukan squash, dapat menggunakan perintah:
```bash
git merge --squash {branch name}
```

## Git Branching Strategy
1. [Gitflow Workflow](https://nvie.com/posts/a-successful-git-branching-model/)
2. [Trunk Based Development Workflow](https://nvie.com/posts/a-successful-git-branching-model/)
3. [Forking Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/forking-workflow)

