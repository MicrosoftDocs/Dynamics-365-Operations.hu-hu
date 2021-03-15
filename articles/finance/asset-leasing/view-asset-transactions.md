---
title: Kötelezettség-, eszköz- és költségtranzakciók megtekintése
description: Ez a témakör a lízingbe adott eszköz tranzakcióinak megtekintését ismerteti. Ezek a tranzakciók magukban foglalják a lízingkötelezettséggel kapcsolatos tranzakciókat és a feladott végrehajtási költségtranzakciókat.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 76c7eff17df92b01317544112099e391fd05d105
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995368"
---
# <a name="view-liability-asset-and-expense-transactions"></a>Kötelezettség-, eszköz- és költségtranzakciók megtekintése

[!include [banner](../includes/banner.md)]

Ez a témakör a lízingbe adott eszköz tranzakcióinak megtekintését ismerteti. Ezek a tranzakciók magukban foglalják a lízingkötelezettséggel kapcsolatos tranzakciókat és a feladott végrehajtási költségtranzakciókat. A kötelezettség és a használatijog-eszköz (ROU) könyv szerinti értékeit több jelentésben is felhasználják. A korrekciós értékek kiszámítására is szolgálnak.

## <a name="liability-transactions"></a>Kötelezettség tranzakciói

A lízingkötelezettség-tranzakciók megtekintéséhez válasszon ki egy lízinget a **Lízing összegzése** lapon, majd válassza a **Könyvek** lehetőséget a lízingrekordhoz csatolt könyvek megnyitásához. A kezdeti megjelenítés, a számla vagy a kamatnapló feladása után válassza a **Kötelezettségtranzakciók** lehetőséget.

A **Kötelezettségtranzakciók** lap azokat a tranzakciókat jeleníti meg, amelyek növelik vagy csökkentik a lízingkötelezettséget. Az ezen az oldalon szereplő negatív összegek a standard alkalmazásban szereplő jóváírási tranzakciókat jelölik. A kamatelhatárolások negatív értékként jelennek meg, és növelik a teljes lízingkötelezettséget. A lízingkiigazítások a lízingkönyv jellegétől és hatásától függően pozitív vagy negatív értékként jelennek meg. A kiválasztott lízing lízingkötelezettség aktuális nettó teljes egyenlege az oldal bal alsó sarkában látható.

## <a name="asset-transactions"></a>Eszköztranzakciók

A lízingeszköz-tranzakciók megtekintéséhez válasszon ki egy lízinget a **Lízing összegzése** lapon, majd válassza a **Könyvek** lehetőséget a lízingrekordhoz csatolt lízingkönyvek megnyitásához. Majd válassza a **Eszköztranzakciók** lehetőséget.

Az **Eszköztranzakció** lap azokat a tranzakciókat jeleníti meg, amelyek növelik vagy csökkentik a lízingeszközt és a halmozott értékcsökkenési számlákat. A tartozási értékek pozitív értékként, a jóváírások pedig negatív értékként jelennek meg, mint a **Kötelezettségtranzakciók** lapon. A könyvelt kezdeti megjelenítés és a következő halmozott értékcsökkenés az oldal bal alsó sarkában jelenik meg eszközegyenlegként. 

## <a name="expenses-transactions"></a>Költségtranzakciók

A lízingköltség-tranzakciók megtekintéséhez válasszon ki egy lízinget a **Lízing összegzése** lapon, majd válassza a **Könyvek** lehetőséget a lízingrekordhoz csatolt lízingkönyvek megnyitásához. Majd válassza ki a **Költségtranzakciók** lehetőséget.

A **Költségtranzakciók** lap a lízinggel szemben feladott összes költséget megjeleníti, például a kamatköltségeket, az értékcsökkenési költségeket és a végrehajtási költségeket.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]