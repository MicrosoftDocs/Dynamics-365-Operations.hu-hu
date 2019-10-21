---
title: Fordított naplófeladás
description: Ez a témakör bemutatja azokat a funkciókat, amelyek lehetővé teszik a bizonylatok sztornírozását a bizonylati tranzakciólistáról vagy a pénzügyi naplókból.
author: MikeFalkner
manager: AnnBe
ms.date: 08/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a5456e60f1f3cee5f83ac7f725f7e01ba5bd7a1
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/30/2019
ms.locfileid: "2248585"
---
# <a name="reverse-journal-posting"></a>Naplófeladás sztornírozása

[!include [banner](../includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 Finance egyik funkcióját mutatja be, amelyek lehetővé teszik a teljes napló sztornírozását, illetve egy vagy több bizonylat sztornírozását a bizonylati tranzakciólistáról, az eredettől függetlenül. 

## <a name="reversing-journals"></a>Naplók sztornózása

A naplósorok egyenként is sztornírozhatók. A sztornírozási naplófeladással a teljes pénzügyi naplót is sztornírozhatja. Napló sztornírozása: 
- A pénzügyi napló megnyitása és a feladott naplók szűrése
- Kattintson a képernyő felső részén lévő Sztornírozás menüre
- Megjelenik a bizonylatok és a bizonylatsorok teljes száma, valamint a sztornírozott sorok teljes összege
- Válassza az Igen lehetőséget, ha a meglévő tranzakciós dátumokat szeretné használni, vagy a Nem lehetőséget új beírásához. Bizonyos esetekben előfordulhat, hogy az eredeti tranzakció időszaka le van zárva, és új tranzakció dátumát szeretné megadni a sztornírozáshoz.
- Ha a Nem beállítást választotta, adjon meg egy tranzakciós dátumot a sztornírozáshoz. 
- Írjon be egy megjegyzést, amelyet a sztornírozási tranzakcióhoz szeretne adni
- Kattintson a Sztornírozás gombra.

A tranzakció sztornírozva lesz. 

Ha a bizonylatsorok száma meghaladja a 100 sort, akkor a sztornírozási folyamat kötegelt feldolgozással futtatható. Megtekintheti a sztornírozás eredményeit a futtatott kötegelt feladatban szereplő megjegyzések megtekintésével. A program minden hibát feljegyez a kötegelt feladat előzményeiben.

Ha a bizonylatsorok száma 100 vagy kisebb, akkor a sztornírozási folyamat azonnal elindul. Az eredmények egy párbeszédablakban jelennek meg, amely minden olyan bizonylatot megjelenít, amely nem sztornírozható, és megadja a sztornírozás okát is. Zárja be a párbeszédpanelt az OK gombra kattintva.

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a>Bizonylatok sztornírozása a bizonylati tranzakciók listájából. 

A bizonylatokat a **Bizonylat tranzakciólista** modulból sztornírozhatja az összes alfőkönyvet lefedve. Ezenkívül egyszerre egynél több bizonylatot is sztornírozhat. 

Egy vagy több bizonylat sztornírozása: 
- Kattintson a képernyő felső részén lévő Sztornírozás menüre
- Megjelenik a bizonylatok és a bizonylatsorok teljes száma, valamint a sztornírozott sorok teljes összege
- Válassza az Igen lehetőséget, ha a meglévő tranzakciós dátumokat szeretné használni, vagy a Nem lehetőséget új beírásához. Bizonyos esetekben előfordulhat, hogy az eredeti tranzakció időszaka le van zárva, és új tranzakció dátumát szeretné megadni a sztornírozáshoz.
- Ha a Nem beállítást választotta, adjon meg egy tranzakciós dátumot a sztornírozáshoz. 
- Írjon be egy megjegyzést, amelyet a sztornírozási tranzakcióhoz szeretne adni
- Kattintson a Sztornírozás gombra.

A tranzakció sztornírozva lesz. 

Ha a bizonylatsorok száma meghaladja a 100 sort, akkor a sztornírozási folyamat kötegelt feldolgozással futtatható. Megtekintheti a sztornírozás eredményeit a futtatott kötegelt feladatban szereplő megjegyzések megtekintésével. A program minden hibát feljegyez a kötegelt feladat előzményeiben.

Ha a bizonylatsorok száma 100 vagy kisebb, akkor a sztornírozási folyamat azonnal elindul. Az eredmények egy párbeszédablakban jelennek meg, amely minden olyan bizonylatot megjelenít, amely nem sztornírozható, és megadja a sztornírozás okát is. Zárja be a párbeszédpanelt az OK gombra kattintva.

