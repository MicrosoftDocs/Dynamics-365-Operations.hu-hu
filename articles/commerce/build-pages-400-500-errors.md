---
title: Egyéni válaszlapok összeállítása a 4xx/5xx állapotkódhibákhoz
description: Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce szerkesztési eszközeivel egyéni válaszoldalakat létrehozni a 4xx és 5xx állapotkódú hibákhoz.
author: v-chgri
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d21ce20b2c7ac8c656a718749dabd76f33893da8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991465"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a>Egyéni válaszlapok összeállítása a 4xx/5xx állapotkódhibákhoz


[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce szerkesztési eszközeivel egyéni válaszoldalakat létrehozni a 4xx és 5xx állapotkódú hibákhoz.

## <a name="overview"></a>Áttekintés

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