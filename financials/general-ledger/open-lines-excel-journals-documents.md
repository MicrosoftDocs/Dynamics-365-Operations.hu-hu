---
title: "Naplósorok és dokumentumok közzététele Excelből"
description: "Ez a témakör bemutatja, hogyan adhat meg és tehet közzé főkönyvinaplók-sorokat Microsoft Excelből. A megadott tranzakciók típusától függően használható különböző sablonokkal kapcsolatos információkat is tartalmaz."
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62213
ms.assetid: 211874a7-4bf0-4a0c-96c2-fa05042777d3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ef99caf4570969d2b920cec8b53669ce2094965
ms.openlocfilehash: 087339cb3002b42bcb985c2ccfc2d97c752a817c
ms.lasthandoff: 03/31/2017


---

# <a name="publish-journal-lines-and-documents-from-excel"></a>Naplósorok és dokumentumok közzététele Excelből

Ez a témakör bemutatja, hogyan adhat meg és tehet közzé főkönyvinaplók-sorokat Microsoft Excelből. A megadott tranzakciók típusától függően használható különböző sablonokkal kapcsolatos információkat is tartalmaz.

A felhasználók Microsoft Excelből adhatnak meg és tehetnek közzé sorokat pénzügyi naplókhoz. Miután egy felhasználó létrehoz egy naplót, a rendelkezésre álló sablonokban megjelenik a **Sorok megnyitása az Excel programban** gomb. A sablonokat konkrét esetek támogatására tervezték; nem minden számlatípus kombinációja támogatott a naplóban . A következő táblázat bemutatja a rendelkezésre álló sablonokat és az általuk támogatott számlatípusokat.
|                          |                                                                                                                         |                                                                                         |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| **Sablon**             | **Támogatott számlatípusok**                                                                                             | **Hogyan érhető el a sablon**                                                          |
| Főkönyvi naplósorok     | Számola: főkönyvi, vevői, szállítói, banki ellenszámla: főkönyvi, vevői, szállítói, banki vállalatközi támogatott.       | Általános napló                                                                         |
| Számlajegyzék         | Számla: Szállítói ellenszámla: a főkönyvi vállalatközi nem támogatott.                                                    | Szállítói számlajegyzék                                                                     |
| Számlanapló          | Számlák: Szállítói ellenszámla: a főkönyvi vállalatközi támogatott.                                                      | Kötelezettségszámla-napló                                                                      |
| Szállítói számla           |                                                                                                                         | Szállítói számla                                                                          |
| Vevői számlanapló | Számlák: Vevői ellenszámla: a főkönyvi vállalatközi támogatott.                                                     | Általános napló                                                                         |
| Szabadszöveges számla        |                                                                                                                         | A **Szabadszöveges számla** oldalon kattintson a **Megnyitás az Excel programban** elemre (a Microsoft Office-ikonra). |
| Tárgyi eszközök naplója     | Eszköz főkönyvbe, bankhoz, vevőhöz vagy szállítóhoz. A vállalatközi nem támogatott.                                               | Tárgyieszköz-napló                                                                     |
| Szállító kifizetési naplója   | Számla: Szállítói ellenszámla: Főkönyvi, banki vállalatközi támogatott.                                                 | Szállító kifizetési naplója                                                                  |
| Vevő kifizetési naplója | Számlák: Vevői ellenszámla: Főkönyvi, Banki vállalatközi támogatott.                                               | Vevő kifizetési naplója                                                                |
| Projektköltségnapló  | Számola: projekt, főkönyvi, vevői, szállítói ellenszámla: projekt, főkönyvi, vevői, szállítói vállalatközi támogatott. | Főkönyvinapló-kiadás (a projektvezetés és könyvelés részben)                       |

A sorok közzétételkor ellenőrzésre kerülnek annak érdekében, hogy biztosan megfeleljenek a pénzügyi naplókban beállított szabályoknak. A sorok közzététele után a felhasználók szerkeszthetik vagy feladhatják a bizonylatokat a Microsoft Dynamics 365 for Operationsből. 

Pénzügyi dimenziók sablonhoz történő hozzáadásához további módosításokra szükség. További információkért lásd: [Dimenziók hozzáadása Microsoft Excel-sablonhoz](\dev-itpro\financial-dimensions\add-dimensions-excel-templates). Dimenziók az entitáshoz való hozzáadása után érhetővé válnak az Excel-tervezőben és hozzá lehet adni őket a sablonhoz.




