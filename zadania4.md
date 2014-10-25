[Zadania](http://wbzyl.inf.ug.edu.pl/sp/labs04)

1\. Wyświetl listę plików z aktualnego katalogu, zamieniając wszystkie małe litery na duże.
```sh
$ find . -maxdepth 1 -type f -printf "%f \n" | tr "[:lower:]" "[:upper:]"
.ZSH-UPDATE
.ESD_AUTH
.ZSH_HISTORY
.ZCOMPDUMP-LOCALHOST-5.0.6
NOTATKA.TXT
.BASHRC
LISTA.TXT
.VIMINFO
.BASH_HISTORY
.BASH_PROFILE
```

2\. Wyświetl listę praw dostępu do plików w aktualnym katalogu, ich rozmiar i nazwę.
```sh
$ ls -l --human-readable| grep ^- | awk '{print $1, $5, $8}'
-rwxrwxr-x. 1,2K fedy-installer*
-rw-rw-r--. 518 lista.txt
-rw-rw-r--. 169 notatka.txt
```

3\. Wyświetl listę plików w aktualnym katalogu, posortowaną według rozmiaru pliku.
```sh
$ ls -lS | grep ^- | awk '{print $8}'
fedy-installer*
lista.txt
notatka.txt
```

4\. Wyświetl zawartość pliku /etc/passwd posortowaną według numerów UID w kolejności od największego do najmniejszego.
```sh
$ sort -n -t ':' -k3 /etc/passwd
```

5\. Wyświetl zawartość pliku /etc/passwd posortowaną najpierw według numerów GID w kolejności od największego do najmniejszego, a następnie UID.
```sh
$ sort -nr -t ':' -k4 /etc/passwd; echo; sort -nr -t ':' -k3 /etc/passwd
```

6\. Podaj liczbę plików każdego użytkownika.

7\. Sporządź statystykę praw dostępu (dla każdego z praw dostępu podaj ile razy zostało ono przydzielone).

8\. Czy potrafisz odpowiedzieć jaki będzie efekt wykonania poniższych poleceń?
```sh
ls -l > lsout.txt                           #  1 - zapisze(nadpisując) w pliku lsout.txt liste plików i katalogów
ls -la >> lsout.txt                         #  2 - dopisze do pliku lsout.txt liste plików i katalogów
ps >> psout.txt                             #  3 - dopisze do pliku psout.txt listę aktywnych procesów
free -m >> ~/wynik                          #  4
kill -1 1234 > killout.txt 2>killerr.txt    #  5
kill -1 1234 > killout.txt 2>&1             #  6
kill -1 1234 > /dev/null 2>&1               #  7
sort psout.txt > pssort.txt                 #  8
ps | sort > pssort.txt                      #  9
cat lsout.txt | sort > lssort.txt           # 10
who | sort | more                           # 11
who | sort | less                           # 12
find -type f | wc                           # 13
find -type f -print0 | wc --files0-from=-   # 14
```

A co wypisze na standardowym wyjściu to polecenie:

tr -sc 'A-Za-z' '\n' < idiota.txt \
  | sort \
  | uniq -c \
  | sort -k1,1 -rn

Użyty w powyższym poleceniu plik idiota.txt zawiera tekst powieści Fiodora Dostojewskiego „Idiota”. Plik pobrałem z serwisu Gutenberg.

9\. Załóżmy, że w pliku .bashrc mamy zdefiniowane następujące dwie zmienne go_libs, go_flags oraz alias go_c:

go_libs="-lm"
go_flags="-g -Wall -include stdio.h"
alias go_c="c99 -xc '-' $go_libs $go_flags"

Czy potrafisz wyjaśnić jaki będzie wynik wykonania poniższego polecenia na terminalu:

go_c << '---'
int main(){ printf("hello world from the command line.\n"); }
---

(Przykład z książki Bena Klemensa „21st Century C”.)
