---
title: Global Inventory Accounting főkönyv
description: Ez a témakör a Global Inventory Accounting főkönyvét írja le, amelyeket egy pénznem, egy naptár, egy megállapodás és egy jogi személy és egy jogi személy kombinációja határoz meg.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e956bac61df4b694ef347b804fed139e9e22e6f95d1bac7ea483a07946cb110f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722439"
---
# <a name="global-inventory-accounting-ledger"></a>Global Inventory Accounting főkönyv

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

A Global Inventory Accounting szolgáltatásnak saját főkönyvi készlete van. A rendszer minden alkalommal, amikor egy adott jogi személy készlettel kapcsolatos tranzakcióját feldolgozhatja, a rendszer szükség esetén bármilyen számú Global Inventory Accounting főkönyvet figyelembe tud venni a tranzakcióért.

A főkönyv a tartozások és a jóváírások mértékei. Ezek az intézkedések a költségelemek és az arelikszámlák alapján vannak osztályozva. A Global Inventory Accounting főkönyvét egy pénznem, egy naptár, egy megállapodás és egy jogi személy és egy jogi személy kombinációja határoz meg.

A Global Inventory Accounting főkönyvek beállításához menjen a **Global inventory accounting \> Beállítás \> Global inventory accounting főkönyvek** lehetőségre. Állítsa be a következő mezőket minden egyes főkönyvhöz:

- **Név** – Írja be a főkönyv nevét.
- **Leírás** – Adja meg a főkönyv leírását.
- **Pénzügyi naptár** – Adja meg a főkönyv pénzügyi naptárát.
- **Pénznem és árfolyamtípus** – A gyorsététi űrlap mezőivel kiválaszthatja a főkönyvben használt könyvelési pénznemet, valamint az árfolyam típusát. A kiválasztott pénznem eltérhet a jogi személy által használt pénznemtől. A Global Inventory Accounting szolfáltatásban a felhasználók a lehető legtöbb költségszámítási főkönyvet meghatározhatják. A Global Inventory Accounting támogatja a készletek könyvelését több pénznemben és többféle értékelésben. Állítsa be a következő mezőket:

    - **Pénznem** – A készlettel kapcsolatos értékek karbantartásához használt költségszámítási pénznem kiválasztása. Ezek közé tartozik a készletérték, az eladott áruk beszerzési értéke, az átmenő készlet és minden különbözet.
    - **Árfolyamtípus** – Válassza ki, hogy milyen árfolyamot használ a rendszer a tranzakció összegének a tranzakció pénznemében történő átváltása során, valamint a cikkek elszámolóárát a költségszámítási pénznemre.

- **Megállapodás neve** – Egy megállapodás megadása. A szabályok olyan irányelvek gyűjteménye, amelyek meghatározzák a költségek főkönyvben való könyvelésének a mikéntjét.
- **Jogi személy** – A főkönyv figyelembe veszi a kijelölt jogi személynek feladott dokumentumokat.
- **Alapeset** – Annak kiválasztása, hogy a főkönyv létrehozása előtt létrehozott készlettranzakciókat a főkönyvben használt pénznem és megállapodás szerint kell-e feldolgozni. Válasszon a következő értékek közül:

    - **Aktiválva** – A főkönyvnek fel kell feldolgoznia a főkönyv létrehozása előtt létrehozott tranzakciókat.
    - **Deaktiválva** – A főkönyvnek csak a főkönyv létrehozása után létrehozott tranzakciókat kell feldolgoznia.

    > [!IMPORTANT]
    > Az új dokumentumok beíratás után **nem** lehet visszatérni és beállítani ezt a mezőt.

- **Állapot** – A rendszer automatikusan a *Felkészülés* állapotra állítja az újonnan létrehozott főkönyvek állapotát.
