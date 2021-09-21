---
title: Engedélyezett szállító hatályos dátuma nem változtatható meg
description: Az Engedélyezett szállító lista a termék entitása nem teszi lehetővé a hatályos dátum módosítását
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: cb6dbd134d63daa163261cabdbd7eceb978877ae
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476508"
---
# <a name="cant-change-the-effective-date-for-an-approved-vendor"></a>Engedélyezett szállító hatályos dátuma nem változtatható meg


## <a name="symptoms"></a>Tünetek

A termék olyan engedélyezett szállítóval rendelkezik, amely például 2018. január 11-i (*01/11/2018*) érvényességi dátummal és a *Soha* lejárati dátummal rendelkezik. Ha a hatályosság dátumát 2018. január 10-re (*01/10/2018*) vagy 2018. január 12-re (*01/12/2018*) szeretné módosítani, akkor a következő hibaüzenet jelenik meg:

> Nem hozható létre rekord az Engedélyezett szállítói listán (PdsApproveVendorList). A „Lejárat” értéknek nagyobbnak kell lennie, mint a „Hatályos” értéknek.

## <a name="resolution"></a>Megoldás

Csak addig hosszabbíthatja meg azt az időszakot, ameddig a szállítót jóváhagyták. Az alábbi szabályokat kell betartani:

- Ha azt szeretné, hogy a program a hatályossági dátumot a szállítóhoz tartozó létező rekordoknál (időszakok) korábbira módosítsa, akkor az új időszak lejárati dátumának korábban kell lennie a meglévő rekordok összes lejárati dátumával.
- Ha módosítani szeretné a lejárati dátumot úgy, hogy az később legyen, mint a meglévő időszakok, akkor az érvényességi dátumnak a legkésőbbi lejárati dátum után kell lennie minden meglévő rekordban.
- Ha csökkenteni szeretné a szállító számára jóváhagyott teljes időszakot, akkor törölnie kell vagy módosítania kell a meglévő rekordokat. Azt is megteheti, hogy az Importálás során a **csonkolás** kapcsolót használja. Ez a kapcsoló törli a táblából a jóváhagyott szállítókhoz tartozó összes meglévő rekordot.

A probléma leírásában ismertetett példa esetében, amikor a rekord érvényességi dátuma *01/11/2018* érvényességi dátuma és a lejárati dátuma *Soha*, importálhat egy olyan új rekordot, amelynek érvényességi dátuma *01/10/2018*, és a lejárati dátuma *Soha*. Az időszakot azonban nem lehet csökkenteni úgy, hogy az érvényességi dátumot *01/12/2018* értékre módosítja az adatkezelési folyamaton keresztül. Ezt a módosítást a felhasználói felületen keresztül kell elvégeznie.
