---
title: Global Inventory Accounting főkönyv
description: Ez a cikk a globális készletkönyvelés főkönyvét írja le, amelyeket egy pénznem, egy naptár, egy megállapodás és egy jogi személy és egy jogi személy kombinációja határoz meg.
author: JennySong-SH
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4f860e0c64573ccfe60e4854697c1e06feeed0c2
ms.sourcegitcommit: 6b209919de39c15e0ebe4abc9cbcd30618f2af0b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/11/2022
ms.locfileid: "9135389"
---
# <a name="global-inventory-accounting-ledger"></a>Global Inventory Accounting főkönyv

[!include [banner](../includes/banner.md)]

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
