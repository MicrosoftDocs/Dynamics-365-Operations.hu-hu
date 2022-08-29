---
title: Részlegesen foglalt átmozgatási rendelések kötegelt kiadása
description: Ez a témakör azt ismerteti, hogyan lehet beállítani és alkalmazni a részlegesen lefoglalt átátviteli rendelések kötegelt kiadását egy mobileszközről.
author: perlynne
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, WHSFulfillmentPolicy
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 741377a43e2bfe702b213647cc6460a3d6ad93fb
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/02/2022
ms.locfileid: "9218682"
---
# <a name="batch-release-of-partially-reserved-transfer-orders"></a>Részlegesen foglalt átmozgatási rendelések kötegelt kiadása

[!include [banner](../includes/banner.md)]

A részlegesen foglalt átmozgatási rendelések kötegelt kiadása funkció lehetővé teszi az átmozgatási rendelések részleges kiadását egy raktárba kötegelt feldolgozással.
Mivel lehetőség van egy részleges mennyiség kiadására, egy rendelés kiadásához nem kell megvárni, hogy a teljes rendelési mennyiség elérhető legyen a raktárban.

A rendelések raktárba való kiadása raktárkezelési folyamatok (WMS) folyamat. A folyamat olyan tevékenységeket foglal magában, például kitárolás, csomagolás és a szállítás, amelyeket egy raktári dolgozó mobileszköz használatával tud végrehajtani.

## <a name="where-it-applies"></a>Alkalmazási kör

Ehhez a funkcióhoz az átmozgatási rendelések kiadása kötegelt feldolgozással történik meg a raktárba. Ez a funkció akkor hasznos, ha nincs elegendő készlet a raktárban, de továbbra is el szeretné vinni a cikkek az egyik raktárból a másikba.

## <a name="how-it-is-set-up"></a>Hogyan van beállítva

### <a name="specify-fulfillment-criteria-for-transfer-orders-and-sales-orders"></a>Átmozgatási rendelések és értékesítési rendelések teljesítési feltételeinek megadása

Mielőtt egy rendelés részben is kiadható egy raktárnak kötegelve, a teljesítési feltételeknek teljesülniük kell. A teljesítési feltételeket a teljesítési irányelv határozza meg.

Az átmozgatási rendelések és az értékesítési rendelések teljesítési irányelvei a vállalat szintjén vannak megadva. A teljesítési irányelv beállításától függően a rendelések kötegelt kiadása elfogadásra vagy elutasításra kerül. A rendelések feldolgozása ennek megfelelően fog megtörténni.

- Az áthozott rendelésekre **\>\>\>** és értékesítési rendelésekre vonatkozó teljesítő irányelvek létrehozásához menjen a Raktárkezelés beállítása raktári teljesítés irányelveibe, és a név és leírás megadásával hozzon létre egy teljesítési házirendet.
- A teljesítési ráta, egy értéktípus és a teljesítési irányelv megszegése esetén megjelenő üzenet megadásához váltsa át a Raktárkezelés **\>\>\> beállítása raktári teljesítési irányelvként való kiadását,** **és állítsa be a Teljesítési ráta,** **·** **az Érték típusa és a Teljesítés** megszegése üzenetmezőket.

### <a name="set-the-fulfillment-policies-for-transfer-orders-and-sales-orders"></a>Átmozgatási rendelések és értékesítési rendelések teljesítési irányelveinek megadása

- Az átvezetési **\>\>** rendelések teljesítási kötvényeinek beállításához váltsa át a Készletkezelés beállítása – Készlet- és raktárkezelési paramétereket, **·** **majd válassza ki az átvezetési rendelés teljesítésére vonatkozó házirendet az Átvezetési rendelések lap Raktárkezelés** területén.
- Az értékesítési rendelések teljesítási **\>\>** kötvényeinek beállításához váltsa át a Kinnlevőségek beállítása – paraméterek gombra, **majd** a Raktárkezelés lapon válassza ki az értékesítési rendelések teljesítási irányelvét.

## <a name="allow-release-in-a-batch-and-specify-the-quantity-that-should-be-released-in-a-batch"></a>Kiadás engedélyezése kötegben, és a kötegben kiadandó mennyiség megadása

A kötegelt feladat rendelések raktárba történő kiadására szolgál, kötegelt módon. A kötegelt feladatban magában lehet beállítani a paramétereket, amelyek megkülönböztetik a kötegelt rendelésként futtatandó rendeléseket.

A **Mennyiség** paraméter határozza meg, hogy a teljes mennyiséget vagy a ténylegesen lefoglalt mennyiséget kell kiadni kötegelve. A **Részben kiadott rendelések kiadásának engedélyezése** paraméter határozza meg, hogy a kötegelt rendeléseket el kell-e fogadni vagy el kell-e utasítani, ha részben ki lettek adva korábban.

- Az átvezetési **rendelések** **·** **részlegesen kiadott rendelési paramétereinek beállítására és kiadásának engedélyezése a Raktárkezelés \>\> raktárba kiadása az átvezetési rendelések automatikus kiadására ugrással történik.**
- Az értékesítési rendelések **részlegesen** **·** **kiadott rendelési paramétereinek mennyiség és kiadás engedélyezése beállításhoz menjen a Raktárkezelés \>\> kiadása raktárba – értékesítési rendelések automatikus kiadása.**


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
