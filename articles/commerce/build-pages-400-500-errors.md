---
title: Egyéni válaszlapok összeállítása a 4xx/5xx állapotkódhibákhoz
description: Ez a témakör azt ismerteti, hogyan lehet egyéni válaszlapokat felépíteni a 4xx- és 5xx-es állapotkódhibákhoz a Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 4a3b1762cebc74c1b77f9ca60925608bc966e306
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276400"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a>Egyéni válaszlapok összeállítása a 4xx/5xx állapotkódhibákhoz

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet egyéni válaszlapokat felépíteni a 4xx- és 5xx-es állapotkódhibákhoz a Microsoft Dynamics 365 Commerce.

Ha egy kérés nem sikerült, a kiszolgáló HTTP-állapotkódos hibajelzéseket ad ki. A 404-es állapotkódot rögzíti és adja vissza a program, ha nem találja meg a lapot, és az 500-as állapotkódot rögzíti és adja vissza a rendszer a kiszolgáló meghibásodása esetén. A Dynamics 365 Commerce alkalmazás felhasználói egyéni állapotkód hibaválaszoldalakat állíthatnak össze, amelyek ezeknél az állapotkód hibaüzenetek esetében megjelenítésre kerülnek a felhasználó számára.

## <a name="build-a-status-code-error-response-page"></a>Állapotkód hibaválaszoldal összeállítása

Állapotkód hibaválaszoldal összeállításához hajtsa végre az alábbi lépéseket.

1. A kívánt webböngészőben jelentkezzen be a Dynamics 365 Commerce alkalmazásba. 
1. Válassza ki a webhelyet, amelyhez a 4xx/5xx állapotkód hibaválaszoldalt össze kívánja állítani.

### <a name="build-the-template"></a>Állítsa össze a sablont

Állapotkód hibaválaszoldal sablonjának összeállításához hajtsa végre az alábbi lépéseket.

1. Ugorjon a **Sablonok** részre.
1. Válassza az **Új** lehetőséget egy oldalsablon létrehozásához.
1. Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg az új sablon nevét, majd válassza az **OK** gombot.
1. Állítsa össze a sablont a struktúra alapján, amelyet az állapotkód hibaválaszoldalának kíván adni.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez. 

### <a name="build-the-status-code-error-response-page"></a>Az állapotkód hibaválaszoldal összeállítása

Állapotkód hibaválaszoldal összeállításához hajtsa végre az alábbi lépéseket.

1. Lépjen az **Oldalak** pontra.
1. Válassza az **Új** lehetőséget egy oldal létrehozásához.
1. A **Sablon kiválasztása** párbeszédpanelen válasszon ki egy sablont, majd az **Oldal neve** területen írja be az állapotkód-válasz lap nevét. Hagyja üresen az **Oldal URL-címe** mezőt.
1. Állítsa össze a lapot.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

> [!NOTE]
> A 4xx és a 5xx állapotkódú hibákhoz külön állapotkód hibaválaszoldalakat lehet létrehozni. Másik lehetőségként ugyanaz az általános állapotkód hibaválaszoldal használható mindkét hibakategória esetén.

### <a name="set-up-a-redirect-for-the-status-code-error-response-page"></a>Átirányítás beállítása az állapotkód hibaválaszoldal számára

Állapotkód hibaválaszoldal átirányításának beállításához hajtsa végre az alábbi lépéseket.

1. Lépjen az **URL-ek \> Új \> Új álnév** lehetőségre, majd válassza ki a korábban összeállított állapotkód hibaválaszoldalt.
1. Az **Álnév** mezőbe írja be az **alapértelmezett-4xx** vagy az **alapértelmezett-5xx** értéket attól függően, hogy melyik állapotkód hibaválaszoldalhoz állít be átirányítást. Ezeket az álneveket közzé kell tenni. Ellenkező esetben az átirányítás nem fog működni.
1. A hivatkozás véglegesítéséhez válassza az **OK** lehetőséget.

> [!NOTE]
> Ha egyetlen állapotkód-hibaválaszoldalt használ a mindkét hibakategória esetén, akkor ismételje meg ezt az eljárást, hogy egy álnevet hivatkozzon ugyanannak a lapnak a másik hibakategóriájához.

## <a name="additional-resources"></a>További erőforrások

[Sablonok használata](work-with-templates.md)

[Új webhelyoldal hozzáadása](add-new-page.md)

[Weblap URL-jének létrehozása](create-page-url.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
