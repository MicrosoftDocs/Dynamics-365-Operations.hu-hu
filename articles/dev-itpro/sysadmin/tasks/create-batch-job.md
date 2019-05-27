---
title: Kötegelt feladat létrehozása
description: A kötegelt feladat egy Alkalmazásobjektum-kiszolgáló (AOS) példányához elküldött feladatcsoport az automatikus feldolgozáshoz.
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fbb844ebcf8d4b47b127132a5bf0ea45fa40f747
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562881"
---
# <a name="create-a-batch-job"></a>Kötegelt feladat létrehozása

[!include [task guide banner](../../includes/task-guide-banner.md)]

A kötegelt feladat egy Alkalmazásobjektum-kiszolgáló (AOS) példányához elküldött feladatcsoport az automatikus feldolgozáshoz. A Kötegelt feladatok futtatása a feladatot létrehozó felhasználó biztonsági hitelesítő adatainak használatával történik. A következő eljárásokkal lehet meghatározni a kötegelt feladatot. Ez az eljárás az USMF bemutatócéget használja.


## <a name="create-the-batch-job"></a>Kötegelt feladat létrehozása
1. Ugorjon a Rendszerfelügyelet > Lekérdezések > Kötegelt feladatok pontra.
2. Kattintson az Új lehetőségre.
3. A Munkaköri leírás mezőbe írjon be egy értéket.
4. Az Ütemezett kezdő dátum/idő mezőben adjon meg egy dátumot és időt.
5. Kattintson a Mentés gombra.

## <a name="create-a-recurrence"></a>Ismétlődés létrehozása
1. Kattintson a Művelet Panelen a Kötegelt feladat lehetőségre.
2. Kattintson az Ismétlődésre.
    * E beállítások segítségével megadhatja az ismétlődés tartományát és a mintáját.  
3. Kattintson az OK gombra.

## <a name="add-alerts"></a>Figyelmeztetések hozzáadása
1. Kattintson a Művelet Panelen a Kötegelt feladat lehetőségre.
2. Kattintson a figyelmeztetések lehetőségre.
    * Jelezze, ha szeretne figyelmeztető üzenetet kapni a kötegelt feladat befejeződése, meghibásodása vagy törlődése esetén. Adja meg, ha azt szeretné, hogy a figyelmeztetések előugró üzenetekként jelenjenek meg.   
3. Kattintson az OK gombra.

