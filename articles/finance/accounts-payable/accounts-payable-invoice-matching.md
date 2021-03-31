---
title: Kötelezettségek számlaegyeztetése – áttekintés
description: A kötelezettségek számlaegyeztetése a szállítói számla, a beszerzési rendelés és a termékbevételezés egyeztetési folyamatát jelenti.
author: abruer
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoicePostingHistory
audience: Application User
ms.reviewer: roschlom
ms.custom: 27361
ms.assetid: 9f3dace7-05d8-4974-8f85-aca2e224876c
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1ecbfdd157985899da04aa6b41d9a96cdf2fa6bc
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213044"
---
# <a name="accounts-payable-invoice-matching-overview"></a>Kötelezettségek számlaegyeztetése – áttekintés

[!include [banner](../includes/banner.md)]

A kötelezettségek számlaegyeztetése a szállítói számla, a beszerzési rendelés és a termékbevételezés egyeztetési folyamatát jelenti.

Az egyeztetett dokumentumok közötti különbségeket egyeztetési eltéréseknek nevezzük. Az egyeztetési eltéréseket a rendszer összeveti a megadott tűréshatárokkal. Amennyiben az egyezési eltérés meghaladja a tűréshatár-százalékot vagy összeget, a Szállítói számla lapon, illetve a Számlázási előzmények és egyeztetési részletek lapon egyeztetési eltérés ikonok jelennek meg. 

Például beszerzési rendelést visz be 1,00 darabáron 1000 telepet tartalmazó egyetlen sorral. Megtörténik a beszerzési rendelés jóváhagyása és elküldése a szállító számára. A szállító leszállítja az 1000 telepet, a rendszerbe beviszik az 1000 telepet 1,00 egységárral tartalmazó termékbevételezést. A telepek készletárát a rendszer ezzel az árral frissíti. 

Számla érkezik 1000 telepről 1,10 darabárral. A jogi személyekre vonatkozó irányelvek az ilyen kategóriájú cikkekhez 5 százalék nettó egységár-különbözeti tűrést engednek meg. 1,05 elfogadható lenne árként, de 1,10 nem. A számla adatainak bevitelekor a rendszer felismeri az áregyeztetési eltérést, és a számlát menteni lehet, amíg meg nem történik az eltérés feloldása.

A Kötelezettségek számlaegyeztetése funkció következő típusai használhatók:

-   Számlaösszegek egyeztetése – A számlán szereplő végösszegek és a beszerzési rendelésen szereplő végösszegek egyeztetése. Az ilyen típusú számlaegyeztetés a legkevésbé részletes, így ez a lehetőség olyan ellenőrzések beállítására használható, amelyek minimálisra csökkentik a számlaegyeztetés áttekintésére fordítandó munkaidőt.
-   Kétirányú egyeztetés – A számlán szereplő árinformációk és a beszerzési rendelésen szereplő árinformációk egyeztetése.
-   Háromirányú egyeztetés – A számlán szereplő árinformációk és a beszerzési rendelésen szereplő árinformációk egyeztetése. Ezenkívül a számlán szereplő mennyiségadatok és a számlához kiválasztott termékbevételezéseken szereplő mennyiségadatok egyeztetése.
-   Költségek egyeztetése – A számlán szereplő költséginformációk (összegek) és a beszerzési rendelésen szereplő költséginformációk (összegek) egyeztetése.

> [!NOTE]
> A számlaellenőrzés más formái a szállítói számla irányelveinek segítségével hajthatóak végre. 

