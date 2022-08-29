---
title: Fordított naplófeladás
description: Ez a témakör olyan lehetőségeket ismertet, amelyek lehetővé teszik bizonylatok sztornírozését a bizonylattranzakciók listájából vagy pénzügyi naplókból.
author: kweekley
ms.date: 10/08/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.form: LedgerTransVoucher, LedgerJournalTable
ms.openlocfilehash: 7e3a22f43bcc312fe60b77db2fc3bc94d15950c5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9284851"
---
# <a name="reverse-journal-posting"></a>Fordított naplófeladás

[!include [banner](../includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365-ös pénzügyi képességeket írja le, amelyek lehetővé teszik egy teljes napló sztornírozését, illetve egy vagy több bizonylat sztornírozését a bizonylattranzakciók listájából, az eredetétől függetlenül. 

A jelen cikk leírásában ismertetett egyik funkció használata előtt be kell kapcsolva lennie a rendszerben. A rendszergazdák használhatják a **Funkciókezelés** munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A funkció a következő módon jelenik meg:
 - Modul: Főkönyv
 - Funkció neve: **Több dokumentum tömeges sztornírozása**

## <a name="reversing-journals"></a>Naplók sztornózása

A naplósorok egyenként is sztornírozhatók. A sztornírozási naplófeladással a teljes pénzügyi naplót is sztornírozhatja. Napló sztornírozása: 

- Szűrje a feladott naplókat, és nyissa meg a napló **Sorok** nézetét.
- Kattintson a képernyő felső részén lévő **Sztornírozás** menüre.
- Megjelenik a bizonylatok és a bizonylatsorok teljes száma, valamint a sztornírozott sorok teljes összege.
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

- Kattintson a képernyő felső részén lévő **Napló teljes legördülő menüjének sztornírozása** menüre.
- Megjelenik a bizonylatok és a bizonylatsorok teljes száma, valamint a sztornírozott sorok teljes összege.
- Válassza az **Igen** lehetőséget, ha a meglévő tranzakciós dátumokat szeretné használni, vagy a **Nem** lehetőséget új beírásához. Bizonyos esetekben előfordulhat, hogy az eredeti tranzakció időszaka le van zárva, és új tranzakció dátumát kell megadni a sztornírozásához.
- Ha a **Nem** beállítást választja, adjon meg egy tranzakciós dátumot a sztornírozáshoz. 
- Megjegyzés megadása a sztornírozási tranzakció leírásához.
- Kattintson a **Sztornírozás** gombra.

A tranzakció sztornírozva lesz. 

Ha a bizonylat sorainak száma meghaladja a 100-at, akkor a sztornírozási folyamat kötegelt feldolgozással futtatható. Megtekintheti az eredményeket a kötegelt feladat megjegyzésinek megtekintésével. A nem sztornírozható tranzakciók jelezve lesznek a kötegelt feladat előzményeiben.

Ha a bizonylatsorok száma 100 vagy kevesebb, akkor a sztornírozási folyamat azonnal elindul. Az eredmények egy párbeszédablakban jelennek meg, amely minden olyan bizonylatot megjelenít, amely nem sztornírozható, és megadja a annak okát. Az **OK** gombbal zárja be a párbeszédpanelt.

A tranzakciókat csak akkor lehet sztornírozni, ha megfelelnek a sztornírozáshoz szükséges üzleti szabályoknak. A szállítói kifizetések nem sztornírozhatóak az ebben a cikkben ismertetett képességekkel. A szállítói kifizetéseket a [Szállítói kifizetés sztornózása](../accounts-payable/reverse-vendor-payment.md) leírt lépésekkel lehet sztornírozni.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
