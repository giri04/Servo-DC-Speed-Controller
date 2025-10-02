# Servo-DC-Speed-Controller
1.Servo standar (positional servo) → PWM mengatur posisi, kecepatan hanya bisa diatur tidak langsung.
2.Continuous rotation servo → PWM bisa mengatur kecepatan dan arah.
3.Motor DC biasa (non-servo) → PWM langsung mengontrol kecepatan.

Teknis bagaimana kecepatan servo standar (positional servo) bisa diatur secara tidak langsung melalui PWM:
**Bagaimana Mengatur Kecepatan (Tidak Langsung)**
**Step Besar (target jauh)**
Misal dari 0° langsung diperintah ke 180°.
Servo akan berusaha bergerak secepat mungkin sampai posisi tercapai → kecepatan maksimum internal.
**Step Kecil Bertahap (target dekat-dekat)**
Misal dari 0° → 10° → 20° → … → 180°, dengan jeda waktu tertentu.
Karena target hanya bergeser sedikit tiap langkah, servo bergerak lebih lambat.
**Kontrol Timing (delay)**
Waktu antar perintah PWM (delay antar update) menentukan seberapa cepat servo berpindah.
Semakin rapat perintah posisi → gerakan lebih cepat.
Semakin jarang update posisi → gerakan lebih lambat.
