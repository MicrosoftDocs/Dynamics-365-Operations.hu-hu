---
title: Feladat-útmutatók mentése LCS-re, és újbóli lejátszásuk
description: Ez a témakör bemutatja, hogyan lehet menteni feladat-útmutatót a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásba, majd ezután újra lejátszani őket.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 54251aed1a54f626e5cd6cbd983e3eb4589a02e8
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8068359"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a>Feladat-útmutatók mentése LCS-re, és újbóli lejátszásuk


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Környezet részletes adatai** 

A Microsoft Dynamics 365 Human Resources, amelyet a Microsoft Dynamics Lifecycle Services (LCS) rendszeren keresztül telepítettek

**Kiadás**

A vevő új feladatrögzítéseket szeretne elmenteni az LCS-projekthez, majd újra lejátszani az elmentett feladat-útmutatókat.

**Felbontás**

Kövesse ezeket a lépéseket egy feladatrögzítés LCS-be való elmentéséhez.

1. Jelentkezzen be az LCS-be, és válassza ki a projektet.
2. Válassza ki az **Üzletifolyamat-modellező** csempét.
3. Tekintse meg az oldalt a „Megújult BPM-környezetben”.
4. Válasszon ki egy könyvtárat, majd válassza a **Másolás** elemet.
5. Adja meg az üzletifolyamat-modellező (BPM) modell nevét.
6. Jelentkezzen be a Human Resources rendszerbe az LCS-ből.
7. A **Keresés** mezőbe írja be a **segítség** szót. A Lifecycle Services Súgója megnyílik.
8. Válassza ki a **Frissítés** gombot Lifecycle Services Súgó konfigurációjához.

    Az új BPM-könyvtárnak meg kell jelennie, és aktívnak kell lennie.

9. Zárja be a lapot.
10. Hozzon létre egy feladatrögzítést.
11. Amikor elkészült, válassza ki **Mentés a Lifecycle Services szolgáltatásba** lehetőséget.

    ![Mentés a Lifecycle Services szolgáltatásba.](media/task-guides.png)

12. Válassza ki a BPM-könyvtárat és csomópontot, ahova a feladatrögzítést szeretné menteni.

Kövesse az alábbi lépéseket a feladat-útmutató LCS-ből való visszajátszásához.

1. Indítsa el a Feladatrögzítőt.
2. Válassza a **Megnyitás LCS-ből** lehetőséget.
3. Válassza ki a könyvtárat és a BPM-csomópontot, amelyek a mentett feladat-útmutatót tartalmazzák.
4. Nyissa meg a feladat-útmutatót.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