A kétirányú és a háromirányú egyeztetés mindig az egységár alapján egyezteti az árinformációkat. Úgy is beállíthatja ezeket az egyeztetési módokat, hogy az árinformációk egyeztetése a teljes ár alapján történjen.
-   Nettó egységárak egyeztetése – A kétirányú vagy háromirányú egyeztetés árinformációinak egyeztetése a számla minden egyes sorára számított nettó egységárak és a beszerzési rendelésen szereplő ugyanezen nettó egységárak összehasonlításával. A nettó egységár számítása a következő képlettel történik: A sorban szereplő Nettó összeg / A sorban szereplő Mennyiség
-   Teljes árak egyeztetése – A kétirányú vagy háromirányú egyeztetés árinformációinak egyeztetése a számla minden egyes sorára számított nettó összegek (teljes árak) és a beszerzési rendelésen szereplő ugyanezen nettó összegek összehasonlításával. A nettó összeg számítása a következő képlettel történik: *(Egységár \* A sorban szereplő Mennyiség) + A sorban szereplő Költségek - A sorban szereplő Engedmények*. Teljes árak egyeztetése során százalékkal, a rendszer a tranzakciós pénznem használatával hasonlítja össze az értékeket. Teljes árak egyeztetése során mennyiség alapján, a rendszer a könyvelési pénznem használatával hasonlítja össze az értékeket.

A számlaegyeztetési számítások legtöbbször automatikusan történnek, amikor a Szállítói számla lapon szállítói számlákat szerkeszt. Másik lehetőségként a számlaegyeztetés igény szerinti időpontban is végrehajtható. A jogi személyre nézve az igény szerint lefuttatható számlaegyeztetés a Számla ellenőrzése lap Kötelezettségek paraméterei oldalán, a Számlafejléc állapotának automatikus frissítése lehetőséggel vezérelhető. A számlaegyeztetés a számlaellenőrzési folyamat részeként is elvégezhető. A számlaegyeztetés eredményeit a Szállítói számla oldalon és a kapcsolódó számlaegyeztetési oldalakon tekintheti meg.

## <a name="invoice-totals-matching"></a>Számlaösszegek egyeztetése
A számlaösszegek egyeztetése annak biztosításában nyújt segítséget, hogy a számlák végösszegei és a várható összegek egy elfogadható eltérésnél nagyobb mértékben ne különbözzenek. A Számlaösszegek egyeztetésének részletei oldalon a következő táblázatban szereplő hat összeg összehasonlítására kerül sor. Ha a számlaösszegek egyeztetésének megengedhető tűréshatára 20%, akkor az engedmény teljes összegének 100%-os eltérése egyeztetési eltérésként jelenik meg.

| Összeg mező    | Tényleges számlaösszeg | Várt számlaösszeg | Eltérés százaléka | Egyeztetési állapot |
|----------------|----------------------|------------------------|---------------------|--------------|
| Egyenleg        | 495,00               | 495,00                 | 0%                  | Megfelelt       |
| Összengedmény | 0,00                 | 9,90                   | 100%                | Sikertelen       |
| Költségek        | 64,90                | 64,90                  | 0%                  | Megfelelt       |
| Forgalmi adó      | 139,98               | 137,50                 | 2%                  | Megfelelt       |
| Lekerekítés      | 0,00                 | 0,00                   | 0%                  | Megfelelt       |
| Számla összege | 699,88               | 687,50                 | 2%                  | Megfelelt       |

A jogi személyre nézve a számlaösszegek egyeztetését a Számlaösszegek egyeztetése gomb kezeli, amit a Kötelezettségek paraméterei oldalon talál meg. A rendszer a várt számlaösszegek és a tényleges Számlaösszegek egyeztetését hajtja végre. A várt számlaösszegek számítása a beszerzési rendelésben található árak, költségek és áfaadatok, valamint a számlán szereplő mennyiségek alapján történik.

## <a name="two-way-price-totals-matching"></a>Teljes árak kétirányú egyeztetése
Kétirányú egyeztetés használatával elősegítheti annak biztosítását, hogy a beszerzési rendelésen, illetve a számlán szereplő áradatok közti eltérés az elfogadható tűréshatárokon belül maradjon. Összehasonlíthatja az összes, a számla egyes soraiban feltüntetett nettó összegekre vonatkozó árinformációt és az összes függőben lévő, illetve korábban feladott számlasort a megfelelő beszerzési rendelési sorral. Ezt teljes árak egyeztetésének nevezzük. 

A teljes árak egyeztetése történhet százalék, összeg, vagy százalék és összeg alapján. 

