---
title: Szállítók és szállítói bankszámlák beállítása ISO20022 típusú átutalásokhoz
description: Ez az eljárás bemutatja, hogyan állíthatja be a szállítót és a szállítóspecifikus bankszámlaadatokat az ISO20022 átutalási, illetve másmilyen szállítói fizetési fájl létrehozásához.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ab8c52b9b457505c2cf2bfca46cb938e73c0142e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174892"
---
# <a name="set-up-vendors-and-vendor-bank-accounts-for-iso20022-credit-transfers"></a>Szállítók és szállítói bankszámlák beállítása ISO20022 típusú átutalásokhoz

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan állíthatja be a szállítót és a szállítóspecifikus bankszámlaadatokat az ISO20022 átutalási, illetve másmilyen szállítói fizetési fájl létrehozásához. 

Ez az eljárás az DEMF bemutatócéget használja.
Ez a negyedik azon öt eljárás közül, amelyek elektronikus jelentési beállítások használatával mutatják be a szállítói kifizetési folyamatot. Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.


## <a name="set-up-bank-details"></a>Bankadatok beállítása
1. Ugrás a Kötelezettségek > Szállítók > Minden szállító elemre.
2. Rekordok kereséséhez használja a gyorsszűrőt. Például szűkítsen a Szállítói számla mezővel a „DE-001” értéket beírva.
3. A szállítói adatok megadásához kattintson a DE-001 lehetőségre.
4. A Művelet ablaktáblában kattintson a Szállító elemre.
5. Kattintson a Bankszámlák lehetőségre.
6. Kattintson a Szerkesztés lehetőségre.
    * Ha nincs elérhető bank, hozzon létre újat.  
7. A SWIFT kód mezőbe írja be a „COBADEFFXXX” értéket.
8. Az IBAN mezőbe írja be a „DE36200400000628808808” értéket.
9. Zárja be a lapot.

## <a name="set-up-a-method-of-payment-for-the-vendor"></a>A szállító fizetési módjának beállítása
1. Kattintson a Szerkesztés lehetőségre.
2. Bontsa ki vagy zárja be a Kifizetés szakaszt.
3. A Fizetési mód mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. A listában kattintson a SEPA CT sorban lévő hivatkozásra.
5. Kattintson a Mentés gombra.

