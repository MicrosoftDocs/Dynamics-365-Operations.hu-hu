---
title: Alaptervezési feladat visszavonása
description: Ez a témakör azt mutatja be, hogyan lehet érvényteleníteni egy olyan aktív tervezési feladatot, amely a beépített tervezési funkciót használja.
author: ChristianRytt
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
ms.author: crytt
ms.search.validFrom: 2019-12-16
ms.dyn365.ops.version: ''
ms.openlocfilehash: 27a48473a934e0db9986d6e588fc769ba9d2f605d72b2465976cb20a1ad93d16
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718011"
---
# <a name="cancel-a-master-planning-job"></a>Alaptervezési feladat visszavonása

[!include [banner](../includes/banner.md)]

A Microsoft Dynamics 365 Supply Chain Management alkalmazásban több lehetőség van az alaptervezés feladat visszavonására. Előfordulhat például, hogy vissza szeretne vonni egy alaptervezési feladatot, ha azt tévedésből indította el, vagy a vártnál tovább tart, és meg szeretné szakítani. A tervezési feladatok megszakításához a legjobb módszer a **Befejezetlen tervezési folyamatok** lap. A **Kötegelt feladatok** és a **Kötegelt feladatok – speciális** lapok alternatív lehetőségei csak akkor használhatók, ha az alaptervezési feladat a **Befejezetlen tervezési folyamatok** lapról néhány percen belül nem fejeződött be.

## <a name="preferred-cancel-option"></a>Előnyben részesített visszavonási beállítás
### <a name="cancel-master-planning-job-from-unfinished-planning-processes-page"></a>Alaptervezési feladat visszavonása a **Befejezetlen tervezési folyamatok** lapról
1. Lépjen az **Alaptervezés > Lekérdezések és jelentések > Alaptervezés > Befejezetlen tervezési folyamatok** elemre.
2. Válassza ki a visszavonni kívánt tervezési folyamathoz tartozó sort.
3. Kattintson a **Mégse** gombra.

## <a name="additional-cancel-options"></a>További visszavonási lehetőségek
Ezek csak akkor használhatók, ha az alaptervezési feladat megszakítása a **Befejezetlen tervezési folyamatok** lapról nem fejeződött be pár percen belül.

### <a name="delete-master-planning-job-from-the-batch-jobs-page"></a>Az alaptervezési feladat törlése a **Kötegelt feladatok** oldalról
1. Ugorjon a **Rendszerfelügyelet > Lekérdezések > Kötegelt feladatok** pontra.
2. Válassza ki a törölni kívánt tervezési feladathoz tartozó sort.
3. Kattintson a **Törlés** gombra.

### <a name="abort-master-planning-job-task-from-the-batch-jobs-enhanced-page"></a>Az alaptervezési feladat megszakítása a **Kötegelt feladatok – speciális** oldalról
1. Ugorjon a **Rendszerfelügyelet > Lekérdezések > Kötegelt feladatok** pontra.
2. Ha a feladatazonosító nem jelenik meg a listában, kattintson a **Váltás a speciális nézetre** lehetőségre, különben folytassa a következő lépéssel.
3. Nyissa meg a kötegelt feladatot. Kattintson a befejezendő feladatokkal rendelkező kötegelt feladat **Feladatazonosító** elemére.
4. A **Kötegelt feladatok** területen válassza ki a befejezendő feladatokat.
5. Kattintson az **Állapot módosítása**, majd a **Visszavonás** elemre, majd az **OK** gombra.
6. A **Kötegelt feladatok** gyorslapon kattintson a **Megszakítás** parancsra.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]