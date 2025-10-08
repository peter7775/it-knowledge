# tr

Program **tr** čte data ze standardního vstupu, transformuje je dle zadání a posílá na standardní výstup. Díky přesměrování vstupů a výstupů (které jsme si již dříve vysvětlovali) nám umožní snadno zpracovávat soubory. Zde několik ukázek. První změní velikost písmen v souboru:

`$ tr "[:lower:]" "[:upper:]" < /etc/resolv.conf`

Můžeme třeba zaměnit znak „e“ za „o“:

`$ cat /etc/resolv.conf | tr "e" "o"`

Můžete také například chtít naformátovat ošklivý nepřehledný soubor tak, že mezery nahradíme tabelátory. Vstup vypadá takto:

`$ cat osklivy_soubor`
1. 2,13 8,3 OK
2. 0,00 1,3 ERROR
3. 2,16 5,5 OK

Hezčí výstup:

`$ cat osklivy_soubor | tr " " "\t"`
1.      2,13    8,3     OK
2.      2.      0,00    1,3     ERROR
3.      2,16    5,5     OK

Pokud se naopak chceme zbavit nějakého znaku, použijte parametr  -d:

`$ cat osklivy_soubor | tr -d ","`

Praktičtější asi bude ukázka nahrazení desetinné čárky tečkou:

`$ cat osklivy_soubor | tr "," "."`
