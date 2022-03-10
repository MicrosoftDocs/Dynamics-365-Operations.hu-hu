---
title: A termelési útvonalakban használt költségkategóriák
description: Ez a cikk tájékoztatást ad az útvonalakat használó gyártási környezetekre vonatkozó költségkategóriákról.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjCategory, RouteCostCategoryPrice
audience: Application User
ms.reviewer: kamaybac
ms.custom: 78153
ms.assetid: a3fdc76c-0a27-4723-b1c7-4322f707d89e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ca4c0c9cecb79366cdd41069cb6c96f01b44a2094f4caf57077c391beb6ac106
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6779686"
---
# <a name="cost-categories-used-in-production-routing"></a>A termelési útvonalakban használt költségkategóriák

[!include [banner](../includes/banner.md)]

Ez a cikk tájékoztatást ad az útvonalakat használó gyártási környezetekre vonatkozó költségkategóriákról.

A költségkategóriák az útvonalat alkalmazó gyártási környezetekre vonatkoznak. Hozzá vannak rendelve az üzemi erőforrásokhoz és az útvonalműveletekhez, az óránkénti költségek meghatározása és a legyártott cikkek számított költségei között szereplő költség-hozzájárulások felosztása céljából. A költségkategóriákhoz hozzárendelt költségcsoportok tehát a gyártási költségek hozzájárulásait az üzemi erőforrás, és a tevékenységtípus (például beállítási és futási idő) alapján sorolják be. A költségcsoportok kiosztásának sajátossága lehetővé teszi a gyártási többletköltségek útvonaladatok alapján történő számítását. 

**Megjegyzés:** A gyártási környezetekben a költségkategóriák több néven is ismeretesek, úgy mint élőmunka-díjkódok vagy gépi díjkódok. 

Minden költségkategóriához tartoznak társított költségrekordok, illetve egy társított költségcsoport. Különböző termelési célokhoz különböző költségkategóriák szükségesek.

-   Eltérő óránkénti költségek hozzárendelése az üzemi erőforrás függvényében. Például a költségek eltérőek lehetnek a szakértelem, a gépek vagy a gyártócellák különböző típusai esetén.
-   Eltérő óránkénti költségek hozzárendelése egy útvonalművelethez társított beállítási vagy futási időhöz.
-   Üzemi erőforrásköltségek hozzárendelése az óránkénti költség helyett a kimenő mennyiség alapján, például darabbérezés esetén.
-   A legyártott cikk számított költségét alkotó költség-hozzájárulások költségcsoport szerinti szegmentálása. A szegmentálást végezheti például a munka- és gépköltségek szerint.
-   A többletköltség-számítási képletek költségcsoportalapjának biztosítása, például a munkához vagy a gépekhez kapcsolódó többletköltségek képletei, vagy a beállítási és a futási időhöz kapcsolódó többletköltségek.

A költségkategóriák hozzárendelhetők a beállítási időhöz, a feldolgozási időhöz és az útvonalművelethez tartozó mennyiséghez. Amikor például a költségek vagy költségcsoportok szegmentálása eltérő a beállítási idő és a feldolgozási idő között, különböző költségkategóriákat kell meghatározni, és a beállítási időhöz és a feldolgozási időhöz rendelni. A beállítási időre, feldolgozási időre és mennyiségre vonatkozó költségkategóriák szelektív használatát a művelethez rendelt útvonalcsoport határozza meg. A költségkategóriák időhöz és mennyiséghez rendelése előírható a **Gyártásvezérlési paraméterek** oldalon található, egész vállalatra kiterjedő szabályok által. 

Mindegyik költségkategóriához tartoznak társított költségek, amelyek a költségszámítási verzióban megtalálható költségrekordok definícióin alapulnak. Használja a **Költségkategória ára** oldalt, egy adott költségszámítási verzióhoz és helyhez tartozó költségrekordok meghatározásához. Amikor a költségkategóriához tartozó költségrekordot először megadja egy **Függő** állapottal és egy tervezett érvényességi dátummal jön létre. A költségrekord aktiválásakor az állapot **Jelenleg aktív** állapotúra frissül, továbbá az érvénybelépési dátum az aktiválási dátumra módosul. Különböző költségrekordok különböző helyeket, érvénybe lépési dátumokat vagy állapotokat tükrözhetnek. A jövőbeli vagy múltbeli dátumokra vonatkozó anyagjegyzék-számítások a vonatkozó érvényességi dátummal rendelkező költségrekordokat használják. Az éppen aktuális aktív költségrekordot használja a rendszer a termelési rendelés költségeinek becslésére, és a jelentett idő termelési rendeléssel szembeni értékelésére. 

A költségrekord, amely egy költségkategóriára vonatkozik lehet helyspecifikus, vagy egész vállalatra kiterjedő. Hogy helyspecifikussá tegyen egy költségrekordot rendeljen hozzá egy helyet. Különben az üres érték azt jelzi, hogy a költségrekord a vállalaton belüli összes helyre érvényes. Mivel a költségek eltérőek lehetnek például különböző helyeken, a költségrekordokat helyspecifikusként kell megadni. 

Az útvonalműveletek általában öröklik az üzemi erőforráshoz vagy az alapművelethez hozzárendelt költségkategóriákat. Amikor egy termelési rendelés létrejön, a termelési útvonalon belüli útvonalműveletek a kiválasztott útvonalverziónak megfelelőek. A termelési útvonalon belüli műveletekhez hozzárendelt költségkategóriák felülbírálhatók. 

A termelési munkák bizonyos típusai vonatkozhatnak a projektek időbecslésére és jelentésekre. Ebben az esetben a költségkategóriára termelési és projektcélokból van szükség. További projektekkel kapcsolatos információkat kell meghatározni, amikor a költségkategória projekthasználatra engedélyezetté válik.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]