---
title: Mozgóátlag – tartalék költségsorrend
description: Ez a témakör a Microsoft mozgóátlagon keresztüli számításának tartalékköltség-sorozatait mutatja be Dynamics 365 Supply Chain Management.
author: JennySong-SH
ms.date: 03/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2020-03-25
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: ad67828e2608f4754a3dffd76c64292f6a91e95f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868014"
---
# <a name="moving-average-fallback-cost-sequence"></a>Mozgóátlag tartalék költségsorrend

[!include [banner](../includes/banner.md)]

A készlet költségének kiszámítására használt egyik módszer a _mozgóátlag_. Az egyes készletcikkekhez legfeljebb három költségérték tartozhat:

- **Utolsó kiadás** – Az utolsó kiadási költség, ami hozzá lett rendelve, mielőtt a készlet negatívba ment át
- **Aktív költség** – Egy költségszámítási verzióban aktivált legutóbbi költség
- **Cikk ára** – A kiadott termékhez megadott költség

Annak eldöntéséhez, hogy a mozgóátlag-számításokhoz melyik költségadat legyen használva, a rendszer egy _tartalék költségsorrendet_ használ az értékek rangsorának meghatározásához. Ha a preferált költségérték nem érhető el, akkor a rendszer a következő preferált értéket használja, és így tovább.

A Microsoft Dynamics 365 Supply Chain Management korábbi verzióiban a rendszer rögzített tartalék költségsorozatot használt (_Utolsó kiadás – Aktív költség – Cikkár_). A 10.0.11 verzióban ez a sorozat továbbra is az alapértelmezett sorrend. Ugyanakkor lehetőség van olyan funkció bekapcsolására is, amely lehetővé teszi, hogy a három rendelkezésre álló költségsorozat közül válasszon. Ez a funkció különösen akkor hasznos lehet olyan szervezeteknél, amelyek gyakran használnak negatív készletértékeket.

Ha azt szeretné, hogy a költségsorozat kiválasztó modulja elérhető legyen, akkor Ön (vagy egy rendszergazda) a [Szolgáltatások kezelése](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) használatával kapcsolja be a _Mozgóátlag tartalék költségsorrend_ nevű funkciót.

Az mozgóátlag-számítások költségsorozatának kiválasztásához hajtsa végre az alábbi lépéseket.

1. Nyissa meg a **Paraméterek** oldalt.
2. A **Készletkönyvelés** lap **Mozgóátlag** szakaszában a következő értékek egyikére állítsa be a **Mozgóátlag tartalék költségsorrend** mezőt:

    - **Utolsó kiadás – aktív költség – cikkár** – Ez a sorozat az alapértelmezett sorozat. Ez ugyanaz a sorrend, ami akkor van használva, ha a _Mozgóátlag tartalék költségsorrend_ funkció nincsen bekapcsolva.
    - **Aktív költség – Utolsó kiadás**
    - **Aktív költség – Cikkár** – A vállalatok teljesítménnyel kapcsolatos problémákat tapasztalhatnak, ha olyan üzleti folyamatokat alkalmaznak, amelyeknél a készlet rendszeres időközönként negatívba megy át, és ezzel egyidejűleg a tranzakciók mennyisége is magas. Ez a beállítás segít enyhíteni a teljesítménnyel kapcsolatos problémákat.

![Készletkönyvelési paraméterek.](media/inventory-accounting-parameters.png "Készletkönyvelési paraméterek")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]