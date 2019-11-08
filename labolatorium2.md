# Zadania

## Labolatorium 2
 
 1. Wyświetl na ekran 2 pierwsze wiersze pliku program.c. (head)
 
 less nauka/c/program.c | head -n 2
 
 2. Wyświetl na ekran 4 ostatnie wiersze pliku program.c. (head, tail)

 less nauka/c/program.c | tail -n 4
 
 3. W pliku program.c znajdź wszystkie wiersze z wystąpieniem słowa „main”. (grep)
 
 grep -i -n "main" nauka/c/program.c
 
 4. Plikowi program.c nadaj następujące uprawnienia: właściciel – czytanie, pisanie, grupa – czytanie, pozostali użytkownicy: brak uprawnień. (chmod)
 
chmod 640 nauka/c/program.c

5. Będąc w katalogu temp przenieś katalog wazne-sprawy do katalogu praca.

mv -rf dom/wazne-sprawy praca/wazne-sprawy

6. Zarchiwizuj cały katalog temp. (zip i tar)

zip -r temp.zip temp
tar zcf temp.tar.gz temp

7. Usuń katalog temp.

rm -rf temp

8. Odtwórz z archiwum katalog temp. (unzip i tar)

unzip temp.zip
tar -zxf temp.tar.gz

9. Posprzątaj na swoim koncie.

rm -rf temp temp.tar temp.zip LUB rm -rf tem*

## Labolatorium 3

1. Wyświetl plik /etc/passwd z podziałem na strony przyjmując, że strona na 5 linii tekstu. (raczej more niż less)

more -5 /etc/passwd

2. Korzystając z polecenia cat utwórz plik tekst3.txt, który będzie składał się z zawartości pliku tekst1.txt, ciągu znaków podanego ze standardowego wejścia (klawiatury) i pliku tekst2.txt.

touch tekst1.txt
touch tekst2.txt
cat tekst1.txt tekst2.txt > tekst3.txt

3. Wyświetl po 5 pierwszych linii wszystkich plików w swoim katalogu domowym w taki sposób, aby nie były wyświetlane ich nazwy.



4. Wyświetl linie o numerach 3, 4 i 5 z pliku /etc/passwd.

sed -n '3,5p' /ect/passwd

5. Wyświetl linie o numerach 7, 6 i 5 od końca pliku /etc/passwd.

tail -n 7 /ect/passwd | head -n 1
tail -n 6 /etc/passwd | head -n 1
tail -n 5 /etc/passwd | head -n 1

6. Wyświetl zawartość pliku /etc/passwd w jednej linii.

cat /etc/passwd | tr "\n" " "

7. Za pomocą filtru tr wykonaj modyfikację pliku plik.txt, polegającą na wypisaniu każdego słowa w osobnej linii.

cat /etc/passwd | tr " " "\n"

8. Zlicz wszystkie pliki znajdujące się w katalogu /var i jego podkatalogach.

ls -l /var | wc -l

9. Napisać polecenie zliczające ilość znaków z pierwszych trzech linii pliku /etc/passwd.

cat /etc/passwd | head -n3 | wc -c

## Labolatorium 5

1. Znajdź w swoim katalogu domowym (bez podkatalogów) wszystkie pliki, które zostały zmodyfikowane w ciągu ostatnich dziesięciu dni i wyświetl ich nazwy.

find ~/ -maxdepth 1 -mtime -10 -type f

2. Znajdź wszystkie pliki zwykłe w systemie, które mają w nazwie ciąg znaków „conf” i wyświetl ich nazwy na ekranie.

find /etc -name \*config\* -type f 2> /dev/null

3. Znajdź w swoim katalogu domowym wszystkie pliki, które nie były używane w ciągu ostatnich 20 dni.

find ~/ -atime 20

4. Znajdź w katalogu /etc wszystkie niepuste podkatalogi i pliki o nazwach zaczynających się na literę „a”.

find /etc \( -type f -and -name a* \) -or \( -type d -and ! -empty \) 2> /dev/null
