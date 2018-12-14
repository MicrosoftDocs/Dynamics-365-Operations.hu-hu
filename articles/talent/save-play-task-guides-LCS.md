---
title: "Feladat-útmutatók mentése az LCS szolgáltatásba, és ismételt lejátszásuk"
description: "Ez a témakör bemutatja, hogyan lehet menteni feladat-útmutatót a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásba, majd ezután újra lejátszani őket."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 40b4c3154a04a557b8a670e1f1ae3722c71122fe
ms.contentlocale: hu-hu
ms.lasthandoff: 12/04/2018

---

# <a name="save-task-guides-to-lcs-and-replay-them"></a>Feladat-útmutatók mentése az LCS szolgáltatásba, és ismételt lejátszásuk

[!include [banner](includes/banner.md)]

**Környezet részletes adatai** 

Microsoft Dynamics 365 for Talent, amelyet a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatáson keresztül telepítettek

**Probléma**

A vevő új feladatrögzítéseket szeretne elmenteni az LCS-projektjéhez, majd újra lejátszani az elmentett feladat-útmutatókat.

**Felbontás**

Kövesse ezeket a lépéseket egy feladatrögzítés LCS-be való elmentéséhez.

1. Jelentkezzen be az LCS-be, és válassza ki a projektet.
2. Válassza ki az **Üzletifolyamat-modellező** csempét.
3. Tekintse meg az oldalt a „Megújult BPM-környezetben”.
4. Válasszon ki egy könyvtárat, majd válassza a **Másolás** elemet.
5. Adja meg az üzletifolyamat-modellező (BPM) modell nevét.
6. Jelentkezzen be a Talent alkalmazásba az LCS-ből.
7. A **Keresés** mezőbe írja be a **segítség** szót. A Lifecycle Services Súgója megnyílik.
8. Válassza ki a **Frissítés** gombot Lifecycle Services Súgó konfigurációjához.

    Az új BPM-könyvtárnak meg kell jelennie, és aktívnak kell lennie.

9. Zárja be a lapot.
10. Hozzon létre egy feladatrögzítést.
11. Amikor elkészült, válassza ki **Mentés a Lifecycle Services szolgáltatásba** lehetőséget.

    ![Mentés a Lifecycle Services szolgáltatásba](media/task-guides.png)

12. Válassza ki a BPM-könyvtárat és csomópontot, ahova a feladatrögzítést szeretné menteni.

Kövesse az alábbi lépéseket a feladat-útmutató LCS-ből való visszajátszásához.

1. Indítsa el a Feladatrögzítőt.
2. Válassza a **Megnyitás LCS-ből** lehetőséget.
3. Válassza ki a könyvtárat és a BPM-csomópontot, amelyek a mentett feladat-útmutatót tartalmazzák.
4. Nyissa meg a feladat-útmutatót.

