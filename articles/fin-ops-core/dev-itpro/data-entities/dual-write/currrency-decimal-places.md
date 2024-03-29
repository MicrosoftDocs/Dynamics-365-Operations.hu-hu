---
title: Pénznem-adattípus áttelepítése kettős írás esetén
description: Ez a témakör azt ismerteti, hogyan lehet módosítani a kettős írással pénznemek szempontjából támogatott tizedesjegyek számát.
author: RamaKrishnamoorthy
ms.date: 12/08/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-04-06
ms.openlocfilehash: 327d6ced7fca4bdae1fd80928086dafed6b0f931
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289714"
---
# <a name="currency-data-type-migration-for-dual-write"></a>Pénznem-adattípus áttelepítése kettős írás esetén

[!include [banner](../../includes/banner.md)]



A pénznemneknél legfeljebb 10 értékű tizedesjegyszám-növelés használható. Az alapértelmezett korlát négy tizedesjegy. A tizedesjegyek számának növelésével megakadályozhatja, hogy az adatvesztést szenvedjen, amikor a kettős írással szinkronizálja az adatokat. A tizedeshelyek számának növekedése egy választható változás. A végrehajtásához segítséget kell kérnie a Microsofttól.

A tizedesjegyek számának módosítási folyamata két lépésből áll:

1. Áttelepítés kérése a Microsofttól.
2. A tizedes jegyek számának csökkentése a Dataverse megoldásban.

A Pénzügy és műveletek alkalmazásnak Dataverse, és ugyanannak a tizedesjegyszámnak kell támogatottnak lennie a pénznemértékek között. Ellenkező esetben adatvesztés fordulhat elő, ha ez az információ szinkronizálva van az alkalmazások között. Az áttelepítési folyamat újrakonfigurálja a pénznem- és árfolyamértékek tárolásának módját, de az adatok nem módosulnak. Az áttelepítés befejeződése után a pénznemkód és az árképzés tizedesjegyei száma növelhető, és a felhasználó által megadott és megtekintett adatok több tizedesjegy pontossággal is rendelkezhetnek.

A migráció nem kötelező. Ha több tizedesjegyet támogatása hasznos lehet Önnek, ajánlott fontolóra venni a migrációt. Azoknak a szervezeteknek, amelyeknek nem szükséges négy tizedesjegynél pontosabb érték, nem kell áttelepíteniük.

## <a name="requesting-migration-from-microsoft"></a>Áttelepítés kérése a Microsofttól

A meglévő pénznemoszlopok esetében a Dataverse nem támogat négy tizedesjegynél többet. Ezért az áttelepítési folyamat során a program átmásolja az adatbázis új belső oszlopaiba a pénznemek értékeit. Ez a folyamat addig történik folyamatosan, amíg az összes adatot át nem telepítik. A belső működést tekintve, az áttelepítés végén az új tárolási típusok felülírják a régi tárolási típusokat, de az adatértékek változatlanok. A pénznem oszlop így már legfeljebb 10 tizedesjegyet képes támogatni. Az áttelepítési folyamat alatt a Dataverse megszakítás nélkül használható.

Ugyanekkor az árfolyamok úgy módosulnak, hogy legfeljebb 12 tizedesjegyet támogassanak az aktuális 10-es határ helyett. Erre a módosításra azért van szükség, hogy a tizedesjegyek száma a pénzügyi és a műveletalkalmazásban és a Dataverse.

Az áttelepítés nem változtatja meg az adatokat. A pénznem és az árfolyam oszlop átalakítását követően az adminisztrátor beállíthatja, hogy a rendszer legfeljebb 10 tizedesjegyet használjon a pénznem oszlopoknak, az egyes tranzakciós pénznemek és árképzések tizedesjegyszámának megadásával.

### <a name="request-a-migration"></a>Áttelepítés kérése

Ha elérhetővé szeretné tenni ezt a funkciót, írjon e-mailt a **CDSExpandDecimal@microsoft.com** címre, és a következő adatokat tartalmazza:

+ **Tárgy:** A kiterjesztett tizedesjegy-támogatás engedélyezésére irányuló kérelem \<organizationID\> számára
+ **E-mail törzse:** Szeretném engedélyezni a kiterjesztett decimális támogatását a szervezetem számára – \<organizationID\>.

A Microsoft egy képviselője a következő lépések elvégzéséért két-három munkanapon belül kapcsolatba fog lépni Önnel.

Áttelepítés esetén a következő adatokat kell figyelembe venni, és ennek megfelelően kell tervezni:

+ Az adatok áttelepítéséhez szükséges idő a rendszerben található adatok mennyiségétől függ. A nagyméretű adatbázisok áttelepítése több napot is igénybe vehet.
+ Az adatbázis mérete ideiglenesen nő az áttelepítés futtatása közben, mivel az indexekhez további hely szükséges. A további lemezterület többsége felszabadítható az áttelepítés befejezésekor.
+ Az áttelepítési folyamat során, ha olyan hibák történnek, amelyek megakadályozzák az áttelepítés befejezését, a rendszer figyelmeztetéseket küld a Microsoft terméktámogatásnak, hogy a támogató munkatársak beavatkozhassanak. Ha azonban az áttelepítés során hibák is lépnek fel, a Dataverse rendszeres használatra továbbra is teljes mértékben elérhető.
+ Az áttelepítési folyamat nem vonható vissza.

