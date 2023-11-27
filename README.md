# Képgaléria React-tal

Projekt létrehozása:
npx create-react-app appneve
cd appneve
dockerben: npm run start&   //nem dockerben: npm start

## JSX

A JSX egy „syntax extension”, amellyel  HTML-szerűen írhatunk  a JavaScriptünkbe. Rendereléskor a React JS kóddá alakítja. NEM HTML! 
A JS kódot mindig {} közé tesszük

## Komponens

A React legfontosabb építőegysége a komponens. A Reacttal épített appokban gyakorlatilag minden komponensekből áll. 

A komponens a UI egy önálló, újrafelhasználható darabja, amely egy jól körülírt feladatot lát el. A komponensek egymástól független, önmagukban megálló kóddarabok. 

A komponensek  függvények, melyeknek a return értéke egy React elem. 
A komponensek egymásba ágyazhatóak

## Props

Props-ok segítségével küldhetünk adatokat egyik komponensből a másikba. Jellemzően a komponensek attribútumaként adjuk át.

A szülőkomponens ad át adatot a gyerekkomponensnek.

Egy  komponens sosem módosíthatja a saját props-át!

## Elemek listázása és az array.map metódus

Rendezzük tömbbe az adatainkat, majd járjuk be a tömböt a map metódussal és térjünk vissza a metóduson belül egy React elemmel.  Figyeljünk arra, hogy a tömb.map( () => { return() }) metódus js kód, tehát { } közé kell tenni! 
Minden egyes elemnek saját egyedi azonosító key attribútummal kell rendelkeznie! Ezért adjuk hozzá a key attribútumot is a komponenshez! Kulcsként használhatjuk a tömb indexeit. A kulcsoknak csak testvérelemek között kell egyedinek lenniük, nem pedig globálisan.  A React azért gyors, mert mindig csak azt a komponenst frissíti, amelyik megváltozott, ezért kell az egyedi azonosító.



## Adatok átadása a szülőkomponensnek - Eseménykezelők

A React alaplogikája az, hogy a megjelenés és a működési logika szorosan tartozzon össze, ezért az eseményeket nem utólag akasztjuk az egyes elemekre, hanem inline eseménykezelőket használunk. A handler metódus neve kapcsos zárójelben áll, és nincs mögötte zárójel!

Most már tudjuk, hogy a szülőelem a props-on keresztül tud paramétereket átadni a gyereknek. De hogy tudja a gyerek tudatni a szülővel a saját állapotát? 
Ugyancsak a props-on keresztül, mégpedig oly módon, hogy a szülőelem a props-ban átadja a saját függvényét, melyet a gyerekelemben meghívhatunk. 


## State

Minden komponensnek lehet egy saját állapota, melyet a state reprezentál. A state állapotértékeinek megváltoztatásával automatikusan újragenerálódik a komponens. 
Függvénykomponensek esetén ehhez az úgynevezett useState hook-ot használjuk. Használatához be kell importálni aa React useState metódusát. 
import React, { useState } from 'react';

A szintaxis a következő:
const [stateValtozo, setStateValtozotkezeloFuggveny] = useState("kezdoertek");
A fenti sor jelentése a következő: 
A stateValtozó tetszőleges változónév lehet. Ha erre a változóra hivatkozunk valahol a programban, akkor az az érték automatikusan frissül az oldalon, ha a program futása során változik az értéke. 
A setStateValtozotkezeloFuggveny  az a függvény, aminek a feladata, hogy megváltoztassa a hozzárendelt state változó értékét. Csak ekkor fog frissülni az oldalon az adat, ha a változó értékét ezen keresztül változtatjuk. 
useState("kezdoertek") – ezzel párosítottuk össze a változót a függvénnyel és megadtuk neki a kezdőértéket. 


