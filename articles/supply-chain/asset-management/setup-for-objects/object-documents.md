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
ms.openlocfilehash: 5b830d835d99122a8c0572481f4c229c37d97d0c
ms.sourcegitcommit: 0099fb24f5f40ff442020b488ef4171836c35c48
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/23/2019
ms.locfileid: "2653251"
---
# <a name="asset-documents"></a>Eszközdokumentumok

[!include [banner](../../includes/banner.md)]

 

Ez a témakör bemutatja az Eszközkezelés eszközdokumentumait.

Az Eszközkezelés modulban beállíthat dokumentumokat, amelyek automatikusan kapcsolódnak a feladattípusokhoz, eszközgyártókhoz, eszköztípusokhoz vagy például eszközökhöz. Ez a funkció akkor hasznos, ha a frissített dokumentumverziókat adnak ki. Ebben az esetben a frissített dokumentumot csak el kell helyezni a -dokumentumokhoz használt megszokott helyen, és csatolni a Supply Chain Management dokumentumot a létrehozott eszközdokumentum-rekordhoz. A frissített dokumentum elérhető az **Összes eszköz**, **Aktív eszközök**, **Saját aktív eszközök**, **Összes munkarendelés** és **Aktív munkarendelési feladatok** menüelemekből. A dokumentumok eszközdokumentum-rekordokhoz történő csatolásának folyamata a szokásos dokumentumkezelő rendszert használja.

**1. példa** : Egy feladattípushoz kapcsolódó dokumentum leírhatja a feladattípushoz tartozó eljárást.

**2. példa** : Egy dokumentum, amely egy eszköztípus, gyártó és modell kombinációjához tartozik, lehet a kiválasztott eszközgyártói modell szabványos kézikönyve.

## <a name="create-asset-document-relation"></a>Eszköz-dokumentum közti kapcsolat létrehozása

1. Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Eszközdokumentumok** elemet.
2. Válassza az **Új** lehetőséget az eszközdokumentum-rekord létrehozásához.
3. A dokumentumkapcsolat specifikusságának szükséges szintjétől függően végezze el a releváns kiválasztásokat egy vagy több mezőn a következő közül: **Eszköztípus**, **Gyártó**, **Modell**, **Eszköz**, **Feladattípus-kategória**, **Feladattípus**, **Feladattípus változata** és **Feladat követelménye**. A **Feladattípus-változat** és a **Feladat követelménye** mezőkben elérhető lehetőségek a **Feladattípus** mezőben kiválasztott beállítástól függenek.

    > [!NOTE]
    > Amikor a rendszer olyan dokumentumokat keres, amelyek egy eszközhöz vagy egy munkarendeléshez kapcsolódnak, az Eszközkezelés minden eszközdokumentum-rekordon végigmegy lehetséges egyezést keresve. Mindig a leginkább meghatározott kombinációt ellenőrzi először. Más szóval az Eszközkezelés modul először a **Feladat követelménye** mezővel való egyezést ellenőrzi. Ha nem talál egyezést, akkor a **Feladattípus változata** mezővel való egyezést ellenőrzi. Ha nem talál egyezést, akkor a **Feladattípus** mezővel való egyezést ellenőrzi, és így tovább. Ahogy az az **Eszközdokumentumok** oldal elrendezésében is látható, ez a viselkedésmód azt jelenti, hogy a legspecifikusabb kombináció megkereséséhez az Eszközkezelés minden egyes rekordot jobbról balra ellenőriz egyezést keresve. Egy eszközhöz vagy egy munkarendeléshez több dokumentum is kapcsolódhat. A karbantartási kérés vagy a munkarendelés szolgáltatási szintjét igény szerint módosíthatja.

4. **Mellékletek** kiválasztása. Megjelenik a szabványos **Dokumentumkezelés** lap.
5. Állítsa be az eszközdokumentum-rekordhoz csatolandó dokumentumokat vagy jegyzeteket. Dokumentumok csatolása után a **Mellékletek** mező a rekordhoz kapcsolódó dokumentumok számát jeleníti meg.
