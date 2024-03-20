GIT BRANCH
1.Poin-Poin Utama:
A. Apa itu Git Branch
Branch adalah cabang, nah Branch ini digunakan untuk bekerja pada fitur baru atau memperbaiki bug tanpa
mengubah kode yang ada di cabang utama proyek (biasanya disebut sebagai &quot;master&quot; atau &quot;main&quot;). Dengan
menggunakan branch, Anda dapat mengisolasi perubahan yang Anda buat sehingga tidak memengaruhi kode yang
sudah ada atau pekerjaan yang sedang dilakukan oleh anggota tim lainnya. Setiap cabang dalam Git memiliki
riwayat perubahan yang terpisah, yang memungkinkan Anda untuk mengembangkan fitur atau memperbaiki bug
secara independen. Anda dapat membuat cabang baru, berganti cabang, menggabungkan perubahan dari
satu cabang ke cabang lainnya, dan menghapus cabang yang tidak lagi diperlukan.

B. Code Git Branch
1.) Menggunakan perintah &quot;git branch namabranch&quot; untuk membuat branch baru, dan gunakan perintah &quot;git branch&quot;
untuk melihat ada berapa branch yang anda punya. Saat menggunakan perintah tersebut secara default seharusnya
anda berada di dalam branch master/main ditandai dengan tanda bintang.

    2.) Dengan mengunakan perintah &quot;git switch namabranch&quot; atau &quot;git checkout namabranch&quot; anda berarti
    berpindah dari branch utama ke branch lain, Anda bisa mengecek apakah anda ada di dalam branch tersebut
    atau tidak dengan menggunakan perintah &quot;git branch --show-current&quot;.

    3.) Jika ada kesalahan dalam penulisan nama branch, anda juga bisa mengubah nama branch dengan syarat anda
    harus berada didalam branch yang ingin anda ubah namanya, dengan menggunakan perintah
    &quot;git branch -m namabranchbaru&quot;.

    4.) Jika anda dapat menghapus branch dengan menuliskan perintah &quot;git branch --delete namabranch&quot;
    namun syaratnya anda harus kembali ke branch utama terlebih dahulu.

C. Merging
Adalah proses dimana anda menyatukan branch lain dengan branch lain, baik branch utama dengan branch lainnya.
Menggabungkan dua branch atau lebih artinya menarik kode program dari fitur a ke fitur utama, dan branch yang
digabungkan tidak akan dihapus, dan anda tetap bisa melakukan commit di branch yang sudah di merge.

    1.) Anda bisa menggabungkan branch lain dengan branch utama atau branch lain, namun ada syarat untuk
    melakukan penggabungan branch lain dengan branch lainnya. Syaratnya adalah anda harus berada didalam
    branch yang dimana akan dilakukan merge ,Contohnya anda kembali ke branch master/main dengan menggunakan
    perintah &quot;git branch feature/1&quot; artinya anda menarik semua perubahan yanga ada di feature/1 ke branch master.

    2.) Setelah dilakukan merge anda dapat melihat apakah merging antara branch master dengan feature/1
    dengan menggunakan perintah &quot;git log --oneline --graph&quot;.

    3.) Cara menyelesaikan merge konflik harus dengan cara manual, dengan mengubahnya di text editor secara
    personal

D. Cherry Pick
1.) Digunakan untuk meng-commit satu atau beberapa perubahan tertentu dari satu cabang ke cabang lain
tanpa harus menggabungkan seluruh riwayat commit.

E. Tag
1.) Merupakan fitur untuk menandai sebuah commit, Tag biasanya digunakan untuk penanda versi rilis sebuah
aplikasi.
2.) Gunakan perintah &quot;git tag --list&quot; untuk menampilkan ada berapa banyak Tag yang anda punya.
3.) Anda juga bisa menggunakan Tag sebagai reference untuk berpindah ke ke snapshot sebelumnya tanpa harus
menggunakan commited, jadi cukup gunakan perintah &quot;git checkout namatag&quot;.
4.) Tag tidak bisa diubah, jadi jika ingin mengubah Tag anda bisa membuat Tag baru lalu menghapus tag
yang lama, dan perintah untuk menghapus tag &quot;git tag --delete namatag&quot;.

