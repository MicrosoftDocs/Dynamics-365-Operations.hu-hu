---
title: Szállítónak kiállított, jövőben esedékes csekk kiegyenlítése
description: Rendezzen egy jövőben esedékes, szállító számára kibocsátott csekket, amennyiben bank a csekk lejárta és törlése után törölte a csekktranzakciót.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPostDatedChecks, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3e3816a2f1c95d568a173cb07daad0473703da9c
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779501"
---
# <a name="settle-a-postdated-check-for-a-vendor"></a>Szállítónak kiállított, jövőben esedékes csekk kiegyenlítése

[!include [banner](../../includes/banner.md)]

Rendezzen egy jövőben esedékes, szállító számára kibocsátott csekket, amennyiben bank a csekk lejárta és törlése után törölte a csekktranzakciót. 

Ez előtt a folyamat előtt végezze el a következőeket.

1) Jövőben esedékes csekkek beállítása

2) Szállító részére kiállított, jövőben esedékes csekk regisztrálása és feladása



Ezen eljárás szerepköre: Pénztáros. Ez az eljárás az USMF bemutatócéget használja.

1. Ugrás a **Kötelezettségek > és > jövőben esedékes csekkek számára**.
2. Kattintson az Egyenlítés **gombra**.
3. Kattintson az elszámolási **tételek kiegyenlítése elemre**.
    * Rendezze a csekktranzakció szállítói számláját.  
4. Zárja be a lapot.
5. Ugorjon a **Főkönyv > Naplóbejegyzések > Általános naplók** pontra.
6. A Show **mezőben** válassza a Mind **lehetőséget**.
7. Jelölje be a Csak a felhasználó **által létrehozottak megjelenítése jelölőnégyzetet, vagy törölje a** jelölést a jelölőnégyzetből.
8. A listában jelölje meg a kiválasztott sort.
9. Kattintson a **Sorok** pontra.
10. Kattintson a **Bizonylat** elemre.
11. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
