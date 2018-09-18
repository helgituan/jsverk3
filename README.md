# jsverk3JavaScript
Verkefni 3. Prototype (6%)

1. Útskýrðu Prototype kerfið í JavaScript. Hver er munurinn á því t.d. og ObjectOriented
forritun (OOP) í öðrum málum eins og Python? (1%)

Í JavaScript þegar þú býrð til objecta með function constructor þá færðu instance , constructor og prototype en Python t.d. færðu bara instance og constructor


2. Útskýrðu eins vel og þú getur hvað gerist í kóðanum(1%)
a. Þegar prototype er sleppt

  Það breytist ekki neitt nema ef ég geri Book.prototype.getIsbn = 1234; þá kemur undir Book.prototype getIsbn: 1234

b. Hvað gerir prototype í Book.prototype.getIsbn

    það er eins og það sé falið þangað tilæ ég gerir Book.prototype.getIsbn = eitthvað;
```javascript
function Book(isbn) {
 this.isbn = isbn;
}
// Book.prototype.getIsbn
Book.getIsbn = function () {
 return "Isbn is " + this.isbn;
};

```

3. Classical Model (function constructor and prototype) (2%)
a) Búðu til þrjár geimflauga objecta með function smið sem hafa
mismunandi heiti. Geimflaugarnar eiga einnig að hafa eigindin speed og
life með upphafsgildinu 10.
Spaceship-name generator:
http://www.fantasynamegenerators.com/spaceshipnames.php#.WnQsPqhl-M8
```javascript
function Spaceship(name, health = 10 ,speed = 10){
  this.name = name;
  this.health = health;
  this.speed = speed;
}
let Eminem = new Spaceship("Eminem" , 15 , 15)
let MGK = new Spaceship("MGK", 1 , 7)
let Drake = new Spaceship("Drake" , 3 , 1)
```
b) Gefðu geimflaugunum mismunandi speed gildi.
Eminem.speed = 123;

c) Notaðu Prototype til að bæta við nýrri method fly sem hækkar gildið
speed um 1. Þetta fá allar flaugarnar.
```javascript
Spaceship.prototype.fly = function () {
  this.speed += 1;
};
Eminem.fly();
```
d) Búðu til undirhóp flauga (2 flaugar) af einni geimflauginni sem þú bjóst til
að ofan. Gefðu þessum flaugum einhver eigindi og gildi. Þessar flaugar
eiga að auki að hafa aðferðina setLife() sem hækkar life um 1.
```javascript
function WarSpaceship(name , health = 10 , speed = 10){
  Spaceship.call(this, name , health , speed);
};
let Lilwayne = new WarSpaceship("Lilwayne")

WarSpaceship.prototype.setLife = function (){
  this.health += 1;
}
```

4. Gerðu það sama og í lið 3 en með notkun class (ES2015). Notaðu constructor,
get, set, static, extends, super, mix-ins eftir þörfum. (2%)
Námsmat og skil.

Skilaðu github slóð með lausnum á Innu.
Gefið er full fyrir rétt og fullnægjandi lausn eða svar, hálft ef lausn eða svar er ábótavant.
