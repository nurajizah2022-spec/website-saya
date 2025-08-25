import random

# Papan ular dan tangga
# format: {posisi_awal: posisi_tujuan}
ular_tangga = {
    3: 22,   # Tangga
    5: 8,    # Tangga
    11: 26,  # Tangga
    20: 29,  # Tangga
    27: 1,   # Ular
    21: 9,   # Ular
    17: 4,   # Ular
    19: 7    # Ular
}

# Posisi pemain
posisi = 0

print("=== Game Ular Tangga 🎲🐍 ===")
print("Naik ke 30 untuk menang!\n")

while posisi < 30:
    input("Tekan ENTER untuk lempar dadu...")
    dadu = random.randint(1, 6)
    print(f"Kamu dapat angka {dadu}")

    posisi += dadu

    if posisi in ular_tangga:
        if posisi < ular_tangga[posisi]:
            print("🎉 Hore! Naik tangga!")
        else:
            print("😱 Oh tidak! Digigit ular!")
        posisi = ular_tangga[posisi]

    if posisi > 30:
        posisi = 30

    print(f"Posisi kamu sekarang: {posisi}\n")

print("🏆 Selamat! Kamu menang!")
