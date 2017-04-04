---
title: "Továbbfejlesztett banki egyeztetés áttekintés"
description: "A cikk a továbbfejlesztett banki egyeztetés folyamatát ismerteti. A továbbfejlesztett banki egyeztetési funkcióval importálhatja a banki tranzakciókból automatikusan egyeztethető banki kivonatokat."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 22104
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 00f022da597b1de2454e93123de31731c6a65962
ms.openlocfilehash: 20363ef1917f7d0796cb0d5cd8e623c598b5ee01
ms.lasthandoff: 03/31/2017


---

# <a name="advanced-bank-reconciliation-overview"></a>Továbbfejlesztett banki egyeztetés áttekintés

A cikk a továbbfejlesztett banki egyeztetés folyamatát ismerteti. A továbbfejlesztett banki egyeztetési funkcióval importálhatja a banki tranzakciókból automatikusan egyeztethető banki kivonatokat.

A továbbfejlesztett banki egyeztetés szolgáltatás lehetővé teszi a banki kivonatok importálását. Az importált banki kivonatot ezután automatikusan lehet egyeztetni, a banki tranzakciókon belül. A lépések a következők a továbbfejlesztett banki egyeztetés folyamatban.

1.  Banki kivonat importálásának beállítása.
    -   Banki kivonatok importálása az adatentitás keretrendszeren keresztül.
    -   Három jellemző banki kivonatformátum be vannak építve: ISO20022, BAI2 és MT940.
    -   A funkciót minden formátumba ki lehet terjeszteni.

2.  Állítsa be a továbbfejlesztett banki egyeztetés során használandó számsorozatot, és állítsa be a banki egyeztetési szabályokat.
    -   Egy egyeztetési szabály egy banki kivonat sorainak és a Microsoft Dynamics 365 banki műveletek tranzakciósorok szűrése az egyeztetés során használt feltételek. Attól függően, hogy a vállalati gyakorlat állíthat be egynél több egyeztetési szabály automatizálásához és az egyeztetési folyamat optimalizálása.

3.  Műveletek banki tranzakciókhoz a Dynamics 365 bankszámlakivonatok egyeztetése.
    -   Automatikus egyeztetés végrehajtása és egyeztetési napló létrehozása.
    -   Bankszámlakivonatok megtekintése és műveletek banki tranzakciók egymás Dynamics 365.
    -   Műveletek banki tranzakciók feladása a Dynamics 365 automatikusan Ha jelenik meg a bankszámlakivonaton, de a Dynamics 365 műveletekhez nem jelennek meg.
    -   Egyeztetési kivonat létrehozása.




