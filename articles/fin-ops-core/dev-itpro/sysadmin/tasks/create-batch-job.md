---
title: Kötegelt feladat létrehozása
description: A kötegelt feladat egy Alkalmazásobjektum-kiszolgáló (AOS) példányához elküldött feladatcsoport az automatikus feldolgozáshoz.
author: maertenm
manager: AnnBe
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 27541c84a40fe9b7e7705162e06167ad4f7e4ed9
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2191385"
---
# <a name="create-a-batch-job"></a>Kötegelt feladat létrehozása

[!include [task guide banner](../../includes/task-guide-banner.md)]

A kötegelt feladat egy Alkalmazásobjektum-kiszolgáló (AOS) példányához elküldött feladatcsoport az automatikus feldolgozáshoz. A Kötegelt feladatok futtatása a feladatot létrehozó felhasználó biztonsági hitelesítő adatainak használatával történik. A következő eljárásokkal lehet meghatározni a kötegelt feladatot. Ez az eljárás az USMF bemutatócéget használja.


## <a name="create-the-batch-job"></a>Kötegelt feladat létrehozása
1. Ugorjon a **Navigációs lap > Modulok > Rendszerfelügyelet > Lekérdezések > Kötegelt feladatok** pontra.
2. Kattintson az **Új** elemre.
3. A **Munkaköri leírás** mezőbe írjon be egy értéket.
4. Az **Ütemezett kezdő dátum/idő** mezőben adjon meg egy dátumot és időt.
5. Kattintson a **Mentés** gombra.

## <a name="create-a-recurrence"></a>Ismétlődés létrehozása
1. Kattintson a Művelet panelen a **Kötegelt feladat** lehetőségre.
2. Kattintson az **Ismétlődésre**. E beállítások segítségével megadhatja az ismétlődés tartományát és a mintáját.  
3. Kattintson az **OK** gombra.

## <a name="add-alerts"></a>Figyelmeztetések hozzáadása
1. Kattintson a Művelet panelen a **Kötegelt feladat** lehetőségre.
2. Kattintson a **Figyelmeztetések** lehetőségre. Jelezze, ha szeretne figyelmeztető üzenetet kapni a kötegelt feladat befejeződése, meghibásodása vagy törlődése esetén. Adja meg, ha azt szeretné, hogy a figyelmeztetések előugró üzenetekként jelenjenek meg.   
3. Kattintson az **OK** gombra.

## <a name="adjust-batch-job-status"></a>Kötegelt feladat állapotának beállítása
1. Ugorjon a **Rendszerfelügyelet > Lekérdezések > Kötegelt feladatok** pontra.
2. Jelölje ki a megfelelő kötegelt feladatokat.
3. Kattintson a Művelet panelen a **Kötegelt feladat > Funkciók > Állapot módosítása** lehetőségre.
4. Válassza ki a megfelelő állapotot.
    - **Visszatartás**: A kötegelt feladat **visszatartási** értékre állítása, így a kötegelt munkaütemezőből visszatartható. A *leállítással* egyenértékű.
    - **Várakozás**: A kötegelt feladat **várakozásra** történő beállítása, így a kötegelt munkaütemező által elindítható. A *mehettel* egyenértékű.
5. Kattintson az **OK** gombra.
