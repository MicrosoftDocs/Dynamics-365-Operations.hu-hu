---
title: Fizetési ütemezés alkalmazása a számlanaplóba
description: Ez a témakör azt ismerteti, hogyan lehet kifizetéseket hozzáadni a szállítói számlanaplóhoz.
author: sunfzam
ms.date: 01/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: f6481c3fc033acf4bb563bf1716789216646b60b
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/26/2022
ms.locfileid: "8358339"
---
# <a name="apply-a-payment-schedule-to-the-invoice-journal"></a>Fizetési ütemezés alkalmazása a számlanaplóba

[!include [banner](../includes/preview-banner.md)]

A Microsoft Dynamics 365 Finance 10.0.25-ös verziójában mostantól támogatott a fizetési ütemezés a szállítói **számlanaplóban**.

A funkció használatához engedélyeznie **kell a Fizetési ütemezés alkalmazása a számlanaplóra** funkciót a Funkciókezelésben.

A funkció engedélyezése után a Rendszer új fizetési ütemezési mezőt ad hozzá a **Számlanapló** **laphoz**. Számlanaplósor létrehozásakor, ha a fizetési feltételek karbantartva vannak a szállítónál, és a fizetési feltételek ki vannak választva a fizetési ütemezésben, **·** **akkor** a Program frissíti a Kifizetés ütemezése mezőt a Számlanapló lapon.

Az alkalmazott fizetési ütemezés az üzleti követelménynek megfelelően megváltoztatható. A szállítói számlanapló feladása során a nyitott szállítói tranzakciók a fizetési ütemezésnek megfelelően lesznek létrehozva.

 - Ha több, a fizetési ütemezés alapján létrehozott nyitott szállítói tranzakciót is át kell vennie, **\>\>** nyissa meg a Kötelezettségek számlái – Nyitott szállítói számlák gombra, és adja meg a számlaszámot vagy a szállítói számlát.
 - A fizetési ütemezés áttekintéshez vagy konfigurálásához kattintson **a Kötelezettségek – \>\> Kifizetés beállítása fizetési ütemezése gombra**.
 - A fizetési feltételek beállításához és a fizetési ütemezés hozzárendeléshez kattintson a **Kötelezettségek – Fizetési \> beállítás feltételei gombra \>**.
 - A szállítóra vonatkozó fizetési feltételek karbantartásához kattintson a Kötelezettségek – Összes szállító gombra, válassza ki a **\>** szállítói számlát, **·** **majd** a Fizetés lapon állítsa be a Fizetési feltételek mezőt.

A fizetés ütemezése funkció a szállítói **számlajegyzék folyamata során is elérhető**. Ha a számlajegyzéknaplóban ki van választva a fizetési ütemezés, **a** számlajegyzék feladása során nem jön létre több szállítói fizetési sor. A szállítói kifizetési sorok a számla jóváhagyásakor jönnek létre.

## <a name="limitation"></a>Korlátozás

Függőben lévő szállítói számlák esetén, ha a fizetési ütemezés a számla fejlécében van, egy speciális lap van, amellyel a felhasználók szerkeszthetik a kifizetési sorokat. (Például a felhasználók szerkeszthetik az egyes fizetési sorok fizetési dátumát és értékét.) A számlanaplóból létrehozott fizetési sorok értéke a fizetési ütemezésben szereplő érték lesz.

Ez a funkció egy jövőbeli **kiadásban** **lesz** elérhető a Szállítói számlanapló és a Függő számlák számára.
