---
title: "Egyetlen bizonylatos és pénznemes értékelési frissítés"
description: "Egyes szervezetek olyan naplókat adnak meg, amelyek egynél több ügyféllel vagy szállítóval rendelkező bizonylatot tartalmaznak, valamint a Kinnlevőségek és a Kötelezettségek devizaátértékelési folyamatát is. Ez a témakör bemutatja azokat a lépéseket, amelyeket ezeknek a szervezeteknek követniük kell, amikor frissítenek a Microsoft Dynamics 365 for Operations 1611-es verziójára."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: d3c6d817424be79b09ccdd89deb7f31599fe9bf5
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="single-voucher-and-currency-revaluation-upgrade"></a>Egyetlen bizonylatos és pénznemes értékelési frissítés

[!include[banner](../includes/banner.md)]


Egyes szervezetek olyan naplókat adnak meg, amelyek egynél több ügyféllel vagy szállítóval rendelkező bizonylatot tartalmaznak, valamint a Kinnlevőségek és a Kötelezettségek devizaátértékelési folyamatát is. Ez a témakör bemutatja azokat a lépéseket, amelyeket ezeknek a szervezeteknek követniük kell, amikor frissítenek a Microsoft Dynamics 365 for Operations 1611-es verziójára.

Kövesse ezeket a lépéseket, amikor frissít a Microsoft Dynamics 365 for Operations 1611-es verziójára.

1.  A Dynamics 365 for Operations frissítése előtt futtassa le a devizaátértékelés folyamatait a Kinnlevőségeknél és a Kötelezettségeknél. A **Módszer** mezőben állítsa be a **Számla dátuma** értéket. Átértékelési tranzakció jön létre, amely visszaállítja a legutóbbi devizaátértékelést. Emiatt a nyitott tranzakciók értékelése az eredeti könyvelési pénznemben történik.
2.  Frissítsen a Dynamics 365 for Operations 1611-es verziójára.
3.  Futtassa le újra a devizaátértékelés folyamatait a Kinnlevőségeknél és a Kötelezettségeknél. Ekkor állítsa a **Módszer** mezőt **Normál** értékre. Új átértékelési tranzakció jön létre, amelynek alapját a jelenlegi átváltási árfolyamok jelentik. Ez a tranzakció rögzíti a nem realizált nyereséget/veszteséget és a megfelelő összefoglaló főkönyvi számlát.





