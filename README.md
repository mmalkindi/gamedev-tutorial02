# Tutorial 2 - Introduction to Game Engine

## Latihan: Playtest

> Q: Apa saja pesan log yang dicetak pada panel Output?

A: Pesan "Platform initialized" dicetak ketika playtest dimulai

> Q: Coba gerakkan landasan ke batas area bawah, lalu gerakkan kembali ke atas hingga hampir menyentuh batas atas.
> Apa saja pesan log yang dicetak pada panel Output?

A: Pesan "Reached objective!" dicetak ketika roket menyentuh batas atas jendela playtest

> Q: Buka scene MainLevel dengan tampilan workspace 2D.
> Apakah lokasi scene ObjectiveArea memiliki kaitan dengan pesan log yang dicetak pada panel Output pada percobaan sebelumnya?

A: Iya, ObjectiveArea menjadi *trigger* yang mendeteksi dan mencetak pesan log ketika roket menyentuhnya

## Latihan: Memanipulasi Node dan Scene

> Q: Scene `BlueShip` dan `StonePlatform` sama-sama memiliki sebuah child node bertipe Sprite.
> Apa fungsi dari node bertipe Sprite?

A: Menampilkan tekstur 2D untuk parent node

> Q: Root node dari scene `BlueShip` dan `StonePlatform` menggunakan tipe yang berbeda.
> `BlueShip` menggunakan tipe `RigidBody2D`, sedangkan `StonePlatform` menggunakan tipe `StaticBody2D`.
> Apa perbedaan dari masing-masing tipe node?

A: `RigidBody2D` memanfaatkan *physics simulation* untuk bergerak (gravity, impulses, dll),
sedangkan `StaticBody2D` tidak dapat digerakkan oleh sumber eksternal (gravity, impulses, dll) sehingga perlu kode manual

> Q: Ubah nilai atribut `Mass` pada tipe `RigidBody2D` secara bebas di scene `BlueShip`,
> lalu coba jalankan scene `MainLevel`. Apa yang terjadi?

A: Kecepatan jatuh `BlueShip` tidak dipengaruhi oleh atribut `Mass`

> Q: Ubah nilai atribut `Disabled` pada tipe `CollisionShape2D` di scene `StonePlatform`,
> lalu coba jalankan scene `MainLevel`. Apa yang terjadi?

A: `BlueShip` tidak dapat mendarat di platform karena properti *physics*nya dimatikan

> Q: Pada scene `MainLevel`, coba manipulasi atribut `Position`, `Rotation`, dan `Scale` milik node `BlueShip` secara bebas.
> Apa yang terjadi pada visualisasi `BlueShip` di `Viewport`?

A: Perubahan atribut `Position` dan `Rotation` akan terlihat di playtest,
namun atribut `Scale` akan direset ke *default* (1) selama playtest

> Q: Pada scene `MainLevel`, perhatikan nilai atribut `Position` node `PlatformBlue`, `StonePlatform`, dan `StonePlatform2`.
> Mengapa nilai `Position` node `StonePlatform` dan `StonePlatform2` tidak sesuai dengan posisinya di dalam scene (menurut Inspector)
> namun visualisasinya berada di posisi yang tepat?

A: Karena nilai atribut `Position` di `StonePlatform` dan `StonePlatform` menggambarkan posisi *relative* terhadap posisi parent mereka (`PlatformBlue`)
