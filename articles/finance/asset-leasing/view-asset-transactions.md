---
title: Kötelezettség-, eszköz- és költségtranzakciók megtekintése
description: Ez a témakör a lízingbe adott eszköz tranzakcióinak megtekintését ismerteti. Ezek a tranzakciók magukban foglalják a lízingkötelezettséggel kapcsolatos tranzakciókat és a feladott végrehajtási költségtranzakciókat.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: be11250a85d160aa71ab76af9cfdb0258fd7bf11
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2022
ms.locfileid: "8727482"
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
