---
title: ER – Szükséges konfigurációk létrehozása adatok importálásához egy külső fájlból
description: Ez a témakör bemutatja, hogyan lehet az elektronikus jelentési konfigurációt úgy megtervezni, hogy külső fájlból importáljon adatokat a Microsoft Dynamics 365 Finance alkalmazásába.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERSolutionCreateDropDialog, EROperationDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula, Tax1099Summary, VendSettlementTax1099
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0492fae6cfad505fc9fee5cd20f483c9c6d2a061
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093723"
---
# <a name="er-create-required-configurations-to-import-data-from-an-external-file"></a>ER – Szükséges konfigurációk létrehozása adatok importálásához egy külső fájlból

[!include [banner](../../includes/banner.md)]

A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre egy elektronikus jelentés (ER) konfigurációt adatok importálására az alkalmazásba külső fájlból. Ebben a példában létrehozzuk a szükséges ER-konfigurációkat a Litware, Inc. mintavállalatra vonatkozóan. A lépések végrehajtásához először a következő feladat-útmutató lépéseit kell végrehajtani: „ER – Konfigurációszolgáltató létrehozása, és megjelölés aktívként.” A lépések a USMF-adathalmazzal hajthatók végre. Emellett le kell tölteni és helyben menteni kell a következő fájlokat az Elektronikus jelentések áttekintése témakör hivatkozásainak (https://go.microsoft.com/fwlink/?linkid=852550): használatával: 1099model.xml, 1099format.xml, 1099entries.xml, 1099entries.xlsx.

Az ER lehetővé teszi az üzleti felhasználók számára, hogy a  táblázataiba történő külső adatfájl-importálás folyamatához az XML- vagy a TXT-formátumot konfigurálják. Először ki kell alakítani egy absztrakt adatmodell és egy ER adatmodell konfigurációt, amely leképezi az importálandó adatokat. Ezután definiálni kell az importálandó fájl struktúráját, valamint azt az eljárást, amelyet az adatok portolására fog használni a fájlból az absztrakt adatmodellbe. Az absztrakt adatmodellhez létre kell hozni az ER-formátum konfigurációját, amely leképezi a megtervezett adatmodellt. Ezt követően az adatmodell konfigurációját ki kell bővíteni a leképezéssel, amely leírja, hogyan marad meg az importált adatok absztrakt adatmodellje, és hogyan történik a felhasználása a táblák frissítéséhez.  Az ER-adatmodell konfigurációját ki kell egészíteni egy új modell-leképezéssel, amely leírja az adatmodell kötését az alkalmazás céljához.  

A következő forgatókönyv az ER-adatimportálási lehetőségeket jeleníti meg. Ez magában foglalja a külsőleg nyomon követett, majd az importált szállítói tranzakciókat, amelyeket később a szállítói kiegyenlítés 1099-es jelentéshez kell jelenteni.   

## <a name="add-a-new-er-model-configuration"></a>Új ER-modellkonfiguráció hozzáadása
1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.

    Ellenőrizze, hogy a konfigurációszolgáltató a Litware, Inc. elérhető és aktívként megjelölt legyen. Ha nem látja a konfigurációszolgáltatót, először el kell végeznie a „Konfigurációszolgáltató létrehozása, és megjelölés aktívként” eljárásban szereplő lépéseket.   

2. Kattintson a Jelentéskészítés konfigurációi lehetőségre.

    Ahelyett, hogy új modellt hozna létre az adatimportálás támogatásához, töltse be a korábban letöltött 1099model.xml fájlt. Ez a fájl tartalmazza az egyéni adatmodellt a szállítók tranzakcióihoz. Ez az adatmodell hozzá van rendelve az adatösszetevőkhöz, amelyek az AOT-adatentitásban találhatók.   

3. Kattintson az Átváltás lehetőségre.
4. Kattintson a Betöltés XML-fájlból lehetőségre.

    Kattintson a Böngészés lehetőségre, és a navigáljon a korábban letöltött 1099model.xml fájlhoz.  

5. Kattintson az OK gombra.
6. A fastruktúrában válassza ki ezt: „1099 fizetések modellje”.

## <a name="review-data-model-settings"></a>Adatmodell-beállítások áttekintése
1. Kattintson a Tervező pontra.

    Ezt a modellt a szállítók tranzakcióinak leképezésére tervezték üzleti szempontból, és független a megvalósításától.   

2. A fastruktúrában bontsa ki a következőt: „1099-MISC”.
3. A fastruktúrában válassza ki ezt: „1099-MISC\Tranzakciók”.
4. A fastruktúrában bontsa ki ezt: „1099-MISC\Tranzakciók”.

    A modell Tranzakciók eleme az egyes tranzakciókat jelöli. A gyermekelemek segítségével adhatja meg a szükséges adatokat, például a szállítói számlát és a tranzakció dátumát, minden egyes tranzakcióhoz.   

5. Zárja be a lapot.

## <a name="add-a-new-er-format-configuration-that-supports-data-import"></a>Az adatok importálását támogató új ER-formátumkonfiguráció hozzáadása
A részfeladat lépései megmutatják, hogyan hozható létre új formátumkonfiguráció az adatok importálásához külső fájlokból.   
1. A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.
2. Az Új mezőbe írja be az „1099 Fizetések modellen alapuló formátum” kifejezést.
3. A Támogatja az adatimportálást mezőben válassza az Igen lehetőséget.
4. Nyomja le az ESC billentyűt az oldal bezáráshoz.

    Ahelyett, hogy új formátumot hozna létre az adatimportálás támogatásához, töltse be a korábban letöltött 1099format.xml fájlt. Ez a fájl tartalmazza az importálandó fájl definiált szerkezetét, valamint a struktúra hozzárendelését a szállítók tranzakcióinak egyéni adatmodelljéhez.   
5. Kattintson az Átváltás lehetőségre.
6. Kattintson a Betöltés XML-fájlból lehetőségre.
    Kattintson a Böngészés lehetőségre, és a navigáljon a korábban letöltött 1099format.xml fájlhoz.  
7. Kattintson az OK gombra.
8. A fastruktúrában bontsa ki ezt: „1099 Payments model”
9. A fastruktúrában válassza ki ezt: „1099 Payments model\Format for importing vendors' transactions”.

## <a name="review-format-settings"></a>Formátumbeállítások ellenőrzése
1. Kattintson a Tervező pontra.
2. Kapcsolja be a Részletek megjelenítése lehetőséget.
3. Kattintson a Csomópont kibontása/összecsukása lehetőségre.
4. Kattintson a Csomópont kibontása/összecsukása lehetőségre.

    A tervezett formátum a külső fájl várt struktúráját jelöli. A fájlnak XML-formátumúnak kell lennie, és tartalmaznia kell a kiegyenlítés gyökérelemet. Minden szállítói tranzakciót a tranzakció elem jelöl, amelynek a definíció szerint null-sok multiplicitása van. Ez azt jelenti, hogy a beérkező fájl bármennyi tranzakciót tartalmazhat zéró és sok között. A tranzakció elem beágyazott elemei egy adott tranzakció attribútumait képviselik. Vegye figyelembe, hogy az ország kivételével mindegyik attribútum kötelező jelölésű, amit azt jelenti, hogy kötelezően szerepelniük kell az importált fájlban.   

## <a name="review-the-settings-of-the-format-mapping-to-the-data-model"></a>Az adatmodellhez tartozó formátumleképezés beállításainak ellenőrzése
1. Kattintson a Formátum hozzárendelése modellhez lehetőségre.

    A „Szállítók tranzakcióinak importálásához” hozzárendelés tartalmazza az átviteli szabályokat a bejövő XML-fájlból az egyéni adatmodell kiválasztott részéhez, amely az 1099-MISC definíció kiválasztásával határozható meg.  

2. Kattintson a Tervező pontra.
3. Kapcsolja be a Részletek megjelenítése lehetőséget.
4. A fában bontsa ki a következőt: „formátum: Rekord”.
5. Válassza ki a „formátum: Rekord” lehetőséget a fastruktúrában.

    Megjegyzendő, hogy a tervezett formátum itt adatforrás-összetevőként jelenik meg.  

6. A fastruktúrában bontsa ki a `format: Record\*settlement: XML Element 1..1 (settlement): Record` csomópontot.
7. A fastruktúrában bontsa ki a `format: Record\*settlement: XML Element 1..1 (settlement): Record\transaction: XML Element 0..* (transaction): Record list` csomópontot.
8. A fastruktúrában bontsa ki a `format: Record\*settlement: XML Element 1..1 (settlement): Record\transaction: XML Element 0..* (transaction): Record list\*vendor: XML Element 1..1 (vendor): Record` csomópontot.
9. A fastruktúrában bontsa ki a `format: Record\*settlement: XML Element 1..1 (settlement): Record\transaction: XML Element 0..* (transaction): Record list\country: XML Element 0..1 (country): Record` csomópontot.
10. A fastruktúrában válassza ki a `format: Record\*settlement: XML Element 1..1 (settlement): Record\transaction: XML Element 0..* (transaction): Record list\*vendor: XML Element 1..1 (vendor): Record` csomópontot.

    Megjegyzés: a kötelező és választható formátumelemek megjelenítése eltér az előre meghatározott „formátum” adatforrás-összetevőben.  
11. A fastruktúrában bontsa ki ezt: „Tranzakciók: Record list= format.settlement.'$enumerated'”.

    Vegye figyelembe, hogy az importált fájl szerkezetét meghatározó formátum elemei az egyéni adatmodell elemeihez vannak kötve. A kötések alapján az importált XML-fájl tartalma futásidőben lesz tárolva a meglévő adatmodellben. Figyeljen oda az ország elem kötésére. A beérkező fájl összes olyan tranzakcióeleme esetében, amely nem rendelkezik az ország elemmel, a rendszer az alapértelmezett „USA” országkóddal tölti fel az adatmodellt.  

12. Kattintson az Ellenőrzések fülre.

    Ez a formátummegfeleltetés felhasználó által definiált logikát tartalmazhat, amely üzleti szempontból ellenőrzi az importált adatok pontosságát. Például a beállítások alapján, az importált fájlban található, meghatározott országkód nélküli bármely tranzakció esetében, figyelmeztető üzenet jön létre az információs naplóban, amely értesíti a felhasználót az esetről, és a megadja a tranzakció sorszámát.  

13. Zárja be a lapot.

## <a name="run-the-format-mapping-to-the-data-model"></a>A formátumleképezés futtatása az adatmodellhez
Hajtsa végre ezt a formátumleképezést tesztelési célokra. Használja a korábban letöltött 1099entries.xml fájlt. Ezt a fájlt az 1099entries.xlsx munkafüzetből exportálhatja, amely a szállítói tranzakciók kezelésére szolgál. A létrehozott kimenet importálása a kijelölt XML-fájlból történik, és a valós importáláskor tölti fel az egyéni adatmodellt.  

1. Kattintson a Futtatás elemre.

    Kattintson a Böngészés lehetőségre, és a navigáljon a korábban letöltött 1099entries.xml fájlhoz.  

2. Kattintson az OK gombra.

    Figyelje meg a figyelmeztető üzenetet az importált fájlban a tranzakcióból hiányzó országkód kapcsolatban.  
    
    Tekintse át az XML-formátumú kimenetet, amely azokat az adatokat jelöli, amelyeket a kiválasztott fájlból importált, és az adatmodellbe portolt a rendszer.   

3. Zárja be a lapot.
4. Zárja be a lapot.

## <a name="review-the-settings-for-the-model-mapping-to-the-destinations"></a>A célokhoz tartozó modell-leképezés beállításainak ellenőrzése
1. A fastruktúrában válassza ki ezt: „1099 fizetések modellje”.
2. Kattintson a Tervező pontra.
3. Kattintson a Modell hozzárendelése adatforráshoz gombra.

    Az 1099-es manuális tranzakciók importálásának hozzárendelése a cél céliránytípussal van definiálva. Ez azt jelenti, hogy meg van adva az adatimportálás támogatásához, és tartalmazza azokat a szabályokat, amelyek megadják, hogy az importált külső fájlt, amely absztrakt modelladatként őrződik meg, hogyan használja a rendszer a táblák frissítéséhez.  

4. Kattintson a Tervező pontra.
5. A fastruktúrában bontsa ki a „modell: Adatmodell 1099 Fizetési modell” lehetőséget.
6. A fastruktúrában bontsa ki a következőt: „modell: Adatmodell 1099 Fizetési modell\Tranzakciók: Rekordlista”.

    Megjegyzendő, hogy a tervezett modell itt adatforráselemként jelenik meg. Futásidőben tartalmazni fogja a külső fájlból az importált adatokat. Több tábla hozzáadása történt adatforráselemként annak a biztosítására, hogy az importált adatok megfeleljenek a jelenlegi alkalmazás adatainak, beleértve azt is, hogy az importáló tranzakciószállító rendelkezésre áll-e a rendszerben, létezik-e az importáló ország és az államkód kombinációja, stb.  

7. A fastruktúrában válassza ki ezt: „modell: Adatmodell 1099 Fizetési modell\Tranzakciók: Rekordlista\$failed: Calculated field = IF(OR(ISEMPTY(model.Transactions.'$refs'.vendor), ISEMPTY(model.Transactions.'$refs'.vendor1099), ISEMPTY(model.Transactions.'$refs'.box1099), ISEMPTY(model.Transactions.'$refs'.country), ISEMPTY(model.Transactions.'$refs'.state), ISEMPTY(model.Transactions.'$refs'.location)), true, false): Boolean”.
8. Kattintson a Szerkesztés lehetőségre.
9. Kattintson a Receptúra szerkesztése lehetőségre.

    Ha legalább egy ellenőrzés sikertelen egy adott importált tranzakció esetében, ez a tranzakció sikertelenként lesz megjelölve a „$failed” adatforrás-attribútummal.  

10. Zárja be a lapot.
11. Kattintson a Mégse gombra.
12. A fastruktúrában válassza ki ezt: „tax1099trans: Table 'VendSettlementTax1099' records= model.Validated”.
13. Kattintson a Cél szerkesztése lehetőségre.

    Ennek az ER-célnak a hozzáadása azért történt meg, hogy megadja, hogyan frissítik az importált adatok az alkalmazástáblákat.. Ebben az esetben a VendSettlementTax1099 adattábla van kiválasztva. Mivel a Beszúrás rekordművelet van kiválasztva, az importált tranzakciókat a rendszer a VendSettlementTax1099 táblába szúrja be. Vegye figyelembe, hogy az egyetlen modelles hozzárendelés több rendeltetési helyet is tartalmazhat. Ez azt jelenti, hogy az importált adatok egyszerre több alkalmazás tábláinak frissítésére használhatók. ER-célként táblák, nézetek és adatentitások használhatók.   

    Ha a hozzárendelést olyan pont (például gomb vagy menüelem) hívja meg, amelyet kifejezetten erre a műveletre terveztek, az ER-céljának az integrációs pontot kell megjelölni. Ebben a példában ez az ERTableDestination#VendSettlementTax1099 pont.  

14. Kattintson a Mégse gombra.
15. Kattintson az Összes megjelenítésére lehetőségre.
16. Kattintson a Csak a hozzárendeltek megjelenítése lehetőségre.
17. A fastruktúrában bontsa ki ezt: „tax1099trans: Table 'VendSettlementTax1099' records= model.Validated”.

    Megjegyzés: a csak az ellenőrzött tranzakciókat tartalmazó adatforráselem a létrehozott célhoz van kötve. Az importált tranzakciók szűrhetők, hogy kihagyhatók legyenek azok, amelyek nem kompatibilisek az alkalmazások adataival.  

18. A fastruktúrában válassza ki ezt: „failed: Table 'VendSettlementTax1099Entity' records= model.Failed”.
19. Kattintson az Ellenőrzések fülre.

    Ez a modellmegfeleltetés felhasználó által definiált logikát tartalmazhat, amely ellenőrzi az importált adatok pontosságát a meglévő alkalmazásadatokból. Például a jelenlegi beállítások alapján, az importált fájlban található, a rendszerben nem szereplő szállítói számlát tartalmazó tranzakciók esetében, figyelmeztető üzenet jön létre, amely értesíti a felhasználót, és a megadja a hibás szállítói számla kódját.  

    Ne feledje, hogy minden ellenőrzés esetében használható az ellenőrzés utáni művelet, amellyel megadható, hogy az importálási folyamat folytatódjon vagy leálljon, valamint az, hogy a rendszer megtartsa vagy visszavonja a már végrehajtott beszúrásokat/frissítéseket.  

20. Kattintson a Csak a hozzárendeltek megjelenítése lehetőségre.
21. Kattintson az Összes megjelenítésére lehetőségre.
22. Zárja be a lapot.

    Hajtsa végre ezt a modell-hozzárendelést a megtervezett formátum- és modell-hozzárendelések tesztelésére. Használja az 1099entries.xml fájlt. Megtörténik a kijelölt fájlból származó adatok importálása a rendszerbe.  

23. Kattintson a Futtatás elemre.

    Vegye figyelembe, hogy a párbeszédpanel nem tartalmaz további kérdéseket a formátum-hozzárendelésre nézve, amelyet az importált fájl elemzésére, majd az adatoknak az adatmodellbe portolására kell használni. Ennek az oka az, hogy jelenleg csak egy formátum használja ezt a modellt, amely az adatimportálás támogatására tervezettként van megjelölve.  
    
    Adja meg a bizonylatazonosítót, hogy megkülönböztethesse az importált tranzakciókat más tranzakcióktól, amelyeket korábban manuálisan vittek be vagy importáltak.  

24. A Bizonylat azonosítójának megadása mezőbe írja be a következőt: „IMPORT-001”.

    Keresse meg az „1099entries.xml” fájlt.  

25. Kattintson az OK gombra.

    A figyelmeztetések generált listája információkat nyújt a helytelen szállítói számlákról, a helytelen adóazonosító 1099-es mezőkódról, a hiányzó országkódokról, stb. Hasonlítsa össze a figyelmeztetések listáját a végrehajtási XML-fájl tartalmával.  

26. Zárja be a lapot.
27. Zárja be a lapot.
28. Zárja be a lapot.
29. Zárja be a lapot.
30. Ugrás a Kötelezettségek > Időszakos feladatok > 1099-es adóűrlap > Szállítói kiegyenlítések az 1099-es jelentéshez elemre.

    Ezen a képernyőn láthatók a Tax1099Summary tábla kumulatív tranzakciói, amelyek az importált tranzakciók alapján jöttek létre.  

31. A Kezdő dátum mezőben állítsa „2000-01-01” értékűre a dátumot.
32. Kattintson a Manuális 1099-es tranzakciók lehetőségre.

    Ez a képernyő tartalmazza azoknak a tranzakcióknak a listáját, amelyek manuálisan lettek hozzáadva, illetve azokét, amelyeknél egyszerű importálás történt.  

33. Nyissa meg a Bizonylat oszlopszűrőt.
34. Adja meg az „IMPORT-001” szűrőértékét a „Bizonylat” mezőben az „ezzel kezdődik” szűrési operátor használatával.

## <a name="review-the-relationship-between-model-and-format-mappings"></a>Tekintse át a modell- és a formátumleképezések közötti kapcsolatot
1. Zárja be a lapot.
2. Zárja be a lapot.
3. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
4. Kattintson a Jelentéskészítés konfigurációi lehetőségre.
5. A fastruktúrában válassza ki ezt: „1099 fizetések modellje”.

    Feltételezi, hogy ugyanazoknak az adatoknak az importálását kívánja támogatni, de TXT-fájl formátumból.   

6. A Konfiguráció létrehozása gombra kattintva megnyithatja a párbeszédablakot. 
7. Az Új mezőbe írja be az „1099 Fizetések modellen alapuló formátum” kifejezést.
8. A Név mezőbe írja be, hogy „Adatok importálása TXT-fájlból”.
9. A Támogatja az adatimportálást mezőben válassza az Igen lehetőséget.
10. Kattintson a Konfiguráció létrehozása lehetőségre.
11. Kattintson a Tervező pontra.
12. Kattintson a Formátum hozzárendelése modellhez lehetőségre.
13. Kattintson az Új lehetőségre.
14. A Leírás mezőben adjon meg vagy válasszon ki egy értéket.

    Válassza az „1099-MISC” lehetőséget.  

15. A Név mezőbe írja be, hogy „Adatok importálása TXT-fájlból”.
16. A Leírás mezőbe írja be, hogy „Adatok importálása TXT-fájlból”.
17. Kattintson a Mentés gombra.
18. Zárja be a lapot.
19. Zárja be a lapot.
20. Kattintson a Szerkesztés lehetőségre.

    Ha telepítette a következő gyorsjavítást: „KB 4012871 GER-modell-leképezések támogatása elkülönített konfigurációkban különböző típusú előfeltételek megadásának képességével a telepítésükhöz a Dynamics 365 Finance különböző verzióiban” ([KB 4012871](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871)), hajtsa végre a következő lépést: „Alapértelmezett modell-leképezéshez jelző bekapcsolása” a megadott formátumkonfigurációhoz. Ellenkező esetben hagyja ki a következő lépést.  

21. Válassza az Igen lehetőséget a Modell-leképezés alapértelmezett értéke mezőben.
22. A fastruktúrában válassza ki ezt: „1099 fizetések modellje”.
23. Kattintson a Tervező pontra.
24. Kattintson a Modell hozzárendelése adatforráshoz gombra.
25. Kattintson a Futtatás elemre.

    Ha telepítette a következő gyorsjavítást: KB 4012871 GER-modell-leképezések támogatása elkülönített konfigurációkban különböző típusú előfeltételek megadásának képességével a telepítésükhöz a különböző verziókban” ([KB 4012871](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871)), válassza ki az előnyben részesített modell-leképezést a keresés mezőben. Ha még nem telepítette a gyorsjavítást, ugorjon a következő lépésre, mert a leképezést már kiválasztotta az alapértelmezett formátumkonfiguráció meghatározása.  
    
    Ha még nem telepítette a KB 4012871 gyorsjavítást, figyelje meg, hogy a párbeszédpanel egy további modell-leképezési kérdést tartalmaz, amelyet a rendszer az importálandó fájl elemzéséhez használ. Ezután megtörténik az adatok portolása a párbeszédpanelből az adatmodellbe. Jelenleg az importálandó fájl típusától függően választhatja ki a használandó formátumleképezést.  
    
    Ha azt tervezi, hogy a modell-leképezést egy kifejezetten erre a műveletre tervezett pontról hívja meg az alkalmazásban az ER-célhelyét és a formátumleképezést meg kell jelölni az integráció részeként.  

26. Kattintson a Mégse gombra.
27. Zárja be a lapot.
28. Zárja be a lapot.

