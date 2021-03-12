---
title: Minőségkezelési folyamatok
description: Ez a cikk a nem megfelelő termékekre vonatkozó minőségkezelési folyamatról nyújt tájékoztatást. a minőségellenőrzési funkció használatát, továbbá a szabálytalanságok meghatározásának, karbantartásának, illetve a helyesbítések kezelésének módját írja le.
author: perlynne
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventItemSampling, InventNonConformanceHistory, InventNonConformanceTable, InventQualityOrderLineResults, InventQualityOrderTable, InventTestCorrection, InventTestDiagnosticType, InventTestInstrument, InventTestReportSetup, InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 11574
ms.assetid: 5ac8a059-5cb4-4cb5-ba14-b944bd08dae9
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b87fe141c6d53f68e90f5f2346da0633a09b1af1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4987379"
---
# <a name="quality-management-processes"></a>Minőségkezelési folyamatok

[!include [banner](../includes/banner.md)]

Ez a cikk a nem megfelelő termékekre vonatkozó minőségkezelési folyamatról nyújt tájékoztatást. a minőségellenőrzési funkció használatát, továbbá a szabálytalanságok meghatározásának, karbantartásának, illetve a helyesbítések kezelésének módját írja le.

A minőségbiztosítás magába foglalja a terméktesztelést és a nem megfelelő anyagok kezelését. A minőségirányítási folyamatok segítik biztosítani a kiemelkedő minőségű termékeket az önök ellátási láncában. Ezek a folyamatok segítik továbbá optimalizálni az ellátási lánc folyamatait és növelik a vásárlók elégedettségét. A minőségirányítás segítséget nyújt a szabálytalan termékek javítási folyamatának kezelésében, azok eredetétől függetlenül. A diagnosztikai eredményeket csatolhatja a javítási feladatokhoz. A rendszer képes ütemezni a feladatokat annak érdekében, hogy kijavítsa a hibákat és ily módon segít megelőzni a problémák visszatérését a jövőben. A minőségellenőrzés segít továbbá a problémák típus szerinti kinyomozásában (a belső problémákat is beleértve) és segít megtalálni a rövid- és a hosszú távú megoldásokat is. A fő teljesítménymutatókról (KPI-kről) vezetett statisztikák betekintést nyújtanak a múltban felmerült szabálytalansági problémákba és az azok javítására használt megoldásokba. Az előzményadatok segítségével felülvizsgálhatja a korábbi minőségi mérések hatékonyságát, és kidolgozhatja a jövőben alkalmazni kívánt megfelelő méréseket.

## <a name="controlling-the-quality-management-process"></a>A minőségirányítási folyamat ellenőrzése
Íme néhány módszer a minőségirányítási folyamat kézben tartására:

-   Készítsen minőségi rendeléseket, melyek olyan kritériumokon alapulnak, mint például a „termék bizonylat” belföldi műveletek esetén vagy a „termék felvétel” külföldi műveletek esetén.
-   Dokumentálja a teszt eredményeket és határozza meg, hogy az eredmények mennyiben egyeznek meg a megállapított tesztkövetelményekkel és az elfogadható minőségszintekkel.
-   Alkalmazzon dokumentumkezelést részletes termékleírásokhoz és felhasználó specifikus jegyzetekhez, hogy így jelenthessen a megfigyelési folyamat során.
-   Gondoskodjon a szabálytalan termékekről és viszonyításképp lássa el őket információval a szabálytalanságokról, hogy lekövethesse a probléma eredetét.
-   Dokumentálja a szabálytalanság kezelésének költségeit. Ezek a költségek magukba foglalhatnak eszközöket (például pótalkatrészeket), különféle díjakat, és a szabálytalanság kijavítására szánt óradíjakat.
-   Ütemezze a javítási folyamatokat a minőségi rendelésekhez csatolt korrekció kezelő segítségével.

[![Minőségkezelési folyamat](./media/quality-management-process-diagram.png)](./media/quality-management-process-diagram.png)  

## <a name="product-testing-and-quality-orders"></a>Terméktesztelés és minőségi rendelések.
A terméktesztelést más néven minőségkezelésnek is nevezik és minőségi rendeléseket használ eszközéül. A minőség-ellenőrzési szolgáltatások igénybe vételével a következőket teheti:

