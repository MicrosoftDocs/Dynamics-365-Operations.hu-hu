---
title: Felosztások feldolgozása
description: A cikk tájékoztatást nyújt a felosztásokról, azok Microsoft Dynamics 365 for Finance and Operations rendszerben történő feldolgozásukról és arról, hogy hogyan alkalmazzuk őket a költségvetési tervben. A felosztások segítségével összegeket oszthat fel több főkönyvi számla kombináció között. Ezek garantáljak azt, hogy a költségek vagy a bevételek a megfelelő objektumot terhelik a könyvelés során.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9a1946875460e9dfafb481b288a6d6a10ba8931d
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846799"
---
# <a name="process-allocations"></a>Felosztások feldolgozása

[!include [banner](../includes/banner.md)]

A cikk tájékoztatást nyújt a felosztásokról, azok Microsoft Dynamics 365 for Finance and Operations rendszerben történő feldolgozásukról és arról, hogy hogyan alkalmazzuk őket a költségvetési tervben. A felosztások segítségével összegeket oszthat fel több főkönyvi számla kombináció között. Ezek garantáljak azt, hogy a költségek vagy a bevételek a megfelelő objektumot terhelik a könyvelés során.

A Microsoft Dynamics 365 for Finance and Operations a folyamat támogatásához az alábbi funkciókat biztosítja:

-   Manuálisan is lefoglalhatók tranzakcióösszegek a Felosztás művelettel a könyvelési felosztás pontban, vagy pénzügyi dimenzió alapértelmezett sablonjainak használatával egy dokumentumre. További tudnivalókért lásd: [Könyvelési felosztások.](../accounts-payable/accounting-distributions.md)
-   Tranzakcióösszegek automatikus felosztása az egyes fő számlán megadott felosztási feltételek alapján. Felosztási számlabejegyzések generálódnak minden naplóhoz, a százalék és a főkönyvi célszámla alapján, amikor egy számlázási bejegyzés megfelel a forrás főkönyvi számlában megadott feltételeknek.
-   főkönyvi egyenlegek, vagy fix összegek automatikus felosztása a főkönyvi felosztási szabályok alapján. A főkönyvi felosztási szabályok feldolgozása rendszeres időközönként történik, felosztási naplók használatával. 

###  <a name="allocations-in-budget-planning"></a>Felosztások a költségvetési tervezésben

Főkönyvi felosztási szabályok a költségvetési tervekhez is használhatóak. Főkönyvi felosztási szabályok használatakor a költségvetés-tervezési felosztási szabályok munka a ugyanúgy, ahogy az a főkönyvben, de a forrásadatok, és a cél adatainak a költségvetési terv származik. Kezdődő a Főkönyvi felosztási szabályok költségvetési tervek. Másik lehetőségként használhatja a munkafolyamatok részeként futó egy felosztási ütemezés.

> [!NOTE]
> Kezdődő   , használhatja a Főkönyvi felosztási szabályok költségvetési tervek.





