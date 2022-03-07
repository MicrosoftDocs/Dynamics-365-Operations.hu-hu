---
title: Alkalmazzon fizetési ütemezést a számlanaplóba
description: Ez a témakör leírja, hogyan vehet fel fizetést a szállítói számlanaplóba.
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
ms.openlocfilehash: bd288ac48ef59d8e2a4e0922aa652276dddb666d
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075732"
---
# <a name="apply-a-payment-schedule-to-the-invoice-journal"></a>Alkalmazzon fizetési ütemezést a számlanaplóba

[!include [banner](../includes/preview-banner.md)]

A Microsoftban Dynamics 365 Finance 10.0.25 kiadás, a fizetési ütemezés mostantól támogatott a szállítói számlanaplóban.

A funkció használatához engedélyeznie kell a **Fizetési ütemezés alkalmazása a számlanaplóba** funkció a Funkciókezelésben.

A funkció engedélyezése után egy új **Fizetési ütemterv** mező hozzáadódik a **Számlanapló** oldalon. Számlanapló sor létrehozásakor, ha a fizetési feltételeket a szállító karbantartja, és a fizetési feltételek a fizetési ütemezésben vannak kiválasztva, a **Fizetési ütemterv** mező frissül a **Számlanapló** oldalon.

A használt fizetési ütemezést az üzleti igényeinek megfelelően módosíthatja. A szállítói számlanapló feladása során a szállítói nyitott tranzakciók a fizetési ütemezés szerint jönnek létre.

Ha több, a fizetési ütemezésből generált szállítói nyitott tranzakciót szeretne áttekinteni, nyissa meg a következőt: **Kötelezett számlák \> Számlák \> Nyitott szállítói számlák**, majd adja meg a számlaszámot vagy a szállítói fiókot.

A fizetési ütemezés áttekintéséhez vagy konfigurálásához lépjen a következő helyre: **Kötelezett számlák \> Fizetési beállítások \> Fizetési ütemterv**.

A fizetési feltételek konfigurálásához és a fizetési ütemezés hozzárendeléséhez lépjen a következő helyre: **Kötelezett számlák \> Fizetés beállítása \> Fizetési feltételek**.

Egy szállító fizetési feltételeinek fenntartásához látogasson el ide **Fizetendő számlák \> Minden eladó**, válassza ki a szállítói fiókot, majd a **Fizetés** lapon állítsa be a **Fizetési feltételek** terület.

A fizetési ütemezés funkció is elérhető a **Szállítói számlanyilvántartás** folyamat. Ha fizetési ütemezés van kiválasztva a számlanyilvántartási naplóban, akkor több szállítói fizetési sor is megtörténik **nem** a számlanyilvántartás feladásakor jön létre. A szállítói fizetési sorok a számla jóváhagyásakor jönnek létre.

## <a name="limitation"></a>Korlátozás

Függőben lévő szállítói számlák esetén, ha a fizetési ütemezés szerepel a számla fejlécében, van egy speciális oldal, amely lehetővé teszi a felhasználók számára a fizetési sorok szerkesztését. (Például a felhasználók szerkeszthetik az egyes fizetési sorok esedékességi dátumát és értékét.) A számlanaplóból generált fizetési sorok a fizetési ütemezésből származó értékkel rendelkeznek.

Ez a funkció a szállítói számlanapló és a függőben lévő számlák számára elérhető lesz egy jövőbeli kiadásban.
