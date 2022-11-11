---
title: Az elavult alaptervezési motor használatával létrehozott feladat megszakítása
description: Ez a témakör ismerteti, hogyan lehet visszavonni egy olyan aktív tervezési feladatot, amely az elavult alaptervezési motort használja.
author: t-benebo
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace, ReqProcessList
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-12-16
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7b71a43f407050dccb7550db7c4b6a98a596d589
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740877"
---
# <a name="cancel-a-job-that-was-created-using-the-deprecated-master-planning-engine"></a>Az elavult alaptervezési motor használatával létrehozott feladat megszakítása

[!include [banner](../includes/banner.md)]

Az elavult alaptervezési motor segítségével létrehozott feladat megszakítása többféle lehetőséggel is lehetséges. Előfordulhat például, hogy vissza szeretne vonni egy alaptervezési feladatot, ha azt tévedésből indította el, vagy a vártnál tovább tart, és meg szeretné szakítani.

A tervezési feladatok megszakításához a legjobb módszer a **Befejezetlen tervezési folyamatok** lap. A **Kötegelt feladatok** és a **Kötegelt feladatok – speciális** lapok alternatív lehetőségei csak akkor használhatók, ha az alaptervezési feladat a **Befejezetlen tervezési folyamatok** lapról néhány percen belül nem fejeződött be.

## <a name="preferred-cancel-option"></a>Előnyben részesített visszavonási beállítás

### <a name="cancel-master-planning-job-from-the-unfinished-planning-processes-page"></a>Alaptervezési feladat megszakítása a Befejezetlen tervezési folyamatok lapról

1. Lépjen az **Alaptervezés > Lekérdezések és jelentések > Alaptervezés > Befejezetlen tervezési folyamatok** elemre.
2. Válassza ki a visszavonni kívánt tervezési folyamathoz tartozó sort.
3. Válassza a **Mégse** lehetőséget.

## <a name="additional-cancel-options"></a>További visszavonási lehetőségek

Ezek csak akkor használhatók, ha az alaptervezési feladat megszakítása a **Befejezetlen tervezési folyamatok** lapról nem fejeződött be pár percen belül.

### <a name="delete-master-planning-job-from-the-batch-jobs-page"></a>Az alaptervezési feladat törlése a **Kötegelt feladatok** oldalról

1. Ugorjon a **Rendszerfelügyelet > Lekérdezések > Kötegelt feladatok** pontra.
2. Válassza ki a törölni kívánt tervezési feladathoz tartozó sort.
3. Válassza a **Törlés** lehetőséget.

### <a name="abort-master-planning-job-task-from-the-batch-jobs-enhanced-page"></a>Az alaptervezési feladat megszakítása a **Kötegelt feladatok – speciális** oldalról

1. Ugorjon a **Rendszerfelügyelet > Lekérdezések > Kötegelt feladatok** pontra.
2. Ha a feladatazonosító nem jelenik meg a listában, kattintson a **Váltás a speciális nézetre** lehetőségre, különben folytassa a következő lépéssel.
3. Nyissa meg a kötegelt feladatot. Válassza ki **a kötegelt feladat** feladatazonosítóját, amely a be kívánt feladatokat tartalmazza.
4. A **Kötegelt feladatok** területen válassza ki a befejezendő feladatokat.
5. Válassza az **Állapot módosítása** lehetőséget, és kattintson a **Mégse gombra**, majd kattintson az **OK gombra**.
6. A **Kötegelt feladatok** gyorslapon kattintson a **Megszakítás** parancsra.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]