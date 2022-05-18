---
title: Felosztások feldolgozása
description: Ez a témakör a felosztásokkal, Microsoft Dynamics a 365 Pénzügyben történő feldolgozásuk lehetőségéről és a költségvetés-tervezésben való használhatókról nyújt tájékoztatást. A felosztások segítségével összegeket oszthat fel több főkönyvi számla kombináció között. Ezek garantáljak azt, hogy a költségek vagy a bevételek a megfelelő objektumot terhelik a könyvelés során.
author: kweekley
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: kfend
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d300654269ef0ad52140f160f918707397c843ad
ms.sourcegitcommit: 602a319f4720b39a56b7660b530236912d484391
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/06/2022
ms.locfileid: "8721954"
---
# <a name="process-allocations"></a>Felosztások feldolgozása

[!include [banner](../includes/banner.md)]

A témakör tájékoztatást nyújt a felosztásokról, a rendszerben történő feldolgozásukról és arról, hogy hogyan alkalmazzuk őket a költségvetési tervben. A felosztások segítségével összegeket oszthat fel több főkönyvi számla kombináció között. Ezek garantáljak azt, hogy a költségek vagy a bevételek a megfelelő objektumot terhelik a könyvelés során.

A következő képességek támogatják ezt a folyamatot:

-   Manuálisan is lefoglalhatók tranzakcióösszegek a Felosztás művelettel a könyvelési felosztás pontban, vagy pénzügyi dimenzió alapértelmezett sablonjainak használatával egy dokumentumre. További tudnivalókért lásd: [Könyvelési felosztások.](../accounts-payable/accounting-distributions.md).
-   Tranzakcióösszegek automatikus felosztása az egyes fő számlán megadott felosztási feltételek alapján. Felosztási számlabejegyzések generálódnak minden naplóhoz, a százalék és a főkönyvi célszámla alapján, amikor egy számlázási bejegyzés megfelel a forrás főkönyvi számlában megadott feltételeknek. További információ: [Fő számla felosztási feltételei](../general-ledger/main-account-allocation-terms.md)
-   főkönyvi egyenlegek, vagy fix összegek automatikus felosztása a főkönyvi felosztási szabályok alapján. A főkönyvi felosztási szabályok feldolgozása rendszeres időközönként történik, felosztási naplók használatával. További információ: [Felosztási szabályok](../general-ledger/ledger-allocation-rules.md).

###  <a name="allocations-in-budget-planning"></a>Felosztások a költségvetési tervezésben

Főkönyvi felosztási szabályok a költségvetési tervekhez is használhatóak. Főkönyvi felosztási szabályok használatakor a költségvetés-tervezési felosztási szabályok munka a ugyanúgy, ahogy az a főkönyvben, de a forrásadatok, és a cél adatainak a költségvetési terv származik. Kezdődő a Főkönyvi felosztási szabályok költségvetési tervek. Másik lehetőségként használhatja a munkafolyamatok részeként futó egy felosztási ütemezés.

> [!NOTE]
> Kezdődő   , használhatja a Főkönyvi felosztási szabályok költségvetési tervek.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
