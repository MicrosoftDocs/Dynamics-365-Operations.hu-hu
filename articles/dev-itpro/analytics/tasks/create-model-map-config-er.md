---
title: Elektronikus jelentés (ER) modell-leképezési konfigurációk kezelése elektronikus jelentéskészítéshez
description: A folyamat segítségével új, elektronikus jelentésen (ER) alapuló modell-leképezési konfigurációt tervezhet meg, és a beépített ER-funkciók segítségével hatékony összesített számításokat végezhet.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 614ef06fcf5761f1cf2afb6e7655558d2858d763
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544956"
---
# <a name="create-electronic-reporting-er-model-mapping-configurations"></a>Elektronikus jelentés (ER) modell-leképezési konfigurációk kezelése elektronikus jelentéskészítéshez

[!include [task guide banner](../../includes/task-guide-banner.md)]

A folyamat segítségével új, elektronikus jelentésen (ER) alapuló modell-leképezési konfigurációt tervezhet meg, és a beépített ER-funkciók segítségével hatékony összesített számításokat végezhet. Ebben a folyamatban egy konfigurációt hoz létre a Litware, Inc. minta vállalatra vonatkozóan. 

Ez az eljárás a rendszergazda vagy az elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználók számára készült.

Ezek a lépések bármely adathalmazzal végrehajthatók. Hajtsa végre az alábbi lépéseket: először hajtsa végre a „Konfigurációszolgáltató létrehozása és aktívként történő megjelölése” eljárás lépéseit.

1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
    * Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és aktívként van megjelölve a konfigurációszolgáltató. Ha nem látja a konfigurációszolgáltatót, végezze el a „Konfigurációszolgáltató létrehozása, és megjelölés aktívként” eljárásban szereplő lépéseket.  
2. Kattintson a Jelentéskészítés konfigurációi lehetőségre.
3. Kattintson a Szűrők megjelenítése pontra.
4. Írja be az „Intrastat” szűrőértéket a Név mezőbe az „ezzel kezdődik” szűrési operátor használatával.
    * Alkalmazza ezt a szűrőt az Intrastat adatmodell-konfiguráció keresésekor. Megtörténhet, hogy a modell már létezik a konfigurációs fán. Ha igen, ugorjon a következő alfeladatra.   

## <a name="get-the-intrastat-model-configuration-provided-by-microsoft"></a>A Microsoft által biztosított Intrastat modellkonfiguráció beszerzése
1. Zárja be a lapot.
2. Zárja be a lapot.
3. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
4. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válassza ki a Microsoft lapot.  
5. Kattintson a Tárházak gombra.
    * Kattintson a Tárházak lehetőségre a Microsoft lapon.  
6. Kattintson a Szűrők megjelenítése pontra.
7. Írja be az „erőforrások” szűrőértéket a Típusnév mezőbe a „tartalmazza” szűrési operátor használatával. 
8. Kattintson a Megnyitás gombra.
9. A fastruktúrában válassza ki az „Instrastat modell” elemet.
10. Kattintson az Importálás gombra.
11. Kattintson az Igen gombra.
    * Importálta azt az ER modellkonfigurációt, amely tartalmazza azt az adatmodellt, amelyet használni fog az új ER-funkciók használatának megismerése során.  
12. Zárja be a lapot.
13. Zárja be a lapot.
14. Kattintson a Jelentéskészítés konfigurációi lehetőségre.

## <a name="add-a-new-model-mapping-configuration"></a>Új modell-leképezési konfiguráció hozzáadása
1. A fastruktúrában válassza ki az „Instrastat modell” elemet.
2. A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.
3. Az Új mezőbe írja be az „Intrastat adatmodellen alapuló modell-leképezés” kifejezést.
4. A Név mezőbe írja be az „Intrastat mintaleképezés” szöveget.
    * Intrastat mintaleképezés  
5. Kattintson a Konfiguráció létrehozása lehetőségre.

