---
title: Folyamatkompenzáció
description: A kompenzációfeldolgozás lehetővé teszi, hogy új alapkompenzációs összegeket számoljon ki az alkalmazottai számára a részvénymódosítások, az érdemi elismerések és a teljesítmény alapján.
author: andreabichsel
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: 2faa5c02e3641a7b80e410e3b9cc05d08d99f92f
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898179"
---
# <a name="process-compensation"></a>Folyamatkompenzáció

A kompenzációfeldolgozás lehetővé teszi, hogy új alapkompenzációs összegeket számoljon ki az alkalmazottai számára a részvénymódosítások, az érdemi elismerések és a teljesítmény alapján. Ez a témakör a kompenzációfeldolgozás alapvető folyamatát mutatja be a rögzített kompenzációs konstrukciók esetében az alkalmazotti teljesítmény beszámítása nélkül.

## <a name="plan-the-new-compensation-amounts-and-budgets"></a>Tervezze meg az új kompenzációs összegek és költségvetéseket
Ha érdemen alapuló emelést szeretne adni az alkalmazottaknak, be kell állítania egy fix növekményes költségvetést minden szervezeti egységekben: Kompenzációkezelés > Hivatkozások > Érdemen alapuló emelési célok. (A képernyőt megnyithatja ezen a részlegen keresztül is: Szervezet > Részlegek.) Itt megadhatja, hogy bizonyos szakszervezetben vagy helyen lévő alkalmazottak eltérő növekményszázalékot kapjanak. A **Költségvetés** és a **Pénznem** mezők csak tájékoztatásul szolgálnak, és felhasználhatók a költségvetés pénznemének megjelölésére.

## <a name="set-up-the-compensation-process"></a>Kompenzációs folyamat beállítása
A feldolgozási események lehetővé teszik a kompenzációs feldolgozás paramétereinek megadását. Ez magában foglalja a kompenzációs összegek meghatározásához szükséges értékelési időszakot és az új kártérítési összegek hatályba lépésének időpontját.

Tetszés szerint egy fix fizetés arányosított felvételi dátumot is beírhat, ha fix kompenzációs konstrukció százalékos felvételi szabályt használ. Az ilyen konstrukciók esetében a ciklus kezdő dátuma után és a fix fizetés arányosított felvételi dátuma előtt alkalmazott emberek a kiszámított érdem vagy az általános emelés 100%-át kapják. A fix fizetés arányosított felvételi dátuma után és a ciklus záró dátuma előtt alkalmazott emberek a kiszámított emelés egy részét kapják meg, amelyet annak alapján számolnak ki, hogy a teljes ciklusban hány napig voltak alkalmazásban. Például ha a ciklus január 1. és december 31. között tart, és a fix fizetés arányosított felvételi dátuma április 1-jei, a márciusban felvett alkalmazott a teljes kiszámított emelést kapja, míg a július 1-jén felvett alkalmazott a kiszámított emelés körülbelül felét.

Az **Időpont szerinti** feldolgozási esemény dátum csak bizonyos változó kompenzációs konstrukciók feldolgozására szolgál, és nem mutatjuk be itt. Az **Átvizsgálási határidő** az a határidő, amellyel minden ajánlást meg kell tenni annak érdekében, hogy az új kompenzációs összegek betölthetőek legyenek az alkalmazotti rekordba. Az átvizsgálás dátuma csak tájékoztatásra szolgál.

A feldolgozási esemény paramétereinek mentése után kattinthat a **Beállítás** gombra, hogy megadja a feldolgozásba bevenni kívánt konstrukciókat, valamint hogy milyen fix kompenzációs műveletet kell végrehajtani minden egyes konstrukcióhoz.

Kattintson a **Hozzáadás** gombra a **Csomagok** lapon egy kompenzációs konstrukció feldolgozási eseményhez történő hozzáadása érdekében. A **Más emelés használata**, **Emelési tényező** és **Emelés leírása** oszlopok csak a változó kompenzációs konstrukciók használatosak, és nem tartoznak ebbe a témakörbe.