-   Határozza meg az anyagfelhasználáshoz szükséges teszteket. Ezek a tesztek magukba foglalják a minőségi elvárásokat, az alkalmazandó tesztberendezéseket, a tesztet leíró dokumentumokat, a mintavételi tervet és az elfogadható minőségi szinteket. (AQL).
-   Készítsen minőségi rendelést, mely megállapítja az egy adott rendelésez (például beszerzési rendelés, termelési rendelés vagy készletmennyiség) szükséges teszteket. A minőségi rendelések létrehozhatók manuálisan, illetve a minőségi irányelvek alapján generálhatók automatikusan is.
-   Határozza meg a minőségi irányelveket, melyek a beszerzésre, elzárásra, gyártásra és az értékesítésre vonatkoznak, hogy ezek segítségével automatikusan generálhasson minőségi rendelést, melyek azonosítják a be- és kimenő anyagokra érvényes tesztelési követelményeket.
-   Rögzítse a minőségi rendelés teszteredményeit, majd mérje össze azokat az általánosan elvárt minőségi szinttel (AQL) és nyomtasson elemzési tanúsítványt, melyen szerepelnek a teszteredmények.

## <a name="nonconformance"></a>Szabálytalanság
A szabálytalanság rendelkező cikkeket minőségi probléma ismerteti. A szabálytalansági folyamat segít szabálytalan rendeléseket létrehozni, melyek leírják a szabálytalan anyagok mennyiségét, a probléma forrását és típusát, valamint magyarázó megjegyzéseket. A problématípusokat előre osztályozhatja, hogy megkönnyítse a nem megfelelő anyagok elemzését. Nyomtathat továbbá szabálytalansági címkét és szabálytalansági jelentést, hogy irányítsa a nem megfelelő anyagok áthelyezését. Például, a címke és a jelentés jelezhetnek **Használhatatlan** vagy **Korlátozottan felhasználható** állapotot. 

Az alábbi táblázat felsorolja a hat alapértelmezett szabálytalanságtípust és leírja a feljegyezendő információkat mindegyik típushoz.

| Szabálytalanság-típus   | A forrásra vonatkozó adatok                                                                                                                                                                                                                          |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Vevő              | A vásárlói vevőkód, az értékesítési rendelés száma vagy az értékesítési rendelés tranzakciójának adagszáma. Például, a szabálytalanság összefüggésben állhat specifikus értékesítési rendelés szállítmánnyal vagy vásárlói visszajelzéssel a termék minőségét illetően.       |
| Szolgáltatáskérés       | A vásárlói vevőkód, az értékesítési rendelés száma vagy az értékesítési rendelés tranzakciójának adagszáma. Például, a szabálytalanság összefüggésben állhat specifikus értékesítési rendelés szállítmánnyal vagy egy vásárló panaszával a termék minőségét illetően.     |
| Szállító                | Szállítókód, a beszerzési rendelés száma vagy a beszerzési rendelés tranzakciójának adagszáma. A szabálytalanság kapcsolódhat például egy adott beszerzési rendelés bevételezéséhez, vagy lehet egy szállító probléma bejelentése az általa szállított alkatrészekre vonatkozóan. |
| Termelés            | A termelési rendelés száma vagy a termelési rendelés tranzakciójának adagszáma. A szabálytalanság kapcsolódhat például egy legyártott köteghez.                                                                      |
| Belső              | Minőségi rendelés száma vagy a minőségi rendelés tranzakciójának adagszáma. A szabálytalanság kapcsolódhat például egy alkatrészen a minőségi rendelés keretében végrehajtott tesztekhez, vagy egy alkalmazott termékminőségre vonatkozó bejelentéséhez.     |
| Társtermék gyártása | Társtermék termelési rendelés szabálytalansága, mely termelési rendelések egy kötegéhez köthető.                                                                                                                                                    |

A szabálytalanságok problématípusokhoz vannak társítva. A problématípusok a **Problématípusok** oldalon vannak meghatározva, ahol pontosíthatja melyik probléma típus, milyen szabálytalansági típussal azonosítható. Például, a **Szolgáltatáskérés** típusú szabálytalanságok tükrözhetnek osztályozott vásárlói panaszokat, míg a **Belső**problématípusok hibakódok osztályozását.

Új szabálytalanságok létrehozásakor ki kell választani a szabálytalanságtípust és problématípust. A kezdeti jóváhagyási állapot **Új**, amely jelzi a műveletre vonatkozó kérelmet. A következő lépés a jóváhagyási állapot megváltoztatása **Elfogadott** vagy **Megtagadott** állapotba, így jelezvén, hogy tesz-e további lépéseket a szabálytalanság ellen. Lehetőség van a szabálytalanság bezárására is (külön jelölőnégyzet kiválasztásával), így jelezve, hogy készen van vele, vagy újranyithatja a szabálytalanságot, hogy jelezze, szükség van annak újragondolására.

