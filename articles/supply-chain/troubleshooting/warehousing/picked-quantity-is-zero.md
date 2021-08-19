---
title: Nem erősítheti meg a szállítmányt, mert nulla a mennyisége
description: Nem erősítheti meg a szállítmányt, mert nulla a mennyisége
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: b2f9f8deaca30e318d0393fb1d7911eebf63060ccca83dc6f1de9b04b9e30e11
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6712886"
---
# <a name="you-cant-confirm-a-shipment-because-there-is-zero-quantity"></a>Nem erősítheti meg a szállítmányt, mert nulla a mennyisége

Hibakód: LoadLineWarningUpdatedToZero

## <a name="symptoms"></a>Tünetek

Szállítmány megerősítésekor a rendszer a következő hibaüzenetet jeleníti meg:

> A(z) %1 cikkhez és %2 szállítmányhoz tartozó rakománysor frissült nulla mennyiségre az alulszállítási beállítás miatt, amely nem engedélyezi az adott cikk bármilyen mennyiségének szállítását.

Ezért nem tudja megerősíteni a szállítmányt a betöltéshez.

## <a name="cause"></a>Ok

A rendszer kiértékeli, hogy a kitárolt mennyiség a várt korlátokon belül van-e, a kitárolt mennyiség, a rakománysor mennyisége és az alulszállítás százalékos aránya alapján. Ha a rendszer úgy találja, hogy a rakománysoron kitárolt mennyiség 0 (nulla), akkor nem lehet megerősíteni a szállítmányt. Ez a probléma például akkor fordulhat elő, ha a munkát visszavonták, és a rakománysor alulszállítási százaléka 100 százalék.

## <a name="resolution"></a>Felbontás

Ellenőrizze a rakománysorokat, hogy az alulszállítás százalékos aránya és mennyiségei összhangban vannak-e a kitárolt munkával.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. Válassza ki azt a rakományt, amelynél a szállítmányt nem lehet megerősíteni.
1. A **Rakománysorok** gyorslapon válassza ki annak a cikknek rakománysorát, amely meghaladja az alulszállítás százalékos arányát.
1. Szükség szerint módosítsa az **Alulszállítás** vagy a **Mennyiség mező** értékét.

> [!TIP]
> Ha a probléma továbbra sincs megoldva, akkor lehet, hogy a kapcsolódó értékesítési vagy átmozgatási rendeléseken további kitárolási munkát kell végrehajtania, amíg a rendelkezésre álló mennyiség nem igazodik a rakományhoz vagy szállítmányhoz.
