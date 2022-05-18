---
title: Szállítónak kiállított, jövőben esedékes csekk kiegyenlítése
description: Rendezzen egy jövőben esedékes, szállító számára kibocsátott csekket, amennyiben bank a csekk lejárta és törlése után törölte a csekktranzakciót.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPostDatedChecks, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f9564bf0ded6acbd05c7953798ea02959babbdfd
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2022
ms.locfileid: "8726294"
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
