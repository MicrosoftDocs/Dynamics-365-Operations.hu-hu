---
title: A szabálytalanságkezelésre vonatkozó előfeltételek beállítása
description: Ebben a témakörben megtudhatja, hogyan engedélyezheti a szabálytalanságkezelési folyamatokat.
author: perlynne
manager: AnnBe
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventParameters, InventTestReportSetup, SysUserManagement, SysUserSetup, InventTestDiagnosticType, InventTestMiscCharges, InventTestOperation, InventProblemType, InventProblemTypeSetup, InventQuarantineZone
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 78d38b00d8039612aa236b3aa9593693983407dc
ms.sourcegitcommit: e10491a2ff04f65d9f306ef6e068ee123213b23b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/21/2019
ms.locfileid: "1914722"
---
# <a name="set-up-prerequisites-for-nonconformance-management"></a>A szabálytalanságkezelésre vonatkozó előfeltételek beállítása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ebben a témakörben megtudhatja, hogyan engedélyezheti a szabálytalanságkezelési folyamatokat. A szabálytalanság ismerteti azt az elemet vagy eljárást, amely minőségi problémával rendelkezik, ahol a leíró jellegű információ a forrást és a probléma típusát tartalmazza. Ez az eljárás az USMF bemutatócéget használja. Ezt az eljárást általában a minőségbiztosítási vezető végzi el.


## <a name="enable-quality-management-processes-within-the-company"></a>Engedélyezze a Minőségkezelési folyamatokat a vállalaton belül
1. A Navigációs ablaktáblában válassza a **Modulok > Készletkezelés > Beállítás > Készlet- és raktárkezelési paraméterek** lehetőséget.
2. Válassza ki a **Minőségkezelés** lapot.
3. Válassza ki az **Igen** lehetőséget a **Minőségkezelés használata** mezőben, hogy a vállalat számára engedélyezze a minőségkezelési folyamatokat.
4. Az **Órabér** mezőbe írjon be egy összeget helyi pénznemben. A rendszer az óradíjjal számítja ki a szabálytalansággal kapcsolatos műveletek költségeit. Az óradíj és a számított költségek csak a szabálytalanságokra vonatkoznak, más funkciókat nem érintenek.  
5. Válassza ki a **Jelentés beállítása** lehetőséget a különféle minőségkezelési jelentésekhez használandó minőségjelentési megjegyzéstípusok meghatározásához.

## <a name="enable-user-for-nonconformance-processing"></a>Engedélyezze a szabálytalanságok feldolgozására a felhasználót
1. A navigációs ablaktáblán ugorjon a **Modulok > Rendszerfelügyelet > Felhasználók > Felhasználók** lehetőségre. 
2. A gyorsszűrő használatával keresse meg azt a felhasználót, aki jóváhagyja vagy elutasítja a szabálytalanságrekordokat. Például végezzen szűrést a **Név** mezőben a `Ricardo` érték megadásával. A szabálytalanság jóváhagyásának feldolgozásához azon felhasználónak, aki jóváhagyja vagy elutasítja a szabálytalanságokat a **Felhasználók** lapon hozzárendelt „Név” értékkel kell rendelkeznie. A dokumentummegjegyzések használatához a felhasználónak rendelkeznie kell a Dokumentumkezeléssel, amelyet a felhasználói beállításokban kell aktiválni.  
3. Jelölje meg a kívánt rekord sorát.
4. Válassza a **Felhasználói beállítások** elemet.
5. Válassza ki a **Beállítások** lapot.
6. Válassza az **Igen** lehetőséget a **Dokumentumkezelés engedélyezése** mezőben.

