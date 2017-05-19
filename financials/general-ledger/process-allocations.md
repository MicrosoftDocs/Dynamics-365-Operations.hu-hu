---
title: "Felosztások feldolgozása"
description: "A cikk tájékoztatást nyújt a felosztásokról, a Microsoft Dynamics 365 for Operations rendszerben történő feldolgozásukról és arról, hogy hogyan alkalmazzuk őket a költségvetési tervben. A felosztások segítségével összegeket oszthat fel több főkönyvi számla kombináció között. Ezek garantáljak azt, hogy a költségek vagy a bevételek a megfelelő objektumot terhelik a könyvelés során."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: f66414beeacafdbbe3b6f7bcba8481096636e025
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="process-allocations"></a>Felosztások feldolgozása

[!include[banner](../includes/banner.md)]


A cikk tájékoztatást nyújt a felosztásokról, a Microsoft Dynamics 365 for Operations rendszerben történő feldolgozásukról és arról, hogy hogyan alkalmazzuk őket a költségvetési tervben. A felosztások segítségével összegeket oszthat fel több főkönyvi számla kombináció között. Ezek garantáljak azt, hogy a költségek vagy a bevételek a megfelelő objektumot terhelik a könyvelés során.

A Microsoft Dynamics 365 for Operations a folyamat támogatásához az alábbi funkciókat biztosítja:

-   Manuálisan is lefoglalhatók tranzakcióösszegek a Felosztás művelettel a könyvelési felosztás pontban, vagy pénzügyi dimenzió alapértelmezett sablonjainak használatával egy dokumentumre. További tudnivalókért lásd: [Könyvelési felosztások.](../accounts-payable/accounting-distributions.md)
-   Tranzakcióösszegek automatikus felosztása az egyes fő számlán megadott felosztási feltételek alapján. Felosztási számlabejegyzések generálódnak minden naplóhoz, a százalék és a főkönyvi célszámla alapján, amikor egy számlázási bejegyzés megfelel a forrás főkönyvi számlában megadott feltételeknek.
-   főkönyvi egyenlegek, vagy fix összegek automatikus felosztása a főkönyvi felosztási szabályok alapján. A főkönyvi felosztási szabályok feldolgozása rendszeres időközönként történik, felosztási naplók használatával. 

###  <a name="allocations-in-budget-planning"></a>Felosztások a költségvetési tervezésben

Főkönyvi felosztási szabályok a költségvetési tervekhez is használhatóak. Főkönyvi felosztási szabályok használatakor a költségvetés-tervezési felosztási szabályok munka a ugyanúgy, ahogy az a főkönyvben, de a forrásadatok, és a cél adatainak a költségvetési terv származik. Kezdődő a Főkönyvi felosztási szabályok költségvetési tervek. Másik lehetőségként használhatja a munkafolyamatok részeként futó egy felosztási ütemezés.

> [!NOTE]
> Kezdődő   , használhatja a Főkönyvi felosztási szabályok költségvetési tervek.






