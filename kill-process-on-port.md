# Jak zjistit a ukončit proces na určitém portu

## Metoda 1: Použití `lsof` (doporučeno)

### Zjistit, co běží na portu
```bash
lsof -i :5000
```

Tento příkaz zobrazí všechny procesy používající port 5000. Výstup bude vypadat například takto:
```
COMMAND   PID   USER   FD   TYPE DEVICE SIZE/OFF NODE NAME
python   1234  user   3u  IPv4  12345      0t0  TCP *:5000 (LISTEN)
```

### Ukončit proces
```bash
kill 1234
```

Nebo pokud proces neodpovídá:
```bash
kill -9 1234
```

### Kombinace v jednom příkazu
```bash
kill $(lsof -t -i :5000)
```

Pokud chcete vynutit ukončení:
```bash
kill -9 $(lsof -t -i :5000)
```

## Metoda 2: Použití `netstat`

### Zjistit PID procesu
```bash
netstat -tulpn | grep :5000
```

Výstup:
```
tcp   0   0  0.0.0.0:5000   0.0.0.0:*   LISTEN   1234/python
```

### Ukončit proces
```bash
kill 1234
```

## Metoda 3: Použití `ss` (moderní náhrada netstat)

### Zjistit proces na portu
```bash
ss -tulpn | grep :5000
```

### Ukončit proces
```bash
kill [PID_z_výstupu]
```

## Metoda 4: Použití `fuser`

### Zjistit a ukončit proces v jednom kroku
```bash
fuser -k 5000/tcp
```

Tento příkaz automaticky ukončí všechny procesy používající port 5000.

## Skripty pro automatizaci

### Skript pro bezpečné ukončení
```bash
#!/bin/bash
PORT=$1
if [ -z "$PORT" ]; then
    echo "Použití: $0 <port>"
    exit 1
fi

PID=$(lsof -t -i :$PORT)
if [ -z "$PID" ]; then
    echo "Žádný proces na portu $PORT"
else
    echo "Ukončuji proces $PID na portu $PORT"
    kill $PID
    sleep 2
    if kill -0 $PID 2>/dev/null; then
        echo "Proces stále běží, vynucuji ukončení"
        kill -9 $PID
    fi
fi
```

### Použití skriptu
```bash
chmod +x kill-port.sh
./kill-port.sh 5000
```

## Užitečné tipy

- **kill** - normální ukončení (SIGTERM)
- **kill -9** - vynucené ukončení (SIGKILL)
- Vždy zkuste nejdříve normální ukončení
- `lsof` je nejspolehlivější metoda
- `fuser -k` je nejrychlejší pro přímé ukončení

## Příklad pro port 5000
```bash
# Zjistit co běží na portu 5000
lsof -i :5000

# Ukončit proces
kill $(lsof -t -i :5000)

# Nebo vynutit ukončení
kill -9 $(lsof -t -i :5000)
```