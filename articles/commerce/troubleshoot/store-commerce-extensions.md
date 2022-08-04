---
title: A Store Commerce bővítményekkel kapcsolatos problémák elhárítása
description: Ez a témakör ismerteti, hogyan lehet elhárítani a Store Commerce alkalmazás bővítésével Microsoft Dynamics 365 Commerce kapcsolatos problémákat.
author: mugunthanm
ms.date: 06/01/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: b440183e255e05c4f93a4f11106be2967163ff74
ms.sourcegitcommit: c271b2edc4bf777f7194b09139ccbd174a359c75
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/16/2022
ms.locfileid: "9169017"
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
