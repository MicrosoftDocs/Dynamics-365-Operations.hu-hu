---
title: "Termelési rendelés alapbeállításai a gyártásvégrehajtásban"
description: 
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: JmgProdParameters
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 70073
ms.assetid: 620944ae-3e20-444a-807e-65495f160904
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: af6e6db2523041dd8dbcef692c252c596802c22d
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="production-order-defaults-in-manufacturing-execution"></a>Termelési rendelés alapbeállításai a gyártásvégrehajtásban

[!include[banner](../includes/banner.md)]




Alaposan fontoljon meg a **Termelési rendelés alapértékei** oldal beállításait, mielőtt a dolgozók elkezdenek regisztrációkat tenni a termelési feladatokba. Ha a vállalat a többhelyes funkciót használja, érdemes a gyártási rendeléseknél mindegyik helyhez más alapértelmezett értékeket beállítani. A rendelés alapértelmezései a Gyártásvezérléssel **Termelési rendelés alapértelmezései** lapon a következő oldalakon állíthatók be:

-   **Általános** – Általános rendelési alapértelmezések a termelési feladatokhoz a Gyártásvégrehajtás modulban.
-   **Kezdő** – Rendelési alapértelmezések, amelyek a termelési feladatok vagy a műveletek indításakor vannak érvényben.
-   **Műveletek** – A termelési feladatokra és műveletekre alkalmazott rendelési alapértelmezések a termelési folyamat során.
-   **Jelentés készként** – A cikkek készként való jelentésekor használt jelentési alapértelmezések a termelési rendelés utolsó műveletekor.
-   **Mennyiség ellenőrzése** – A termelési rendelések kezdő és a visszajelzési mennyiségeinek ellenőrzésekor használt rendelési alapértelmezések.

## <a name="types-of-production-jobs"></a>A termelési feladatok típusai
A **Műveletek** lapon azokat a termelési feladattípusokat választjuk ki, amelyek a **Feladatregisztráció** oldalon regisztrációt igényelnek. Általában a dolgozók beállítási feladatokon és feldolgozási feladatokon regisztrálnak. Azonban ha feladatütemezést alkalmaznak, kiválaszthat további feladattípusokat, például a szállítási feladatokat, melyeken a dolgozóknak regisztrálniuk kell a termelési rendelés feldolgozása során. **Fontos:** Győződjön meg arról, hogy minden releváns feladattípus ki van választva. Ellenkező esetben feladatok lehet, hogy nem lesznek elérhetők a regisztrációhoz a **Regisztráció** oldalon. Egyeztesse a kiválasztásokat a **Munkakezelés** oszlopban megadott kiválasztásokkal az **Útvonalcsoportok** lapon. Ha a **Munkakezelés** van kiválasztva az útvonalcsoporton, a feladattípus készként lesz jelentve a termelési rendelésen. Ez a jelentés fordul elő, amikor a feladat készként van jelentve a Gyártásvégrehajtás modulban. Ha minden feladattípus, amelyhez a **Munkakezelés** ki van jelölve, készként lett jelentve egy művelet esetén, a Gyártásvégrehajtás modul is készként jelenti a műveletet. **Megjegyzés:** Egyes feladattípusok saját kezűleg is készként jelenthetők a termelési naplókon keresztül. Ebben az esetben válassza a **Munkakezelés** lehetőséget a feladattípushoz, de ne válassza ki a feladattípus regisztrációját a **Műveletek** lapon a **Termelési rendelés alapértelmezései** oldalon.

## <a name="bom-consumption-and-picking-list-journals"></a>Anyagjegyzék-felhasználás és kitárolási listák naplói
Az anyagokat be lehet állítani úgy, hogy azokat automatikusan vagy kézzel lehessen a termelés során felhasználni. Az automatikus felhasználást az ürítési elv irányítja, amely az anyagjegyzék (AJ) sorokon, és a termelési rendelés alapértelmezéseinél, az **Automatikus Anyagjegyzék-felhasználás** mezőben van beállítva. Az automatikus felhasználást be lehet állítani úgy, hogy akkor jelenjen meg, amikor egy termelési rendelés elkezdődik vagy készként van jelentve. Másik lehetőségként a feladat szintjén feladat kezdése vagy befejezése esetén is megjelenhet.

### <a name="controlling-material-consumption-when-a-production-order-is-started"></a>A termelési rendelés indításakor az anyagfelhasználás irányítása

Az anyagfelhasználást egy termelési rendelés indítása során az **Automatikus anyagjegyzék-felhasználás** mező irányítja, a **Start** lapon. A következő értékek állnak rendelkezésre:

-   **Ürítési elv** – A termelési rendelés indításakor az anyagmennyiségek a termelési anyagjegyzék-sorokban beállított ürítési elv szerint lesznek felhasználva. Csak olyan anyagsorok lesznek felhasználva a termelés indításakor, ahol az ürítési elv **Start** lehetőségre van beállítva.
-   **Mindig** – Az elindított mennyiséggel arányos anyagmennyiséget mindig felhasználásként rögzíti.
-   **Soha** – Az anyagmennyiségek soha nem lesznek felhasználva.

### <a name="controlling-material-consumption-when-a-production-job-is-started-or-completed"></a>A termelési feladat indításakor vagy befejezésekor az anyagfelhasználás irányítása

Az anyagfelhasználást egy termelési feladat indítása vagy befejezése során az **Automatikus anyagjegyzék-felhasználás** mező irányítja, a **Műveletek** lapon. A következő értékek állnak rendelkezésre:

-   **Ürítési elv** – Ha egy mennyiség egy termelési feladaton elindul vagy befejeződik, az anyagmennyiségek a termelési anyagjegyzék-sorokban beállított ürítési elv szerint lesznek felhasználva. Csak olyan anyagsorok lesznek felhasználva, ahol az ürítési elv **Start** vagy a **Befejezés** lehetőségre van beállítva.
-   **Mindig** – A feladaton elindított mennyiséggel arányos anyagmennyiséget mindig felhasználásként rögzíti.
-   **Soha** – Az anyagmennyiségek soha nem lesznek felhasználva.

### <a name="controlling-material-consumption-when-a-production-order-is-reported-as-finished"></a>A termelési rendelés befejezésekor az anyagfelhasználás irányítása

Az anyagfelhasználást egy termelési rendelés készként való jelentése során az **Automatikus anyagjegyzék-felhasználás** mező irányítja, a **Készként való jelentés** lapon. A következő értékek állnak rendelkezésre:

-   **Ürítési elv** – A termelési rendelés készként való jelentésekor az anyagmennyiségek a termelési anyagjegyzék-sorokban beállított ürítési elv szerint lesznek felhasználva. Csak olyan anyagsorok lesznek felhasználva, ahol az ürítési elv a **Befejezés** lehetőségre van beállítva.
-   **Mindig** – A készként jelentett mennyiséggel arányos anyagmennyiséget mindig felhasználásként rögzíti.
-   **Soha** – Az anyagmennyiségek soha nem lesznek felhasználva.





