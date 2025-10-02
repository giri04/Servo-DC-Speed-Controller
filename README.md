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

**Intinya:**
Servo standar tidak punya perintah kecepatan langsung.
Kecepatan dikendalikan secara tidak langsung dengan cara:
Mengatur besar langkah posisi per update.
Mengatur interval waktu antar update.

**Peran PWM pada Servo Standar**
Input PWM biasanya periode 20 ms (50 Hz).
Lebar pulsa:
1.0 ms → posisi minimum (mis. 0°)
1.5 ms → posisi tengah (mis. 90°)
2.0 ms → posisi maksimum (mis. 180°)
PWM ini tidak mengatur kecepatan langsung, melainkan hanya target posisi.

**Servo DC konvensional (hobby servo / RC servo):**
-Input kontrol berupa sinyal PWM dengan lebar pulsa (pulse width) tertentu (misalnya 1–2 ms dengan periode 20 ms).
-Sinyal PWM pada servo bukan untuk mengatur kecepatan langsung, melainkan untuk menentukan posisi sudut poros servo.
-Servo jenis ini memiliki kontrol internal (closed-loop): ada motor DC kecil di dalamnya, gearbox, serta potensiometer untuk feedback posisi.
-Jadi kalau PWM diubah cepat-berubah → poros servo akan bergerak cepat ke target; kalau perubahan posisi target kecil → pergerakan servo lebih lambat.
👉 Kesimpulan: kecepatan hanya bisa dikontrol tidak langsung, melalui laju perubahan setpoint posisi.
