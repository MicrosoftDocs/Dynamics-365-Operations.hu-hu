---
title: Pénznem-adattípus áttelepítése kettős írás esetén
description: Ez a témakör azt mutatja be, hogyan lehet módosítani azoknak a tizedesjegyeknek a számát, amelyeket a kettős írás támogat a pénznemhez.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-04-06
ms.openlocfilehash: 78820ff49958fc3b474038c0fcd126bcf6886d0d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560823"
---
# <a name="currency-data-type-migration-for-dual-write"></a>Pénznem-adattípus áttelepítése kettős írás esetén

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

A pénznemneknél legfeljebb 10 értékű tizedesjegyszám-növelés használható. Az alapértelmezett korlát négy tizedesjegy. A tizedesjegyek számának növelésével megakadályozhatja, hogy az adatvesztést szenvedjen, amikor a kettős írással szinkronizálja az adatokat. A tizedeshelyek számának növekedése egy választható változás. A végrehajtásához segítséget kell kérnie a Microsofttól.

A tizedesjegyek számának módosítási folyamata két lépésből áll:

1. Áttelepítés kérése a Microsofttól.
2. A tizedes jegyek számának csökkentése a Dataverse megoldásban.

Az Finance and Operations alkalmazásnak és a Dataverse megoldásnak a pénznemben azonos számú tizedesjegyet kell támogatnia. Ellenkező esetben adatvesztés fordulhat elő, ha ez az információ szinkronizálva van az alkalmazások között. Az áttelepítési folyamat újrakonfigurálja a pénznem- és árfolyamértékek tárolásának módját, de az adatok nem módosulnak. Az áttelepítés befejeződése után a pénznemkód és az árképzés tizedesjegyei száma növelhető, és a felhasználó által megadott és megtekintett adatok több tizedesjegy pontossággal is rendelkezhetnek.

A migráció nem kötelező. Ha több tizedesjegyet támogatása hasznos lehet Önnek, ajánlott fontolóra venni a migrációt. Azoknak a szervezeteknek, amelyeknek nem szükséges négy tizedesjegynél pontosabb érték, nem kell áttelepíteniük.

## <a name="requesting-migration-from-microsoft"></a>Áttelepítés kérése a Microsofttól

A meglévő pénznemoszlopok esetében a Dataverse nem támogat négy tizedesjegynél többet. Ezért az áttelepítési folyamat során a program átmásolja az adatbázis új belső oszlopaiba a pénznemek értékeit. Ez a folyamat addig történik folyamatosan, amíg az összes adatot át nem telepítik. A belső működést tekintve, az áttelepítés végén az új tárolási típusok felülírják a régi tárolási típusokat, de az adatértékek változatlanok. A pénznem oszlop így már legfeljebb 10 tizedesjegyet képes támogatni. Az áttelepítési folyamat alatt a Dataverse megszakítás nélkül használható.

Ugyanekkor az árfolyamok úgy módosulnak, hogy legfeljebb 12 tizedesjegyet támogassanak az aktuális 10-es határ helyett. Ennek a módosításnak meg kell lennie, hogy a tizedesjegyek száma megegyezzeb mind a Finance and Operations alkalmazásban, mind a Dataverse megoldásban.

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

![Pénznem rendszerbeállításai](media/currency-system-settings.png)

### <a name="business-management-currencies"></a>Üzleti menedzsment: Pénznemek

Ha azt szeretné, hogy az adott pénznemre vonatkozó pontossági érték eltérjen az árképzéshez használt pénznem pontosságától, akkor ez módosítható. Nyissa meg a **Beállítások \> Üzleti menedzsment** lehetőséget, válassza ki a **Pénznemek** elemet, majd válassza ki a módosítani kívánt pénznemet. Ezt követően állítsa be a **Pénznem pontossága** oszlopot a kívánt tizedesjegyek számával, ahogy az a következő ábrán látható.

![Adott területi beállításhoz tartozó pénznemek beállításai](media/specific-currency.png)

### <a name="tables-currency-column"></a>táblák: Pénznem oszlop

A megadott pénznem oszlopokhoz konfigurálható tizedesjegyek száma legfeljebb négy lehet.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]