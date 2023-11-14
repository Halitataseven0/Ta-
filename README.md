import random

def rastgele_secim():
    secenekler = ["taş", "kağıt", "makas"]
    return random.choice(secenekler)

def oyunu_oyna(kullanici_secimi):
    bilgisayar_secimi = rastgele_secim()

    print("Senin seçimin: " + kullanici_secimi)
    print("Bilgisayarın seçimi: " + bilgisayar_secimi)

    if kullanici_secimi == bilgisayar_secimi:
        return "Berabere! Tekrar dene."
    elif (
        (kullanici_secimi == "taş" and bilgisayar_secimi == "makas") or
        (kullanici_secimi == "kağıt" and bilgisayar_secimi == "taş") or
        (kullanici_secimi == "makas" and bilgisayar_secimi == "kağıt")
    ):
        return "Tebrikler! Kazandın."
    else:
        return "Maalesef kaybettin. Daha şanslı olabilirsin."

while True:
    kullanici_secimi = input("Taş, kağıt veya makas? (Çıkmak için 'q' tuşuna basın): ").lower()

    if kullanici_secimi == 'q':
        print("Oyundan çıkılıyor. İyi günler!")
        break

    if kullanici_secimi in ["taş", "kağıt", "makas"]:
        sonuc = oyunu_oyna(kullanici_secimi)
        print(sonuc)
    else:
        print("Geçersiz bir seçim yaptınız. Lütfen 'taş', 'kağıt' veya 'makas' seçin.")