Fűzhet kommentárokat is egy szabálytalansághoz, dokumentum csatolásával. Tanácsos egyedi dokumentumtípust megadni a szabálytalanságokhoz a **Dokumentum típus** oldal segítségével. Ezután használhatja a **Jelentés beállítás** oldalt, hogy megállapítsa szükséges-e feltüntetni a szabálytalansági jelentésen és a szabálytalansági címkén az ahhoz a dokumentumhoz tartozó kommentárokat. A nyomtatott szabálytalansági jelentések és szabálytalansági címkék segíthetnek az anyagmozgatások során. Létrehozhat jelentéseket és címkéket a szabálytalanságokhoz köthető kiválasztási kritériumok alapján. Ilyen kritériumok például a szabálytalanság száma, cikk, vevő, szállító és állapot.

A szabálytalansági jelentésben megjelenik a szabálytalanság száma, a cikk és a probléma típusa. Az ön által felállított jelentés beállítási irányelvek alapján, a jelentés tartalmazhatja a kapcsolódó kommentárokat is a szabálytalanságot illetően. A szabálytalansági címke hasonló adatokat jelenít meg, valamint tartalmazza a szabálytalansághoz rendelt karantén zónát és típust (mint például **Korlátozott felhasználás** vagy **Használhatatlan**), így segítve a hibás anyagok áthelyezését.

## <a name="approved-nonconformance"></a>Jóváhagyott szabálytalanság
Tetszés szerint meghatározhat egy vagy több kapcsolódó műveletet egy jóváhagyott szabálytalansághoz. A kapcsolódó művelet leírja az elvégzendő munkát és tartalmaz egy listát azokról a minőségi műveletekről, melyeket megállapított, valamint leíró szöveget a munka okáról. Miután meghatározza a műveletet, tetszés szerint meghatározhatja az egyéb költségeket, az eszközöket és a munka teljesítéséhez szükséges munkaórák számát. A számított költségek a kapcsolódó művelethez jelennek meg, míg az összköltségek szabálytalansághoz. A számított költségek és a mögöttes részletek (cikkek, munkaórák és vegyes költségek) hivatkozási információk és csak a minőségkezelés funkcióiként alkalmazottak.

Amennyiben szeretné, létrehozhat minőségi rendelést a szabálytalanságokból úgy, hogy először végrehajt egy lekérdezést a minőségi rendelésekért, majd alkot egy új minőségi rendelést. Például, egy minőségi rendelés felvetheti annak a szükségét, hogy tesztelje (vagy újra tesztelje) a hibás anyagot. Az újonnan létrehozott minőségi rendelés az eredeti szabálytalanság linkjét mutatja.

Az egyes szabálytalanságok tetszés szerint egymáshoz kapcsolhatók, illetve a meglévőkből új szabálytalanságok is létrehozhatók. Például a kapcsolat tükrözheti az egyes minőségi problémák közötti összefüggéseket.

## <a name="correction-handling"></a>Korrekció kezelés
A **Javítások** lap lehetővé teszi a kijavítandó szabálytalanságok listázását. Minden javító eszköz kapcsolatban áll azzal a diagnosztikai típussal, amely lehetővé tette a probléma felfedezését. A **Javítások** lap információval szolgál továbbá arról is, hogy kinek és mikor kell elvégeznie a javítási műveletet. Leírhatja a probléma és a szükséges javítási művelet részleteit is, amennyiben csatol egy dokumentumot a korrekcióhoz. Miután a szabálytalanságot megnevezte vagy kijavította, „bezáratja” a javító eszközt a **Befejeződött** opció kiválasztásával. Azt is jelezheti, hogy ha megoldás csak rövid távú.

Tanácsos egyedi dokumentumtípust megadni a javításokhoz a **Dokumentum típus** oldal segítségével. Ezután használhatja a **Jelentés beállítás** oldalt, hogy megállapítsa megvannak-e jelenítve az ehhez a dokumentum típushoz tartozó megjegyzések a javítási jelentésen. A nyomtatott javítási jelentésben információk találhatóak a szabálytalanságról és a kapcsolódó szabálytalansági jegyzetekről. A jelentés tartalmazza a javítási információkat, mint például a diagnózis típusát, valamint a kapcsolódó javítási jegyzeteket.

<a name="additional-resources"></a>További erőforrások
--------

[Minőségkezelés áttekintése](enable-quality-management.md)

[Szabálytalanság kezelése](enable-nonconformance-management.md)

[Készletzárolás](inventory-blocking.md)

[Karanténutasítások](quarantine-orders.md)

[Minőségi rendelések beállítása](tasks/set-up-quality-orders.md)

[Áru minőségének ellenőrzése](tasks/inspect-quality-goods.md)
