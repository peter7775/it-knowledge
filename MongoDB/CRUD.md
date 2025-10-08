## Create

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

## Read

// Najít všechny dokumenty
db.uzivatele.find()

// Najít s podmínkou
db.uzivatele.find({vek: {$gt: 25}})

// Najít jeden dokument
db.uzivatele.findOne({jmeno: "Petr"})

// Limitovat výsledky
db.uzivatele.find().limit(5)

## Update
// Aktualizovat jeden dokument
db.uzivatele.updateOne(
  {jmeno: "Petr"},
  {$set: {vek: 31}}
)

// Aktualizovat více dokumentů
db.uzivatele.updateMany(
  {vek: {$lt: 30}},
  {$set: {kategorie: "mladý"}}
)

## Delete

// Smazat jeden dokument
db.uzivatele.deleteOne({jmeno: "Petr"})

// Smazat více dokumentů
db.uzivatele.deleteMany({vek: {$lt: 25}})

## Indexes

// Vytvořit index
db.uzivatele.createIndex({email: 1})

// Zobrazit indexy
db.uzivatele.getIndexes()

// Smazat index
db.uzivatele.dropIndex({email: 1})

## Agregation

// Základní agregace
db.uzivatele.aggregate([
  {\$match: {vek: {\$gte: 25}}},
  {\$group: {_id: "\$kategorie", pocet: {\$sum: 1}}}
])