Ha a teljes beszerzési ár tűréshatárát százalékban adja meg, akkor öt mező összehasonlítására kerül sor, a következő táblázatban bemutatottak szerint. Mivel a teljes beszerzési ár tűréshatára 10 %, 50 %-os eltérés a teljes árban egyeztetési eltérésként jelenik meg.

| Egyeztetési állapot | Számla nettó összege | Várható nettó összeg | Nem egyeztetett teljes beszerzési ár (eltérés összege) | Nem egyeztetett teljes beszerzési ár százalékos értéke (eltérés százalékos értéke) | Beszerzési ár teljes tűréshatárának százaléka |
|--------------|--------------------|---------------------|--------------------------------------------------|-----------------------------------------------------------------|----------------------------------------|
| Megfelelt       | 105,00             | 100,00              | 5,00                                             | 5%                                                              | 10%                                    |
| Sikertelen       | 150,00             | 100,00              | 50,00                                            | 50%                                                             | 10%                                    |

Ha a teljes beszerzési ár tűréshatárát összegként adja meg, akkor öt mező összehasonlítására kerül sor, a következő táblázatban bemutatottak szerint. Mivel a teljes beszerzési ár tűréshatárának összege 100,00, 105,00 összegű eltérés a teljes árban egyeztetési eltérésként jelenik meg.

| Egyeztetési állapot | Számla nettó összege | Várható nettó összeg | Nem egyeztetett teljes beszerzési ár (eltérés összege) | Nem egyeztetett teljes beszerzési ár a könyvelés pénznemében (eltérés összege) | Beszerzési ár teljes tűréshatára |
|--------------|--------------------|---------------------|--------------------------------------------------|-------------------------------------------------------------------------|--------------------------------|
| Megfelelt       | 150,00             | 100,00              | 50,00                                            | 50,00                                                                   | 100,00                         |
| Sikertelen       | 205,00             | 100,00              | 105,00                                           | 105,00                                                                  | 100,00                         |

Ha a teljes árak egyeztetése egy százalékos tűréshatár és egy tűréshatár-összeg (más néven túllépési határ) alapján történik, sorok egyeztetési eltéréseinek megállapításakor a rendszer mindkét tűréshatárt tekintetbe veszi. Ha a százalékos érték és az összeg bármelyike meghaladja a tűréshatárt, az egyeztetési eltérésként jelenik meg, amint a következő táblázat 150,00 és 205,00 sorai mutatják.

| Egyeztetési állapot | Számla nettó összege | Várható nettó összeg | Nem egyeztetett teljes beszerzési ár százalékos értéke (eltérés százalékos értéke) | Beszerzési ár teljes tűréshatárának százaléka | Nem egyeztetett teljes beszerzési ár a könyvelés pénznemében (eltérés összege) | Beszerzési ár teljes tűréshatára |
|--------------|--------------------|---------------------|-----------------------------------------------------------------|----------------------------------------|-------------------------------------------------------------------------|--------------------------------|
| Megfelelt       | 105,00             | 100,00              | 5%                                                              | 10%                                    | 5,00                                                                    | 100,00                         |
| Sikertelen       | 150,00             | 100,00              | 50%                                                             | 10%                                    | 50,00                                                                   | 100,00                         |
| Sikertelen       | 205,00             | 100,00              | 105%                                                            | 10%                                    | 105,00                                                                  | 100,00                         |

A jogi személyre nézve a kétirányú egyeztetést a Soregyeztetési irányelv mező kezeli, amelyet a Kötelezettségek paraméterei oldalon talál meg. Az Egyeztetési irányelv felülbírálásának engedélyezése mező beállításától függően választhatja a kétirányú egyeztetést egy adott szállítóra, cikkre, illetve ezek kombinációjára vonatkozóan az Egyeztetési irányelv oldalon, valamint egy adott beszerzési rendelésre vonatkozóan a Beszerzési rendelés oldalon.

