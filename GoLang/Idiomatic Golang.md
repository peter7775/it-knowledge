## Základní principy idiomatického Go

Idiomatický Go staví na **explicitnosti** závislostí, využívání **kompozice** místo dědičnosti a důrazu na **jednoduchost** před složitostí. Cílem je psát čitelný, předvídatelný kód, který je snadné udržovat i spravovat v týmech.[^3][^1]

- Závislosti se injektují přes konstruktory, neglobální proměnné.
- Chyby se vždy řeší — ignorování je považováno za anti-pattern.
- Používají se malé, cílené interface, nikoliv velké “god” interface.
- Kontext (např. context.Context) se předává jako první parametr funkcí, nikdy se neukládá do struktury.[^1]


## Struktura projektu a styl

- Oddělujte obchodní logiku do samostatných balíčků, main pouze jako vstupní bod aplikace.[^2]
- Striktně používejte `go fmt` pro automatické formátování zdrojového kódu.[^2]
- Důležité je konzistentní pojmenovávání: krátká, výstižná jména (např. `err`, `ctx`, `pkg` místo dlouhých nebo neobvyklých názvů).[^3]
- Preallocace slice s kapacitou místo dynamického zvětšování optimalizuje výkon.[^1]


## Práce s chybami

- Chyby se kontrolují pomocí konstrukcí typu `errors.Is/As` nebo `if err != nil`.[^4][^2][^1]
- Pokud potřebujete více informací, chybu "wrapujte" třeba přes `fmt.Errorf("%w", err)`, nikdy neporovnávejte jen hodnotu chyby.
- Chybu nikdy neignorujte — vždy ji zpracujte, případně snižte dopad nebo ji propusťte výše.[^4]


## Konkurence a synchronizace

- Moderní idiom je používání balíčku `errgroup` pro správu gorutin, protože umožňuje snadné rušení a zpracování chyb napříč gorutinami.
- Klasický `sync.WaitGroup` se hodí pouze pro synchronizaci bez pokročilého error handlingu nebo cancelování.[^1]


## Defer, rozhraní, struktury

- `defer` je typicky použit pro uzavírání souborů, zámků, uvolnění prostředků.[^2]
- Rozhraní jsou malé, definované spotřebitelem, nikoli dodavatelem knihoven.[^2][^1]
- Struktury jsou preferovány před třídami, metody se přidávají podle potřeb API balíčku, místo složité dědičnosti se používá kompozice.[^5][^1]


## Další idiomatické techniky

- Logování se provádí strukturovaně (např. pomocí log/slog), nikoli přes fmt.Printf bez dalšího zpracování.[^1]
- Minimalizace magických hodnot v kódu a jasné vysvětlení algoritmů nebo procesů přímo ve zdroji.
- Dokumentace, testy a komentáře konzistentně dodržují styl typický pro komunitu Go.[^2][^1]


## Doporučené anti-patterny (na co si dát pozor)

| Anti-pattern | Idiomatické řešení | Proč vyhnout? |
| :-- | :-- | :-- |
| Globální proměnné | Závislosti injekovat přes konstruktory [^1] | Skrytá vazba, horší testovatelnost [^1] |
| Ignorování chyb | Vždy validovat a zpracovat | Tiché pády, nesnadné ladění |
| Velké interface | Rozdělit na menší, spotřebitelské | Špatná rozšiřitelnost, tight coupling |
| Dlouhá jména proměnných | Krátká jména, konvence (err, ctx) | Nepřehledné, obtížná údržba |

Idiomatický Go v poslední verzi (Go 1.23+) klade důraz na důsledné uplatňování těchto zásad, které jsou průběžně aktualizovány podle vývoje jazyka i požadavků na cloud, mikroservisy a moderní infrastrukturu.[^5][^3][^1]
<span style="display:none">[^10][^11][^12][^13][^14][^15][^16][^17][^18][^19][^20][^6][^7][^8][^9]</span>

<div style="text-align: center">⁂</div>

[^1]: https://gist.github.com/ashokallu/26445f706d33308b0f243f76618cb687

[^2]: https://englyk.com/book2/Writing_Idiomatic_Go/

[^3]: https://dev.to/jjpinto/the-power-of-idiomatic-go-what-makes-it-different-from-java-and-c-529h

[^4]: https://techkoalainsights.com/5-best-practices-for-writing-idiomatic-go-code-6d153a6c3b09

[^5]: https://www.videosdk.live/developer-hub/websocket/golang-struct

[^6]: https://www.jc-correct.com/blog/nejznamejsi-anglicke-idiomy-se-zviraty-2/

[^7]: https://www.helpforenglish.cz/article/2007041101-czech-english-proverbs

[^8]: https://www.anglictina-olomouc.cz/nejznamejsi-anglicke-idiomy/

[^9]: https://www.ef-czech.cz/pruvodce-anglictinou/anglicke-idiomy/

[^10]: https://www.youtube.com/watch?v=JTjzQdyX1LM

[^11]: https://theses.cz/id/eu5zwg/15801349

[^12]: https://go.dev/doc/effective_go

[^13]: https://www.helpforenglish.cz/article/2017071102-idiom-second-thoughts

[^14]: https://www.calhoun.io/learning-go-in-2025/

[^15]: https://www.reddit.com/r/golang/comments/17kewuv/real_go_projects_that_would_be_considered/

[^16]: https://www.anglictina-bez-biflovani.cz/Files/Pracovni_list_anglicke_idiomy.pdf

[^17]: https://www.reddit.com/r/golang/comments/1mktjem/im_experiencing_a_high_pressure_from_new_go/

[^18]: https://withcodeexample.com/idiomatic-go-writing-mistakes-beginners-should-avoid/

[^19]: https://dspace.cuni.cz/bitstream/handle/20.500.11956/175347/130343706.pdf?sequence=1\&isAllowed=y

[^20]: https://github.com/pthethanh/effective-go

