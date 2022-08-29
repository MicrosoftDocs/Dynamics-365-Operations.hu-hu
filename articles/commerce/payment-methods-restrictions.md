---
title: Nyugta nélküli visszárukhoz használható fizetési módok korlátozása
description: Ez a témakör azt ismerteti, hogyan lehet bizonyos kifizetési típusokat visszatérítésre korlátozni, ha a visszatérítés bevételezés nélkül történik.
author: josaw1
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2019-02-01
ms.dyn365.ops.version: AX 10.0.0, Retail Feb 2019 update
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.industry: Retail
ms.search.form: RetailTenderTypeTable
ms.openlocfilehash: 9b14d7d8f6a2d9209ad6a12cd53bce4a9b50178d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281396"
---
# <a name="restrict-payment-methods-for-returns-without-a-receipt"></a>Nyugta nélküli visszárukhoz használható fizetési módok korlátozása


[!include [banner](includes/banner.md)]

Minden egyes fizetéstípust, amelyet a kiskereskedő elfogad, konfigurálni kell a rendszer beállításakor. Ez a témakör azt ismerteti, hogyan lehet bizonyos kifizetési típusokat visszatérítésre korlátozni, ha a visszatérítés bevételezés nélkül történik.

## <a name="set-up-payment-methods"></a>Fizetési módok beállítása

Fizetési módok beállításához a következő feladatokat kell elvégezni.
1. A teljes szervezet által elfogadott fizetési módok létrehozása.
2. Szervezeti szinten elfogadott kártyatípusok és kártyaszámok létrehozása. Ha elfogadja a hitelkártyákat és bankkártyákat, akkor létre kell hoznia egy fizetési típust a kártyákhoz, majd létre kell hoznia a szervezetnél elfogadott kártyatípusokat és azok számait.
3. Üzlethez tartozó fizetési módok beállítása. Minden egyes üzlethez fizetési módokat kell társítania, majd meg kell adnia az egyes fizetési módok adott üzletben jellemző beállításait.
4. Kártyás fizetési módok beállítása az üzletekhez. Minden kártyás fizetési módhoz, amelyet az üzlet elfogad, végezze el a kártyabeállítást.

![Üzlet beállítása.](media/NoReceiptReturns1.png "Retail áruház beállítása") 


## <a name="restrict-payment-methods-for-returns-without-a-receipt"></a>Nyugta nélküli visszárukhoz használható fizetési módok korlátozása

Minden üzleti fizetési módhoz a **Üzlet kezelése** oldalon, a **Nyugta nélküli visszatérítések** alatt állítsa be a **Nyugta nélkül visszatérítések korlátozása** elemet **Igen** értékre. 

Az kapcsoló alapértelmezés szerinti értéke **Nem**, amely biztosítja, hogy a fizetési mód engedélyezve legyen a visszatérítésekhez. 

Ha a **Nyugta nélkül visszatérítések korlátozása** értékre **Igen**, a választott fizetési nem érhető el visszatérítésekhez. 

![Üzlet fizetési módja.](media/NoReceiptReturns3.png "Retail áruházi fizetési mód") 

> [!NOTE]
> Amikor a pénztáros kiválaszt egy fizetési módot, amely korlátozva van nyugta nélküli visszatérítéshez megjelenik egy üzenet az elfogadható fizetési módok ellenőrzéséhez.

![Elfogadható fizetési módok.](media/NoReceiptReturns4.png "Elfogadható fizetési módok") 

Ha egy tranzakcióhoz nyugtás és nyugata nélküli visszatérítés is tartozik akkor a korlátozási feltételek nem lesznek alkalmazva, mivel a tranzakció visszatérítés munkafolyamat lesz nyugtával. 



[!INCLUDE[footer-include](../includes/footer-banner.md)]
