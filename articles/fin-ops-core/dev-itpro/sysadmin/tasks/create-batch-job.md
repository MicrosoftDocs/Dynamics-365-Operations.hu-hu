---
title: Kötegelt feladat létrehozása
description: A kötegelt feladat egy Alkalmazásobjektum-kiszolgáló (AOS) példányához elküldött feladatcsoport az automatikus feldolgozáshoz.
author: maertenm
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f498014555e0beccbc8965dd43e5162944867978
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745861"
---
# <a name="create-a-batch-job"></a>Kötegelt feladat létrehozása

[!include [banner](../../includes/banner.md)]

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


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]