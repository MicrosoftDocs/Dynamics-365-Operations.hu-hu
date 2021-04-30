---
title: Beragadt kötegelt feladatok alaphelyzetbe állítása
description: Ez a témakör bemutatja, hogyan oldhatja meg a beragadt kötegelt feladatokkal kapcsolatos problémákat.
author: andreabichsel
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: 906a391b3c28d15445f6ddf0fc547ebcf842ba19
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881760"
---
# <a name="reset-stuck-batch-jobs"></a>Beragadt kötegelt feladatok alaphelyzetbe állítása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="issue"></a>Kiadás

A Microsoft Dynamics 365 Human Resources esetében olyan kötegelt feladatokkal kapcsolatos problémákat tapasztalhat, amelyek **Végrehajtás** vagy **Megszakítás** állapotban vannak, és nem fejeződnek be.

## <a name="resolution"></a>Felbontás

Ha egy kötegelt feldolgozás **Végrehajtás** vagy **Megszakítás** állapotban van, a feladat törlésének kényszerítésével alaphelyzetbe állíthatja az állapotot. A megszakítás után visszaállíthatja a kötegelt feldolgozást **Várakozás** állapotra. Ezután a következő ütemezett kötegfuttatásban újra fel lehet venni a végrehajtáshoz.

1. A **Rendszerfelügyelet** munkaterületen jelölje ki a **Hivatkozások** lapot, és válassza a **Kötegelt feladatok** lehetőséget.

2. A **Kötegelt feladat** listaoldalon jelölje ki az alaphelyzetbe állításhoz szükséges feladatokat.

3. A művelet menüszalagján válassza a **Megszakítás kényszerítése** lehetőséget, és erősítse meg a műveletet.

   > [!NOTE]
   > A **Megszakítás kényszeítése** művelet csak akkor érhető el, ha a kijelölt kötegelt feldolgozás **Végrehajtás** vagy **Megszakítás** állapotú, és a feladathoz nem fut kötegelt végrehajtási vagy törlési folyamat.

4. A művelet menüszalagján válassza az **Állapot módosítása** lehetőséget.

5. Az **Új állapot kiválasztása** lapon válassza a **Várakozás** lehetőséget, majd kattintson az **OK** gombra.

   ![Új kötegelt feldolgozási állapot kiválasztása](./media/hr-admin-reset-batch-job-status.png)

## <a name="see-also"></a>Lásd még

[Teljesítmény optimalizálása a kötegelt feladatok munkaidő utáni ütemezésével](hr-admin-troubleshooting-batch-jobs.md)<br>
[Teljesítmény optimalizálása automatikus tisztítási feladatokkal](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
