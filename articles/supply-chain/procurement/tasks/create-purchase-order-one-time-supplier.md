---
title: Beszerzési rendelés létrehozása egyszeri szállítóhoz
description: Ez az eljárás bemutatja, hogy hogyan lehet létrehozni egy beszerzési rendelést egy egyszeri szállítóhoz.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d1abd942da608bc221a7a66e03b5269fa30e2c20
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5212030"
---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a>Beszerzési rendelés létrehozása egyszeri szállítóhoz

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogy hogyan lehet létrehozni egy beszerzési rendelést egy egyszeri szállítóhoz. A rendszer automatikusan létrehozza a szállítót a beszerzési rendeléssel együtt, a szállítói számla manuálisan történő létrehozása helyett. Általában a beszerzési ügynök hozza létre a beszerzési rendeléseket. Az útmutatóban mutatott példa használható az USMF demo adatok cégben. Ez az előfeltétele annak, hogy a Kötelezettségek paraméterei lapon az egyszeri szállítói számla legyen beállítva.


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a>Beszerzési rendelés létrehozása egyszeri szállítóhoz
1. Ugorjon a Beszerzés és forrás > Beszerzési rendelés > Összes beszerzési rendelés pontra.
2. Kattintson az Új lehetőségre.
3. Válassza ki az Igen lehetőséget az Egyszeri szállító mezőben.
    * A rendszer automatikusan létrehozza a szállítói számlát és hozzárendeli a beszerzési rendeléshez. A rendszer a szállítói számlát a Kötelezettségek paraméterei oldal Általános lapon megadott sablon alapján hozza létre.  
4. Írja be a szállító nevét a Név mezőbe.
5. Kattintson az OK gombra.
    * Lehetséges, hogy már kész van a beszerzési rendelés, és ugyanúgy fel van dolgozva, mint a többi rendelés. Nincsenek olyan különleges jellemzők, amelyek kapcsolatban állnak azzal, hogy hogyan jött létre. A számla számot ad az esedékes tranzakcióról azon a szállítói számlán, amelyet a rendeléssel hoztak létre, illetve a kifizetés ezt követően történik meg.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]