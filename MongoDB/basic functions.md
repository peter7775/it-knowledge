# Instalace (Manjaro/Arch)
sudo pacman -S mongodb-bin

# Spuštění služby
sudo systemctl start mongodb
sudo systemctl enable mongodb

# Připojení k databázi
mongosh

# Zobrazit databáze
show dbs

# Vybrat/vytvořit databázi
use mojeDatabaze

# Zobrazit aktuální databázi
db

# Smazat databázi
db.dropDatabase()

# Zobrazit kolekce
show collections

# Vytvořit kolekci
db.createCollection("uzivatele")

# Smazat kolekci
db.uzivatele.drop()

// Vložit jeden dokument
db.uzivatele.insertOne({
  jmeno: "Petr",
  vek: 30,
  email: "petr@example.com"
})

// Vložit více dokumentů
db.uzivatele.insertMany([
  {jmeno: "Anna", vek: 25},
  {jmeno: "Pavel", vek: 35}
])

