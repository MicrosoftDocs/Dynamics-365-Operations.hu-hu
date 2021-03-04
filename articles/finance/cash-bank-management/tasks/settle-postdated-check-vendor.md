---
title: Szállítónak kiállított, jövőben esedékes csekk kiegyenlítése
description: Rendezzen egy jövőben esedékes, szállító számára kibocsátott csekket, amennyiben bank a csekk lejárta és törlése után törölte a csekktranzakciót.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPostDatedChecks, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee66bdb93d1252486efc7be25adeb6ee7cc6ce05
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444040"
---
# <a name="settle-a-postdated-check-for-a-vendor"></a>Szállítónak kiállított, jövőben esedékes csekk kiegyenlítése

[!include [banner](../../includes/banner.md)]

Rendezzen egy jövőben esedékes, szállító számára kibocsátott csekket, amennyiben bank a csekk lejárta és törlése után törölte a csekktranzakciót. 

Ez előtt a folyamat előtt végezze el a következőeket.

1) Jövőben esedékes csekkek beállítása

2) Szállító részére kiállított, jövőben esedékes csekk regisztrálása és feladása



Ezen eljárás szerepköre: Pénztáros. Ez az eljárás az USMF bemutatócéget használja.

1. Ugorjon a Kötelezettségek > Kifizetések > Szállító jövőben esedékes csekkjei pontra.
2. Kattintson a Kiegyenlítés elemre.
3. Kattintson az Elszámolási tételek kiegyenlítése elemre.
    * Rendezze a csekktranzakció szállítói számláját.  
4. Zárja be a lapot.
5. Ugorjon a Főkönyv > Naplóbejegyzések > Általános naplók pontra.
6. A Megjelenítés mezőben válassza ki a következőt: „Mind”.
7. Jelölje be vagy törölje a jelölést a Megjelenítés csak a felhasználó által létrehozott jelölőnégyzetéből.
8. A listában jelölje meg a kiválasztott sort.
9. Kattintson a Sorok pontra.
10. Kattintson a Bizonylat elemre.
11. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]