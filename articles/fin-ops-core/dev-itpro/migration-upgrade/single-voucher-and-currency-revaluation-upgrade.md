---
title: Egyetlen bizonylatos naplók és pénznemes értékelések frissítése
description: Egyes szervezetek olyan naplókat adnak meg, amelyek egynél több ügyféllel vagy szállítóval rendelkező bizonylatot tartalmaznak, valamint a Kinnlevőségek és a Kötelezettségek devizaátértékelési folyamatát is. Ez a témakör bemutatja azokat a lépéseket, amelyeket ezeknek a szervezeteknek követniük kell, amikor frissítenek a Microsoft Dynamics 365 for Operations 1611-es verziójára.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7c06e54c5be8d0a410b9f15f2a89def3076b4638
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681024"
---
# <a name="upgrade-single-voucher-journals-and-currency-revaluations"></a>Egyetlen bizonylatos naplók és pénznemértékelések frissítése

[!include [banner](../includes/banner.md)]

Egyes szervezetek olyan naplókat adnak meg, amelyek egynél több ügyféllel vagy szállítóval rendelkező bizonylatot tartalmaznak, valamint a Kinnlevőségek és a Kötelezettségek devizaátértékelési folyamatát is. Ez a témakör bemutatja azokat a lépéseket, amelyeket ezeknek a szervezeteknek követniük kell, amikor frissítenek a Microsoft Dynamics 365 for Operations 1611-es verziójára.

Kövesse az alábbi lépéseket, amikor frissít a Microsoft Dynamics 365 for Operations 1611 verziójára.

1.  A Finance and Operations frissítése előtt futtassa le a devizaátértékelés folyamatait a Kinnlevőségeknél és a Kötelezettségeknél. A **Módszer** mezőben állítsa be a **Számla dátuma** értéket. Átértékelési tranzakció jön létre, amely visszaállítja a legutóbbi devizaátértékelést. Emiatt a nyitott tranzakciók értékelése az eredeti könyvelési pénznemben történik.
2.  Frissítés a 1611 verzióra.
3.  Futtassa le újra a devizaátértékelés folyamatait a Kinnlevőségeknél és a Kötelezettségeknél. Ekkor állítsa a **Módszer** mezőt **Normál** értékre. Új átértékelési tranzakció jön létre, amelynek alapját a jelenlegi átváltási árfolyamok jelentik. Ez a tranzakció rögzíti a nem realizált nyereséget/veszteséget és a megfelelő összefoglaló főkönyvi számlát.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]