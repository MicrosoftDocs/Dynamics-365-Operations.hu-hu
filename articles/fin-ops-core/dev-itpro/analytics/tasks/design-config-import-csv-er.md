---
title: ER-konfigurációk tervezése adatok külső, CSV-fájlokból történő importálásához (ER)
description: A folyamat bemutatja, hogyan lehet az elektronikus jelentési (ER) konfigurációt úgy megtervezni, hogy külső, CSV formátumú fájlból importáljon adatokat a Finance and Operations alkalmazásába.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c8511b83a5d327f6a1d5c9ace091eae9e546307b
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142247"
---
# <a name="design-er-configurations-to-import-data-from-external-csv-files"></a>ER-konfigurációk tervezése adatok külső, CSV-fájlokból történő importálásához (ER)

[!include [banner](../../includes/banner.md)]

A folyamat bemutatja, hogyan lehet az elektronikus jelentési (ER) konfigurációt úgy megtervezni, hogy külső, CSV formátumú fájlból importáljon adatokat. Ebben az eljárásban létrehozzuk a szükséges ER-konfigurációkat a Litware, Inc. mintavállalatra vonatkozóan. A lépések végrehajtásához először a következő eljárás lépéseit kell végrehajtani: „ER – Konfigurációszolgáltató létrehozása, és megjelölés aktívként.” 

Ez az eljárás a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkör rendelkező felhasználók számára készült. A lépések a USMF-adathalmazzal hajthatók végre. 

