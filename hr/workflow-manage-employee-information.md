---
title: "Alkalmazottadatok kezelése munkafolyamatok segítségével"
description: "Ez a témakör bemutatja, hogy miként használhatja az Emberi erőforrások munkafolyamatait az alkalmazottak információinak kezelésére. Például egy munkafolyamatot társíthat egy pozícióhoz, és konfigurálhat egy jóváhagyási munkafolyamatot, amely akkor kezdődik, amikor az alkalmazottak módosítják a rekordjaikat."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Core
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 806860e5df9252c074e04e9e1670f4215fd94ca2
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="use-workflows-to-manage-employee-information"></a>Alkalmazottadatok kezelése munkafolyamatok segítségével

[!include[banner](includes/banner.md)]


Ez a témakör bemutatja, hogy miként használhatja az Emberi erőforrások munkafolyamatait az alkalmazottak információinak kezelésére. Például egy munkafolyamatot társíthat egy pozícióhoz, és konfigurálhat egy jóváhagyási munkafolyamatot, amely akkor kezdődik, amikor az alkalmazottak módosítják a rekordjaikat.

Az Emberi erőforrások munkafolyamat-lehetőségei számos munkafolyamatot biztosítanak az emberierőforrás-tevékenységek kezeléséhez. Ezenkívül számos opció áll rendelkezésre, hogy bizonyos munkafolyamatokat módosíthasson, és társíthassa azokat egy jelentéshierarchiához. Munkafolyamatok állnak rendelkezésre, amelyek segítenek számos szabványos alkalmazottinformáció-típus változásainak kezelésében. A munkafolyamatok beosztásokkal társíthatók. Ha az alkalmazottak ezután megváltoztatják az alkalmazotti rekordjukat, akkor elindul egy munkafolyamat, amely jóváhagyást igényel az új információk mentése előtt. A munkafolyamatok előre definiálva vannak az alábbi típusú információkhoz, amelyek segítenek hatékonyan kezelni a változásokat, illetve megőrizni az alkalmazottak adatainak pontosságát:

-   Azonosítószámok
-   Tanfolyamok
-   Végzettség
-   Kép
-   Kölcsönzött cikkek
-   Szakmai tapasztalat
-   Projekttapasztalat
-   Szakértelem
-   Bizalmi beosztások
-   Emberi erőforrásokkal kapcsolatos műveletek
-   Tanfolyami regisztráció

Alkalmazottak felvétele, áthelyezése vagy elbocsátása esetén a munkafolyamat felülvizsgálati folyamatot is tartalmazhat. Ily módon egy-egy dokumentum felülvizsgálható, illetve egy művelet feltételei a munkafolyamat részeként határozhatók meg. Az ellenőrzési folyamat befejezése után a dokumentum vagy a művelet befejeződik, és a munkafolyamat egy végső jóváhagyási lépéshez kerül.

## <a name="associate-a-workflow-with-a-position-hierarchy"></a>Munkafolyamatok társítása beosztáshierarchiával
A munkafolyamatot egy tetszőleges, Ön által konfigurált hierarchiához társíthatja. Ha például egy pozíció egy mátrixjelentési hierarchiához társul, akkor konfigurálhat egy olyan munkafolyamatot, amely egy adott projekt költségeit a projektvezetőhöz irányítja az adott pozícióhoz társított munkavállaló vezetője helyett. Új munkafolyamat létrehozásához, illetve meglévő módosításához kattintson az **Emberi erőforrások munkafolyamata** lapon az **Új** lehetőségre. Válasszon ki egy munkafolyamatot a listából a Munkafolyamat-tervező elindításához. A tervező segítségével új munkafolyamatot hozhat létre, illetve módosíthatja egy meglévő munkafolyamat lépéseit. Amikor módosít egy meglévő munkafolyamatot, a módosításai új verzióként kerülnek mentésre. Így szükség esetén bármikor visszatérhet egy korábbi verzióhoz.

## <a name="configure-a-human-resources-workflow"></a>Emberi erőforrások munkafolyamatának konfigurálása
Ha konfigurálni szeretne egy alapvető munkafolyamatot, amelyik akkor indul el, amikor az alkalmazottak személyes azonosítójuk módosításait kérik, kövesse az alábbi lépéseket.

1.  Az **Emberi erőforrások munkafolyamatai** lapon kattintson az **Új** lehetőségre.
2.  Válassza ki a rendelkezésre álló munkafolyamatok listájánál az **Azonosítószámok** lehetőséget.
3.  Kattintson a **Futtatás** lehetőségre a Munkafolyamat-tervező elindításához, majd adja meg a felhasználónevet és a jelszót, amikor a rendszer erre kéri.
4.  Húzza az **Azonosítószám jóváhagyása** elemet a munkafolyamat-elemek listájáról a tervezői vászonra.
5.  Csatlakoztassa a jóváhagyási elemet a **Kezdés** és **Befejezés** pontokhoz.
6.  Kattintson duplán az **Elem jóváhagyása** pontra, majd kattintson a jobb gombra, és válassza ki a **Tulajdonságok** lehetőséget.
7.  Kövesse az alábbi lépéseket a munkatétel hozzáadásához:
    1.  Válassza ki a **Hozzárendelés** elemet, majd a **Hierarchia** lehetőséget a hozzárendelés típusánál.
    2.  A **Hierarchia** kijelölés alatt válassza ki a **Konfigurálható hierarchia** lehetőséget.
    3.  Adja hozzá a leállási feltételt, majd zárja be az oldalt.

8.  Töltse ki a további utasításokat (ne maradjanak további figyelmeztetések).
9.  Kattintson a **Mentés és bezárás** pontra. Aktiválja az új munkafolyamatot, amikor megnyílik a párbeszédpanel, és válassza ki a **Legyen aktív** lehetőséget.
10. Lépjen az **Emberi erőforrások** &gt; **Beosztások** &gt; **Beosztáshierarchia-típusok** ponthoz.
11. Válassza ki a **Mátrix** lehetőséget.
12. Adja hozzá a **Dolgozó azonosítószáma** munkafolyamatot a listához.





