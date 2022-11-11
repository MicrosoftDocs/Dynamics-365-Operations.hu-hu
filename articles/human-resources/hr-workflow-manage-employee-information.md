---
title: Alkalmazotti adatok kezelése munkafolyamatok segítségével
description: Ez a cikk bemutatja, hogy hogyan használhatók a munkafolyamatok az alkalmazotti adatok kezelésére.
author: twheeloc
ms.date: 11/03/2022
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
ms.openlocfilehash: dbbbb0ee807cb65fa4f4f9a29cc4a2b6b045b08c
ms.sourcegitcommit: 2b654e60e2553a5835ab5790db4ccfa58828fae7
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/08/2022
ms.locfileid: "9750734"
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

A munkafolyamatokat bármilyen beállított beosztáshierarchiához társíthatja. A munkafolyamat-útválasztásban két hierarchiatípus használható: **a vezetői és** a **konfigurálható**.

- A **vezetői** hierarchia a vállalat vagy szervezet jelentési struktúráját jelöli. A hierarchiatípussal kapcsolatos további tudnivalókat lásd a Jelentés-to-to [pozícióban](hr-personnel-positions.md#reports-to-position).
- A **konfigurálható** hierarchia mátrixot vagy egyéni hierarchiát képvisel. A hierarchiatípussal kapcsolatos további tudnivalókat lásd: [Kapcsolatok](hr-personnel-positions.md#relationships).

### <a name="managerial-hierarchy-example"></a>Vezetői hierarchia – példa

A munkafolyamatot beállíthatja úgy, hogy amikor egy alkalmazott beszerzési kérelmet nyújt be egy új számítógéphez, a rendszer elküldi a kérést az alkalmazott felettesének, és kihagyja a szintkezelőt. A munkafolyamat-lépés konfigurálása során állítsa a **Hozzárendelés típus mezőjét** **Hierarchiára**. Ezt követően **elérhetővé válik** a Hierarchiatípus lap. Ebben a példában válassza a Vezetői **hierarchia** lehetőséget.

### <a name="configurable-hierarchy-example"></a>Példa a konfigurálható hierarchia hierarchiára

Ha egy beosztás mátrix típusú jelentési hierarchiához van társítva, konfigurálhat olyan munkafolyamatot, amely az alkalmazott kezelője helyett egy adott projekt költségeit a projekt-érdeklődőhöz társítja. Ebben az esetben állítsa a **Hozzárendelés típus mezőjét** **Hierarchiára**. Ezután a Hierarchiatípus **lapon** válassza ki **a Konfigurálható** hierarchiát. A munkafolyamat beállítása **után** jelölje be a Hierarchia társítása lehetőséget **a** Munkafolyamat beállítása lapon, és válassza ki a munkafolyamat-útvonalhoz használni kívánt hierarchiát.

> [!IMPORTANT]
> Amikor egy dokumentumot, tranzakciót vagy alaprekordot küld el jóváhagyásra, a rendszer a beküldő elsődleges pozícióját használja annak meghatározására, hogy kihez kell a dokumentumot legközelebb átkésni.

### <a name="hierarchy-setting-in-workflow-parameters"></a>Hierarchia beállítása a Munkafolyamat paraméterei között

1. A Munkafolyamat **paraméterei lapon** kattintson a Hierarchia **útvonalára**.
2. Alapértelmezés szerint a Beosztáshierarchia **használata** beállítás Nem beállításra **van beállítva**. Ebben az esetben a munkafolyamat a dolgozó elsődleges beosztását használja a hierarchiába való navigáláskor. Igen beállítás esetén **a** munkafolyamat a beosztás szülőját használja a hierarchia navigálása során.

### <a name="additional-example"></a>További példa 

Grace Semberman alkalmazottnak két beosztása van: konzulens és tanácsadó. Graces elsődleges beosztása az alappozíció. Amikor nem az új alkalmazottakat edz, akkor tanácsadói munkára van szüksége. Az elsődleges beosztásán keresztül Grace az emberi erőforrások igazgatójának készít jelentést. Az akkretajelentések a Tol. A tanácsadói beosztása szerint Grace-nek több pontozott kapcsolata van a projekttől függően.

Grace vállalata olyan munkafolyamat-útvonal szabályokat hoz létre, amelyek konfigurálható **hierarchián** (mátrix-/projekt alapú hierarchiákon) alapulnak. Ez a hierarchia Grace tanácsadói pozícióját használja. **Ha a Beosztáshierarchia** **használata** beállítás Nem beállításra van állítva, és egy dokumentum grace-hez kerül jóváhagyásra, a munkafolyamat meg fogja keresni az elsődleges pozícióját (alappozícióját), és meghatározza, hogy hova kell legközelebb a dokumentumot továbbkösni. Ebben az esetben az 100000000000000000000,<a1/–<a4/––<a4 Ha a **beállítás Igen**, és a munkafolyamat Konfigurálható hierarchiát használ, a **munkafolyamat** meg fogja keresni Grace tanácsadói pozícióját és a jelentési viszonyt, és meghatározza, hogy hova kell legközelebb a dokumentumot irányítanának.

### <a name="configure-a-human-resources-workflow"></a>Emberi erőforrások munkafolyamatának konfigurálása
Ha konfigurálni szeretne egy alapvető munkafolyamatot, amelyik akkor indul el, amikor az alkalmazottak személyes azonosítójuk módosításait kérik, kövesse az alábbi lépéseket.

1.  Az Emberi erőforrások **munkafolyamatok lapon** válassza az Új **lehetőséget**.
2.  Válassza ki a rendelkezésre álló munkafolyamatok listájánál az **Azonosítószámok** lehetőséget.
3.  A Munkafolyamat-tervező **megnyitásához** válassza a Futtatás lehetőséget, majd adja meg felhasználónevét és jelszavát.
4.  Az Azonosítószám **jóváhagyása elem áthelyezése** a munkafolyamat-elemek listájából a tervezői vásznat.
5.  Csatlakoztassa a jóváhagyási elemet a **Kezdés** és **Befejezés** pontokhoz.
6.  Kattintson duplán az elem jóváhagyására, **válassza** ki és tartsa lenyomva (vagy kattintson a jobb gombbal), majd válassza a Tulajdonságok **lehetőséget**.
7.  Kövesse az alábbi lépéseket a munkatétel hozzáadásához:

    1.  Válassza ki a **Hozzárendelés** elemet, majd a **Hierarchia** lehetőséget a hozzárendelés típusánál.
    2.  A **Hierarchia** kijelölés alatt válassza ki a **Konfigurálható hierarchia** lehetőséget.
    3.  Adja hozzá a leállási feltételt, majd zárja be az oldalt.

8.  Töltse ki az esetleges további utasításokat.
9.  Válassza a **Mentés és bezárás** lehetőséget. Aktiválja az új munkafolyamatot, amikor megnyílik a párbeszédpanel, és válassza ki a **Legyen aktív** lehetőséget.
10. Lépjen az **Emberi erőforrások** &gt; **Beosztások** &gt; **Beosztáshierarchia-típusok** ponthoz.
11. Válassza ki a **Mátrix** lehetőséget.
12. Adja hozzá a **Dolgozó azonosítószáma** munkafolyamatot a listához.

## <a name="additional-resources"></a>További erőforrások

[A cím változásainak megtekintése és kezelése](hr-personnel-view-address-changes.md) 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
