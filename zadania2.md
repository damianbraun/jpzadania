[Zadania](http://wbzyl.inf.ug.edu.pl/sp/labs02)

1\. Wyświetl na ekran 2 pierwsze wiersze pliku program.c. (head)
```sh
$ head --lines=2 program.c 
// Program wczytujący zmienną i drukujący ją
#include <stdio.h>
```

2\. Wyświetl na ekran 4 ostatnie wiersze pliku program.c. (head, tail)
```sh
$ tail --lines=2 program.c 
    return 0;
}
```

3\. W pliku program.c znajdź wszystkie wiersze z wystąpieniem słowa „main”. (grep)
```sh
$ grep main program.c 
main()
```

4\. Plikowi program.c nadaj następujące uprawnienia: właściciel – czytanie, pisanie, grupa – czytanie, pozostali użytkownicy: brak uprawnień. (chmod)
```sh
chmod 640 program.c 
```

5\. Będąc w katalogu temp przenieś katalog wazne-sprawy do katalogu praca.
```sh
mv dom/wazne-sprawy/ praca/
```

6\. Zarchiwizuj cały katalog temp. (zip i tar)
```sh
tar -cf archiwum.tar temp/
zip -r archiwum.zip temp/
```

7\. Usuń katalog temp.
```sh
rm -r temp
```

8\. Odtwórz z archiwum katalog temp. (unzip i tar)


9\. Posprzątaj na swoim koncie.
