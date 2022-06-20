---
title: Beragadt kötegelt feladatok alaphelyzetbe állítása
description: Ez a cikk bemutatja, hogyan lehet megoldani a beszorult kötegelt feladatokkal kapcsolatos problémákat.
author: twheeloc
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: b56a16257a45dd093d10b7550b13d6a4a1ceb1f7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896018"
---
# <a name="reset-stuck-batch-jobs"></a>Beragadt kötegelt feladatok alaphelyzetbe állítása


[!INCLUDE [PEAP](../includes/peap-2.md)]

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

   ![Új kötegelt feldolgozási állapot kiválasztása.](./media/hr-admin-reset-batch-job-status.png)

## <a name="see-also"></a>Lásd még

[Teljesítmény optimalizálása a kötegelt feladatok munkaidő utáni ütemezésével](hr-admin-troubleshooting-batch-jobs.md)<br>
[Teljesítmény optimalizálása automatikus tisztítási feladatokkal](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