Mentse a rekordot, majd kattintson a **Hozzáadás** gombra a **Műveletek** lapon a fix kompenzációs műveletek kijelölt konstrukcióhoz való hozzáadásához. Használja az **Ajánlás engedélyezése** lehetőséget, ha a művelethez más összeget szeretne megadni, mint a kiszámított előirányzott növekmény. Ha azt szeretné, hogy egy művelet az előző, több kompenzációs konstrukciót összekapcsoló művelet eredménye alapján legyen kiszámolva, jelölje be az **Előző eredmény használata** lehetőséget. A fix kompenzációs műveletek a kompenzációs logika olyan típusai, amelyeknek jól felismerhető neveket adhat. Fokozatos vagy széles sávú konstrukciójú terv esetén csak a következő típusú fix kompenzációs műveleteket adhatja hozzá:

| Fix kompenzációs művelet típusa | Funkciók                                                                                                                                                                                                                                                                                                                                                                                                    |
|-------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Részvény                        | A tőkeműveletek összehasonlítják az alkalmazott fizetési díjalapját a ciklus záródátumától a legalacsonyabb hivatkozási ponttal az alkalmazott munkakörében szereplő szintig. Ha az alkalmazott fizetési díjalap kisebb mint a minimális hivatkozási pont, ki kell számítani az alkalmazottnak a tartomány minimális pontjára való emelése értékét.                                                                                |
| Érdem                         | Az érdemen alapuló tevékenységek az alkalmazott fizetési díjalapjára alapozva számítanak ki egy emelést a ciklus záró dátuma és az alkalmazott részlegének, szakszervezetének és helyének fix növekményes költségvetésében található növekményszázalék alapján.                                                                                                                                                                                         |
| Általános                       | Az általános műveletek az emelést egy Százalék alapján számítják ki, vagy fix összeget adnak az alkalmazottaknak. Ez az **Általános** lap **Rögzített kompenzáció** részének beállításai alapján történik.                                                                                                                                                                                                                        |
| Előléptetés                     | A promóciós műveletek megadják azt a megnevezett helyet, ahol emelést alkalmazhat, ezért figyeljen arra, hogy jelölje be az **Ajánlás engedélyezése** lehetőséget, amelynek segítségével ajánlást adhat a promóciókat kapó alkalmazottaknak.  A javasolt emeléssel nem rendelkező alkalmazottak fix kompenzációs rekordjaihoz a **Promóció** művelet nem lesz hozzáadva.                                                                       |
| Egyéb szintváltás            | Az előző példában A **Lefokozás** a **Fix kompenzációs** művelet neve **Egyéb szintváltás** típussal. Ez egy 0 (nulla módosítás) előirányzott növekményt hoz létre, így beírhat egy ajánlási összeget az alkalmazott fizetési díjalapjának módosításához. (Figyeljen arra, hogy jelölje meg az **Ajánlás engedélyezése** lehetőséget.) Az ajánlással nem rendelkező alkalmazottak fix kompenzációs rekordjához ez a művelet nem adódik hozzá. |

Lépés típusú tervhez kizárólag Lépés típusú **Fix kompenzációs** műveleteket adhat hozzá.

| Fix kompenzációs művelet típusa | Funkciók                                                                                                                                                                                           |
|--------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Lépés                           | Az Általános lapon adja meg, hogy ez a Lépés művelet az alkalmazottakat 0, 1 vagy két lépéssel vigye előre az alkalmazottakat.                                                                                  |
|                                | **0 lépés** – Az alkalmazott megkapja az aktuális lépés fizetési díjalapját.                                                                                                                      |
|                                | **1 lépés** – A rendszer ellenőrzi, hogy az alkalmazott a szintje utolsó hivatkozási pontjánál van-e már.                                                                                             |
|                                | **2 lépés** – A rendszer az alkalmazottat az aktuális szintjéhez képest két lépéssel helyezi előre. Megtörténhet, hogy a rendszer csak akkor helyezi előre az alkalmazottat az egy vagy nulla lépések esetén, ha azok elérik a szintjük legutóbbi hivatkozási pontját. |

