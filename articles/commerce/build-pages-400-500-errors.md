---
title: Egyéni válaszlapok összeállítása a 4xx/5xx állapotkódhibákhoz
description: Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce szerkesztési eszközeivel egyéni válaszoldalakat létrehozni a 4xx és 5xx állapotkódú hibákhoz.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4477a0a43971b5322c6acd6971cba2e79e2dc8c6
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001128"
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

1. Lépjen a **Sablonok \> Új sablon** lehetőségre.
1. Nevezze el az új sablont.
1. Állítsa össze a sablont a struktúra alapján, amelyet az állapotkód hibaválaszoldalának kíván adni.
1. Adja be a sablont és tegye közzé.

### <a name="build-the-status-code-error-response-page"></a>Az állapotkód hibaválaszoldal összeállítása

Állapotkód hibaválaszoldal összeállításához hajtsa végre az alábbi lépéseket.

1. Lépjen a **Lapok \> Új lap** lehetőségre.
1. Nevezze el az állapotkód hibaválaszoldalt, de **ne** állítsa be az **URL** mezőt.
1. Állítsa össze a lapot.
1. Adja be a lapot, és tegye közzé.

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
