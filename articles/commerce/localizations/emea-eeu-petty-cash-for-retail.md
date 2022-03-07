---
title: Commerce pénztárkezelés (Kelet-Európa)
description: Ez a témakör leírja, hogyan lehet beállítani és használni a készpénzkezelő funkciókat a Commerce esetében Kelet-Európában.
author: epopov
ms.date: 10/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.search.industry: Retail
ms.author: epopov
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 7a4c2e404b42a10a8d5f8b57135c56ae479a9efc3f5a8cef30831d02a3e53fe6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6719912"
---
# <a name="petty-cash-management-for-commerce-for-eastern-europe"></a>Commerce pénztárkezelés (Kelet-Európa)

[!include [banner](../includes/banner.md)]

A cikk közép-kelet-európai kereskedelemi iparághoz alkalmazkodó lokalizálásokról tartalmaz információkat.

A kelet-európai könyvelési előírásoknak megfelelően beállíthat műveleteket készpénzes számlákhoz a nyugták, készpénzdokumentumok és készpénzjelentések folyamatainak automatizálása érdekében. További információ: [(EEUR) Paraméterek beállítása a készpénzkezeléshez](/dynamicsax-2012/appuser-itpro/eeur-set-up-parameters-for-cash-management).

A kiskereskedők fogadhat különböző típusú fizetés ellenében a termékek és szolgáltatások, amelyek értékesítik. A leggyakrabban használt képernyő Fizetési ugyan a készpénz kiskereskedők is bevételezhető fizetési bizonylatok, kártyák és csekkek formájában. Kiskereskedelmi Pénztár (POS) készpénz, a hitelkártya-bizonylatokat és egyéb kifizetések feldolgozása egy készpénz keresztül.

A következőket teheti a készpénz-kezeléssel a Commerce megoldásban:

- Hozzon létre egy készpénzes számlára, az egyes üzletek kimutatási módszerét a választott fizetési mód.
- Pénztárnaplók segítségével készpénztranzakciók feladása, a vevői kifizetések, amely a retail POS érkeznek.
- Egy kivonatsor-tranzakciók összevonása, a kimutatás feladásakor. Csökkentett csepp összesítését, banki csepp, Bizonylattranzakciók, eltávolíthatja fizetési tranzakciók, váltópénz adatbeviteli tranzakciókról, bevételi tranzakciók, Projektköltség-tranzakciókhoz, a vevői kifizetések, értékesítési tranzakciók, és visszáru-tranzakciók.

Az összes kerül sor, a POS terminálon tranzakcióit a főkönyvi napló segítségével. Készpénz-kifizetési naplók, a vevői kifizetési naplók és a főkönyvi naplók segítségével létrehozása és a kimutatások feladása. További információ: [Kiskereskedelmi üzlet kimutatásainak létrehozása, kiszámítása és feladása](/dynamics365/unified-operations/retail/tasks/create-calculate-post-statement-retail-store).

A **Feladott kimutatások** oldalon, a műveleti ablak, a következőket teheti:

- Menjen a **Lekérdezések \> Készpénz-kifizetési napló** a kimutatáshoz kapcsolódó készpénzfizetési naplók eléréséhez.
- Kattintson ide: **Lekérdezések \> Általános napló** a vevői kifizetések és a készpénzfizetések kivételével a kimutatás kapcsolódó főkönyvi naplók eléréséhez.

## <a name="set-up-for-cash-management-for-pos"></a>Beállítás pénzgazdálkodáshoz a POS rendszerhez

A pénzgazdálkodás használata előtt a következő műveletet kell beállítania:

- Fizetéstípus beállítása minden olyan fizetési módhoz, amelyet a kiskereskedő elfogad a **Fizetéstípusok** képernyőn. Különféle fizetési módokat használhat a költségtranzakciók feladásához a POS esetében. A fizetés módokkal kapcsolatos további tudnivalókat lásd: [Fizetési módok](/dynamics365/unified-operations/retail/payment-methods).
- Paraméterek beállítása a készpénzes folyamatokhoz.
- Készpénzes fizetés fizetési mód beállítása az üzletekben.

### <a name="set-up-parameters-for-cash-operations"></a>Paraméterek beállítása a készpénzes folyamatokhoz

