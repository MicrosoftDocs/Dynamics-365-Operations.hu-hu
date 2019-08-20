---
title: Eszközdokumentumok
description: Ez a témakör bemutatja az Eszközkezelés eszközdokumentumait.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d1c90788da7ad536fb9978db18160ccf6c158033
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783309"
---
# <a name="asset-documents"></a>Eszközdokumentumok

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Ez a témakör bemutatja az Eszközkezelés eszközdokumentumait.

Az Eszközkezelés modulban beállíthat dokumentumokat, amelyek automatikusan kapcsolódnak a feladattípusokhoz, eszközgyártókhoz, eszköztípusokhoz vagy például eszközökhöz. Ez a funkció akkor hasznos, ha a frissített dokumentumverziókat adnak ki. Ebben az esetben a frissített dokumentumot csak el kell helyezni a Microsoft Dynamics 365 for Finance and Operations-dokumentumokhoz használt megszokott helyen, és csatolni a dokumentumot a létrehozott eszközdokumentum-rekordhoz. A frissített dokumentum elérhető az **Összes eszköz**, **Aktív eszközök**, **Saját aktív eszközök**, **Összes munkarendelés** és **Aktív munkarendelési feladatok** menüelemekből. A dokumentumok eszközdokumentum-rekordokhoz történő csatolásának folyamata a szokásos dokumentumkezelő rendszert használja a Finance and Operations modulban.

**1. példa** : Egy feladattípushoz kapcsolódó dokumentum leírhatja a feladattípushoz tartozó eljárást.

**2. példa** : Egy dokumentum, amely egy eszköztípus, gyártó és modell kombinációjához tartozik, lehet a kiválasztott eszközgyártói modell szabványos kézikönyve.

## <a name="create-asset-document-relation"></a>Eszköz-dokumentum közti kapcsolat létrehozása

1. Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Eszközdokumentumok** elemet.
2. Válassza az **Új** lehetőséget az eszközdokumentum-rekord létrehozásához.
3. A dokumentumkapcsolat specifikusságának szükséges szintjétől függően végezze el a releváns kiválasztásokat egy vagy több mezőn a következő közül: **Eszköztípus**, **Gyártó**, **Modell**, **Eszköz**, **Feladattípus-kategória**, **Feladattípus**, **Feladattípus változata** és **Feladat követelménye**. A **Feladattípus-változat** és a **Feladat követelménye** mezőkben elérhető lehetőségek a **Feladattípus** mezőben kiválasztott beállítástól függenek.

    > [!NOTE]
    > Amikor a rendszer olyan dokumentumokat keres, amelyek egy eszközhöz vagy egy munkarendeléshez kapcsolódnak, az Eszközkezelés minden eszközdokumentum-rekordon végigmegy lehetséges egyezést keresve. Mindig a leginkább meghatározott kombinációt ellenőrzi először. Más szóval az Eszközkezelés modul először a **Feladat követelménye** mezővel való egyezést ellenőrzi. Ha nem talál egyezést, akkor a **Feladattípus változata** mezővel való egyezést ellenőrzi. Ha nem talál egyezést, akkor a **Feladattípus** mezővel való egyezést ellenőrzi, és így tovább. Ahogy az az **Eszközdokumentumok** oldal elrendezésében is látható, ez a viselkedésmód azt jelenti, hogy a legspecifikusabb kombináció megkereséséhez az Eszközkezelés minden egyes rekordot jobbról balra ellenőriz egyezést keresve. Egy eszközhöz vagy egy munkarendeléshez több dokumentum is kapcsolódhat. A karbantartási kérés vagy a munkarendelés szolgáltatási szintjét igény szerint módosíthatja.

4. **Mellékletek** kiválasztása. A Finance and Operations modulban megjelenik a megszokott **Dokumentumkezelés** oldal.
5. Állítsa be az eszközdokumentum-rekordhoz csatolandó dokumentumokat vagy jegyzeteket. Dokumentumok csatolása után a **Mellékletek** mező a rekordhoz kapcsolódó dokumentumok számát jeleníti meg.