A jogi személyre nézve a teljes árak egyeztetését a Teljes árak egyeztetése mező kezeli, amit a Kötelezettségek paraméterei oldalon talál meg. Ugyanezen a lapon adhatja meg a teljes beszerzési ár tűréshatárának százalékos értékét és a tűréshatár összegét (a túllépési határt).

## <a name="two-way-net-unit-price-matching"></a>Nettó egységárak kétirányú egyeztetése
Kétirányú egyeztetés használatával elősegítheti annak biztosítását, hogy a beszerzési rendelésen, illetve a számlán szereplő áradatok közti eltérés az elfogadható tűréshatárokon belül maradjon. Összehasonlíthatja a számlán szereplő minden egyes cikkre vonatkozó nettó egységár-adatokat. Ezt nettó egységárak egyeztetésének nevezzük. 

A Számlaösszegek egyeztetésének részletei oldalon a következő táblázatban szereplő kilenc sorérték összehasonlítására kerül sor. Ha a nettó egységárak egyeztetésének megengedhető ártűréshatára 10%, akkor a nettó egységár 22,61%-os eltérése egyeztetési eltérésként jelenik meg.

| Sor mező                    | Számlaérték | Beszerzési rendelés értéke | Eltérés százaléka | Egyeztetési állapot |
|-------------------------------|---------------|----------------------|---------------------|--------------|
| Egységár                    | 55,40         | 55,38                | 0%                  | Megfelelt       |
| Áregység                    | 1,00          | 1,00                 | 0%                  | Megfelelt       |
| Beszerzések költségei          | 50,00         | 0,00                 | 100%                | Sikertelen       |
| Kedvezmény                      | 0,00          | 0,00                 | 0%                  | Megfelelt       |
| Engedményszázalék              | 0,00          | 0,00                 | 0%                  | Megfelelt       |
| Többsoros engedmény            | 0,00          | 0,00                 | 0%                  | Megfelelt       |
| Többsoros kedvezmény százaléka | 0,00          | 0,00                 | 0%                  | Megfelelt       |
| Nettó összeg                    | 271,60        | 221,52               | 22,61%              | Sikertelen       |
| Nettó egységár                | 67,9000       | 55,3800              | 22,61%              | Sikertelen       |

A jogi személyre nézve a kétirányú egyeztetést a Soregyeztetési irányelv mező kezeli, amelyet a Kötelezettségek paraméterei oldalon talál meg. Az Egyeztetési irányelv felülbírálásának engedélyezése mező beállításától függően választhatja a kétirányú egyeztetést egy adott szállítóra, cikkre, illetve ezek kombinációjára vonatkozóan az Egyeztetési irányelv oldalon, valamint egy adott beszerzési rendelésre vonatkozóan a Beszerzési rendelés oldalon. 

A jogi személyre nézve a nettó egységárak egyeztetését a Számlaegyeztetés ellenőrzésének engedélyezése mező kezeli, amit a Kötelezettségek paraméterei oldalon talál meg. A nettó egységár-különbözeti tűréshatár százalékos értéke beállítható cikkekre, cikkcsoportokra, szállítókra, szállítói csoportokra, cikk és szállító kombinációira vagy jogi személyre vonatkozóan az Árkülönbözet tűréshatárai oldalon.

## <a name="two-way-price-totals-matching-and-net-unit-price-matching"></a>Teljes árak és nettó egységárak kétirányú egyeztetése
Teljes árakat és nettó egységárakat együttesen is egyeztethet. Ez a példa a következő beállításokat feltételezi:

-   A nettó egységár-különbözeti tűréshatár az USB Meghajtó cikk esetén 10%.
-   A teljes árak egyeztetési tűréshatára a jogi személy esetén 15 %, illetve 500,00.

A beszerzési rendelés tartalmazza a következő sort.

| Cikkszám | Mennyiség | Egységár | Nettó összeg |
|-------------|----------|------------|------------|
| USB Meghajtó   | 1000    | 10,00      | 10000,00  |