Beállíthatja a paramétereket a készpénzes tranzakciók Commerce megoldásbeli létrehozásához és feladásához. Használhat készpénz-kifizetési naplókat, vevői kifizetési naplókat vagy főkönyvi naplókat az értékesítési tranzakciók és a fizetési tranzakciók feladásához a pénztárban. A kimutatás feladásakor a megegyező tulajdonságokkal rendelkező tranzakciókat összevonhatja.

1. Menjen a **Kiskereskedelem és kereskedelem \> Központ beállítása \> Paraméterek \> Kiskereskedelmi paraméterek** lehetőségre. A bal oldali panelen kattintson a **Feladás** gombra.
2. A **Feladás** területen, az **Aggregáció** gyorslapon állítsa a **Fizetőeszköz eltávolítása/váltópénz** beállítását **Igen** beállításra, ha a kimutatás feladásakor összesíteni szeretné a fizetési tranzakciók eltávolítását vagy a kivonatsorral társított váltópénz-tranzakciókat. Amikor készpénzt távolít el a POS pénztárfiókból, a rendszer létrehozza a fizetőeszköz kivételének tranzakcióját. Amikor készpénzt tesz be a POS pénztárfiókjába, a rendszer létrehozza a váltópénz tranzakcióját.
3. Aktiválja az alábbi paranétereket a kivonatsorhoz társított tranzakciókat összesítéséhez a kimutatás feladásakor:

    - **Banki befizetés** – A banki tranzakciók összesítése.
    - **Széfes befizetés** – A széfes tranzakciók összesítése.
    - **Bevételi/kiadási tranzakciók** – Bevételi és kiadási tranzakciók összegzése.
    - **Bizonylattranzakciók** – Bizonylattranzakciók összesítése.
    - **Vevői kifizetések** – Vevői kifizetések összesítése.
    - **Értékesítés és visszáru** – Értékesítés és visszáru-tranzakciók összesítése.

4. A **Kifizetések** gyorslapon válassza ki a megjelenő alapértelmezett naplónevet a következő lehetőségekhez:

    - **Vevői fizetési napló** – Ez a napló a vevői fizetések feladásához használatos.
    - **Készpénzes fizetési napló** – Ez a napló a készpénzes fizetések feladásához használatos.
    - **Általános napló** – Ez a napló a nem készpénzes és vevői kifizetésektől eltérő tranzakciók feladásához használandó.

### <a name="set-up-a-payment-method-for-cash-payments-in-a-store"></a>Készpénzes fizetés fizetési mód beállítása az üzletekben

A következő eljárással készpénzes fizetés fizetési mód beállítása az üzletekben.

1. Ugorjon a következő oldalra: **Kiskereskedelem és kereskedelem \> Csatornák \> Üzletek \> Minden kiskereskedelmi üzlet**.
2. A **Minden kereskedelmi üzlet** listaoldalon jelölje ki azt az üzletet, amelyhez fizetési módokat kíván beállítani.
3. A Műveleti ablaktáblán a **Beállítás** lapon a **Beállítás** csoportban kattintson a **Fizetési módok** lehetőségre.
4. A **Fizetési mód** lapon hozzon létre vagy válasszon egy fizetési módot.
5. A **Feladás** gyorslapon a **Számla** mezőcsoportban, a **Számlatípus** mezőben válassza ki **Készpénzszámla** elemet.

    > [!NOTE]
    > Csak akkor választhatja a **Készpénzszámla** elemet a **Számlatípus** mezőben, ha bejelöli a **Normál** vagy a **Fizetőeszköz-eltávolítási/váltópénz** lehetőséget a **Funkció** mezőben.

6. A **Számlaszám** mezőben válasszon ki egy készpénzszámla a fizetési mód.
7. A **Fizetőeszköz eltávolítása/váltópénz** mezőcsoportban található **Ellenszámla** mezőben, válassza ki az ellenszámla feladása fizetőeszköz kivétele vagy váltópénz-adatbeviteli tranzakciókról, a fizetési mód.

> [!NOTE]
> Ellenszámlát kell beállítani a fizetőeszköz készpénzes fizetés fizetési mód és a fizetőeszköz eltávolítása vagy váltópénz-bejegyzés üzlet fizetési módhoz. Ez a fizetőeszköz eltávolítása vagy váltópénz-bejegyzés tranzakciókhoz ellensúlyozott főkönyvi tételeket hoz létre.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]