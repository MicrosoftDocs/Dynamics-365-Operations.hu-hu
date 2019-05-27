---
title: Az elszámolóár előfeltételei
description: Ez a témakör az elszámolóár használatának alaplépéseit fedi le.
author: AndersGirke
manager: AnnBe
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventStdCostConv, CostingVersion
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d5a4a4e49ef1cee923011ddab24497c65f85c1e3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1547813"
---
# <a name="prerequisites-for-standard-costs"></a>Az elszámolóár előfeltételei

[!include [banner](../includes/banner.md)]

Ez a témakör az elszámolóár használatának alaplépéseit fedi le. A további lépések a vállalati működéstől függenek. Például a lépések eltérőek nem termelési környezet, útvonal nélküli termelési környezet és útvonalakat használó termelési környezet esetén. 

Az elszámolóár beállításához kövesse az alábbi lépéseket.

**1. Hozzon létre egy cikkmodellcsoportot az elszámolóáraknak.**

Használja a **Cikkmodellcsoportok** lapot, és hozzon létre egy új csoportot az elszámolóárhoz, és rendeljen hozzá egy **Elszámolóár** készletmodellt. A cikkmodellcsoport azonosítójának kifejezőnek kell lennie, például: **Elszámolóár**. Jelölje be a jelölőnégyzeteket annak jelzésére, hogy a csoportnak lehetővé kell tennie a pénzügyi negatív készleteket, és hogy fizikai leltárt és pénzügyi leltárt kell feladnia. Ez az elszámolóáras csoport cikkekhez kerül hozzárendelésre.

**2. Határozza meg az elszámolóár különbözeteihez tartozó főkönyvi számlákat.** 

A **Számlatükör adatai** képernyő segítségével határozza meg az elszámolóár különbözeteihez tartozó főkönyvi számlákat. Ahhoz hogy a főkönyvi számlák a **Feladás** képernyőn hozzárendelhetőek legyenek, előbb meg kell határozni őket. A főkönyvi számlák cikkcsoportokat és költségcsoportokat tükrözhetnek vissza.

**3. Rendeljen főkönyvi számlákat az elszámolóár-eltérésekkel kapcsolatos cikkfeladásokhoz.** 

Használja a **Feladás** oldalt a elszámolóár-eltérésekkel kapcsolatos főkönyvi számlák hozzárendeléséhez. Eldöntheti, hogy egy eltérés főkönyvi számláját cikk (vagy cikkcsoport) és költségcsoport (vagy költségcsoport-típus) szerint adja meg, vagy megadhatja, hogy a főkönyvi számla minden cikkre és költségcsoportra vonatkozzon. Ezek a lehetőségek összefüggenek a táblázatok, csoportok és mindenki költségkapcsolataival. 

Cikkfeladási szabályok megadása előtt a **Tranzakciókombinációk** képernyőt használva engedélyezze a költségkapcsolatokat (táblázatokhoz, csoportokhoz és mindenhez).

**4. Adja meg az elszámolóárhoz tartozó készletparamétereket.** 

-  A **Készletkönyvelés** képernyő használatával határozzon meg költségszabályozási paramétereket a **Készletkönyvelési irányelvek beállítása > Paramérerek** oldalon, hogy meghatározza az elszámolóárhoz tartozó két költség-ellenőrzési paramétert.

    -  A **Költséglebontás** mezőben válassza a **Nem** vagy **Részfőkönyv** lehetőséget. Ha a **Részfőkönyv** lehetőséget választja, a költséglebontás egy *aktív* költség lebontását jelenti. Az aktív költséglebontásnak meghatározó szerepe van az elszámolóár-elemek többszintű termékszerkezetének teljes keresztmetszetén át a költségcsoport szegmentálás kiszámításában, megőrzésében és megtekintésében. Ha a költséglebontás aktív, lehet jelenteni és elemezni a készletet, a folyamatban lévő munkát és a költségcsoportonkénti eladott áruk beszerzési értékét (ELÁBÉ) egyszintű, többszintű vagy teljes formában. Ha a költséglebontás aktív, az azt jelenti, hogy ha egy legyártott cikk költségét aktiválja, a költségcsoport-szegmentálás a cikk költségrekordjában lesz eltárolva. 

    -  Ha a **Nincs** lehetőséget választja, a költségcsoport-szegmentálás nem lesz karbantartva az elszámolóáras cikkeknél. Más szóval a legyártott cikk elszámolóára egyetlen összegként lesz kiszámítva és karbantartva, költségcsoport-szegmentálás nélkül. A gyártott összetevők költség-hozzájárulásai egyetlen összegbe lesznek összegyűjtve.

-  Az **Eltérések a szabványtól** mező segítségével válassza ki az **Összesítve** vagy a **Költségcsoportonként** lehetőséget. Ha a **Költségcsoportonként** opciót választja, költségcsoportonként azonosíthatja a beszerzési árkülönbözeteket és termelési eltéréseket. Így azonosíthatja a négyfajta termelési eltérést: adagméret, mennyiség, ár és helyettesítési eltérések. Az **Összesítve** opció kiválasztása azt jelenti, hogy nem lehet költségcsoport szerint szétválasztani a különbözeteket, és nem lehet azonosítani a négyféle termelési eltérést. Csak egy összesített gyártási különbözetet lesz látható.

-  A szokásos különbözetekkel kapcsolatos szabályok a költséglebontás szabályaitól függetlenül működnek. Más szavakkal megteheti hogy költséglebontási szabályként a **Nincs** lehetőséget választja, és a költségcsoportonkénti különbözeteket pedig úgy választja ki, hogy a költségcsoportonkénti gyártási különbözetek mégis meg lesznek tartva.

**5. Költségszámítási verziók készítése az elszámolóárakhoz.** 

A **Költségszámítási verzió beállítása** képernyő segítségével hozzon létre egy vagy több költségszámítási verziót az elszámolóárakhoz. Mindegyik költségszámítási verziót egy **Elszámolóáras** költségszámítási típushoz kell hozzárendelni, és a tartalmában engedélyeznie kell a költségadatokat.

**6. Egy létező ügyfél előkészítése az elszámolóárak használatára** 

Azoknak a vevőknek, akik a meglévő cikkeiket át kívánják alakítani elszámolóáras készletmodellbe, az **Átalakítások elszámolóárra** képernyőt kell használniuk.


<a name="related-topics"></a>Kapcsolódó témakörök
--------

[Átalakítás elszámolóárra – áttekintés](standard-cost-conversion-overview.md)

### <a name="blogs"></a>Blogok

#### <a name="community-blogs"></a>Közösségi blogok

- [Közvetlen anyagok költségének beállítása Dynamics 365 for Finance and Operations](https://financefunction.tech/2018/06/07/how-to-set-up-standard-costs-for-direct-materials-in-dynamics-365-for-finance-and-operations)
- [Szokásos közevetlen munkaerő-költségek: Dynamics 365 for Finance and Operations](https://financefunction.tech/2018/07/16/standard-direct-labor-cost-in-dynamics-365-for-finance-and-operations)
