---
title: Végrehajtási sorrend a Finance and Operations és a Common Data Service kezdeti szinkronizálásához
description: Ez a témakör azt a szinkronizálási sorrendet határozza meg, amelyet a kezdeti adatok létrehozásához követnie kell.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: b74bc2d3133af7e87663a4e6bafb8780e0a6a66f
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797298"
---
# <a name="execution-order-for-initial-sychronization-of-finance-and-operations-and-common-data-service"></a>Végrehajtási sorrend a Finance and Operations és a Common Data Service kezdeti szinkronizálásához

Az adatintegráció használata előtt létre kell hoznia a vevők, szállítók és kapcsolattartók számára szükséges kezdeti adatokat. Ha például **Új szállítói csoport** cikket szeretne létrehozni, és a **Fizetési feltételeket** **Net30** értékre szeretné beállítani akkor a **Szállítói csoport** cikk létrehozása előtt meg kell győződnie arról, hogy **Net30** létezik mind a Finance and Operations, mind a Common Data Service megoldásokban. (Jövőben, kiadunk egy kettős írási funkciót, amelynek neve **Kezdeti szinkronizálás** lesz. Ez egy egyszeri adatszinkronizálást fog végezni a Finance and Operations és a Common Data Service között a kettős írás beállításának részeként.)

Tippek: Felszabadítunk egy kettős írású leképezést minden referenciaadathoz beleértve a **Fizetési feltételek** elemhez. Ha már rendelkezik a kezdeti adatokkal az egyik rendszerben, a rekordon végzett kis frissítési művelet elindíthatja a kettős írást az adott rekordra vonatkozóan. 

Kövesse az alábbi sorrendet, és győződjön meg arról, hogy a kezdeti adatok rendelkezésre állnak a Finance and Operations és a Common Data Service megoldásban is.   

## <a name="vendor"></a>Szállító

A végrehajtási sorrend Szállítóhoz:

```
Vendor Group
    Terms of payment
        Payment day & lines
        Payment schedule
Vendor payment method
```

## <a name="customer-organization"></a>Ügyfél (Szervezet)

A végrehajtási sorrend az ügyfélhez:

```
Customer Group
    Terms of payment
        Payment day & lines
        Payment 
Customer payment method
```

## <a name="contact-person"></a>Kapcsolattartó (személy)

A végrehajtási sorrend a Kapcsolattartóhoz:

```
Customer
Vendor               
```
