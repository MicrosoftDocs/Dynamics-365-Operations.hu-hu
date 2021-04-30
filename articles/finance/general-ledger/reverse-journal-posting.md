---
title: Fordított naplófeladás
description: Ez a témakör bemutatja azokat a funkciókat, amelyek lehetővé teszik a bizonylatok sztornírozását a bizonylati tranzakciólistáról vagy a pénzügyi naplókból.
author: MikeFalkner
ms.date: 10/08/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: roschloma
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ab53f4b8888f77cd41ccbd7956ed307ba1b54ff
ms.sourcegitcommit: 7d0cfb359a4abc7392ddb3f0b3e9539c40b7204d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/14/2021
ms.locfileid: "5897136"
---
# <a name="reverse-journal-posting"></a>Naplófeladás sztornírozása

[!include [banner](../includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 Finance egyik funkcióját mutatja be, amelyek lehetővé teszik a teljes napló sztornírozását, illetve egy vagy több bizonylat sztornírozását a bizonylati tranzakciólistáról, az eredettől függetlenül. 

## <a name="reversing-journals"></a>Naplók sztornózása

A naplósorok egyenként is sztornírozhatók. A sztornírozási naplófeladással a teljes pénzügyi naplót is sztornírozhatja. Napló sztornírozása: 

- A pénzügyi napló megnyitása és a feladott naplók szűrése.
- Kattintson a képernyő felső részén lévő **Sztornírozás** menüre.
- Megjelenik a bizonylatok és a bizonylatsorok teljes száma, valamint a sztornírozott sorok teljes összege
- Válassza az **Igen** lehetőséget, ha a meglévő tranzakciós dátumokat szeretné használni, vagy a **Nem** lehetőséget új beírásához. Bizonyos esetekben előfordulhat, hogy az eredeti tranzakció időszaka le van zárva, és új tranzakció dátumát kell megadni a sztornírozáshoz.
- Ha a **Nem** beállítást választja, adjon meg egy tranzakciós dátumot a sztornírozáshoz. 
- Írjon be egy megjegyzést, amelyet a sztornírozási tranzakcióhoz szeretne adni.
- Kattintson a **Sztornírozás** gombra.

A tranzakció sztornírozva lesz. 

Ha a bizonylat sorainak száma meghaladja a 100 sort, akkor a sztornírozási folyamat kötegelt feldolgozással futtatható. Megtekintheti az eredményeket a kötegelt feladat megjegyzésinek megtekintésével. A nem sztornírozható tranzakciók listázva lesznek a kötegelt feladat előzményeiben.

Ha a bizonylat sorainak száma 100 vagy kisebb, akkor a sztornírozási folyamat azonnal elindul. Az eredmények egy párbeszédablakban jelennek meg, amely minden olyan bizonylatot megjelenít, amely nem sztornírozható, és megadja a sztornírozás okát. Az **OK** gombbal zárja be a párbeszédpanelt.

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a>Bizonylatok sztornírozása a bizonylati tranzakciók listájából. 

A bizonylatokat a **Bizonylat tranzakciólista** modulból sztornírozhatja az összes alfőkönyvet lefedve. Ezenkívül egyszerre egynél több bizonylatot is sztornírozhat. 

Egy vagy több bizonylat sztornírozása: 

- Kattintson a képernyő felső részén lévő **Sztornírozás** menüre
- Megjelenik a bizonylatok és a bizonylatsorok teljes száma, valamint a sztornírozott sorok teljes összege.
- Válassza az **Igen** lehetőséget, ha a meglévő tranzakciós dátumokat szeretné használni, vagy a **Nem** lehetőséget új beírásához. Bizonyos esetekben előfordulhat, hogy az eredeti tranzakció időszaka le van zárva, és új tranzakció dátumát kell megadni a sztornírozásához.
- Ha a **Nem** beállítást választja, adjon meg egy tranzakciós dátumot a sztornírozáshoz. 
- Megjegyzés megadása a sztornírozási tranzakció leírásához.
- Kattintson a **Sztornírozás** gombra.

A tranzakció sztornírozva lesz. 

Ha a bizonylat sorainak száma meghaladja a 100-at, akkor a sztornírozási folyamat kötegelt feldolgozással futtatható. Megtekintheti az eredményeket a kötegelt feladat megjegyzésinek megtekintésével. A nem sztornírozható tranzakciók jelezve lesznek a kötegelt feladat előzményeiben.

Ha a bizonylatsorok száma 100 vagy kevesebb, akkor a sztornírozási folyamat azonnal elindul. Az eredmények egy párbeszédablakban jelennek meg, amely minden olyan bizonylatot megjelenít, amely nem sztornírozható, és megadja a annak okát. Az **OK** gombbal zárja be a párbeszédpanelt.

A tranzakciókat csak akkor lehet sztornírozni, ha megfelelnek a sztornírozáshoz szükséges üzleti szabályoknak. A szállítói kifizetéseket nem lehet sztornírozni az ebben az témakörben leírt képességgel. A szállítói kifizetéseket a [Szállítói kifizetés sztornózása](../accounts-payable/reverse-vendor-payment.md) leírt lépésekkel lehet sztornírozni.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]