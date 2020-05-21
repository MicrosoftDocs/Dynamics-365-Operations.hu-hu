---
title: Adatellenőrzési ellenőrzőlista munkaterülete
description: Az Adatellenőrzési ellenőrzőlista munkaterülete lehetővé teszi az adatok ellenőrzésének folyamatát a vállalatok, a területek és az emberek között. Az ellenőrzőlistát új implementáció, frissítés vagy áttelepítés után lehet használni.
author: bking
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DataValidationWorkspace
audience: Application User
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.assetid: ''
ms.search.region: Global
ms.author: bking
ms.openlocfilehash: ab3d470150a5fbcfebcff685350deaaafa67ec88
ms.sourcegitcommit: 17fe0218e8e3f2f4c57c73c0c438a6ebf1ef32a6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/01/2020
ms.locfileid: "3329911"
---
# <a name="data-validation-checklist-workspace"></a>Adatellenőrzési ellenőrzőlista munkaterülete

[!include [banner](../includes/banner.md)]

Ez a témakör betekintést nyújt az **Adatellenőrzési ellenőrzőlista munkaterületébe** és az ehhez társított beállításokba.

Az **Adatellenőrzési ellenőrzőlista** munkaterülete lehetővé teszi az adatok ellenőrzésének folyamatát a vállalatok, a területek és az emberek között. Az ellenőrzőlistát új implementáció, frissítés vagy áttelepítés után lehet használni. Az **Adatellenőrzési ellenőrzőlista** munkaterület nézetétől függően vagy az egy adatellenőrzési ellenőrzőlistához tartozó összes feladatot és állapotot látja, vagy csak azokat a feladatokat amelyek önre lettek kiosztva.

Először meg kell adnia az adatellenőrzési projektet a munkaterület tetején. Ezután a munkaterületen megjelenített összes adatot szűri a program, a kiválasztott adatellenőrzési projekt szerint.

## <a name="summary-tiles"></a>Összesítő csempék

Az **Összefoglaló** csempéken áttekintheti a folyamatokat, az indikátorok pedig segítik az adatellenőrzési folyamat nyomon követését. Megtekinthet minden fennmaradó feladatot, befejeződött feladatot, illetve el nem kezdődött feladatot a folyamatnál. Ez az információ minden vállalatra vonatkozik, amelyik a kiválasztott adatellenőrzési projektben szerepel.

## <a name="tasks-and-status-section"></a>Feladatok és állapot szakasz

A **Feladatok és állapot** szakaszban, az összesített adatellenőrzési projekt különböző módokon jelenik meg: jogi személy szerinti állapot, terület szerinti állapot és feladatlista szerinti állapot. A szűrőt beállíthatja egy kiválasztott vállalat állapotának mutatására is. Minden állapot lap lebontásra kerül a teljesített feladatok százalékos arányára és a hátralevő feladatok számára.

Az utolsó lapon a részletes feladatok listája látható. A listán a teljes feladatlista jelenik meg.
A feladatlistára számos szűrést alkalmazhat. Kattintson a **Feladat szerkesztése** pontra, ha módosítani szeretné egy feladat állapotát, illetve ki szeretne osztani egy feladatot. Kattintson a **Mellékletek** lehetőségre, ha meg szeretné tekinteni egy feladat mellékleteit.

A feladat neve egy hivatkozás, amely az oldalra mutat, amelyet a felhasználónak fel kell keresnie a feladat befejezéséhez. A **Menüpont neve** mezőben beállíthatja ezt a hivatkozást a feladat **Adatellenőrzési projekt konfigurálása** űrlapon történő szerkesztésekor vagy létrehozásakor.

Csatolhat fájlokat, megjegyzéseket, képeket és URL-eket egy feladathoz a **Mellékletek** művelettel. Mellékelhet például egy jelentésfájlt, amely egy feladathoz lett kinyomtatva. Egy ikon jelenik meg a **Melléklet** oszlopban a feladatnál, ha a feladat rendelkezik melléklettel.

A **Kitöltötte** lehetőség kitöltése a feladatot elvégző dolgozó nevével automatikus azt követően, hogy a feladat elkészül. Amikor egy feladatot befejezettként jelöl meg, akkor a **Befejezés dátuma** mező automatikusan frissül az aktuális dátumra és időre.

## <a name="configure-data-validation-project-page"></a>Adatellenőrzési projekt oldalának konfigurálása

Az **Adat-ellenőrzési ellenőrzőlista** munkaterület használata előtt konfigurálja a folyamatot az **Adatellenőrzési projekt konfigurálása** oldalon. (Kattintson a **Munkaterületek** \> **Adatellenőrzési ellenőrzőlista** \> **Adatellenőrzési projekt konfigurálása** pontra.)

## <a name="task-areas"></a>Feladatterületek

Használhat logikai feladatterületeket a szervezeten belül, csoportos ellenőrzési feladatokhoz. Például a Kötelezettségek, Kinnlevőségek vagy a Főkönyv használható feladatterületként.

A **Menüpont neve** menüelem a feladathoz van rendelve és segítségével közvetlenül a társított oldalara lehet ugrani a feladathivatkozásról a munkaterületen. Például ahhoz, hogy egy adatellenőrzési feladat fusson, a kötelezettségekhez tartozó **Kötelezettségek korosítása** jelentés összekapcsolható a **Kötelezettségek korosítási jelentése** oldallal.
