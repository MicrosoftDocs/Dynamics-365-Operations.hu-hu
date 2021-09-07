---
title: Elemzési jelentések hibaelhárítása
description: Ez a téma elmagyarázza, hogyan kell hibaelhárítani és diagnosztizálni a problémákat, ha egy ügyfél adatváltoztatásai nem jelennek meg az ügyfél egyik munkaterületén sem.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2d085c041c1d12eef1271fd3f78262be19fd0629
ms.sourcegitcommit: 7e32e5e39e762a4b1606161cb603a450d13b5251
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2021
ms.locfileid: "7413435"
---
# <a name="troubleshoot-analytic-reports"></a>Elemzési jelentések hibaelhárítása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Kibocsátás**

A vevő adatainak módosításai nem jelennek meg az **Elemzések** lapon a vevő egyik munkaterületén sem.

**Ok**

Alapértelmezés szerint a Microsoft Power BI jelentések négy óránként frissülnek, a Mérték telepítése kötegelt feladat ütemezése szerint.

**Felbontás**

A probléma lehet, hogy csak az időzítésen múlik. Kövesse az alábbi lépéseket a kötegelt feladat megkezdéséhez és az Elemzések munkaterületek frissítéséhez.

1. Nyissa meg a **Kötegelt feladatok** oldalt a **Rendszerfelügyelet \> Hivatkozások \> Kötegelt feladatok \> Kötegelt feladatok** menüpontban. Azt is megteheti, hogy a Keresésben adja meg **Kötegelt feladatok** kifejezést.
1. Keresse meg a **Mérték telepítése** feladatot a listában.
1. Válassza a **Szerkesztés** lehetőséget az oldal felső részén, és állítsa az ütemezett kezdő dátumot/idépontot olyan értékre, amely a jelenlegi időhöz közelebb frissíti az elemzéseket.

![Kötegelt feladatok.](media/batch-jobs.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
