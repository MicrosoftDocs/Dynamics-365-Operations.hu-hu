---
title: "Alkalmazotti adatok kezelése munkafolyamatok segítségével"
description: "Ez a témakör ismerteti, hogyan használhatja a munkafolyamat képes az emberi erőforrások kezelésére alkalmazott adatai. Például egy munkafolyamat társítani a pozícióhoz és az alkalmazottak módosításakor a rekord elindított jóváhagyási munkafolyamat beállítása."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: a76ec0cd86bcc810b42ae3cd8efd8a584e6c4da3
ms.openlocfilehash: f286436aa4833babaeb3de875ee393d18e5f8eea
ms.lasthandoff: 03/31/2017


---

# <a name="use-workflows-to-manage-employee-information"></a>Alkalmazotti adatok kezelése munkafolyamatok segítségével

Ez a témakör ismerteti, hogyan használhatja a munkafolyamat képes az emberi erőforrások kezelésére alkalmazott adatai. Például egy munkafolyamat társítani a pozícióhoz és az alkalmazottak módosításakor a rekord elindított jóváhagyási munkafolyamat beállítása.

Az emberi erőforrások munkafolyamat képes számos munkafolyamatok biztosít az emberi erőforrások tevékenységek kezelése. Ezenkívül számos beállítások érhetők el, hogy az adott munkafolyamatok módosítása, és társíthatja őket a jelentéstételi hierarchia. A munkafolyamatok is segíti a szokásos típusú alkalmazotti információkat változásainak kezelése. Munkafolyamat olyan helyzetben is társíthat. Ezután az alkalmazott rekordját az alkalmazottak módosítjuk egy munkafolyamat indítása az új információk mentése előtt jóváhagyást igénylő. A munkafolyamatok előre a következő típusú adatok segítségével hatékonyan kezelheti a változások és az alkalmazottak adat pontos megtartása:

-   Azonosítószámok
-   Tanfolyamok
-   Végzettség
-   Kép
-   Kölcsönzött cikkek
-   Szakmai tapasztalat
-   Projekttapasztalat
-   Szakértelem
-   Bizalmi beosztások
-   Emberi erőforrások-műveletek
-   Tanfolyami regisztráció

Alkalmazottak felvett, átadott vagy megszüntetik, amikor a munkafolyamat felülvizsgálati folyamat is tartalmazhat. Ily módon felül kell vizsgálni a dokumentum vagy a művelet feltételeit a munkafolyamat részeként lehet meghatározni. Az ellenőrzési folyamat befejezése után a dokumentum vagy a művelet befejeződik, és a munkafolyamat egy végső jóváhagyási lépés helyezi át.

## <a name="associate-a-workflow-with-a-position-hierarchy"></a>Pozíció hierarchiába munkafolyamat társítása
Minden hierarchiát, beállíthatja a munkafolyamat is társíthat. Például ha olyan helyzetben társítva a mátrix jelentéstételi hierarchia, konfigurálhatja a munkafolyamat, amely egy adott projekt költségek helyett az alkalmazottat, aki az adott helyzetben társított vezetője a projekt vezető irányítja. Hozzon létre egy új munkafolyamat, vagy módosítsa a meglévő munkafolyamat, a **az emberi erőforrások munkafolyamat** lap **új**. A Workflow designer indítása a listában jelölje be a munkafolyamat. A tervező segítségével egy új munkafolyamat létrehozása vagy módosítása a meglévő munkafolyamat lépéseit. Egy létező munkafolyamat módosításához a módosításokat új verzióként menti. Ezért mindig visszatérhet egy korábbi verzióját Ha.

## <a name="configure-a-human-resources-workflow"></a>Az emberi erőforrások munkafolyamat beállítása
Az alkalmazottak kérhetik a személyes azonosítószámát módosítását elindított alapvető munkafolyamat konfigurálásához kövesse az alábbi lépéseket.

1.  A a **emberi erőforrásokkal kapcsolatos munkafolyamatok** lap **új**.
2.  Válassza ki a listából a rendelkezésre álló munkafolyamatok, **azonosító számokat**.
3.  Kattintson a **futtassa a** a Workflow designer indítása, és a rákérdezéskor adja meg a felhasználónevet és a jelszót.
4.  Húzza a **jóváhagyása azonosító számot** a munkafolyamat-elemek listáját a Tervező Vászonhoz viszonyítva elemét.
5.  Csatlakozás a jóváhagyási elem **Start** és **Befejezés**.
6.  Kattintson duplán a **jóváhagyás elem**, és majd kattintson a jobb gombbal, és válassza ki **tulajdonságok**.
7.  Kövesse az alábbi lépéseket a munka elem utasítások hozzáadása:
    1.  Válassza ki **hozzárendelés**, majd **hierarchia** alatt a hozzárendelés-típus.
    2.  Alatt a **hierarchia** kijelölés select **konfigurálható hierarchia**.
    3.  A leállási feltétel hozzáadása, és zárja be a lapot.

8.  Töltse ki a további utasításokat (nincs további figyelmeztetések léteznie kell).
9.  Kattintson a **Mentés és bezárás** pontra. Az új munkafolyamat aktiválása, ha a párbeszédpanel megnyitása mezőbe, és válassza a **legyen aktív**.
10. Ugrás a **az emberi erőforrások**&gt;**pozíciók**&gt;**hierarchia típusok helyezze**.
11. Válassza ki **mátrix**.
12. Adja hozzá a **dolgozó azonosító száma** munkafolyamat listához.



