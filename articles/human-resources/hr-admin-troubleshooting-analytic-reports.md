---
title: Elemzési jelentések hibaelhárítása
description: Ez a cikk bemutatja, hogy mi a teendő, ha a vevő adatainak módosításai nem jelennek meg a vevő munkaterületein.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8dab12213e9730e72aede70c5b5d1368ef77664e
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053539"
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

![Kötegelt feladatok](media/batch-jobs.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]