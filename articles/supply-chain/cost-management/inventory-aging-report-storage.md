---
title: Készletkorosítási jelentés tárolása
description: Ez a témakör bemutatja a funkciókat, amelyekkel készletkorosítási jelentést futtathat és űrlap és diagram formájában elérhetővé teheti a kimeneti fájlt.
author: AndersGirke
manager: tfehr
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2019-01-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8a292bd7a7ccbb09af1955e1e253b45e230c1009
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005427"
---
# <a name="inventory-aging-report-storage"></a>Készletkorosítási jelentés tárolása

[!include [banner](../includes/banner.md)]

A Microsoft Dynamics 365 Supply Chain Management szolgáltatásban futtathat **Készletkorosítás jelentéstárolási** jelentést, és a kimeneti fájlt megoszthatja űrlapként és diagramként. A képernyőn az oszlopok és az összesítő egyenlegek dinamikusan módosulnak, attól függően, hogy milyen elrendezés van beállítva. A diagram olyan vizuális áttekintést nyújt, amely támogatja a szűrést, és lehetővé teszi a részletekbe való leásást. Ezenkívül egy **készletkorosítási jelentés** nevű adatentitás lehetővé teszi, hogy a **készletkorosítási jelentéstárolási** jelentés futtatásának eredményeit egy Microsoft Excel fájl vagy egy PDF-fájl formátumában exportálják.

A **készletkorosítási jelentéstárolási** jelentés futtatására szolgáló módszer olyan esetekben hasznos, amikor a kimenet sok sort tartalmaz. Például a kimenet sok sort fog tartalmazni, ha 50 000 cikket és 300 üzletet készítenek raktárakként, és a készletkorosítást cikk, telephely és raktár szerint kell elvégezni.

## <a name="enable-the-inventory-value-storage-report-feature"></a>A készletérték-tárolási jelentés funkció engedélyezése

A funkció használata előtt engedélyeznie kell azt saját rendszerében. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és szükség esetén engedélyezéséhez. Itt a funkció a következőként szerepel:

- **Modul** – Költségkezelés
- **Funkció neve** – Készletkorosítási jelentés tárolása

## <a name="run-an-inventory-aging-report-storage"></a>Készletkorosítási jelentés tárolása futtatása

1. Lépjen a **Költséggazdálkodás \> Lekérdezések és jelentések \> Készletkorosítási jelentés tárhelye**.
1. Válassza az **Új** lehetőséget.
1. Írja be a jelentés egyedi nevét a **Folyamatazonosító – Név** mezőbe.
1. Válassza ki az **azonosító – ID** jelentést, és szűrje a szükséges módon.

    A jelentés végrehajtása mindig kötegelt feladatként történik.

1. A kötegelt feladat befejezése után a kimeneti fájl megjelenik a **készletkorosítási jelentés tárhelye** lapján.
1. Ha a kimenetet hagyományos rács elrendezésű képernyőként szeretné megtekinteni, válassza a **részletek megtekintése** parancsot. Ha összegzett diagramként szeretné megjeleníteni a kimenetet, válassza a **diagram megtekintése** lehetőséget.

    > [!NOTE]
    > A képernyő nem tartalmaz a jelentés elrendezésében megadott részösszegeket.

A **készlet korosítási jelentés** adatentitása lehetővé teszi egy **készletkorosítási jelentéstárolási** jelentés kimenetének exportálását, ha szűrőt alkalmaz a **Folyamatazonosító – Név** mezőre az adatkezelési támogatások bármely formájává.
