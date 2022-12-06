# Pobo Page Builder tvorba vlastních widgetů

Tento repozitář slouží především pro klienty doplňku Pobo Page Builder, kteří si
chtějí upravovat vzhled svých widgetů. 

## Než začneme...

Ještě předtím než začneme je potřeba mít na svém počítači nainstalované tyto nástroje:  

1. Verzovací systém [git](https://git-scm.com/)
2. [nodejs](https://nodejs.org/en/) (min. >=10.19)
3. [npm](https://www.npmjs.com/) (min. >=6) nebo [Yarn](https://yarnpkg.com/)

## Stažení repozitáře

1. Stáhněte si tento repozitář příkazem: 

```
git clone git@github.com:pobo-builder/widget-asset.git
```

Následně nainstalujeme závislosti příkazem: 
```
npm install
```
Pokud používáte yarn:
```
yarn install
```

# Adresářová struktura

Po instalaci závislostí v adresáři uvidíme následující strukturu:

``` 
├── README.md
├── dist
├── node_modules
├── package-lock.json
├── package.json
└── src
    └── *.scss
```

Nás zajímají hlavně:  

1. Adresář `dist/*` obsahuje JS a CSS, které se kompilují z adresáře `src/*`
2. V adresáři `src/*` se nacházejí zdrojové SCSS soubory jednotlivých Pobo widgetů
3. V Souboru `package.json`, v sekci `scripts` se nacházejí následující příkazy, které můžeme použít:
   1. `watch` (spouštíme příkazem `npm run watch`) sleduje veškeré soubory v adresáři `src/*` a při jejich změně k dojde ke kompilaci do `dist/*`
   2. `build` (příkaz `npm run build`) provede kompilaci souborů `src/*` do `dist/*`, odstraní sourcemaps a zminifikuje kód
   3. `proxy` (`npm run proxy`) vytvoří tunel (proxy) z `localhost:8088` na veřejnou URL (vysvětleno dále) 


## Píšeme první widget

Nyní začneme s kódováním našeho prvního widgetu. Vytvoříme si vlastní SCSS soubor v adresáři `src/*` který výstižně pojmenujeme.
Následně spustíme příkaz `npm run watch` který se postará o sledování změn v SCSS souborech a zkompiluje je. Zároveň můžeme otevřít
adresu http://localhost:8088/ kde změny vidíme ihned. 

V souboru `index.html` k widgetu vytvoříme i HTML a můžeme tak při úpravách SCSS souborů sledovat jak bude náš widget ve finále vypadat.