## <a name="define-diagnostic-types-for-nonconformance-processing"></a>Határozza meg a diagnosztikai típusokat a szabálytalanság feldolgozásához
1. A navigációs ablaktáblán lépjen a **Modulok > Készletgazdálkodás > Beállítás > Minőségkezelés > Diagnosztikai típusok** részre. A **Diagnosztikai típusok** oldalon határozhatja meg a diagnosztikai műveletek osztályozását. A javítás meghatározza, hogy milyen típusú diagnosztikai műveletet kell végrehajtani a jóváhagyott szabálytalanságon, valamint hogy kinek kell elvégeznie, melyik napra kérték és mikorra tervezik a végrehajtást.  
2. Válassza az **Új** lehetőséget.
3. Adjon meg egy értéket a **Diagnosztika** mezőben.
4. Írjon egy értéket a **Leírás** mezőbe.

## <a name="define-quality-charges-for-nonconformance-processing"></a>Határozza meg a minőségbiztosítási költségeket a szabálytalanság feldolgozásához
1. A navigációs ablaktáblán lépjen a **Modulok > Készletgazdálkodás > Beállítás > Minőségkezelés > Minőségbiztosítási költségek** részre. A **Minőségbiztosítási költségek** lap használatával osztályozza azokat a költségeket, amelyeket a szabálytalanságokhoz kapcsolódó műveletekben használ.  
2. Válassza az **Új** lehetőséget.
3. Adjon meg egy értéket a **Költségkódok** mezőben.
4. Írjon egy értéket a **Leírás** mezőbe.

## <a name="define-the-operations-for-nonconformance-processing"></a>Határozza meg a műveleteket a szabálytalanság feldolgozásához
1. A navigációs ablaktáblán lépjen a **Modulok > Készletgazdálkodás > Beállítás > Minőségkezelés > Műveletek** részre. A **Műveletek** lap használatával osztályozza a munkát, amelyet a jóváhagyott szabálytalanságokra vonatkozóan végezhet el. Amikor a szabálytalansághoz egy műveletet rendel, információkat adhat meg a kapcsolódó anyagról, a munkaidőről és a vegyes költségekről, amelyek a művelet végrehajtásához szükségesek. Ezek az adatok képezik az alapot a művelet becsült végrehajtási költségének kiszámításához.  
2. Válassza az **Új** lehetőséget.
3. Adjon meg egy értéket a **Művelet** mezőben.
4. Írjon egy értéket a **Leírás** mezőbe.

## <a name="define-problem-types-for-nonconformance-processing"></a>Határozza meg a problématípusát a szabálytalanság feldolgozásához
1. A navigációs ablaktáblán lépjen a **Modulok > Készletgazdálkodás > Beállítás > Minőségkezelés > Problématípusok** részre. A **Problématípusok** oldalon határozhatja meg a különböző szabálytalanságtípusok esetében felmerülő minőségproblémák osztályozását. A szabálytalanság típusai a következők lehetnek: **Belső**, **Vevő**, **Szállító**, **Szolgáltatáskérés**, **Termelés**, és **Társtermék gyártása**. Egy problématípust több Szabálytalanságtípushoz lehet társítani.  
2. Válassza az **Új** lehetőséget.
3. Adjon meg egy értéket a **Problématípus** mezőben.
4. Írjon egy értéket a **Leírás** mezőbe.
5. Válassza ki a **Szabálytalanságtípusok** elemet. A **Szabálytalanságtípusok oldal** használatával engedélyezze a problématípus használatát egy vagy több szabálytalanságtípusra vonatkozóan. Például egy hibás kódot érintő problématípus minden szabálytalanságtípusra alkalmazható, míg egy vevői panasz csak a vevői és szervizigénylési szabálytalanságtípusokra.  
6. Válassza az **Új** lehetőséget.
7. Az új sor **Szabálytalanságtípus** mezőjében válasszon ki egy lehetőséget.

## <a name="define-quarantine-zones-for-nonconformance-processing"></a>Határozza meg a Karanténzónákat a szabálytalanság feldolgozásához
1. A navigációs ablaktáblán lépjen a **Modulok > Készletgazdálkodás > Beállítás > Minőségkezelés > Karanténzónák** részre.
2. Válassza az **Új** lehetőséget.
3. Írjon be egy értéket a **Karanténzónák** mezőbe.
4. Írjon egy értéket a **Leírás** mezőbe.
5. Zárja be a lapot.

