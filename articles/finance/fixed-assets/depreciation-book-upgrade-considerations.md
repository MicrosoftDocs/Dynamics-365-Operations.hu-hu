---
title: Értékcsökkenési könyv frissítésének áttekintése
description: Ez a témakör a Tárgyi eszközök aktuális könyv funkcióját ismerteti. Ez a funkció a korábbi verziókban elérhető értékmodellfunkción alapul, de magában foglal minden olyan funkciót, amelyek korábban csak az értékcsökkenési könyvekben szerepeltek.
author: moaamer
ms.date: 06/20/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User, Developer
ms.reviewer: kfend
ms.custom:
- "221624"
- intro-internal
ms.assetid: cf434099-36f9-4b0f-a7c8-bed091e34f39
ms.search.region: global
ms.author: moaamer
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 784ec32ae886ef7ea9342b085f893eeeec761961
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8855491"
---
# <a name="depreciation-book-upgrade-overview"></a>Értékcsökkenési könyv frissítésének áttekintése

[!include [banner](../includes/banner.md)]

Ez a témakör a Tárgyi eszközök aktuális könyv funkcióját ismerteti. Ez a funkció a korábbi verziókban elérhető értékmodellfunkción alapul, de magában foglal minden olyan funkciót, amelyek korábban csak az értékcsökkenési könyvekben szerepeltek. Az értékmodell funkcióit és az értékcsökkenési könyv funkcióit egyetlen koncepció alapján egyesítették, ennek neve: könyv. A könyv funkcióval egyetlen lap-, lekérdezés- és jelentéskészletet használhat a szervezet összes tárgyieszköz-folyamatában. Ez a cikk néhány olyan témakört tartalmaz, amelyekről a frissítés előtt érdemes megfontolni. 

A frissítési folyamat áthelyezi a meglévő beállításokat és az összes meglévő tranzakciót az új könyv struktúrájának megfelelően. Az értékmodellek megmaradnak a jelenleg állapotukban, olyan könyvként, amely a főkönyvbe ad fel. Az értékcsökkenési könyvek áthelyezésre kerülnek egy olyan könyvbe, amelynél a Feladás a főkönyvbe opció beállítása Nem. Az értékcsökkenési könyvhöz tartozó naplónevek átkerülnek a főkönyvi napló nevéhez, amelynél a feladási réteg beállítása Nincs. Az értékcsökkenési könyv tranzakciói átkerülnek a tárgyieszköz-tranzakciókhoz.

Mielőtt futtatná az adatfrissítést, meg kell ismernie azt a két lehetőséget, amely rendelkezésre áll ahhoz, hogy az értékcsökkenési könyv naplósorait a tranzakciók bizonylataihoz frissítse, és ismernie kell azt a számsorozatot, amelyet a program a bizonylatszám-sorozatokhoz alkalmaz.

1. módszer:  **Rendszer által meghatározott számsorozat** – Ez az alapértelmezett beállítás a teljesítmény javításához. A frissítés nem fogja használni a számsorozat-keretrendszert, hanem felosztja a bizonylatokat egy készlet alapú megközelítés segítségével. A frissítés után úgy jön létre az új számsorozat, hogy a **Következő számkészlet** a frissített tranzakciókon alapul a megfelelő módon. Alapértelmezés szerint az alkalmazott számsorozat a FADBUpgr\#\#\#\#\#\#\#\#\# formátumban lesz. Amikor ezt a módszert alkalmazzák, rendelkezésre áll néhány paraméter a formátum módosítására:

-   **Számsorozat kódja** – a számsorozatot azonosító kód. A számsorozat ezen kódja nem létezhet, mert a frissítés során jön létre.
    -   Állandó név: **NumberSequenceDefaultCode**
    -   Alapértelmezett érték: "FADBUpgr"
-   **Előtag** – a bizonylatszámok előtagjaként használt, állandó karakterlánc.
    -   Állandó név: **NumberSequenceDefaultParameterPrefix**
    -   Alapértelmezett érték: "FADBUpgr"
-   **Alfanumerikus hossz** – a számsorozat alfanumerikus szegmensének hossza.
    -   Állandó neve: **NumberSequenceDefaultParameterAlpanumericLength**
    -   Alapértelmezett érték: 9
-   **Indítási szám** – a számsorozatban alkalmazandó első szám.
    -   Állandó neve: **NumberSequenceDefaultParameterStartNumber**
    -   Alapértelmezett érték: 1

