---
title: Karbantartási ellenőrzőlisták
description: Ez a témakör bemutatja a karbantartási ellenőrzőlistákat az Eszközkezelés modulban.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 325ff1fa0811d6aac5189cc69f21483fce6b3e8f
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875699"
---
# <a name="maintenance-checklists"></a>Karbantartási ellenőrző listák


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

A karbantartási ellenőrzőlisták a karbantartási feladattípusokon állíthatók be, amikor megy munkarendelésen dolgozik A karbantartási ellenőrzőlisták kitöltése egy munkarendelés elvégzésének része. Lásd a [Karbantartási feladattípus-kategóriák és a karbantartási feladattípusok, a karbantartási feladattípus változatok és karbantartási ellenőrzőlisták](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md) szakaszt a karbantartási beállításával a karbantartási feladattípusokhoz folyamatával kapcsolatban. a **Karbantartási feladattípusok alapértelmezései** képernyőn.

Amikor egy munkarendelésen dolgozik a karbantartási ellenőrző, kitöltheti a karbantartási feladattípusokhoz kapcsolódó előre definiált karbantartási ellenőrzőlistákat. További karbantartási ellenőrzőlisták hozzáadására is lehetősége van.

## <a name="fill-out-a-maintenance-checklist"></a>Karbantartási ellenőrzőlista kitöltése

1. Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.

2. Válassza ki a munkarendelést, majd kattintson a **Karbantartási ellenőrzőlisták** elemre.

3. A **Munkarendelés karbantartásifeladat-ellenőrzőlista**alatt láthatja munkarendelés feladattokkal kapcsolatos karbantartási ellenőrzőlistákat. Ha a munkarendelés-feladatok különböző karbantartási feladattípusokkal rendelkeznek, akkor az egyes munkarendelések feladatai esetében a karbantartási ellenőrzőlisták különbözőek lehetnek. Válassza ki a munkarendelési feladatot. amely a kapcsolódó karbantartási ellenőrzőlistával működik. A kiválasztott karbantartási ellenőrzőlistasor részletei a **Sor részletei** gyorslapon láthatók.

4. Hajtsa végre az összes karbantartási ellenőrzőlista-sort, egyesével a látható sorrendben. A „Fejléc” típusú karbantartásiellenőrzőlista-sor az alatta megjelenő karbantartásiellenőrzőlista-sorok csoportosításához használatos. Nem kötelező kitöltenie egy fejlécet, de az összes karbantartási ellenőrzőlista-sor típushoz hasonlóan **Megjegyzést** is hozzáadhat a fejléchez.

5. Ha a karbantartási ellenőrzőlista sorához kapcsolódnak utasítások, akkor a **Utasítások** jelölőnégyzet be van jelölve. A kiválasztott karbantartási ellenőrzőlista sorához tartozó utasításokat olvassa el a **Sor részletei** gyorslap > **Utasítások** szakaszában.

6. A karbantartási ellenőrzőlista-sor befejezéséhez szükséges adatok a kapcsolódó karbantartási ellenőrzőlistatípustól függően változhatnak. A karbantartási ellenőrzőlista sor kitöltését a **Sor részletei** gyorslap mezőinek kitöltésével végezheti el. Ha például egy „Szöveg” típusú sornál egy **Megjegyzést** ad meg, elmagyarázhatja, hogy mi volt az ellenőrzőlista-sor eredménye. A „Mérés" típusú sorokban megadhatja a berendezésen leolvasott **Számláló értékét**, és szükség esetén **Megjegyzést** is hozzáadhat.

- Ha befejezte a karbantartási ellenőrzőlista sorát, jelölje be az **Ellenőrizve** jelölőnégyzetet a sor befejezettként való megjelöléséhez. Ha szeretné elvetni a karbantartási ellenőrzőlista sorát, mert az nem releváns a munkarendeléshez, jelölje be az **N/A** jelölőnégyzetet a sorban. Ha egy karbantartási ellenőrzőlista-sor **Kötelező**, akkor vagy az „Ellenőrizve” vagy az „N/A” értékkel meg kell jelölni.  
- Csak akkor frissítheti a karbantartási ellenőrzőlista-regisztrációkat, ha a munkarendelés [Aktív](../setup-for-work-orders/work-order-lifecycle-states.md) életciklus-állapotban van.  


