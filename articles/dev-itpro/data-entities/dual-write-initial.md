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
ms.openlocfilehash: 1473c3bad55734d5f83ee3e4c1654921b872f3bb
ms.sourcegitcommit: 3f05ede8b8acdf0550240a83a013e093b4ad043d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/13/2019
ms.locfileid: "1873128"
---
# <a name="execution-order-for-initial-synchronization-of-finance-and-operations-and-common-data-service"></a>Végrehajtási sorrend a Finance and Operations és a Common Data Service kezdeti szinkronizálásához

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Az adatintegráció használata előtt létre kell hoznia a vevők, szállítók és kapcsolattartók számára szükséges kezdeti adatokat. Például hozzon létre egy új **Szállítói csoport** elemet, és adja meg a **fizetési feltételek** értékét a **Net30** értékre. Ebben az esetben a **Szállítói csoport** elemének létrehozása előtt meg kell győződni arról, hogy **a Net30** mind a Microsoft Dynamics 365 for Finance and Operations mind a Common Data Service megoldásokban létezik. (Jövőben, a Microsoft kiad egy kettős írási funkciót, amelynek neve Kezdeti szinkronizálás lesz. Ez a funkció egy egyszeri adatszinkronizálást fog végezni a Finance and Operations és a Common Data Service között a kettős írás beállításának részeként.)

> [!TIP]
> A Microsoft kias kettős írású leképezést minden referenciaadathoz beleértve a **Fizetési feltételek** (Fizetési feltételek) elemhez. Ha már rendelkezik a kezdeti adatokkal az egyik rendszerben, a rekordon végzett kis frissítési művelet elindíthatja a kettős írást az adott rekordra vonatkozóan.

Kövesse az alábbi sorrendet, és győződjön meg arról, hogy a kezdeti adatok rendelkezésre állnak a Finance and Operations és a Common Data Service megoldásban is.

## <a name="vendor"></a>Szállító

A **Szállító** entitás végrehajtásának sorrendje:

1. Szállítói csoport

    1. Fizetési feltételek

        1. Fizetési nap és sorok
        2. Fizetési ütemezés

2. Szállítói fizetési mód

## <a name="customer-organization"></a>Ügyfél (Szervezet)

Az **Ügyfél** entitás végrehajtásának sorrendje:

1. Vevőcsoport

    1. Fizetési feltételek

        1. Fizetési nap és sorok
        2. Fizetés 

2. Vevő fizetési módszere

## <a name="contact-person"></a>Kapcsolattartó (személy)

A **Kapcsolattartó** entitás végrehajtásának sorrendje:

1. Vevő
2. Szállító
