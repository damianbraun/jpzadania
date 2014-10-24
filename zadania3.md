[Zadania](http://wbzyl.inf.ug.edu.pl/sp/labs03)

1\. Wyświetl plik /etc/passwd z podziałem na strony przyjmując, że strona na 5 linii tekstu. (raczej more niż less)
```sh
more -5 /etc/passwd
```

2\. Korzystając z polecenia cat utwórz plik tekst3.txt, który będzie składał się z zawartości pliku tekst1.txt, ciągu znaków podanego ze standardowego wejścia (klawiatury) i pliku tekst2.txt.
```sh
cat tekst1.txt - tekst2.txt > tekst3.txt
```

3\. Wyświetl po 5 pierwszych linii wszystkich plików w swoim katalogu domowym w taki sposób, aby nie były wyświetlane ich nazwy.
```sh
head -n 5 -q ~/* 2&> /dev/null
```

4\. Wyświetl linie o numerach 3, 4 i 5 z pliku /etc/passwd.

5\. Wyświetl linie o numerach 7, 6 i 5 od końca pliku /etc/passwd.

6\. Wyświetl zawartość pliku /etc/passwd w jednej linii.

7\. Za pomocą filtru tr wykonaj modyfikację pliku plik.txt, polegającą na wypisaniu każdego słowa w osobnej linii.

8\. Zlicz wszystkie pliki znajdujące się w katalogu /var i jego podkatalogach.

9\. Napisać polecenie zliczające ilość znaków z pierwszych trzech linii pliku /etc/passwd.
