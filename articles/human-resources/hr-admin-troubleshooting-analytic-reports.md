---
title: Elemzési jelentések hibaelhárítása
description: Ez a cikk bemutatja, hogy mi a teendő, ha a vevő adatainak módosításai nem jelennek meg a vevő munkaterületein.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b500d519d61edfd20456355376e3fc81f16517a0
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794973"
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