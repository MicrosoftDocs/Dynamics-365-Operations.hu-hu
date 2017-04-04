---
title: "Értékcsökkenési könyv frissítése – áttekintés"
description: "A korábbi kiadásokban a tárgyieszköz - értékmodellek és értékcsökkenés könyvek két értékelési fogalmak voltak. A Microsoft Dynamics 365 for Operations 1611-es verziójában az értékmodell funkcióit és az értékcsökkenési könyv funkcióit egyetlen koncepció alapján egyesítették, ennek neve: könyv. Ez a témakör olyan szempontokat ismertet, amelyeket figyelembe kell venni a frissítéshez."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer
ms.search.scope: Operations, Core
ms.custom: 221624
ms.assetid: cf434099-36f9-4b0f-a7c8-bed091e34f39
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: bec019d218d80ba059d5a1c232072f46b1ae3ee2
ms.openlocfilehash: d29cb7bc5acc29be93332b4211adebc4486a7a25
ms.lasthandoff: 03/31/2017


---

# <a name="depreciation-book-upgrade-overview"></a>Értékcsökkenési könyv frissítése – áttekintés

A korábbi kiadásokban a tárgyieszköz - értékmodellek és értékcsökkenés könyvek két értékelési fogalmak voltak. A Microsoft Dynamics 365 for Operations 1611-es verziójában az értékmodell funkcióit és az értékcsökkenési könyv funkcióit egyetlen koncepció alapján egyesítették, ennek neve: könyv. Ez a témakör olyan szempontokat ismertet, amelyeket figyelembe kell venni a frissítéshez. 

A frissítési folyamat áthelyezi a meglévő beállításokat és az összes meglévő tranzakciót az új könyv struktúrájának megfelelően. Az értékmodellek megmaradnak a jelenleg állapotukban, olyan könyvként, amely a főkönyvbe ad fel. Az értékcsökkenési könyvek áthelyezésre kerülnek egy olyan könyvbe, amelynél a **Feladás a főkönyvbe** opció beállítása **Nem**. A főkönyvi napló nevét értékcsökkenéskönyv-naplónevek átkerül a feladási réteg beállítása a **nincs**. Tárgyieszköz-tranzakciók értékcsökkenés könyv tranzakcióinak kerülnek. 

Mielőtt futtatná az adatfrissítést, meg kell ismernie azt a két lehetőséget, amely rendelkezésre áll ahhoz, hogy az értékcsökkenési könyv naplósorait a tranzakciók bizonylataihoz frissítse, és ismernie kell azt a számsorozatot, amelyet a program a bizonylatszám-sorozatokhoz alkalmaz. 

1. módszer:  **Rendszer által meghatározott számsorozat** – Ez az alapértelmezett beállítás a teljesítmény javításához. A frissítés nem fogja használni a számsorozat-keretrendszert, hanem felosztja a bizonylatokat egy készlet alapú megközelítés segítségével. A frissítés után az új számsorozat jön létre a **következő beállítva** megfelelően a frissített tranzakciók alapján. Alapértelmezés szerint használt számsorozatot lesz a FADBUpgr\#\#\#\#\#\#\#\#\# formátumban. Van néhány paraméterek formátumának módosítását, ez a megközelítés használatakor Önnek:

-   **Szám a Számsorozat kódja** – a számsorozat azonosító kódot. A Számsorozat kódja nem létezhet, mert a frissítés készül.
    -   Állandó név: **NumberSequenceDefaultCode**
    -   Alapértelmezett érték: "FADBUpgr"
-   **Előtag** – a bizonylatszámok előtagjaként használt, állandó karakterlánc.
    -   Állandó név: **NumberSequenceDefaultParameterPrefix**
    -   Alapértelmezett érték: "FADBUpgr"
-   **Alfanumerikus hossz** – a számsorozat alfanumerikus szegmensének hossza.
    -   Állandó neve: ** NumberSequenceDefaultParameterAlpanumericLength **
    -   Alapértelmezett érték: 9
-   **Indítási szám** – a számsorozatban alkalmazandó első szám.
    -   Állandó neve: ** NumberSequenceDefaultParameterStartNumber **
    -   Alapértelmezett érték: 1

2. lehetőség: **létező felhasználói számsorozat** -Ez a beállítás lehetővé teszi a frissítés során használandó számsorozat megadása. Érdemes használni ezt a lehetőséget, ha speciális számsorozat-konfigurációt kell. Számsorozat használatához módosítania kell a frissítési osztály ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans a következő információkat:

