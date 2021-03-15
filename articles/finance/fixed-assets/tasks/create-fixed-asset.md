---
title: Tárgyi eszköz létrehozása
description: Ez a témakör azt mutatja be, hogyan lehet új tárgyieszköz-rekordot létrehozni a tárgyi eszköz lista lapjáról.
author: moaamer
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ab330c604b2485687544a7d8b3eef3a652fa2069
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985137"
---
# <a name="create-a-fixed-asset"></a>Tárgyi eszköz létrehozása

[!include [banner](../../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet új tárgyieszköz-rekordot létrehozni a **Tárgyi eszköz** lista lapjáról.

A rendszer hozzárendeli az eszköz számát a tárgyieszköz-csoporthoz rendelt számsorozat alapján. Ha a tárgyi eszköz sablonnal importál eszközöket a Microsoft Excel-bővítmény segítségével, vagy ha másik importálási feladatot alkalmaz, a rendszer automatikusan létrehozza a tárgyieszköz-rekordokat, és növeli a tárgyi eszköz számát.

Eszközrekord kézi létrehozásához hajtsa végre az alábbi lépéseket.

1. Ugorjon a **Navigációs ablaktábla \> Modulok \> Tárgyi eszközök \> Tárgyi eszközök \> Tárgyi eszközök** elemre.
2. A **műveleti ablaktáblán** kattintson az **Új** elemre.
3. A **Tárgyieszköz-csoport** mezőben adjon meg vagy válasszon ki egy értéket. A **Szám** mező alapértelmezett értéket vesz fel, ha engedélyezte **Tárgyi eszközök automatikus számozása funkciót** a **Tárgyi eszközök paramétereinél** és a **Tárgyieszköz-csoportban**. Ha nem, akkor meg kell adni egy egyedi számot a tárgyi eszköz azonosítására.
4. A **Név** mezőben adjon meg egy értéket. Adja meg a kiegészítő információkat amelyek szükségesek a vállalata számára ezzel az eszközzel kapcsolatban.
5. A **Művelet panelen** kattintson a **Könyvek** elemre.
6. Adja meg a dátumot a **Beszerzési dátum** mezőben.
7. Adjon meg egy számot a **Beszerzési ár** mezőben.

    - Adja meg a kiegészítő információkat, amelyek szükségesek a vállalata számára ezzel a könyvvel kapcsolatban.
    - Adja meg a kiegészítő információkat, amelyek szükségesek a vállalata számára a fennmaradó könyvekkel kapcsolatban.

8. Zárja be a lapot.

A tárgyi eszközök importálása az Excel-bővítmény segítségével vagy az **adatkezelés** munkaterületről származó importálási feladat futtatásával is történhet . Az importálás futtatása előtt írja be a sablonban a kötelező mezők értékeit.

Ha nem definiálta a tárgyi eszköz számát az Excel-bővítmény sablonjában vagy az adatkezelés modulban, akkor a rendszer minden importált eszközhöz létrehoz egy tárgyi eszköz számát, és automatikusan megnöveli a számsorozatot mindegyikhez. Ha viszont eszközöket importál, és a sablonban adja meg a tárgyi eszköz számát, a rendszer **nem** növeli automatikusan a számsorozatot. Ebben az esetben előfordulhat, hogy a rendszergazdának manuálisan frissíteni kell a számsorozatot. Ha a tárgyi eszköz számát az Excel-bővítmény sablonjában definiálta, akkor a rendszer a meghatározott tárgyi eszköz számát használja, és növeli a számsorozatot.

> [!NOTE]                                                                                                         
> Az értékcsökkenés feladása után az **Aktivált** és az **Értékcsökkenés futtatási dátum** mezők zárolva lesznek a **Könyv** oldalon. Emellett egyik mező sem frissül az adatentitásból.

> [!WARNING]
> A rögzített eszközrekord nem törlődik, ha a tranzakciókat a kapcsolódó könyvbe adták fel, vagy ha az újonnan létrehozott eszközt naplósorban adták meg, de nem adták fel. 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]