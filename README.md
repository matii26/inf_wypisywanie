# inf_wypisywanie

plik_wyniki = open("wyniki4_1.txt","w") #w zapisujemy jak pliku nie ma to go tworzymy
#jeżeli jest cos w pliku to wszystko nadpisujemy
#a jezeli cos jest to dopisujemy na koncu
literki = "wakacje"
plik_wyniki2 = open("wyniki4_2.txt","w")
with open("slowa.txt", "r") as dane:
    # domyslnie r czyli plik do odczytu
    for wiersz in dane:
        wiersz = wiersz.strip()
        if wiersz.count("w") == wiersz.count("k"):
            plik_wyniki.write(wiersz+"\n")
            ile_wystapien =[]
            for literka in literki:

                ile_wystapien.append(wiersz.count(literka))
            minimum = min(ile_wystapien)
            if minimum >= wiersz.count("a"):
                plik_wyniki2.write(str(minimum))
            else:
                plik_wyniki.write(str(wiersz.count("a")//2)+"\n")


plik_wyniki.close()
plik_wyniki2.close()

print("Podaj słowo")

slowo = input("")
szukane = "wakacje"

doskreslenia = 0
#k szukane
k = 0
for litera in slowo:
    if litera != szukane[k]:
        doskreslenia +=1
    else:
        k = k + 1
    if k == len(szukane):
         k=0
        
print(doskreslenia)
#https://cke.gov.pl/images/_EGZAMIN_MATURALNY_OD_2015/Arkusze_egzaminacyjne/2023/Informatyka/EINP-R2-100-2305.pdf
#zadanie4.3