## <a name="run-the-compensation-process"></a>A kompenzációs folyamat futtatása
Miután a Feldolgozási eseményben beállította a szükséges dátummezőket, terveket és műveleteket, kattinthat a **Folyamat futtatása** lehetőségre a **Feldolgozási esemény** lapon. Ezzel megnyitja a **Kompenzációfeldolgozási események futtatása** párbeszédpanelt. A párbeszédablakban kattintson a **Feldolgozási eredmények megjelenítése** lehetőségre, hogy megtudja, hogyan számolták ki a kompenzációs összegeket az egyes alkalmazottak esetében. Az **OK** gombra történő kattintással futtatja a kompenzációs folyamatot minden olyan alkalmazott esetében, akik a kiválasztott kompenzációs tervekben vannak a ciklus záró dátuma szerint.

## <a name="view-the-process-results"></a>Folyamateredmények megtekintése
A folyamat eredményeinek megtekintéséhez nyissa meg a **Folyamateredmények** lapot. A feldolgozási esemény futtatásakor minden alkalommal létrejön egy új kompenzációs esemény. Ily módon tesztelheti, módosíthatja és többször is futtathatja a kompenzációs eseményt, hogy lássa, milyen hatással vannak a különböző események az alkalmazotti kompenzációra.

A **Folyamateredmények** lap információkat tartalmaz a folyamat futtatásáról, ideértve a futtatás idejét, a folyamatot futtató felhasználót, valamint hogy történtek-e hibák a folyamat futtatása során. Megjelölheti a **Zárolt** lehetőséget is a **Kompenzáció betöltése** gomb letiltásához, valamint hogy letilthasson másokat arról, hogy betöltség a kompenzációs eseményeket az alkalmazottak rekordjaiba. Az **Alkalmazottak eredményei** gombra történő kattintással megjeleníti a futtatásban szereplő alkalmazottak listáját.

Az **Alkalmazotti eredmények** opció magáról a folyamatról nyújt információkat, továbbá minden, a folyamat során végrehajtott kompenzációs műveletről. A **Fix kompenzáció** szakasz rekordot tartalmaz minden olyan műveletről, amely megtalálható a kompenzációs csomag feldolgozott eseményében. A **Jelenlegi iránymutatások** és az **Ajánlások** oszlopok további információkat jelenítenek meg a **Fix kompenzáció** szakaszban kijelölt művelettel kapcsolatban. Ha a művelet mellett az **Ajánlások engedélyezése** be van jelölve, az Ajánlás mezők szerkeszthetők. Ez lehetővé teszi az alkalmazotthoz tartozó összegek manuális korrekcióját. Megjegyzés: ha az **Előző eredmény használata** lehetőséget jelölte be a Feldolgozási esemény műveletéhez, manuálisan kell frissítenie minden függő művelet összegeit.

Miután a kompenzációs összegeket egy alkalmazottra nézve ellenőrizték és a javasolt értékekre megtörténtek a módosítások, módosíthatja az **Állapot** lehetőséget az **Alkalmazotti esemény** sorban annak jelzésére, hogy az esemény engedélyezve van-e vagy figyelmen kívül kell hagyni. Szükség esetén törölheti az alkalmazott ajánlásánál tett módosításokat az **Újraszámítás** gombra kattintva. Ezzel Figyelmen kívül hagyva állapottal jelöli meg a létező alkalmazotti eseményt, és új alkalmazotti eseményt hoz létre újraszámított értékekkel.

## <a name="loading-approved-compensation-changes"></a>Jóváhagyott kompenzációs módosítások betöltése
Amint egy vagy több alkalmazotti eseményállapota Jóváhagyva értékre módosul, ezek betölthetők az alkalmazottak Fix kompenzációs rekordjaiba. Ezt úgy teheti meg, hogy vagy egyenként kijelöl minden alkalmazotti eseményt, és az **Alkalmazotti eredmények** lapon az **Alkalmazotti kompenzáció betöltése** gombra kattint, vagy kattint a **Kompenzáció betöltése** lehetőségre a **Folyamateredmények** lapon az összes jóváhagyott alkalmazotti események egyszerre történő betöltéséhez.

Kattintson az **OK** gombra a **Kompenzáció betöltése** párbeszédpanelen, amellyel hozzáadja a nullától különböző kompenzációs műveletsorokat az **Alkalmazott fix kompenzációja** lapon.