Három számlát viszünk be a következő táblázatnak megfelelően. A 3. Számla esetén számlaegyeztetési eltérés lép fel, mivel az 1880,00 értékű eltérés meghaladja a teljes beszerzési árra vonatkozó, 500,00 értékű tűréshatár összeget. Teljes árak egyeztetésekor a számla nettó összege minden korábban feladott számlát tartalmaz a mellett a számla mellett, amellyel jelenleg dolgozik.

| Cikkszám          | Mennyiség | Egységár | Nettó összeg | Áregyeztetés | Teljes ár egyeztetése |
|----------------------|----------|------------|------------|-------------|-------------------|
| 1. Számla: USB Meghajtó | 800      | 10,80      | 8640,00   | Megfelelt      | Megfelelt            |
| 2. Számla: USB Meghajtó | 100      | 10,80      | 1080,00   | Megfelelt      | Megfelelt            |
| 3. Számla: USB Meghajtó | 200      | 10,80      | 2160,00   | Megfelelt      | Sikertelen            |
| Összesen                |          |            | 11880,00  |             |                   |

## <a name="three-way-matching"></a>Háromirányú egyeztetés

A háromirányú egyeztetés segítségével biztosíthatja, hogy a beszerzési rendelésen, illetve a számlán szereplő áradatok közti eltérés az elfogadható tűréshatárokon belül maradjon, illetve hogy a számlán és a megfelelő termékbevételezéseken szereplő mennyiség megegyezzen.

A Számlaösszegek egyeztetésének részletei oldalon a kétirányú egyeztetésnek megfelelő sorértékek összehasonlítására kerül sor. Ezenkívül a számlán szereplő mennyiségeket is egyezteti a rendszer a már bevételezett mennyiségekkel. Amennyiben a számlán szereplő mennyiség eltér az egyeztetett termékbevételezési mennyiségtől, mennyiségegyeztetési hiba lép fel.

| Sor mező                    | Számlaérték | Beszerzési rendelés értéke | Eltérés százaléka | Egyeztetési állapot |
|-------------------------------|---------------|----------------------|---------------------|--------------|
| Egységár                    | 55,40         | 55,38                | 0%                  | Megfelelt       |
| Áregység                    | 1,00          | 1,00                 | 0%                  | Megfelelt       |
| Beszerzések költségei          | 50,00         | 0,00                 | 100%                | Sikertelen       |
| Kedvezmény                      | 0,00          | 0,00                 | 0%                  | Megfelelt       |
| Engedményszázalék              | 0,00          | 0,00                 | 0%                  | Megfelelt       |
| Többsoros engedmény            | 0,00          | 0,00                 | 0%                  | Megfelelt       |
| Többsoros kedvezmény százaléka | 0,00          | 0,00                 | 0%                  | Megfelelt       |
| Nettó összeg                    | 271,60        | 221,52               | 22,61%              | Sikertelen       |
| Nettó egységár                | 67,9000       | 55,3800              | 22,61%              | Sikertelen       |

| Sor mező                     | Számlaérték | Egyeztetési állapot |
|--------------------------------|---------------|--------------|
| Számlázási mennyiség               | 4,00          |              |
| Az összes egyeztetett termékbevételezés | 0,00          | Sikertelen       |

A jogi személyre nézve a háromirányú egyeztetést a Soregyeztetési irányelv mező kezeli, amelyet a Kötelezettségek paraméterei oldalon talál meg. Az Egyeztetési irányelv felülbírálásának engedélyezése mező beállításától függően választhatja a háromirányú egyeztetést egy adott szállítóra, cikkre, illetve ezek kombinációjára vonatkozóan az Egyeztetési irányelv oldalon, valamint egy adott beszerzési rendelésre vonatkozóan a Beszerzési rendelés oldalon.

## <a name="charges-matching"></a>Költségek egyeztetése
A költségek egyeztetése annak biztosításában nyújt segítséget, hogy a költségek összegei és a várható összegek egy elfogadható százalékos eltérésnél nagyobb mértékben ne különbözzenek. A Költségértékek összehasonlítása - Számla: oldalon történik minden egyes, a számlára és a beszerzési rendelésre vonatkozó költségkód végösszegeinek összehasonlítása, amint az a következő táblázatban látható. Ha a költségkód megengedhető tűréshatára 25%, akkor a licencköltség-kód 99999999999,99%-os eltérése egyeztetési eltérésként jelenik meg.

