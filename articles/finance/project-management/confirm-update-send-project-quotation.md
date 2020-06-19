---
title: Projekt árajánlat megerősítése, frissítése és elküldése
description: Ez a témakör bemutatja, hogy hogyan lehet árajánlatot küldeni a vevőnek megerősítésre, módosítani azt a visszajelzés alapján, majd újraküldeni az árajánlatot.
author: kfend
manager: AnnBe
ms.date: 05/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 7c2f7435ed63702dafb52b0eff57c0f174ff829e
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410228"
---
# <a name="confirm-update-and-send-a-project-quotation"></a>Projekt árajánlat megerősítése, frissítése és elküldése

[!include [banner](../includes/banner.md)]

Miután létrehozta és elküldte a projektárajánlatot a vevőnek, a vevőtől visszaigazolást kell kapnia, mielőtt az árajánlat állapotát **Elküldöttre** frissíti. A vevő által kért módosítások frissíthetők az ajánlatban. Az árajánlat állapotának **Elküldött** értékre frissítése után az nem módosítható. A következő eljárás bemutatja, hogy hogyan lehet árajánlatot küldeni a megerősítés kérése céljából, visszajelzés alapján elvégezni a frissítéseket, majd elküldeni az ajánlatot.

## <a name="send-a-project-quotation-confirmation"></a>Projekt árajánlat megerősítés küldése  

Meglévő projekt árajánlat elküldhet megerősítésre e-mailben vagy nyomtatott kinyomtatva is. 

1. Ugorjon a **Projektvezetés és könyvelés** > **Árajánlatok** > **Projektajánlat** pontra. 
2. A **Projektajánlat** oldalon jelölje ki azt az árajánlatot amelyet el szeretne küldeni megerősítésre. 
3. A **Követés** lapon a **Létrehozás** csoportban válassza a **Megerősítés** elemet. 
4. Az **Ajánlat visszaigazolása** lapon adja meg a szükséges paramétereket. Ha például ki szeretné nyomtatni a visszaigazolást , akkor a **Nyomtatási** beállítások területen kapcsolja be a **Visszaigazolást nyomtatása** lehetőséget, majd kattintson az **OK** gombra.
5. Az **Ajánlat küldése** lapon válassz a **Beállítások** lehetőséget a **Nyomtatási cél beállításai** oldalon , majd válassza, ki hogy az ajánlatot **Képernyőre**, **E-mailben**, **Fájlban**, **Nyomtatási archívumba** vagy **Nyomtatóra** szeretné küldeni, majd végezze el az esetleges módosításokat a **Specifikáció** lapon az árajánlat küldéséhez.
6. A **Nyomtatási cél beállítása** oldalon válassza az **OK** lehetőséget.  

## <a name="update-a-project-quotation"></a>Projektajánlat frissítése

Meglévő projektajánlat módosításához az ajánlat állapota **Létrehozva** kell legyen. Egy meglévő ajánlat frissítéséhez hajtsa végre a következő lépéseket. 

1. Ugorjon a **Projektvezetés és könyvelés** > **Árajánlatok** > **Projektajánlatok** pontra.
2. A **Projektajánlatok** lapon válassza ki a frissíteni kívánt árajánlatot, és a Műveleti ablaktáblán válassza a **Szerkesztés** elemet.
3. Frissítse a szükséges mezőadatokat majd a művelet ablaktáblán válassza a **Mentés** elemet.  

## <a name="send-a-project-quotation-to-a-customer"></a>Projektárajánlat küldése vevőnek 

1. Nyissa meg a **Projektvezetés és könyvelés** > **Ajánlatokat** > **Projektajánlatok** lehetőséget, és válassza ki az elküldeni kívánt projektajánlatot.
2. A **Projekt ajánlatok** oldalon az **Ajánlat** lapon a **Folyamat** csoportban válassz az **Árajánlat küldése** elemet. Az ajánlatok állapota **Elküldve** értékre frissül.

> [!NOTE]
> A projektajánlat nem módosítható, ha az állapota **Elküldve** értékre módosul.
