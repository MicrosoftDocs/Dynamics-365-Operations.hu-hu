---
title: "Naplósorok és az Excel dokumentumok közzététele"
description: "Ez a témakör bemutatja, hogyan adhatja meg, és tegye közzé a Microsoft Excel a főkönyvi naplók sorai. A használt, adta meg tranzakciók típusától függően különböző sablonokat kapcsolatos információkat tartalmaz."
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

# <a name="publish-journal-lines-and-documents-from-excel"></a>Naplósorok és az Excel dokumentumok közzététele

Ez a témakör bemutatja, hogyan adhatja meg, és tegye közzé a Microsoft Excel a főkönyvi naplók sorai. A használt, adta meg tranzakciók típusától függően különböző sablonokat kapcsolatos információkat tartalmaz.

A felhasználók megadása és pénzügyi naplókhoz, a Microsoft Excel sorok közzététele. Miután egy felhasználó létrehoz egy naplót, a **az Excel programban nyissa meg a sorok** gomb megjeleníti a rendelkezésre álló sablonok. Sablonok adott esetben azonban nem minden számlatípust kombinációját támogatja a naplóban támogatására tervezték. A következő táblázat a rendelkezésre álló sablonok és a számlatípusokat, amelyeket támogattak.
|                          |                                                                                                                         |                                                                                         |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| **Template**             | **Támogatott típusok**                                                                                             | **Hogyan érhető el a sablon**                                                          |
| Főkönyvi naplósorok     | Fiók: Főkönyvi, vevői, szállítói, Bank eltolás fiók: főkönyvi, vevői, szállítói, Bank vállalatközi támogatott.       | Általános napló                                                                         |
| Számlajegyzék         | Számla: Szállítói ellenszámla: a vállalatközi főkönyvi nem támogatja.                                                    | Számlaregiszter AP                                                                     |
| Számlanapló          | Fiókok: Szállítói ellenszámla: a vállalatközi főkönyvi rendszer támogatja.                                                      | Kötelezettségszámla-napló                                                                      |
| Szállítói számla           |                                                                                                                         | Szállítói számla                                                                          |
| Vevői számlanapló | Számla: Vevő ellenszámla: a vállalatközi főkönyvi rendszer támogatja.                                                     | Általános napló                                                                         |
| Szabadszöveges számla        |                                                                                                                         | A a **szabadszöveges számla** lap **az Excel programban megnyitott** (a Microsoft Office ikon). |
| Tárgyi eszközök naplója     | Főkönyvi, banki, vevő vagy szállító eszköz. Vállalatközi nem támogatja.                                               | Tárgyieszköz-napló                                                                     |
| Szállító kifizetési naplója   | Számla: Szállítói ellenszámla: vállalatközi főkönyvi, banki támogatott.                                                 | Szállító kifizetési naplója                                                                  |
| Vevő kifizetési naplója | Számla: Vevő ellenszámla: vállalatközi főkönyvi, banki támogatott.                                               | Vevő kifizetési naplója                                                                |
| Projektköltségnapló  | Fiók: Projekt főkönyvi, vevő, szállító eltolás fiók: projekt, főkönyvi, vevői, szállítói vállalatközi támogatott. | Főkönyvi napló kiadás (a projektvezetés és könyvelés)                       |

A sorok közzétételét követően azok validálását, győződjön meg arról, hogy azok megfelelnek a szabályokat, amelyek a pénzügyi naplók állíthatók be. Után a sorok közzétett, a felhasználók szerkeszthetik vagy a Microsoft Dynamics 365 műveletek feladása. 

Pénzügyi dimenziók sablon hozzáadásához további módosításokra szükség. További információkért lásd: [dimenziók hozzáadása a Microsoft Excel-sablon](\dev-itpro\financial-dimensions\add-dimensions-excel-templates). Dimenziók hozzáadódnak az entitás, miután érhetők el az Excel-tervezőben, és hozzá lehet adni a sablont.




