---
title: Nyugta nélküli visszárukhoz használható fizetési módok korlátozása
description: Ez a témakör leírja, hogyan korlátozhatók bizonyos kifizetéstípusok visszatérítésre, ha a vissszatérítés nyugta nélkül történik.
author: rapraj
manager: AnnBe
ms.date: 01/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2019-02-01
ms.dyn365.ops.version: AX 10.0.0, Retail Feb 2019 update
ms.openlocfilehash: 1f84a6382453c0ba7540e618ad90ae1d3c684a2b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "315912"
---
# <a name="restrict-payment-methods-for-returns-without-a-receipt"></a>Nyugta nélküli visszárukhoz használható fizetési módok korlátozása

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Minden egyes fizetéstípust, amelyet a kiskereskedő elfogad, konfigurálni kell a rendszer beállításakor. Ez a témakör leírja, hogyan korlátozhatók bizonyos kifizetéstípusok visszatérítésre, ha a vissszatérítés nyugta nélkül történik.

## <a name="set-up-payment-methods"></a>Fizetési módok beállítása

Fizetési módok beállításához a következő feladatokat kell elvégezni.
1. A teljes szervezet által elfogadott fizetési módok létrehozása.
2. Szervezeti szinten elfogadott kártyatípusok és kártyaszámok létrehozása. Ha elfogadja a hitelkártyákat és bankkártyákat, akkor létre kell hoznia egy fizetési típust a kártyákhoz, majd létre kell hoznia a szervezetnél elfogadott kártyatípusokat és azok számait.
3. Üzlethez tartozó fizetési módok beállítása. Minden egyes üzlethez fizetési módokat kell társítania, majd meg kell adnia az egyes fizetési módok adott üzletben jellemző beállításait.
4. Kártyás fizetési módok beállítása az üzletekhez. Minden kártyás fizetési módhoz, amelyet az üzlet elfogad, végezze el a kártyabeállítást.

![Retail Store beállítása](media/NoReceiptReturns1.png "Retail Store beállítása") 


## <a name="restrict-payment-methods-for-returns-without-a-receipt"></a>Nyugta nélküli visszárukhoz használható fizetési módok korlátozása

Minden üzleti fizetési módhoz a **Kiskereskedelmi üzlet kezelése** oldalon, a **Nyugta nélküli visszatérítések** alatt állítsa be a **Nyugta nélkül visszatérítések korlátozása** elemet **Igen** értékre. 

Az kapcsoló alapértelmezés szerinti értéke **Nem**, amely biztosítja, hogy a fizetési mód engedélyezve legyen a visszatérítésekhez. 

Ha a **Nyugta nélkül visszatérítések korlátozása** értékre **Igen**, a választott fizetési nem érhető el visszatérítésekhez. 

![Kiskereskedelmi üzlet fizetési mód](media/NoReceiptReturns3.png "Kiskereskedelmi üzlet fizetési mód") 

> [!NOTE]
> Amikor a pénztáros kiválaszt egy fizetési módot, amely korlátozva van nyugta nélküli visszatérítéshez megjelenik egy üzenet az elfogadható fizetési módok ellenőrzéséhez.

![Elfogadható fizetési módok](media/NoReceiptReturns4.png "Elfogadható fizetési módok") 

Ha egy tranzakcióhoz nyugtás és nyugata nélküli visszatérítés is tartozik akkor a korlátozási feltételek nem lesznek alkalmazva, mivel a tranzakció visszatérítés munkafolyamat lesz nyugtával. 

