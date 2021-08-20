---
title: Egyetlen bizonylatos naplók és pénznemértékelések frissítése
description: A témakör az egyetlen bizonylatos naplók és pénznemértékelések frissítését ismerteti.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: feafcd5c309360467344618f7cec15235ddbe77df807f75873ac82c941073500
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6735494"
---
# <a name="upgrade-single-voucher-journals-and-currency-revaluations"></a>Egyetlen bizonylatos naplók és pénznemértékelések frissítése

[!include [banner](../includes/banner.md)]

Egyes szervezetek olyan naplókat adnak meg, amelyek egynél több ügyféllel vagy szállítóval rendelkező bizonylatot tartalmaznak, valamint a Kinnlevőségek és a Kötelezettségek devizaátértékelési folyamatát is. Ez a témakör bemutatja azokat a lépéseket, amelyeket ezeknek a szervezeteknek követniük kell, amikor frissítenek a Microsoft Dynamics 365 for Operations 1611-es verziójára.

Kövesse az alábbi lépéseket, amikor frissít a Microsoft Dynamics 365 for Operations 1611 verziójára.

1.  A Finance and Operations frissítése előtt futtassa le a devizaátértékelés folyamatait a Kinnlevőségeknél és a Kötelezettségeknél. A **Módszer** mezőben állítsa be a **Számla dátuma** értéket. Átértékelési tranzakció jön létre, amely visszaállítja a legutóbbi devizaátértékelést. Emiatt a nyitott tranzakciók értékelése az eredeti könyvelési pénznemben történik.
2.  Frissítés a 1611 verzióra.
3.  Futtassa le újra a devizaátértékelés folyamatait a Kinnlevőségeknél és a Kötelezettségeknél. Ekkor állítsa a **Módszer** mezőt **Normál** értékre. Új átértékelési tranzakció jön létre, amelynek alapját a jelenlegi átváltási árfolyamok jelentik. Ez a tranzakció rögzíti a nem realizált nyereséget/veszteséget és a megfelelő összefoglaló főkönyvi számlát.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]