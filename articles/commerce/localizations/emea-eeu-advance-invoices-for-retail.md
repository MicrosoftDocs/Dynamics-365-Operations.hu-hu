---
title: Commerce előlegszámlák (Kelet-Európa)
description: Ez a témakör bemutatja az előzetes értesítések beállítását a Commerce megoldásban Kelet-Európa esetében.
author: epopov
manager: annbe
ms.date: 10/23/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Retail, Operations
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: fc2af93880b634e6cec0015a2469fb8e4e56a7d7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408032"
---
# <a name="advance-invoices-for-commerce-for-eastern-europe"></a>Commerce előlegszámlák (Kelet-Európa)

[!include [banner](../includes/banner.md)]

Ez a témakör a kelet-európai honosításra vonatkozik, és a kereskedelemmel foglalkozik.

Lengyelország, Magyarország és Csehország számára egy vevőtől Point of Sale (POS) keresztül előleg érkezése esetén adózási szempontból regisztrálni kell az előleget, és szükséges egy előzetes számla dokumentum generálása és kinyomtatása, amely tartalmazza az előleg összegét. Ezenkívül Lengyelországban az előzetes számlatranzakciókat fel kell adni a főkönyvbe.

Az értékesítési rendelés számlájának feladásakor a végső dokumentumnak tartalmaznia kell az előlegszámlát, és bármely előleget meg kell jelölni.

Értékesítési rendelések készítéskor a Kinnlevőségekből, manuálisan generálnia kell előlegszámlákat az itt ismertetettek szerint: [Előlegszámlák Kelet-Európa számára](https://docs.microsoft.com/dynamics365/unified-operations/financials/localizations/emea-advance-invoice). Ha értékesítési rendeléseket POS útján generál, a rendszer létrehozza és feladja az előlegszámlákat.

## <a name="supported-scenarios"></a>Támogatott esetek

A varázsló a következő forgatókönyveket támogatja:

- Előlegszámla készítése és feladása.
- Módosítsa a letét összegét. Ha egy ügyfél úgy dönt, hogy növeli a letét összegét, további előlegszámla kibocsájtása történik. Minden egyéb módosításkor a letét összegén (például ha szerkeszti a vevői rendelést), a korábban létrehozott előlegszámlához jóváírás jön létre, és új előlegszámla készítése és feladása történik a helyesbített összeggel.
- Értékesítési rendelés, amely hozzá van kapcsolva az előlegszámlákhoz, érvénytelenítése. Ebben az esetben az előlegszámlához jóváírás jön létre.
- Értékesítési rendelési számla, amely hozzá van kapcsolva az előlegszámlákhoz, feladása. Az értékesítési rendeléshez kapcsolódó előlegszámla sztornírozott az értékesítési számla értékéig. Az előlegszámla tranzakció kiegyenlítése egy előlegszámla sztornírozás tranzakcióval történik.

## <a name="set-up-advance-invoices"></a>Előlegszámlák beállítása

### <a name="turn-on-the-functionality-for-creating-advance-invoices"></a>Az előlegszámlák létrehozásához a funkció bekapcsolása

1. Menjen a **Kiskereskedelem és kereskedelem \> Központ beállítása \> Paraméterek \> Kiskereskedelmi paraméterek** lehetőségre.
2. A **Vevői rendelések** lapon, a **Rendelés** gyorslapon állítsa a **Letéti előlegszámla létrehozása** lehetőséget **Igen** beállításra.

### <a name="define-the-parameters-for-posting-advance-invoices"></a>Az előlegszámlák feladásához tartozó paraméterek meghatározása

1. Lépjen a **Kinnlevőségek \> Beállítások \> Kinnlevőségek paraméterei** pontra.
2. A **Frissítések** lapon, az **Előlegszámla** gyorslapon, állítsa be a **Feladási profil**, **Áfacsoport** és **Cikkáfacsoport** mezőket. Ha ezek a mezők helyesen vannak beállítva, az előlegszámlát feladja a rendszer. Ha ezek a mezők nincsenek beállítva, előlegszámla nem lesz feladva.

### <a name="turn-off-posting-of-the-sales-tax-on-prepayment-journal-voucher"></a>Áfa az előlegnapló-bizonylaton feladási kikapcsolása

Az áfa az előlegnapló-bizonylaton nem adódhat fel, ha az előlegszámla feladása ki van kapcsolva. Ha ellenőrizni szeretné, hogy ez a követelmény teljesül-e, kövesse az alábbi lépéseket.

1. Lépjen a **Kinnlevőségek \> Beállítások \> Kinnlevőségek paraméterei** pontra.
2. Az **Főkönyv és áfa** lapon, a **Fizetés** gyorslapon gondoskodjon arról, hogy a következő mezők üresek legyenek vagy a beállításuk legyen **Nem**:

    - Áfa az előlegnapló-bizonylaton
    - Feladási profil az előlegnapló-bizonylathoz
    - Előleg adócsoportja
    - Cikkáfacsoport

## <a name="print-advance-invoices"></a>Előlegszámlák nyomtatása

A pénztárból származó előlegszámlákat egy Microsoft Windows-nyomtatón, amely a hardverállomáshoz van csatlakoztatva, lehet nyomtatni. Az előlegszámla nyomtatása a pénztár esetében két lehetőség kínálkozik:

- **Előlegszámla nyomtatása miután egy tranzakció lezárult a pénztáron.** Ezt a lehetőséget automatikusan megtörténik, ha előlegszámla jött létre, és a Windows-nyomtató helyesen be van állítva. Ebben az esetben csak az utolsó előlegszámla, amely kapcsolódik a vevői rendeléshez, lesz kinyomtatva.
- **A tranzakciónaplóból egy előzetes számla kinyomtatása.** Válassz a **Napló megjelenítése** lehetőséget a tranzakciók naplójának megnyitásához, keresse meg a vevői rendelést, és válassza az **Előlegszámla nyomtatása** elemet. Ebben az esetben minden számla, amely kapcsolódik a vevői rendeléshez, lesz kinyomtatva.

### <a name="set-up-a-windows-printer"></a>Windows-nyomtató beállítása

Kövesse az alábbi lépéseket ahhoz, hogy a Windows-nyomtatón, amely a hardverállomásra csatlakozik, a pénztárból származó dokumentumok nyomtatva legyenek.

1. Lépjen a **Kiskereskedelem és kereskedelem \> Csatorna beállítás \> POS beállítás \> POS profilok \> Hardverprofilok** pontra.
2. Válassza ki a hardverprofilt, amelyek az üzlethez kapcsolódik, ahol a nyomtatót használják.
3. A **Nyomtató** vagy a **Nyomtató 2** szakaszban, a beállítások frissítése:

    - A **Nyomtató** mezőben válassza: **Windows-illesztőprogram**.
    - Az **Eszköznév** mezőben adja meg a nyomtató nevét.

4. Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem informatika \> Elosztási ütemezés** pontra.
5. Válassza ki az **1090** munkát és kattintson a **Futtatás most** lehetőségre.
