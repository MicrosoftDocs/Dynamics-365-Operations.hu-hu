---
title: A Store Commerce bővítményekkel kapcsolatos problémák elhárítása
description: Ez a témakör ismerteti, hogyan lehet elhárítani a Store Commerce alkalmazás bővítésével Microsoft Dynamics 365 Commerce kapcsolatos problémákat.
author: josaw1
ms.date: 06/01/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 1a2d6a68b7556d8b4d05529efd90f9e66f0c5925
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269781"
---
# <a name="troubleshoot-store-commerce-extension-issues"></a>A Store Commerce bővítményekkel kapcsolatos problémák elhárítása

[!include [banner](../includes/banner.md)]

Ez a témakör ismerteti, hogyan lehet elhárítani a Store Commerce alkalmazás bővítésével Microsoft Dynamics 365 Commerce kapcsolatos problémákat.

## <a name="extensions-packages-arent-loaded"></a>A bővítmények csomagjai nincsenek betöltve.

### <a name="extensions-packages-dont-appear-on-the-pos--settings-page"></a>A bővítmények csomagjai nem jelennek meg a POS-beállítások \> lapon.

Lehet, hogy a Commerce runtime (CRT) eseményindítók frissítése nem történt meg úgy, hogy tartalmazza a bővítménycsomagot, vagy nincsenek telepítve. További tudnivalók: [Commerce runtime (CRT) extensibility és triggers](../dev-itpro/commerce-runtime-extensibility-trigger.md).

### <a name="extensions-packages-appear-on-the-pos--settings-page-but-the-manifest-isnt-loaded"></a>A bővítmények csomagjai megjelennek a POS-beállítások \> lapon, de a jegyzékfájl nincs betöltve.

Győződjön meg arról, hogy a bővítmények csomagjai **léteznek a C:\\ Program Files\\Microsoft Dynamics 365\\ 10.0\\ Store Commerce\\ Extensions mappában**. Ha léteznek csomagok, akkor léteznie kell egy pénztári **mappának, amely tartalmazza a** jegyzékfájlt.

Ha nincs POS **mappa**, győződjön meg arról, hogy a Store Commerce-projekt megfelelően hivatkozik a pénztári (POS) bővítményprojektre. Ellenőrizze a projekt hivatkozási útvonalát, és ellenőrizze, hogy létezik-e. 

A következő példa szerint a telepítőprojektben problémák vannak a hivatkozott bővítményprojekttel.

![A Store Commerce telepítő projekthivatkozása nem érvényes.](media/ReferenceNotValid.png)

Ha a bővítményprojekt hivatkozása megfelelően van hozzáadva, a telepítőprojektben nem jelenik meg figyelmeztetés vagy függőségi probléma, amint azt az alábbi példa mutatja.

![A Store Commerce telepítő projekthivatkozása érvényes.](media/ReferenceValid.png)