2. lehetőség: **Meglévő, felhasználó által meghatározott számsorozat** - Ez a beállítás lehetővé teszi a frissítéshez használandó számsorozat megadását. Akkor fontolja meg ezt a lehetőséget, ha speciális számsorozat-konfigurációra van szüksége. Számsorozat használatához módosítania kell a ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans frissítési osztályt a következő adatokkal:

-   **Számsorozat kódja** – a számsorozatkód kódja.
    -   Állandó név: **NumberSequenceExistingCode**
    -   Alapértelmezett érték: nincs alapértelmezés, ezt frissíteni kell a számsorozat kódjának megfelelően.
-   **Közös számsorozat** – A számsorozat hatókörének azonosítására szolgáló logikai érték. Ha a számsorozatok közösek az összes vállalatnál, használja az "igaz" lehetőséget, ha a hatókör egyetlen vállalatra korlátozódik, használja a "hamis" lehetőséget. A „hamis” használatakor a megadott nevű számsorozatnak minden olyan vállalatnál léteznie kell, amely tartalmazza az értékcsökkenési könyv tranzakcióit. Megosztott számsorozatok minden olyan partíciónál léteznek, amelyek tartalmazzák az értékcsökkenési könyv tranzakcióit.
    -   Állandó név: **NumberSequenceExistingIsShared**
    -   Alapértelmezett érték: igaz

A paraméterek a ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans osztály elején találhatók. 

*// Adja meg a bizonylatok felosztásának előnyben részesített módszerét* 
 *// igaz, ha egy meglévő számsorozat kódját szeretné használni* 
 *// hamis, ha a rendszer által meghatározott számsorozatot (alapértelmezett) szeretné használni* const boolean NumberSequenceUseExistingCode = false;  

*// Ha a rendszer által definiált számsorozatú megközelítést használja, adja meg a számsorozat paramétereit.*
 *// Új számsorozat jön létre ezekkel a paraméterekkel.* const str NumberSequenceDefaultCode = 'FADBUpgr'; const str NumberSequenceDefaultParameterPrefix = 'FADBUpgr'; const int NumberSequenceDefaultParameterAlpanumericLength = 9; const int NumberSequenceDefaultParameterStartNumber = 1;   

*// Ha a meglévő számsorrenden alapuló megközelítést használja, adja meg a meglévő számsorozat kódját.* 
 *// Meglévő számsorozatok esetében a bizonylatok kiosztása soronként fut le.* const str NumberSequenceExistingCode = ''; *// Adja meg a meglévő számsorozat hatókörét* 
 *// igaz, ha a meghatározott számsorozat meg van osztva* 
 *// hamis, ha a megadott számsorozat egyes vállalatokra vonatkozik* 
 *// A rendszer által definiált számsorozat kerül használatra, ha nem található a megadott hatókörű számsorozatkód.* állandó logikai NumberSequenceExistingIsShared = hamis; 

Ha a konstansok megváltoztak, újra kell építenie az osztályt tartalmazó projektet. 

Ha a rendszer által generált számsorozatú megközelítést (1. beállítás) használja, a frissítés halmazalapú feldolgozást fog alkalmazni a bizonylatok felosztására, a frissítési parancsprogram paramétereiben meghatározottak szerint. A felosztást követően létrehoz egy új számsorozat is a megadott paraméterekkel. 

Amikor a felhasználó által definiált, meglévő számsorozaton alapuló megközelítést (2. beállítás) használja, az adatfrissítés ellenőrzi, hogy a megadott hatókörű számsorozat létezik-e az adatbázisban minden olyan partíció és vállalat esetében, amelyek értékcsökkenési könyvéhez tranzakciók tartoznak. Ha létezik, a frissítés soronkénti feldolgozást használ a számsorozat keretrendszerét alkalmazó számsorozat által meghatározott bizonylatszámok felosztására. Ha a megadott hatókörrel rendelkező számsorozat nem létezik, a frissítés az alapértelmezett, a rendszer által definiált számsorozatú megközelítést fogja alkalmazni a bizonylatszámok felosztásához, és új számsorozatot hoz létre a megadott, alapértelmezett paraméterekkel, a felosztás után.

Bármelyik módszert is alkalmazzák, az adatfrissítési parancsfájl a korábbi értékcsökkenési naplónevekhez létrehozott, az új főkönyv-naplóneveknél szereplő **bizonylatsorozatok** mezőjéhez tartozó számsorozatot fogja használni.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
