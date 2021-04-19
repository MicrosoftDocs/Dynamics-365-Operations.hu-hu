---
title: Tényleges értékkel együtt
description: A Cikkmodell csoportok oldal készletmodell gyorslapján található tényleges értékkel együtt jelölőnégyzetet arra használhatja, hogy meghatározza a ténylegesen frissített tranzakciók vajon számításba vannak-e véve egy cikk mozgóátlagon alapuló önköltségi árának kiszámításakor.
author: AndersGirke
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79033
ms.assetid: 1928c145-bf82-436d-87ca-e7a173e31923
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 16ab5ecc74d41610098bf927fc4768bc216e42f4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816676"
---
# <a name="include-physical-value"></a>Tényleges értékkel együtt

[!include [banner](../includes/banner.md)]

A Cikkmodell csoportok oldal készletmodell gyorslapján található tényleges értékkel együtt jelölőnégyzetet arra használhatja, hogy meghatározza a ténylegesen frissített tranzakciók vajon számításba vannak-e véve egy cikk mozgóátlagon alapuló önköltségi árának kiszámításakor.

A **tényleges értékkel együtt** jelölőnégyzet a következő értékekkel rendelkezik.

| Érték    | Eredmény                                                                                                                          |
|----------|---------------------------------------------------------------------------------------------------------------------------------|
| Kijelölve | A mozgóátlagon alapuló önköltségi ár kiszámításához a ténylegesen frissített és a pénzügyileg frissített tranzakciók is felhasználásra kerülnek. |
| Törölve  | Csak a pénzügyileg frissített tranzakciók kerülnek felhasználásra a mozgóátlagon alapuló önköltségi ár kiszámításakor.                                     |

A jelölőnégyzeteknek némileg eltérő hatásuk van, attól függően, hogy milyen készletmodellt alkalmaz.

-   Ha bejelöli a **tényleges értékkel együtt** jelölőnégyzetet a FIFO (elsőként be, elsőként ki), a LIFO (utolsóként be, elsőként ki) vagy a LIFO dátum készletmodellek esetében, akkor a készletzárás a ténylegesen frissített tranzakciókat is kiigazítja.
-   Ha a **Tényleges értékkel együtt** jelölőnégyzet nincs bejelölve a készletmodellek használatakor, akkor a készletzárás csak a pénzügyileg frissített tranzakciókat rendezi.
-   Amikor súlyozott átlagon vagy súlyozott átlagon és dátumon alapuló készletmodellt alkalmaz, a készletzárás csak a pénzügyileg frissített tranzakciókat fogja rendezni attól függetlenül, hogy be van-e jelölve a **Tényleges értékkel együtt** négyzet, vagy sem.

**1. példa** Ön a **tényleges értékkel együtt** jelölőnégyzetet választotta, majd a következő beszerzési rendeléseket kapta:

-   2-es mennyiségű beszerzési rendelés 10,00 USD önköltségi árral, melynek szállítólevele frissítve lett.
-   3-es mennyiségű beszerzési rendelés 12,00 USD önköltségi árral, melynek számlája frissítve lett.

Ebben az esetben a mozgóátlagon alapuló önköltségi ár 11,20 USD = (2x10+3x12)/(2+3), mivel mind a tényleges, mind a pénzügyileg frissített tranzakciók fel lettek használva az önköltség kiszámításakor. 

**2. példa** Ön nem jelölte be a **tényleges értékkel együtt** jelölőnégyzetet és a cikkbeállításoknál szereplő önköltségi ár 10,00 USD. 

-   Kap egy 20-as mennyiségű beszerzési rendelést 12,00 USD önköltségi árral, melynek szállítólevele frissítve lett.

Egy értékesítési rendelés feladásakor, a feladott költségösszeg 10,00 USD, mivel a mozgóátlagon alapuló önköltségi ár nem fogja tartalmazni a ténylegesen feladott tranzakciókat. 

> [!NOTE]
> Összehasonlításképpen: Ha bejelöli a **Tényleges értékkel együtt** jelölőnégyzetet egy értékesítési rendelés feladásakor, akkor a feladott költség összege 12,00 USD lesz.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]