Emellett le kell töltenie és helyben mentenie kell a következő fájlokat: (https://go.microsoft.com/fwlink/?linkid=862266): 1099model.xml, 1099formatcsv.xml, 1099entriescsv.csv.

1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
    * Konfigurálhat egy folyamatot arra, hogy külső, XML, TXT vagy CSV formátumú fájlokat importáljon az alkalmazás táblázataiba. Először létre kell hoznia egy absztrakt adatmodellt, amely üzleti szempontból képviseli az importált adatokat – ehhez egy ER-adatmodell-konfigurációt kell létrehoznia. Ezután definiálja a tervezett adatmodellre leképező importált fájl szerkezetét úgy, hogy a fájlról adatokat küldjön az absztrakt adatmodellre – ehhez ER-formátumú konfigurációt kell létrehozni. Ezt követően az adatmodell konfigurációját ki kell bővíteni egy új leképezéssel, amely leírja, hogyan használják az importált fájl adatait és az absztrakt adatmodell megmaradó adatait a táblák vagy adatentitások frissítéséhez.  
    * A következő lépések megmutatják, hogyan történik a külsőleg nyomon követett szállítói tranzakciók importálása külső CSV-fájlból a szállítói kiegyenlítések 1099-es űrlapokban történő későbbi felhasználására.   
    * Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és aktívként van megjelölve a konfigurációszolgáltató. Ha nem látja a konfigurációszolgáltatót, először el kell végeznie a „Konfigurációszolgáltató létrehozása, és megjelölés aktívként” eljárásban szereplő lépéseket.  
2. Kattintson a Jelentéskészítés konfigurációi lehetőségre.
3. Alkalmazza az „1099 fizetések modellje” szűrőt. Ha már elvégezte a műveletet, a Kötelező konfigurációk létrehozása külső fájlból történő adatok importálásához az elektronikus jelentéskészítésben és az „1099-es fizetések modellje” konfiguráció elérhető a konfigurációs fán, ugorja át ezeket a lépéseket a következő alfeladathoz.   

## <a name="add-a-new-er-model-configuration"></a>Új ER-modellkonfiguráció hozzáadása
1. Ahelyett, hogy új modellt hozna létre az adatimportálás támogatásához, töltse be a korábban letöltött 1099model.xml fájlt. Ez a fájl tartalmazza az egyéni adatmodellt a szállítók tranzakcióihoz. Ehhez az adatmodellhez már hozzá vannak rendelve a szükséges adatösszetevők.  
2. Kattintson az Átváltás lehetőségre.
3. Kattintson a Betöltés XML-fájlból lehetőségre.
4. Kattintson a Böngészés lehetőségre, és a navigáljon a korábban letöltött 1099model.xml fájlhoz.  
5. Kattintson az OK gombra.

## <a name="add-a-new-er-format-configuration-that-supports-data-import"></a>Az adatok importálását támogató új ER-formátumkonfiguráció hozzáadása
1. A fastruktúrában válassza ki ezt: „1099 fizetések modellje”.
2. A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.
3. Az Új mezőbe írja be az „1099 Fizetések modellen alapuló formátum” kifejezést.
4. A Támogatja az adatimportálást mezőben válassza az Igen lehetőséget.
5. Nyomja le az ESC billentyűt az oldal bezáráshoz.
    * Ahelyett, hogy új ER-formátumot hozna létre az adatimportálás támogatásához, töltse be a korábban letöltött 1099formatcsv.xml fájlt. Ez a fájl tartalmazza a beérkező CSV-fájl szerkezetét definiáló szükséges ER-formátumot, valamint a struktúra hozzárendelését a szállítók tranzakcióinak adatmodelljéhez.   
6. Kattintson az Átváltás lehetőségre.
7. Kattintson a Betöltés XML-fájlból lehetőségre.
    * Kattintson a Böngészés lehetőségre, és a navigáljon a korábban letöltött 1099formatcsv.xml fájlhoz.  
8. Kattintson az OK gombra.
9. A fastruktúrában bontsa ki ezt: „1099 Payments model”
10. A fastruktúrában válassza ki ezt: „1099 Payments model\For importing vendors' transactions (CSV)”.

## <a name="review-format-settings"></a>Formátumbeállítások ellenőrzése
1. Kattintson a Tervező pontra.
2. Kattintson a Csomópont kibontása/összecsukása lehetőségre.
3. Kapcsolja be a Részletek megjelenítése lehetőséget.
    * A tervezett formátum a külső fájl várt struktúráját jelöli CSV formátumban.  
4. A fastruktúrában válassza ki ezt: „Incoming: File\Root: Sequence”.
    * A SOROZAT típusú Gyökérelem esetében a „Különleges karakterek” mezőben az „Új sor – Windows (CR LF)” lehetőség van kiválasztva. Ezen beállítás alapján az elemzési fájl minden sorát külön nyilvántartásnak kell tekinteni.   
5. A fastruktúrában válassza ki ezt: „Incoming: File\Root: Sequence\Line: Sequence 1..* ”.
    * A SOROZAT típusú Gyökér\Sor elem esetében a „Multiplicitás” mezőben ki van választva az „Egy a többhöz” lehetőség. Ezen beállítás alapján legalább egy sor fog szerepelni az elemzési fájlban.   
6. A fastruktúrában válassza ki ezt: „Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case ”.
    * Vegye figyelembe, hogy az ESET típusú Gyökér\Sor\Típus elemet a rendszer a Gyökér\Sor sorozat beágyazott elemeként adta hozzá. Mivel ez az ESET elem három beágyazott sorozatelemet tartalmaz, ez a beállítás azt feltételezi, hogy az elemzési fájlban három különböző típusú sor lesz.   
7. A fastruktúrában válassza ki ezt: „Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case\Header: Sequence 1..1 ”.
    * A SOROZAT típus Gyökér\Sor\TípusokCímsor eleme a beágyazott KARAKTERLÁNC elemet tartalmazza, amelynek az értékét rögzített karakterláncértékként határozta meg. Ez a sorozat az elemzési fájl fejlécét fogja elemezni.   
8. A fastruktúrában válassza ki ezt: „Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case\Record: Sequence 1..1 (,)”.
    * A SOROZAT típus Gyökér\Sor\Típusok\Rekord eleme úgy van beállítva, hogy a tranzakciósorokat elemezze. Megjegyzés: az „Egyéni elválasztó” karakter beállítása a vessző. Ez azt jelenti, hogy a vessző fog mezőelválasztóként működni az ilyen típusú sorhoz az elemzési fájlban.   
    * Vegye figyelembe, hogy különböző adattípusok beágyazott elemeit külön mezőkként adta hozzá a Gyökér\Sor\Típusok\Rekord elemhez a tranzakciósorok elemzése érdekében. Vegye figyelembe, hogy az „Árajánlat-kérelem” beállítása Nincs. Ez azt jelenti, hogy az elemzési fájlban minden ilyen típusú mezőt úgy kell tekinteni, mint amelyek nem rendelkeznek zárt karakterekkel.   
9. A fastruktúrában válassza ki ezt: „Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case\Record: Sequence 1..1 (,)\TransactionDate: DateTime”.
    * Például a DÁTUMIDŐ típus Gyökér\Sor\Típusok\Rekord\Tranzakció dátuma elem úgy van beállítva, hogy a tranzakció dátumának és időpontjának értékét az elemzési fájlból „H/n/éééé” formátumban kérje le.   
10. A fastruktúrában válassza ki ezt: „Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case\Record: Sequence 1..1 (,)\CountryCode: String 0..1 ”.
    * Megjegyzés: a KARAKTERLÁNC típus Gyökér\Sor\Típusok\Rekord\Országkód elem úgy van beállítva, hogy a „Multiplicitás” mezőben a „Nulla egy” beállítás érvényes rá. Ez a beállítás az elemzési fájl Országkód mezőjének értékét opcionálisnak tekinti.   
11. A fastruktúrában válassza ki ezt: „Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case\Record: Sequence 1..1 (,)\Remark: Sequence 1..1 (,)”.
    * Megjegyzés: a SOROZAT típusú Gyökér\Sor\Típusok\Rekord\Megjegyzés elem úgy van beállítva, hogy az „Árajánlat-kérelem” mezőben az „Összes” lehetőség van beállítva, az „Idézőjel” mezőben pedig a kettős idézőjel. Ez azt jelenti, hogy az elemzési fájl minden ilyen típusú sorához tartozó mezőt (amelyeket a KARAKTERLÁNC típus Szöveg beágyazott elemei írnak le) úgy tekint a rendszer, mintha kettős idézőjelben jelenne meg.  
12. A fastruktúrában válassza ki ezt: „Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case\Unparsed: Sequence 1..1 ”.
    * A SOROZAT típus Gyökér\Sor\Típusok\Nem elemzett elem úgy van beállítva, hogy olyan struktúra alapján elemezze a tranzakciósorokat, amely nem felel meg a szülő ESET elemben leírtnak.   

## <a name="review-the-setting-of-the-format-mapping-to-the-data-model"></a>Az adatmodellhez tartozó formátumleképezés beállításának ellenőrzése
1. Kattintson a Formátum hozzárendelése modellhez lehetőségre.
    * A „Hozzárendelés modellhez CSV-formátumból” modell-leképezés leírja a bejövő CSV-fájl adatátvitelének áramlását az adatmodellbe.   
2. Kattintson a Tervező pontra.
3. A fastruktúrában bontsa ki ezt: „format”.
    * Megjegyzendő, hogy a tervezett formátum itt adatforrás-összetevőként jelenik meg.  
4. A fastruktúrában bontsa ki ezt: „format\Incoming: File(Incoming)”.
5. A fastruktúrában bontsa ki ezt: „format\Incoming: File(Incoming)\Root: Sequence(Root)”.
6. A fastruktúrában bontsa ki ezt: „format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..* (Line)”.
7. A fastruktúrában bontsa ki ezt: „format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..* (Line)\Types: Case(Types)”.
8. A fastruktúrában bontsa ki ezt: „format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..* (Line)\Types: Case(Types)\Record: Sequence 1..1 (,)(Record)”.
9. A fastruktúrában bontsa ki ezt: „'format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..* (Line)\Types: Case(Types)\Record: Sequence 1..1 (,)(Record)\Data”.
10. A fastruktúrában bontsa ki ezt: „format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..* (Line)\Types: Case(Types)\Record: Sequence 1..1 (,)(Record)\Data\CountryCode: String 0..1 (CountryCode)”.
11. A fastruktúrában válassza ki ezt: „format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..* (Line)\Types: Case(Types)\Record: Sequence 1..1 (,)(Record)\Data\TransactionDate: DateTime(TransactionDate)”.
    * Megjegyzés: a kötelező és választható formátumelemek, pl. a TransactionDate vagy a CountryCode megjelenítése eltér az előre meghatározott „formátum” adatforrás-összetevőben.   
12. A fában bontsa ki a „Transactions = '$both” csomópontot.
    * Vegye figyelembe, hogy az importált fájl szerkezetét meghatározó formátum elemei az adatmodell elemeihez vannak kötve. A kötések alapján az importált CSV-fájl tartalma futásidőben lesz tárolva a meglévő adatmodellben. Figyeljen oda a CountryRegion elem kötésére. A beérkező fájl összes olyan tranzakcióeleme esetében, amely nem rendelkezik meghatározott országkódértékkel, a rendszer az alapértelmezett „USA” országkóddal tölti fel az adatmodellt.   
13. Kapcsolja be a „Részletek megjelenítése” lehetőséget.
14. Kattintson az Ellenőrzések fülre.
15. Kattintson a Keresés gombra.
16. A Keresés mezőbe írja be a következőt: „vend”.
17. Kattintson a Következő keresése lehetőségre.
    * Ez a formátummegfeleltetés felhasználó által definiált logikát tartalmazhat, amely üzleti szempontból ellenőrzi az importált adatok pontosságát. A beállítástól függően például az importáló fájl bármely sora esetén, amelynek szerkezete nem egyezik sem a fejléc, sem a tranzakciós sor struktúrájával, figyelmeztető üzenet jelenik meg az információs naplóban, amely tájékoztatja a felhasználót az esetről, jelezve a tranzakció sorszámát a fájlban.   
18. Zárja be a lapot.

## <a name="run-the-format-mapping"></a>Formátum-hozzárendelés futtatása
Tesztelési célokra hajtsa végre a korábban letöltött 1099entriescsv.csv fájllal formátumleképezést. A létrehozott kimenet olyan adatokat jelenít meg, amelyek importálása a kijelölt CSV-fájlból történik, és a valós importáláskor tölti fel az egyéni adatmodellt.   
1. Kattintson a Futtatás elemre.
    * Kattintson a Böngészés lehetőségre, és a navigáljon a korábban letöltött 1099entriescsv.csv fájlhoz.  
2. Kattintson az OK gombra.
    * Vegye figyelembe a nem elfogadott sorokra vonatkozó figyelmeztető üzeneteket. A 4. sor nem elfogadható formátumú bejövő értéket tartalmaz, míg a 7. sorban nem szerepel a tranzakciószöveg megjegyzése kettős idézőjelek között.   
    * Tekintse át az XML-formátumú kimenetet, amely azokat az adatokat jelöli, amelyeket a kiválasztott fájlból importált, és az adatmodellbe portolt a rendszer. Vegye figyelembe, hogy az importált CSV-fájl mind a 7 sora feldolgozásra került. A mezők címében az 1. sor ki lett hagyva, 4 tranzackió megfelelő elemzése megtörtént, és 2 tranzakció érvénytelenként volt felismerve.   
3. Zárja be a lapot.
4. Zárja be a lapot.