F. Stash
Stash adalah tempat dimana anda bisa menyimpan perubahan sementara di Working Directory atau Staging Index.
Sehingga anda bisa berpindah ke branch yang lain.

    1.) Untuk menyimpan perubahan ke Stash anda bisa menggunakan perintah &quot;git stash push -m 'massage example'&quot;.
    2.) Lalu untuk melihat semua Stash yang anda punya cukup gunakan perintah &quot;git stash list&quot;
    3. Dan untuk melihat perubahan yang terjadi pada Stash bisa gunakan perintah &quot;git stash show stashld&quot;.
    4.) Nah jika anda ingin mengambil perubahan pada Stash bisa gunakan perintah &quot;git stash apply stashld&quot;.
    5.) Dan jika anda ingin menghapus Stash bisa menggunakan perintah &quot;git stash drop stashld&quot;, atau jika
    anda ingin menghapus semua Stash yang ada bisa menggunakan perintah &quot;git stash clear&quot;.

G. Rebase
Melakukan &quot;rebase&quot; di Git melibatkan pemindahan ke branch tempat Anda ingin menerapkan perubahan,
tidak seperti merging di mana Anda tetap berada di cabang saat ini. Rebase melibatkan penulisan ulang
riwayat commit, membuatnya tampak seolah-olah perubahan dibuat langsung pada branch saat ini.

    1.) Untuk melakukan rebase, gunakan perintah &quot;git rebase &quot;, di mana adalah nama branch yang berisi perubahan
    yang akan diterapkan. Squashing commits di Git melibatkan penggabungan beberapa commit menjadi satu
    commit untuk riwayat yang lebih bersih.
    2.) Squashing commits dapat dilakukan selama operasi rebase dengan menggunakan perintah &quot;git rebase -i&quot;
    dan memilih opsi &quot;squash&quot; untuk commit yang diinginkan. Squashing commits membuat riwayat commit menjadi
    lebih ringkas, tetapi dapat mengakibatkan hilangnyapesan dan referensi commit individual.
    Git branching memungkinkan penggabungan beberapa commit menjadi satu dengan menggunakan perintah &quot;squash.
    3.) Rebase akan terlihat lebih rapih dibandingkan Marge kerena dia menulis ulang semua commit yang
    dilakukan. Dan commit id atau hash pasti berubah.

H. Trunk Based Development
Trunk Based Development menyederhanakan branching dengan hanya satu branch utama, dengan fokus pada
pengiriman fitur yang cepat langsung ke produksi setelah pengujian. Dalam TBD, setiap fitur, perbaikan bug,
atau perubahan kode lainnya dimulai dari cabang utama dan diintegrasikan kembali ke dalamnya sesegera
mungkin setelah selesai.

I. Forking Workflow
Forking Workflow adalah hal yang umum dalam project open source, di mana kontributor menduplikasi
repositori utama, membuat perubahan dalam fork mereka, dan kemudian meminta perubahan tersebut untuk
digabungkan ke dalam proyek utama (Pull Request). Forking Workflow memungkinkan kolaborasi sambil
mempertahankan kontrol atas repositori utama dan memastikan perubahan ditinjau sebelum integrasi.

2.Pertanyaan dan Catatan Tambahan

a.Apakah penggunaan Rebase lebih baik daripada merge

3.Kesimpulan

Secara keseluruhan, Pemahaman penggunaan Seperti Gitflow, Trunk Based Development, dan Forking Workflow memberikan fleksibilitas kepada pengembang dalam mengelola kontrol versi dan kolaborasi. Git Merge adalah alat penting<br>
dalam manajemen versi dan pengembangan perangkat lunak yang memungkinkan pengembang untuk mengintegrasikan<br>
perubahan kode dari berbagai cabang ke dalam cabang utama proyek secara efisien.</p>
