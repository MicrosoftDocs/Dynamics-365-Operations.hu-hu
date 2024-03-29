---
title: Fizetési mód beállítása ISO20022-jóváírás átutalásához
description: Ez az eljárás bemutatja, hogyan állítható be a szállító fizetési módja ISO20022 átutalásra vagy egyéb fizetési típusra fájl létrehozásához vezető elektronikus jelentéskészítés használatával.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPaymMode
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7f87cc0dfa47295f047ef97732f60733c362ca4066d9070418322b34934e3ce3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773660"
---
# <a name="set-up-method-of-payment-for-iso20022-credit-transfer"></a>Fizetési mód beállítása ISO20022-jóváírás átutalásához

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan állítható be a szállító fizetési módja ISO20022 átutalásra vagy egyéb fizetési típusra fájl létrehozásához vezető elektronikus jelentéskészítés használatával. 

A feladat elvégzése előtt exportálnia kell a formátumkonfigurációkat és be kell állítania a fizetési számlákat.

Ez a feladat a DEMF bemutatócég segítségével lett létrehozva.

Ez a harmadik azon öt eljárás közül, amelyek elektronikus jelentési beállítások használatával mutatják be a szállítói kifizetési folyamatot. Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.

1. Ugorjon a Kötelezettségek > Kifizetés beállítása > Fizetési módok pontra.
2. Rekordok kereséséhez használja a gyorsszűrőt. Például szűkítsen a „Fizetési mód” mezővel a „SEPA CT” értéket beírva.
3. Kattintson a Szerkesztés lehetőségre.
4. Az Időszak mezőben válassza ki a „Teljes” lehetőséget.
5. A Fizetés típusa mezőben válassza ki az „Elektronikus fizetés” lehetőséget.
6. Bontsa ki a Fájlformátumok szakaszt.
7. Válassza az Igen beállítást az Általános elektronikus jelentéskészítés mezőben.
8. Az Exportformátum konfigurációja mezőben adjon meg vagy válasszon ki egy értéket.
    * A listán válassza ki az ISO20022 jóváírást (DE). Ha a lista üres, a szállítói kifizetésnek nincs importált és aktivált exportálási konfigurációja.  
9. A Fiók típusa mezőben válassza ki a „Bank” lehetőséget.
10. A Fizetési számla mezőben adja meg a „DEMF OPER” értékeket.
11. Kattintson a Mentés gombra.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]