---
title: Lízingjóváhagyási munkafolyamatok beállítása
description: A témakör bemutatja, hogyan állíthat be egy jóváhagyási munkafolyamatot, amely új lízing létrehozásakor fog futni.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: d2135458873963dc7c930b4bcef0c508c7d9635f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992839"
---
# <a name="set-up-lease-approval-workflows"></a>Lízingjóváhagyási munkafolyamatok beállítása

[!include [banner](../includes/banner.md)]

A témakör bemutatja, hogyan állíthat be egy jóváhagyási munkafolyamatot, amely új lízing létrehozásakor fog futni. A munkafolyamat használatáról a [Lízingjóváhagyási munkafolyamatok használata](use-create-lease-wrkflw.md) című témakörben talál további információt. 

1. Nyissa meg az **Eszközlízing \> Beállítás \> Lízingmunkafolyamat** lehetőséget.
2. A **Lízingmunkafolyamat** oldalon válassza az **Új** lehetőséget.
3. A megjelenő párbeszédpanelben a **Munkafolyamat-típus** csoportjában válassza a **Lízingmunkafolyamat** hivatkozást.

    Az alkalmazás megnyílik. Futtatása után jelentkezzen be az Azure Active Directory (Azure AD) alkalmazásba, hogy átirányítsa a munkafolyamat-alkalmazásba.

4. Húzza a **Lízingmunkafolyamat-jóváhagyási** elemét a munkafolyamatra.
5. Csatlakoztasson egy csomópontot a **Start** – **Lízingmunkafolyamat-jóváhagyáshoz**. Ezután csatlakoztassa a **Lízingmunkafolyamat-jóváhagyás** – **Befejezéshez**.
6. Kattintson duplán a **Lízingmunkafolyamat-jóváhagyásra**.
7. Válassza a **Tulajdonságok** lehetőséget, majd az **Alapbeállítások** elemben adja meg a munkafolyamat nevét.

    Ezen a lapon további paramétereket is beállíthat a munkafolyamathoz. Ha bekapcsolta az **Automatikus műveletek** lehetőséget, a rendszer automatikusan végrehajt egy adott műveletet. Az értesítések akkor küldhetők el, ha meg vannak adva az **Értesítések** lapon. A **Speciális beállítások** fülön megadhatja a végső jóváhagyót, beállíthat egy időkorlátot, és kijelölhet konkrét műveleteket, amelyeket végre kell hajtani.

8. Ha befejezte a munkafolyamat-paraméterek beállítását, válassza a **Bezárás** gombot.
9. Válassza ki az **1. lépés** lehetőséget, majd a **Tulajdonságok** elemet.
10. Az **Alapszintű beállítások** lehetőségben adja meg a lépés nevét, hozzon létre egy jóváhagyási tárgysort, és adja meg a jóváhagyásra vonatkozó utasításokat.
11. A **Hozzárendelés** lapon válassza ki a hozzárendelés típusát.
12. Ha adott felhasználókat szeretne hozzárendelni a jóváhagyáshoz, válassza a **Felhasználó** lehetőséget, jelölje ki a lízingeket jóváhagyó felhasználókat, majd válassza a **Bezárás** lehetőséget.
13. A munkafolyamat létrehozásához válassza a **Mentés és a bezárás** lehetőséget. Ezután a rendszer kérésére válassza az **OK** gombot.
14. A **Munkafolyamat létrehozása** oldalon válassza a **Bezárás** lehetőséget.
14. Jelölje ki az új munkafolyamatot, majd válassza a **Verziók** lehetőséget. Ezután válassza az **Aktívvá tétel** lehetőséget, hogy a munkafolyamat aktív legyen.
15. Válassza **Bezárás** lehetőséget. Megjelenik az új aktív verzió.
