---
title: Pénzügyi naplósablonok megnyitása az Office programban
description: Ez a cikk olyan problémákat ír le, amelyek akkor fordulhatnak elő, ha egyéni pénzügyi naplókat hoz létre Microsoft Excel-sablon alapján.
author: kweekley
ms.date: 05/14/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a29ab1cb2980ebfed6c6fa6409538bc802849156
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896347"
---
# <a name="open-financial-journal-templates-in-office"></a>Pénzügyi naplósablonok megnyitása az Office programban

[!include [banner](../includes/banner.md)]

Ez a cikk olyan problémákat ír le, amelyek akkor fordulhatnak elő, ha egyéni pénzügyi naplókat hoz létre Microsoft Excel-sablon alapján.

## <a name="symptom"></a>Tünet

Létrehozott egy egyéni Excel-sablont a pénzügyi naplók számára, de az nem jelenik meg az **Sorok megnyitása az Excelben** menüjében. Másik lehetőségként megjelenhet a menüben, de amikor kiválasztja, egy másik sablont nyit meg.

## <a name="resolution"></a>Megoldás

Az Excel programban történő megnyitás alapértelmezett funkciója az aktuális lap gyökéradatforrását (tábláját) használja annak meghatározására, hogy mely Office-sablonok vagy -adatentitások jelenjenek meg lehetőségként az **Excel programban történő megnyitás** menüben. Ez a viselkedés nem ideális a pénzügyi naplók számára, mivel a pénzügyi naplók sok más típusú napló gyökéradatforrásaként használják ugyanazon táblákat (LedgerJournalTable és LedgerJournalTrans).

Pénzügyi naplók esetén a Sorok megnyitása az Excelben funkció célja az éppen használt naplóhoz – például az általános naplóhoz vagy a kifizetési naplóhoz – készült sablonok megjelenítése. Például egy szállítói kifizetési naplóval való használatra szánt sablon az elsődleges számla szállítói számlaként való érvényesítésére lesz kialakítva.

Ha beállítana egy sablont, hogy az elérhető legyen a **Sorok megnyitása az Excelben** és az **Excel programban történő megnyitás** menükben, akkor egy egyszerű fejlesztői tapasztalat szerint a **LedgerIJournalExcelTemplate** felület implementálása és a **DocuTemplateRegistrationBase** osztály kiterjesztése lehet a megoldás. Erre a megközelítésre számos példa van a rendszerben. Hivatkozásként használható példa az általános naplóhoz (vagy napi naplóhoz) létrehozott **LedgerDailyJournalExcelTemplate** felület.

Ha a sablonhoz implementálva van a **LedgerIJournalExcelTemplate** felület, a **Sorok megnyitása az Excelben** menü a napló típusa szerint szűri a sablonokat, és csak az adott naplóhoz elérhető sablonokat mutatja. A felület olyan ellenőrzési módszert is biztosít, amely gondoskodik arról, hogy ne lehessen megnyitni egy sablont egy naplóhoz, ha az nem felel meg a számlatípus követelményeinek. Megadhatja például, hogy a számlatípus **Szállító** vagy **Főkönyv** típusú legyen.

A további tudnivalókat erről a funkcióról lásd: [Sablonok hozzáadása a Sorok megnyitása az Excelben menühöz](../../fin-ops-core/dev-itpro/user-interface/add-templates-open-lines-excel-menu.md).
