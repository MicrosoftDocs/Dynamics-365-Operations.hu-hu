---
title: Az elszámolóárra való átalakítás előfeltételei
description: Ez a témakör az elszámolóárra való átalakítás futtatása előtt végrehajtandó feladatokat ismerteti.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 50891
ms.assetid: 73af66cf-c924-45be-837a-a648dbd05a31
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: da5605e3542cfb8803b6a9f3645bcb2cc613c0bd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429690"
---
# <a name="prerequisites-for-a-standard-cost-conversion"></a>Az elszámolóárra való átalakítás előfeltételei

[!include [banner](../includes/banner.md)]

Ez a témakör az elszámolóárra való átalakítás futtatása előtt végrehajtandó feladatokat ismerteti. 

Mielőtt futtatná az elszámolóárra való átalakítást, tegye a következőket:

1.  Határozzon meg egy **cikkmodell-csoport** modult az elszámolóárakhoz. A cikkmodell-csoportok lap használatával hozzon létre olyan cikkmodell-csoportot, amely egy elszámolóáras készletmodellt használ. Az elszámolóárra történő átalakítás beállításakor ezt a cikkmodell-csoportot fogja hozzárendelni az átalakítandó cikkekhez.
2.  Minden cikkhez rendeljen hozzá egy **költségcsoport** modult.
    -   A beszerzett cikkhez hozzárendelt költségcsoport az elszámolóárakhoz kapcsolódó főkönyvi számlák alapjaként működhet. Ebbe beleérthető a főkönyvi számlák beszerzési árak eltéréseihez való hozzárendelése. Gyártási környezetben a hozzárendelt költségcsoport határozza meg a költségek szegmentálását a gyártott cikk számított költségeiben.
    -   A gyártott cikkhez hozzárendelt költségcsoportnak alapvető szerepe lehet a főkönyvi számlák hozzárendelésében, mint például főkönyvi számlák termelési különbözetekhez rendelésénél.

3.  Rendeljen a termékhez egy **szokásos rendelési mennyiség** modult, ha a költségei állandók. Egy termék szokásos rendelési mennyisége könyvelési adagméretként viselkedik az állandó költségek amortizációjához vagy arányosításához. Ezek lehetnek beállítási idők az útvonalműveletekhez, vagy egy állandó összetevőmennyiség egy anyagjegyzékben (AJ).
4.  Rendeljen hozzá **főkönyvi számlákat**, amelyek kapcsolódnak az elszámolóárakhoz, különösen az átértékelési eltéréshez. Használja a **Feladás** lapot (**Készletkezelés** &gt; **Beállítás**) elszámolóárakhoz kapcsolódó főkönyvi számlák hozzárendeléséhez. Az elszámolóárra történő átalakításhoz legalább az átértékelési eltérés számláját meg kell adnia minden cikkre és minden költségcsoportra. A **Számlatükör** lapon határozza meg az elszámolóárhoz szükséges főkönyvi számlákat. A **Tranzakciókombinációk** képernyőt használva engedélyezze a költségkapcsolatokat (táblázatokhoz, csoportokhoz és mindenhez), mielőtt megadná a cikkfeladási szabályokat.
5.  Adja meg az elszámolóárhoz tartozó készletparamétereket. Használja a **Számsorozatok** lapot a **Készlet- és raktárkezelési paraméterek** oldalon, és rendeljen hozzá egy számsorozatot az átértékelési bizonylatokhoz. Az átértékelési bizonylat generálására akkor kerül sor, amikor az elszámolóárra történő átalakítás eredményei megváltoztatják a cikk készletértékét. A **Készlet- és raktárkezelési paraméterek** oldal használatával határozzon meg Költségszabályozási paramétereket (A **Készletkönyvelés** panelen), hogy meghatározza az elszámolóárhoz tartozó két paramétert.
    -   Használja a **Költséglebontás** mezőt, és válassza a Nem vagy Részfőkönyv lehetőséget. A Részfőkönyv választása az aktív költséglebontást jelenti. Az aktív költséglebontásnak meghatározó szerepe van az elszámolóár-elemek többszintű termékszerkezetének teljes keresztmetszetén át a költségcsoport szegmentálás kiszámításában, megőrzésében és megtekintésében. Ha a költséglebontás aktív, a következőket jelentheti és elemezheti egy egyszintű, többszintű vagy teljes formátumban:
        1.  Készlet
        2.  Folyamatban lévő munka
        3.  Eladott áruk beszerzési értéke (COGS) költségcsoportonként

        Az aktív költséglebontás azt jelenti, hogy egy legyártott cikk költségét engedélyezi, az eredmény a költségcsoport-szegmentálásban, a cikk költségrekordjában lesz eltárolva. Ha nem ír be értéket a **Költséglebontás** mezőbe, ez azt jelenti, hogy a költségcsoport-szegmentálás nem lesz fenntartva az elszámolóáras cikkeknél. Vagyis a legyártott cikk elszámolóára egy költségcsoport-szegmentálás nélküli önálló összegként lesz kiszámítva és karbantartva, és a gyártott összetevők költség-hozzájárulásai egy önálló összegbe lesznek összegyűjtve.
    -   Az **Eltérések a szabványtól** mező segítségével válassza ki az összesítve vagy a költségcsoportonként lehetőséget. A költségcsoportonként opció lehetővé teszi, hogy költségcsoportonként azonosítsa a beszerzési árkülönbözeteket és termelési eltéréseket. Ez lehetővé teszi, hogy azonosíthassa a négyfajta termelési eltérést (adagméret, mennyiség, ár és helyettesítési eltérések). Az összesítve opciót kiválasztása azt jelenti, hogy nem lehet költségcsoport szerint szétválasztani a különbözeteket, és nem lehet azonosítani a négyféle termelési eltérést. Csak egy összesített gyártási különbözetet lesz látható. A szokásos különbözetekkel kapcsolatos szabályok a költséglebontás szabályaitól függetlenek. Vagyis megteheti hogy nem választ ki egy költséglebontási szabályt sem, és a költségcsoportonkénti különbözeteket pedig úgy választja ki, hogy a költségcsoportonkénti gyártási különbözetek mégis meg lesznek tartva.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]