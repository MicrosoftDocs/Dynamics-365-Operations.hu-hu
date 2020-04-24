---
title: Részlegesen foglalt átmozgatási rendelések kötegelt kiadása
description: Ez a témakör leírja, hogyan állíthatja be és alkalmazhatja mobileszközről a részlegesen foglalt átmozgatási rendelések kötegelt kiadását.
author: pjacobse
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f0707731caaf9b4852e3c19be899ad92f5b84e29
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201295"
---
# <a name="batch-release-of-partially-reserved-transfer-orders"></a>Részlegesen foglalt átmozgatási rendelések kötegelt kiadása

[!include [banner](../includes/banner.md)]

A részlegesen foglalt átmozgatási rendelések kötegelt kiadása funkció lehetővé teszi az átmozgatási rendelések részleges kiadását egy raktárba kötegelt feldolgozással.
Mivel lehetőség van egy részleges mennyiség kiadására, egy rendelés kiadásához nem kell megvárni, hogy a teljes rendelési mennyiség elérhető legyen a raktárban.

A rendelések kiadása egy raktárnak speciális raktárkezelési folyamat. A folyamat olyan tevékenységeket foglal magában, például kitárolás, csomagolás és a szállítás, amelyeket egy raktári dolgozó mobileszköz használatával tud végrehajtani.

## <a name="where-it-applies"></a>Alkalmazási kör

Ehhez a funkcióhoz az átmozgatási rendelések kiadása kötegelt feldolgozással történik meg a raktárba. Ez a funkció akkor hasznos, ha nincs elegendő készlet a raktárban, de továbbra is el szeretné vinni a cikkek az egyik raktárból a másikba.

## <a name="how-it-is-set-up"></a>Hogyan van beállítva

### <a name="specify-fulfillment-criteria-for-transfer-orders-and-sales-orders"></a>Átmozgatási rendelések és értékesítési rendelések teljesítési feltételeinek megadása

Mielőtt egy rendelés részben is kiadható egy raktárnak kötegelve, a teljesítési feltételeknek teljesülniük kell. A teljesítési feltételeket a teljesítési irányelv határozza meg.

Az átmozgatási rendelések és az értékesítési rendelések teljesítési irányelvei a vállalat szintjén vannak megadva. A teljesítési irányelv beállításától függően a rendelések kötegelt kiadása elfogadásra vagy elutasításra kerül. A rendelések feldolgozása ennek megfelelően fog megtörténni.

-   Teljesítési irányelvek létrehozásához az átmozgatási rendelésekhez és az értékesítési rendelésekhez kattintson a **Raktárkezelés** \> **Beállítás** \> **Raktárba való kiadás** \> **Teljesítési irányelv**  elemre, és hozzon létre egy teljesítési irányelvet: ehhez írjon be egy nevet és egy leírást.

-   Teljesítési ráta, értéktípus és üzenet beállításához, amely a teljesítési irányelv megszegése esetén jelenik meg, kattintson a **Raktárkezelés** \> **Beállítás** \> **Raktárba való kiadás** \> **Teljesítési irányelv** elemre, majd adja meg a **Teljesítési ráta**, az **Értéktípus** és a **Teljesítési szabálytalanságok üzenetei** mezők tartalmát.

### <a name="set-the-fulfillment-policies-for-transfer-orders-and-sales-orders"></a>Átmozgatási rendelések és értékesítési rendelések teljesítési irányelveinek megadása

-   Az átmozgatási rendelések teljesítési irányelveinek beállításához kattintson a **Készletkezelés** \> **Beállítás** \> **Készlet- és raktárkezelési paraméterek** \> **Átmozgatási rendelések** \> **Raktárkezelés** elemre, majd válasszon ki egy átmozgatási rendelési teljesítési irányelvet.

-   Kattintson az értékesítési rendelések teljesítési házirendjeinek beállításához kattintson a **Kinnlevőségek** \> **Beállítás** \> **Kinnlevőségek paraméterei** \> **Raktárkezelés** elemre, és válasszon ki egy értékesítésirendelés-teljesítési irányelvet.

## <a name="allow-release-in-a-batch-and-specify-the-quantity-that-should-be-release-in-a-batch"></a>Engedélyezze a kötegelt kiadást, és adja meg a mennyiséget, amelyet kötegelt kiadással kell kiadni.

A kötegelt feladat rendelések raktárba történő kiadására szolgál, kötegelt módon. A kötegelt feladatban magában lehet beállítani a paramétereket, amelyek megkülönböztetik a kötegelt rendelésként futtatandó rendeléseket.

A **Mennyiség** paraméter határozza meg, hogy a teljes mennyiséget vagy a ténylegesen lefoglalt mennyiséget kell kiadni kötegelve. A **Részben kiadott rendelések kiadásának engedélyezése** paraméter határozza meg, hogy a kötegelt rendeléseket el kell-e fogadni vagy el kell-e utasítani, ha részben ki lettek adva korábban.

-   Az átmozgatási rendelések **Mennyiség** és **Részben kiadott rendelések kiadásának engedélyezése** paramétereinek beállításához kattintson a **Raktárkezelés** \> **Raktárba való kiadás** \> **Átmozgatási rendelések automatikus kiadása** elemre.

-   Az értékesítési rendelések **Mennyiség** és **Részben kiadott rendelések kiadásának engedélyezése** paramétereinek beállításához kattintson a **Raktárkezelés** \> **Raktárba való kiadás** \> **Értékesítési rendelések automatikus kiadása** elemre.