## <a name="add-a-maintenance-checklist-line"></a>Karbantartási ellenőrzőlista sor hozzáadása

A karbantartási ellenőrzőlisták a karbantartási feladattípus alapértelmezése definíciója alapján hozza létre a program, és átviszi a munkarendelés feladatára. Ha szükséges, a karbantartási ellenőrzőlista sorait felveheti egy munkarendelés feladatához. A manuálisan hozzáadott karbantartási ellenőrzőlista sorok a „Manuális” hivatkozást kapják.

1. A **Munkarendelés karbantartásifeladat-ellenőrzőlista**alatt válassza ki a munkarendelés-feladatot, amelyet hozzá szeretne adni a karbantartási ellenőrzőlistához.

2. A **Karbantartás ellenőrzőlista sorok** gyorslapon válasszon ki egy karbantartási ellenőrzőlista sort, majd nyomja le a billentyűzet le nyílgombját, ha új sort szeretne beszúrni a kiválasztott karbantartási ellenőrzőlistasor után. A sorozatban következő számautomatikusan be lesz szúrva a **Sor száma** mezőbe. A karbantartási ellenőrzőlista sort is kiválaszthatja, majd a **Sor hozzáadása** gombra kattintva új sort illeszthet be a kiválasztott karbantartási ellenőrzőlista-sor fölé, ha szeretné.

3. A **Név** mezőben adja meg az új karbantartásiellenőrzőlista-sor nevét.

4. A **Típus** mezőben válasszon egy típust karbantartásiellenőrzőlista-sorhoz. Minden karbantartásiellenőrzőlista-típushoz a **Sor részletei** gyorslapon jelennek meg a kapcsolódó mezők.  
  a. A „Szöveg" mezővel adhat hozzá karbantartásiellenőrzőlista sort a feladatot tartalma szöveges leírással. Ez a karbantartásiellenőrzőlista-típust akkor használható, ha azt szeretné, hogy a dolgozó ellenőrizzen vagy megvizsgáljon valamit, de nem vár konkrét (mérhető) eredményt. Adja meg a feladat leírását a **Sor részletei** gyorslap **Utasítások** szakaszában. b. A „Fejléc” fejlécként használatos a fejléc alatt megjelenő karbantartásiellenőrzőlista-sorok csoportosításához. Ez a akkor hasznos, ha több karbantartásiellenőrzőlista-sor van, amelyek meghatározott területekre oszthatók fel. Írjon be egy jól felismerhető nevet a **Név** mezőbe.  
  c. A „Sablon” nem alkalmazható, ha manuálisan ad hozzá egy munkarendelés-feladathoz egy karbantartási ellenőrzőlista sort.  
  nap A „Változó” egy karbantartási ellenőrzőlista-sor lehetséges eredményének tartományát határozza meg. A karbantartási ellenőrzőlisták változóinak beállításáról a következő helyen olvashat bővebben: [Karbantartásifeladat-típusok kategóriái és karbantartásifeladat-típusok, karbantartásifeladat-típusok változatai, karbantartási szakmák és karbantartási ellenőrző listák](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md). Adjon meg egy a változót leíró nevet a **Név** mezőbe. Jelölje ki a változót a **Változó** mezőben. Adja meg a feladat leírását a **Sor részletei** gyorslap **Utasítások** szakaszában.  
  e. A„Mérés” egy adott mérés rögzítésére szolgál. Adjon meg egy nevet a mérésnek a **Név** mezőben. A **Sor részletei** gyorslapon válassza a **Számláló** és az **Egység** elemeket. Írja be a feladat leírását az **Utasítások** szakaszban.  

5. Amikor befejezte a karbantartási ellenőrzőlista sorainak manuális hozzáadását, töltse ki a sorokat a fenti részben leírt módon.

>[!NOTE]
>A **Munkarendelés karbantartási feladatának ellenőrzőlistája** alatt a „Feladattípus” hivatkozással rendelkező karbantartási ellenőrzőlista sorokat nem törölheti. Csak a „Manuális” hivatkozással rendelkező karbantartási ellenőrzőlista sorokat lehet törölni, amelyekhez Ön vagy más karbantartó dolgozók készítettek manuálisan.


![1. ábra](media/14-work-orders.png)