> [!NOTE] 
> A 99999999999,99 %-os eltérés azt jelenti, hogy a beszerzési rendelés alapján várt érték 0 és a számlán pozitív tényleges érték szerepel. 

| Költségek egyeztetési állapota | Számla költségkódja | Tényleges számított összérték | Várt számított összérték | Különbözet összege | Eltérés százaléka | Százalékos tűréshatár |
|----------------------|----------------------|-------------------------------|---------------------------------|-----------------|---------------------|----------------------|
| Sikertelen               | Licenc              | 25                            | 0                               | 25              | 99999999999,99%  | 25%                  |
| Megfelelt               | Fuvardíj              | 200                           | 200                             | 0               | 0%                  | 25%                  |
| Sikertelen               | Sürgős             | 4                             | 2                               | 2               | 100%                | 25%                  |

A jogi személyre nézve a költségek egyeztetését a Költségek egyeztetése gomb kezeli, amit a Kötelezettségek paraméterei oldalon talál meg. A Költségtűréshatárok oldalon állíthatja be a költségekre vonatkozó különbözeti tűréshatár százalékos értékeit.

> [!NOTE]
> A költségek egyeztetése csak olyan költségkódok esetén hajtható végre, amelyekre a Költségkód oldalon található Beszerzési rendelés és számla értékeinek összehasonlítása lehetőség ki van választva.

## <a name="related-functionality"></a>Kapcsolódó funkció
A szállítói számlák gyakran a tényleges szállítmányoknak megfelelő termékbevételezéseken alapulnak, nem a beszerzési rendeléseken. Időnként a számlázott összegek nem felelnek meg a beszerzési rendelés összegeinek, és időnként a kiszállított mennyiségek nem felelnek meg a számlázott mennyiségeknek. A következő módszerekkel megkönnyítheti ezeknek az adatoknak a kezelését:
-   Hozzon létre szállítói számlákat termékbevételezések alapján. Számlák létrehozásakor automatikus javaslatként megjelennek a termékbevételezések, és kiválaszthatja, hogy melyik termékbevételezést kívánja használni. Amennyiben szükséges, több beszerzési rendelésből is kiválaszthat adott termékbevételezési sortételeket.
-   Tekintse meg és hagyja jóvá a számlán szereplő számlázott mennyiség és a termékbevételezésen szereplő bevételezett mennyiség közti mennyiségi különbségeket. Ha különböznek az értékek, elmentheti a számlát és később egyeztetheti azt egy másik termékbevételezéssel, vagy módosíthatja a számlázott mennyiséget úgy, hogy megegyezzen a bevételezett mennyiséggel.
-   Vigye be az eredeti bevételezési rendelésben fel nem tüntetett számlaösszegeket, hogy a számla adatai megegyezzenek a szállítótól kapott számláéival. Összehasonlíthatja a beszerzési rendelés költségeit a számlák költségeivel. Ha szükséges, költségeket adhat a számlákhoz és számlasorokhoz rendelheti azokat.
-   Tekintse meg és hagyja jóvá a számlán szereplő nettó egységár és a beszerzési rendelésen szereplő nettó egységár közti eltéréseket. Az árkülönbözeti tűréshatár-százalékok beállíthatóak jogi személyekre, szállítókra vagy cikkekre vonatkozóan. Ha a szállítói számlasorban lévő ár kívül esik az árkülönbözeti tűréshatáron, a feladás jóváhagyásáig vagy a szállító helyesbítésének beérkezéséig mentheti a számlát.

További tudnivalók: [Háromirányú egyeztetési irányelvek](three-way-matching-policies.md) és [A kötelezettségek modul beállítása a számlaegyeztetés ellenőrzéséhez](tasks/set-up-accounts-payable-invoice-matching-validation.md). 






[!INCLUDE[footer-include](../../includes/footer-banner.md)]