## <a name="changing-the-number-of-decimal-places"></a>A tizedesjegyek számának módosítása

Az áttelepítés befejeződése után a Dataverse több tizedesjegyet tartalmazó számokat tárolhat. Az adminisztrátorok meghatározhatják, hogy hány tizedesjegyet kell használni meghatározott pénznemkód és árképzés esetében. A Microsoft Power Apps, Power BI és Power Automate ezután több tizedesjegyet tartalmazó számok megjelenítésére és használatára használható.

A módosítás érdekében a következő beállításokat kell frissítenie Power Apps megoldásban:

+ **Rendszerbeállítások: Pénznem pontossága az árképzéshez** – A **Pénznem pontosságának beállítása, amely az árképzéshez használt a rendszer egészében** oszlop határozza meg, hogy a pénznem milyen módon viselkedjen a szervezetnél, amikor az **Árképzési pontosság** be van jelölve.
+ **Üzleti menedzsment: Pénznemek** – A **Pénznem pontossága** oszlopban egyéni számú tizedesjegyet lehet megadni egy adott pénznemhez. A szervezeti szintű beállításokra vissza lehet állni.

Vannak bizonyos limitációk:

+ A pénznem oszlop nem állítható be egy táblára.
+ Négy tizedesjegynél több tizedesjegyet csak az **Árképzés** és a **Tranzakciós pénznem** szintjén lehet megadni.

### <a name="system-settings-currency-precision-for-pricing"></a>Rendszerbeállítások: Az árképzéshez használt pénznem pontossága

Az áttelepítés befejeződése után az adminisztrátorok meghatározhatják a pénznem pontosságát. Nyissa meg a **Beállítások \> Adminisztráció** elemet, és válassza a **Rendszerbeállítások** elemet. Ezt követően az **Általános** lapon módosítsa a **Pénznem pontosságának beállítása, amely az árképzéshez használt a rendszer egészében** beállítás értékét, ahogyan az a következő ábrán látható.

![Pénznem rendszerbeállításai.](media/currency-system-settings.png)

### <a name="business-management-currencies"></a>Üzleti menedzsment: Pénznemek

Ha azt szeretné, hogy az adott pénznemre vonatkozó pontossági érték eltérjen az árképzéshez használt pénznem pontosságától, akkor ez módosítható. Nyissa meg a **Beállítások \> Üzleti menedzsment** lehetőséget, válassza ki a **Pénznemek** elemet, majd válassza ki a módosítani kívánt pénznemet. Ezt követően állítsa be a **Pénznem pontossága** oszlopot a kívánt tizedesjegyek számával, ahogy az a következő ábrán látható.

![Adott területi beállításhoz tartozó pénznemek beállításai.](media/specific-currency.png)

### <a name="tables-currency-column"></a>Táblák: Pénznem oszlop

A megadott pénznem oszlopokhoz konfigurálható tizedesjegyek száma legfeljebb négy lehet.

### <a name="default-currency-decimal-precision"></a>Pénznem alapértelmezett tizedes pontossága
Az alapértelmezett pénznem tizedes pontosságának áttelepítés és nem áttelepítési helyzetek esetén várható viselkedését lásd az alábbi táblázatban. 

| Létrehozás dátuma:  | Pénznem tizedesmezője    | Létező szervezet (a Pénznem mező nincs áttelepítve) | Létező szervezet (Pénznemmező áttelepítve) | Az új szervezet által létrehozott felépítési 9.2.21062.00134 |
|---------------------------------------------------------|-------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------|------------------------------------------------|
| Pénznemmező létrehozva a pénznemkódok 9.2.21111.00146  |     |  |       |
|    | A felhasználói felületen látható maximális pontosság   | 4 számjegy    | 10 számjegy    | N/A    |
| | Maximális pontosság látható az adatbázis- és adatbázis-lekérdezés eredményének felhasználói felületén         | 4 számjegy   | 10 számjegy   | N/A    |
| Pénznemmező létrehozva a pénznemkódok 9.2.21111.00146 |    |  |     |   |
|   | A felhasználói felületen látható maximális tizedes pontosság     | 4 számjegy   | 10 számjegy   | 10 számjegy     |
|          | Az adatbázis- és adatbázis-lekérdezés eredményének felhasználói felületén látható maximális tizedes pontosság | 10 számjegy. Azonban csak 4 lényeges a 4 tizedesjegyet túllépő nullák esetén. Ez a szervezet szükség esetén egyszerűbb és gyorsabb áttelepítését teszi lehetővé. | 10 számjegy      | 10 számjegy     |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

