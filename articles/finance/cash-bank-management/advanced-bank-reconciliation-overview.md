---
title: Továbbfejlesztett banki egyeztetés áttekintés
description: A cikk a továbbfejlesztett banki egyeztetés folyamatát ismerteti. A továbbfejlesztett banki egyeztetési funkcióval importálhatja a banki tranzakciókból automatikusan egyeztethető banki kivonatokat.
author: panolte
ms.date: 06/20/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "22104"
- intro-internal
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ebddf6c77df227f896e6f275f741ea69fb68474
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2022
ms.locfileid: "7983592"
---
# <a name="advanced-bank-reconciliation-overview"></a>Továbbfejlesztett banki egyeztetés áttekintés

[!include [banner](../includes/banner.md)]

A cikk a továbbfejlesztett banki egyeztetés folyamatát ismerteti. A továbbfejlesztett banki egyeztetési funkcióval importálhatja a banki tranzakciókból automatikusan egyeztethető banki kivonatokat.

A továbbfejlesztett banki egyeztetés szolgáltatás lehetővé teszi a banki kivonatok importálását. Az importált banki kivonatot ezután automatikusan lehet egyeztetni, a banki tranzakciókon belül. A lépések a következők a továbbfejlesztett banki egyeztetés folyamatban.

1.  Banki kivonat importálásának beállítása.
    -   Banki kivonatok importálása az adatentitás keretrendszeren keresztül.
    -   Három jellemző banki kivonatformátum be vannak építve: ISO20022, BAI2 és MT940.
    -   A funkciót minden formátumba ki lehet terjeszteni.

2.  Állítsa be a továbbfejlesztett banki egyeztetés során használandó számsorozatot, és állítsa be a banki egyeztetési szabályokat.
    -   Az egyeztetési szabály olyan kritériumok készlete, mely a banki kivonat sorainak és a Microsoft Dynamics 365 Finance banki bizonylat sorainak szűrésére szolgálnak az egyeztetési folyamat során. Üzleti gyakorlattól függően egynél több egyeztetési szabályt is beállíthat az egyeztetési folyamat automatizálása és optimalizálása érdekében.

3.  Banki kivonatok egyeztetése a Finance banki tranzakciókkal.
    -   Automatikus egyeztetés végrehajtása és egyeztetési napló létrehozása.
    -   Banki kivonatok és a Finance banki tranzakciók megtekintése egymás mellett.
    -   A Finance banki tranzakciók automatikusan feladása, ha a banki kivonaton megjelennek, de a Finance and Operationsben nem jelennek meg.
    -   Egyeztetési kivonat létrehozása.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]