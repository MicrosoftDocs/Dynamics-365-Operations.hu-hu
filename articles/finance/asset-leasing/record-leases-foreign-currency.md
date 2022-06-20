---
title: Lízing rögzítése külföldi pénznemben
description: Ez a cikk bemutatja, hogyan lehet a könyvelési vagy jelentési pénznemtől különböző pénznemekben rögzíteni a bérleti bérleteket.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseDetail
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 56c15e648d6aa515192a6f41ba06df6405ca79f2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878102"
---
# <a name="record-leases-in-foreign-currencies"></a>Lízing rögzítése külföldi pénznemben

[!include [banner](../includes/banner.md)]

A könyvelési pénznemtől vagy a jelentés pénznemétől eltérő pénznemben lévő lízingszámlák eszközlízing-számláit a **Főkönyv beállítása** oldalon kell létrehozni. Minden lízinget a tranzakció pénznemében kell megadni. Más szóval a lízingszerződésben meghatározott pénznemben kell megadni őket. Ez a cikk bemutatja, hogyan lehet a könyvelési vagy jelentési pénznemtől különböző pénznemekben rögzíteni a bérleti bérleteket.

Ha külföldi pénznemben ad meg lízinget, a használatijog-eszköz (ROU) értékcsökkenése mind a könyvelési pénznemben, mind a jelentés pénznemében lecsökken. Ezek a pénznemek a **Főkönyv beállítása** oldalon vannak konfigurálva. Ez a viselkedés a Tárgyi eszközökben is használatos. Amikor külföldi pénznemben hoz létre lízinget, válassza ki a tranzakció pénznemét a **Pénznem** mezőben.

A **Könyvelési pénznem átváltási árfolyama** a könyvelési árfolyam mező alapértelmezett értéke. A **Jelentési pénznem átváltási árfolyama** a jelentési pénznem árfolyam mező alapértelmezett értéke. Ezek az átváltási árfolyamok a lízing kezdő napján voltak hatályosak. A **Könyvelési pénznem árfolyama** és a **Jelentési pénznem árfolyama** mezők a **Pénzügyi és jelentési árfolyamadatok** gyorslapon találhatók, a **Lízing részletei** lapon.

1. Jelölje be a **Rögzített árfolyam** jelölőnégyzetet az automatikusan beírt árfolyam felülbírálásához, majd adja meg az új árfolyamot.
2. A többi mezőben adja meg a lízinghez szükséges adatokat, majd válassza az **Ütemezések létrehozása** lehetőséget.
3. Az új **Lízingrészletek** oldalon válassza a **Könyvek** lehetőséget.
4. A **Lízingkönyv** lap **Pénzügyi és jelentési árfolyamadatok** lapján ellenőrizze a **Könyvelési pénznem kezdeti használatijog eszköz** és a **Jelentés pénznemének kezdeti használatijog-eszköz** mezőinek értékeit. Ezeknek a mezőknek mindegyike a lefordított ROU-eszközegyenleget mutatja a megfelelő pénznemben. Ezek a mezők minden pénzügyi információ módosításakor frissülnek. Válassza az **Ütemezések létrehozása** lehetőséget a fizetési ütemezés megerősítése előtt.

    A kezdeti megjelenítési naplóbejegyzés a lízingben szereplő árfolyamokat használó ROU-eszközt rögzíti. A naplóbejegyzés tartalmazza a **Könyvelési pénznem kezdeti használatijog-eszköz** és a **Jelentés pénznemének kezdeti használatijog-eszköz** mezőinek értékeit is.

## <a name="subsequent-measurement-for-foreign-currency-leases"></a>A devizaátértékelési lízingek későbbi mérése

Az értékcsökkenési ütemezés a várható értékcsökkenési költség összegeket mutatja a jelentési pénznemben, a könyvelési pénznemben és a tranzakció pénznemében.

Ha a ROU-eszközegyenlegeket és értékcsökkenési összegeket a jelentési pénznemben vagy a könyvelési pénznemben szeretné megtekinteni, nyissa meg az **Eszköz értékcsökkenési ütemezése** lapot, és jelölje be a **Könyvelési pénznemösszegek megjelenítése** vagy a **Jelentéspénznem-összegek megjelenítése** jelölőnégyzetet.

Amikor az értékcsökkenési költség naplóbejegyzéseket devizában denominálják a lízinghez, a bejegyzés a lízingben szereplő árfolyamokat használja. Továbbá használja a **Könyvelési pénznem kezdeti használatijog-eszköz** és a **Jelentés pénznemének kezdeti használatijog-eszköz** mezőinek értékeit is.

A végső értékcsökkenési költség összege kissé eltérő átváltási árfolyam használatával számítható ki, így a ROU-eszköz teljes mértékben amortizálódik mind a könyvelési pénznemben, mind a jelentési pénznemben.

Ha a lízinget **Halasztott bérleti díjként** sorolták be, a rendszer automatikusan törli a könyvelési és jelentési pénznemek átváltási árfolyamait, ha azokat már meghatározták.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
