# cut

Při výběru sloupce nám může také posloužit program cut. Hodí se v případě, že si nedokážete zapamatovat komplexní syntaxi awk. Jeho použití je snadné:

`$ cut -d : -f 1,7 /etc/passwd`

Když známe pevně danou pozici sloupečku, můžeme použít parametr  -c:

`$  uptime`
 4:33PM  up 44 days, 11:26, 1 user, load averages: 0.00, 0.01, 0.00

`$  uptime | cut -c 10-19,28-34`
up 44 days 1 user

Podobná věc, kterou bash umí a není tak často používaná, jsou substringy. Spousta lidí je řeší právě pomocí awk a cut. Ale zkuste si toto:

```
$ text="muj pokusny text"
$ echo ${text:4:7}
pokusny
```

Teď už praktičtější ukázky, vrátíme se k souboru /etc/passwd. Když nás bude zajímat třeba jen četnost jednotlivých shellů:

`$ cut -d : -f 7 /etc/passwd | sort | uniq -c`

Dostaneme podobný výsledek:

   1 /bin/sh
  20 /usr/sbin/nologin
   9 /usr/local/bin/bash

Pokud je výpis dlouhý a chceme jej třeba sestupně setřídit, stačí doplnit:

`$ cut -d : -f 7 /etc/passwd | sort | uniq -c | sort -rn`

  20 /usr/sbin/nologin
   9 /usr/local/bin/bash
   1 /bin/sh

Zajímá-li vás, které příkazy spouštíte nejčastěji:

`$ history | awk '{print $2}' | sort | uniq -c | sort -rn | head`
