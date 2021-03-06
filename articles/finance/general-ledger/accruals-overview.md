---
title: Könyvelések áttekintése
description: A cikk leírást ad a könyveléseket illetően és információt biztosít azok beállításairól és a tranzakciók létrehozásáról.
author: aprilolson
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerAccuralTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 14131
ms.assetid: 0489b59a-37a7-4a78-87bf-4b597e9efad9
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a441828cb7db9b5346ecf086e8be0b2c3a20029a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823812"
---
# <a name="accruals-overview"></a>Könyvelések áttekintése

[!include [banner](../includes/banner.md)]

A cikk leírást ad a könyveléseket illetően és információt biztosít azok beállításairól és a tranzakciók létrehozásáról.

Könyvelések az elhatárolásban használtak, az olyan bevétel követésére, amelyet a megkeresési időszakban ismertek fel, nem a bevételezési időszakhoz, és kiadások (költségek) követésére, amelyeket akkor ismertek fel, amikor megjelentek, nem amikor a fizetés megtörtént.

## <a name="accrual-schemes"></a>Könyvelési sémák
Könyvelési sémák a halasztott bevételek és költségek beállítására szolgálnak, és ugyanaz a könyvelési séma használható bevételekre és a költségekre is. A főkönyvi könyvelések során újra elosztják a naplósorok költségeit és a bevételt, hogy a költségek és bevételek a megfelelő időszakban legyenek elismerve. Az a **Könyvelési séma** lapon megadhatja, a terhelési és a követel számlákat, amelyek a könyvelési séma alkalmazásakor használandóak.

-   **Terhelés** – A fő számla, amelyet megad lecseréli a terhelési fő számlát a naplóbizonylat soron. A sztornírozás halasztására ez a számla lesz használva, a főkönyvi könyvelési tranzakciók alapján.
-   **Követelés** – a fő számla, amelyet megad lecseréli a követelési fő számlát a naplóbizonylat soron. A sztornírozás halasztására ez a számla lesz használva, a főkönyvi könyvelési tranzakciók alapján.

Miután meghatározhatja, hogy milyen számlákat használjon, megadhatja, hogyan jöjjön létre a bizonylatszám, a könyvelési tranzakciók létrehozásakor. Ezen kívül megadhatja, hogy milyen gyakran fordulnak elő a tranzakciók, a tranzakciók létrehozásának számát, és a tranzakciók feladásának számát. A könyvelési séma létrehozása után használhatja azt egyes naplókban, a Főkönyvi könyvelések funkció használatával.

## <a name="ledger-accruals"></a>Főkönyvi könyvelések
Amikor beír egy naplót, kattintson **Főkönyvi könyvelések** a **Funkciók** menüben. Ezután a könyvelési séma kiválasztásakor megjelenik az alapösszeg, a könyvelési séma által meghatározott időszakban terjedő naplóból. Például ha januárban az egész évre kifizeti az alkalmazott biztosítását, és az összeg 12 000, a költséget minden hónapban realizálni kell. A kezdő dátumot kiválaszthatja. Megadhatja azt is, hogy számla vagy az ellenszámla a könyvelt összeg alapja. Miután végrehajtotta a kívánt beállításokat, kattintson a **Tranzakciók** elemre a könyvelési séma alapján létrehozott összes tranzakció megtekintéséhez. Például ha a 12 000-et biztosítási költségként osztotta el az év folyamán, minden hónapnál 1000 jelenik meg. A napló feladása után a tranzakciók megtekintéséhez használja a **Bizonylattranzakciók** lekérdezési oldalt. Ha nem lehet használni a könyvelési sémát (például egy értékesítési rendelési számla vagy a beszerzési rendelési számla érintett), jóváírhatja az előre fizetett összeget és terhelheti a költségösszeget. Ezután kiválaszthatja az **Ellenszámla** lehetőséget a könyvelési séma alkalmazásakor.


További tudnivalókért lásd: [Könyvelési sémák létrehozása](tasks/create-accrual-schemes.md) és [Főkönyvi könyvelés tranzakcióinak létrehozása](tasks/create-ledger-accrual-transactions.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]