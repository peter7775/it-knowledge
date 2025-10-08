# Referenční příručka přepínačů Pacman

Kompletní přehled nejpoužívanějších přepínačů správce balíčků Pacman pro Manjaro Linux.

## Hlavní operace

| Přepínač | Dlouhý tvar | Popis |
|----------|-------------|-------|
| `-S` | `--sync` | Synchronizace/instalace balíčků z repozitářů |
| `-Q` | `--query` | Dotazování na nainstalované balíčky |
| `-R` | `--remove` | Odstraňování balíčků ze systému |
| `-U` | `--upgrade` | Upgrade/instalace lokálních balíčků |
| `-F` | `--files` | Dotazování na soubory v databázi |

## Nejpoužívanější přepínače pro `-S` (instalace)

| Přepínač | Dlouhý tvar | Popis |
|----------|-------------|-------|
| `-y` | `--refresh` | Aktualizace databáze balíčků (-yy vynutí stažení) |
| `-u` | `--sysupgrade` | Aktualizace všech balíčků (-uu povolí downgrade) |
| `-s` | `--search` | Vyhledávání balíčků v repozitářích |
| `-i` | `--info` | Zobrazení informací o balíčku |
| `-c` | `--clean` | Čištění cache (-cc pro úplné vyčištění) |
| `-w` | `--downloadonly` | Pouze stažení bez instalace |
| `--needed` | | Nepřeinstalovat aktuální balíčky |
| `--noconfirm` | | Bez dotazů na potvrzení |

## Nejpoužívanější přepínače pro `-Q` (dotazy)

| Přepínač | Dlouhý tvar | Popis |
|----------|-------------|-------|
| `-s` | `--search` | Vyhledávání v nainstalovaných balíčcích |
| `-i` | `--info` | Informace o balíčku (-ii včetně zálohovacích souborů) |
| `-l` | `--list` | Seznam souborů v balíčku |
| `-o` | `--owns` | Zjištění, který balíček obsahuje soubor |
| `-e` | `--explicit` | Seznam explicitně instalovaných balíčků |
| `-d` | `--deps` | Seznam balíčků instalovaných jako závislosti |
| `-t` | `--unrequired` | Seznam nepotřebných balíčků (sirotci) |
| `-m` | `--foreign` | Seznam balíčků z AUR nebo jiných zdrojů |
| `-u` | `--upgrades` | Seznam aktualizovatelných balíčků |

## Nejpoužívanější přepínače pro `-R` (odstraňování)

| Přepínač | Dlouhý tvar | Popis |
|----------|-------------|-------|
| `-s` | `--recursive` | Odstranění včetně nepotřebných závislostí |
| `-c` | `--cascade` | Odstranění včetně všech závislých balíčků |
| `-n` | `--nosave` | Neukládat konfigurační soubory (.pacsave) |
| `-u` | `--unneeded` | Odstranění pouze nepotřebných závislostí |

## Univerzální přepínače

| Přepínač | Dlouhý tvar | Popis |
|----------|-------------|-------|
| `-v` | `--verbose` | Podrobný výstup |
| `-q` | `--quiet` | Tichý režim s minimálním výstupem |
| `--noconfirm` | | Bez dotazů na potvrzení |
| `--debug` | | Ladící informace |
| `-p` | `--print` | Pouze výpis bez provedení operace |

## Nejčastější kombinace příkazů

| Příkaz | Popis |
|--------|-------|
| `pacman -Syu` | Aktualizace systému (refresh + sysupgrade) |
| `pacman -Ss <hledaný_text>` | Vyhledání balíčku v repozitářích |
| `pacman -Qs <hledaný_text>` | Vyhledání v nainstalovaných balíčcích |
| `pacman -Qo <soubor>` | Zjištění vlastníka souboru |
| `pacman -Rs <balíček>` | Odstranění balíčku s nevyužívanými závislostmi |
| `pacman -Qtdq` | Seznam sirotčích balíčků |
| `pacman -Qdt` | Zobrazení sirotčích balíčků s podrobnostmi |
| `pacman -Si <balíček>` | Informace o balíčku z repozitáře |
| `pacman -Qi <balíček>` | Informace o nainstalovaném balíčku |
| `pacman -Ql <balíček>` | Seznam souborů v nainstalovaném balíčku |

## Praktické příklady použití

### Instalace a aktualizace
```bash
# Aktualizace systému
pacman -Syu

# Instalace balíčku
pacman -S firefox

# Instalace více balíčků najednou
pacman -S firefox vlc gimp

# Instalace bez potvrzení
pacman -S --noconfirm firefox

# Pouze stažení balíčku
pacman -Sw firefox
```

### Vyhledávání
```bash
# Vyhledání v repozitářích
pacman -Ss firefox

# Vyhledání v nainstalovaných balíčcích
pacman -Qs firefox

# Zjištění vlastníka souboru
pacman -Qo /usr/bin/firefox
```

### Odstraňování
```bash
# Odstranění balíčku
pacman -R firefox

# Odstranění s nepotřebnými závislostmi
pacman -Rs firefox

# Odstranění sirotčích balíčků
pacman -Rs $(pacman -Qtdq)
```

### Informace o balíčcích
```bash
# Informace o nainstalovaném balíčku
pacman -Qi firefox

# Seznam souborů v balíčku
pacman -Ql firefox

# Seznam explicitně instalovaných balíčků
pacman -Qe

# Seznam balíčků z AUR
pacman -Qm
```

## Tipy a triky

- **Kombinujte přepínače**: např. `pacman -Syu` pro úplnou aktualizaci
- **Používejte `-v` pro podrobnosti**: pomáhá při ladění problémů
- **Pravidelně čistěte cache**: `pacman -Sc` nebo `pacman -Scc`
- **Kontrolujte sirotčí balíčky**: `pacman -Qtd`
- **Zálohujte seznam balíčků**: `pacman -Qe > packages.txt`

---
*Vygenerováno pro Manjaro Linux - $(date)*