-   **Számsorozat kódja** – a számsorozatkód kódja.
    -   Állandó neve: ** NumberSequenceExistingCode **
    -   Alapértelmezett érték: nincs alapértelmezés, ezt frissíteni kell a számsorozat kódjának megfelelően.
-   **Közös számsorozat** – a számsorozat hatókörének azonosítására szolgáló logikai érték. Ha a számsorozatok közösek az összes vállalatnál, használja az "igaz" lehetőséget, ha a hatókör egyetlen vállalatra korlátozódik, használja a "hamis" lehetőséget. Használata a "hamis", a megadott néven a számsorozat minden olyan társaság, amely tartalmazza az értékcsökkenés könyv tranzakcióinak léteznie kell. Megosztott Számsorozatok minden értékcsökkenés könyv tranzakcióinak tartalmazó partíció található.
    -   Állandó neve: ** NumberSequenceExistingIsShared **
    -   Alapértelmezett érték: igaz

A paraméterek nem található a ReleaseUpdateDB70 elején\_FixedAssetJournalDepBookRemovalDepBookJournalTrans-osztály. 

*Adja meg a bizonylatot kiosztásának előnyös megközelítést*<ph id="t1">
</ph>*/ / igaz, ha egy meglévő számsorozat kódja használni kívánt*<ph id="t2">
</ph>*/ / hamis kívánja használni, a rendszer által definiált számsorozat (alapértelmezett)* logikai NumberSequenceUseExistingCode konstans = HAMIS;  

*Ha a rendszer által definiált szám sorozat megközelítést használ, adja meg a számsorozat a paraméterek. *<ph id="t3">
</ph>*/ / Új számsorozat a paraméterek jön létre.* Const str NumberSequenceDefaultCode = "FADBUpgr"; Const str NumberSequenceDefaultParameterPrefix = "FADBUpgr"; Const int NumberSequenceDefaultParameterAlpanumericLength = 9. Const int NumberSequenceDefaultParameterStartNumber = 1;   

*Ha a meglévő szám sorozat megközelítést használ, adja meg a meglévő számsorozat kódja. *<ph id="t4">
</ph>*/ / Bizonylat foglalása sorról sorra fel meglévő számsorozatok.* Const str NumberSequenceExistingCode = ''; */ / Adja meg a meglévő számsorozat kódja hatókörét*<ph id="t5">
</ph>*/ / igaz, ha a megadott számsorozat megosztott*<ph id="t6">
</ph>*/ / hamis, ha a megadott számsorozat társaság*<ph id="t7">
</ph>*/ / alapértelmezett rendszer által meghatározott számsorozat lesz, ha nem található a megadott hatókörű számsorozatkód.* állandó logikai NumberSequenceExistingIsShared = hamis; 

Ha a konstansok megváltoztak, újra kell építenie az osztályt tartalmazó projektet. 

Ha a rendszer által generált szám sorozat megközelítés alkalmazásával (1. lehetőség), a frissítés használja készlet alapú feldolgozás lefoglalni a bizonylatszámok szerint megadott frissítési parancsfájl paraméterei. Ennek során létrehozza egy új számsorozat a megadott paraméterekkel a felosztás után. 

Amikor a felhasználó által definiált, meglévő számsorozaton alapuló megközelítést (2. beállítás) használja, az adatfrissítés ellenőrzi, hogy a megadott hatókörű számsorozat létezik-e az adatbázisban minden olyan partíció és vállalat esetében, amelyek értékcsökkenési könyvéhez tranzakciók tartoznak. Ha létezik, akkor a frissítés által használt számsorozat keretrendszerével számsorozatot a bizonylatszámok lefoglalni sorról sorra feldolgozás használja. A számsorozatot nem létezik a megadott hatókörű, ha a frissítés használja az alapértelmezett rendszer által definiált szám sorozat megközelítés a bizonylatszámok lefoglalni, és létrehozza a felosztás után megadott alapértelmezett paraméterekkel rendelkező új számsorozat.

Bármelyik módszert is alkalmazzák, az adatfrissítési parancsfájl a korábbi értékcsökkenési naplónevekhez létrehozott, az új főkönyv-naplóneveknél szereplő **bizonylatsorozatok** mezőjéhez tartozó számsorozatot fogja használni.


