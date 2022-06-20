---
title: Alkalmazotti adatok kezelése munkafolyamatok segítségével
description: Ez a cikk bemutatja, hogy hogyan használhatók a munkafolyamatok az alkalmazotti adatok kezelésére.
author: twheeloc
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 2fcbacc3cb891043560fabf28487bfeb12d1b77b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908801"
---
# <a name="use-workflows-to-manage-employee-information"></a>Alkalmazotti adatok kezelése munkafolyamatok segítségével


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a cikk bemutatja, hogy miként használhatja az Emberi erőforrások munkafolyamatait az alkalmazottak információinak kezelésére. Például egy munkafolyamatot társíthat egy pozícióhoz, és konfigurálhat egy jóváhagyási munkafolyamatot, amely akkor kezdődik, amikor az alkalmazottak módosítják a rekordjaikat.

Az Emberi erőforrások munkafolyamat-lehetőségei számos munkafolyamatot biztosítanak az emberierőforrás-tevékenységek kezeléséhez. Ezenkívül számos opció áll rendelkezésre, hogy bizonyos munkafolyamatokat módosíthasson, és társíthassa azokat egy jelentéshierarchiához. A munkafolyamatok segítségével kezelni lehet az alkalmazotti adatok különféle típusainak módosításait. A munkafolyamatok beosztásokkal társíthatók. Ha az alkalmazottak ezután megváltoztatják az alkalmazotti rekordjukat, akkor elindul egy munkafolyamat, amely jóváhagyást igényel az új információk mentése előtt. A munkafolyamatok előre definiált adatokkal segítik a változások hatékony kezelését és az alkalmazottak adatainak pontosságát:

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

Alkalmazottak felvétele, áthelyezése vagy elbocsátása esetén a munkafolyamat felülvizsgálati folyamatot is tartalmazhat. Ily módon a dokumentumot módosítani lehet, vagy a művelet feltételeit meg lehet határozni a munkafolyamat részeként. Az ellenőrzési folyamat befejezése után a dokumentum vagy a művelet befejeződik, és a munkafolyamat egy végső jóváhagyási lépéshez kerül.

## <a name="associate-a-workflow-with-a-position-hierarchy"></a>Munkafolyamatok társítása beosztáshierarchiával
A munkafolyamatot egy tetszőleges, Ön által konfigurált hierarchiához társíthatja. Ha például egy pozíció egy mátrixjelentési hierarchiához társul, akkor konfigurálhat egy olyan munkafolyamatot, amely egy adott projekt költségeit a projektvezetőhöz irányítja az adott pozícióhoz társított munkavállaló vezetője helyett. Új munkafolyamat létrehozásához vagy meglévő munkafolyamat módosításához válassza az **Új lehetőséget az Emberi erőforrások munkafolyamat** **lapon**. Válasszon ki egy munkafolyamatot a listából a Munkafolyamat-tervező megnyitásához. A tervező segítségével új munkafolyamatot hozhat létre, illetve módosíthatja egy meglévő munkafolyamat lépéseit. Amikor módosít egy meglévő munkafolyamatot, a módosításai új verzióként kerülnek mentésre. Így szükség esetén bármikor visszatérhet egy korábbi verzióhoz.

## <a name="configure-a-human-resources-workflow"></a>Emberi erőforrások munkafolyamatának konfigurálása
Ha konfigurálni szeretne egy alapvető munkafolyamatot, amelyik akkor indul el, amikor az alkalmazottak személyes azonosítójuk módosításait kérik, kövesse az alábbi lépéseket.

1.  Az Emberi erőforrások **munkafolyamatok lapon** válassza az Új **lehetőséget**.
2.  Válassza ki a rendelkezésre álló munkafolyamatok listájánál az **Azonosítószámok** lehetőséget.
3.  A **Munkafolyamat-tervező** megnyitásához válassza a Futtatás lehetőséget, majd a kérdés kérdésére írja be a felhasználónevet és a jelszót.
4.  Húzza az **Azonosítószám jóváhagyása** elemet a munkafolyamat-elemek listájáról a tervezői vászonra.
5.  Csatlakoztassa a jóváhagyási elemet a **Kezdés** és **Befejezés** pontokhoz.
6.  Kattintson duplán az elem jóváhagyására, **válassza** ki és tartsa lenyomva (vagy kattintson a jobb gombbal), majd válassza a Tulajdonságok **lehetőséget**.
7.  Kövesse az alábbi lépéseket a munkatétel hozzáadásához:

    1.  Válassza ki a **Hozzárendelés** elemet, majd a **Hierarchia** lehetőséget a hozzárendelés típusánál.
    2.  A **Hierarchia** kijelölés alatt válassza ki a **Konfigurálható hierarchia** lehetőséget.
    3.  Adja hozzá a leállási feltételt, majd zárja be az oldalt.

8.  Töltse ki a további utasításokat (ne maradjanak további figyelmeztetések).
9.  Válassza a **Mentés és bezárás** lehetőséget. Aktiválja az új munkafolyamatot, amikor megnyílik a párbeszédpanel, és válassza ki a **Legyen aktív** lehetőséget.
10. Lépjen az **Emberi erőforrások** &gt; **Beosztások** &gt; **Beosztáshierarchia-típusok** ponthoz.
11. Válassza ki a **Mátrix** lehetőséget.
12. Adja hozzá a **Dolgozó azonosítószáma** munkafolyamatot a listához.

## <a name="additional-resources"></a>További erőforrások

[A cím változásainak megtekintése és kezelése](hr-personnel-view-address-changes.md) 





[!INCLUDE[footer-include](../includes/footer-banner.md)]
