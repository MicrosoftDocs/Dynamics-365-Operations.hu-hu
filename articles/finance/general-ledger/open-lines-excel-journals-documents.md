---
title: Naplósorok és dokumentumok közzététele Excelből
description: Ez a cikk bemutatja, hogy hogyan lehet az általános naplók sorait beírni és közzétenni Microsoft Excel. A megadott tranzakciók típusától függően használható különböző sablonokkal kapcsolatos információkat is tartalmaz.
author: kweekley
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable
audience: Application User
ms.reviewer: kfend
ms.custom: 62213
ms.assetid: 211874a7-4bf0-4a0c-96c2-fa05042777d3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ccb3e7a420f7f048ba93b6fadf5491e312e7ce33
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872470"
---
# <a name="publish-journal-lines-and-documents-from-excel"></a>Naplósorok és dokumentumok közzététele Excelből

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogy hogyan lehet az általános naplók sorait beírni és közzétenni Microsoft Excel. A megadott tranzakciók típusától függően használható különböző sablonokkal kapcsolatos információkat is tartalmaz.

A felhasználók Microsoft Excel alkalmazásból adhatnak meg és tehetnek közzé sorokat pénzügyi naplókhoz. Miután egy felhasználó létrehoz egy naplót, a rendelkezésre álló sablonokban megjelenik a **Sorok megnyitása az Excel programban** gomb. A sablonokat konkrét esetek támogatására tervezték; nem minden számlatípus kombinációja támogatott a naplóban . A következő táblázat bemutatja a rendelkezésre álló sablonokat és az általuk támogatott számlatípusokat.

| Sablon             | Támogatott számlatípusok | Hogyan érhető el a sablon                                                          |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| Főkönyvi naplósorok     | Számola: főkönyvi, vevői, szállítói, banki ellenszámla: főkönyvi, vevői, szállítói, banki vállalatközi támogatott.       | Általános napló                                                                         |
| Számlajegyzék         | Számla: Szállítói ellenszámla: a főkönyvi vállalatközi nem támogatott.                                                    | Szállítói számlajegyzék                                                                     |
| Számlanapló          | Számlák: Szállítói ellenszámla: a főkönyvi vállalatközi támogatott.                                                      | Kötelezettségszámla-napló                                                                      |
| Szállítói számla           |                                                                                                                         | Szállítói számla                                                                          |
| Vevői számlanapló | Számlák: Vevői ellenszámla: a főkönyvi vállalatközi támogatott.                                                     | Általános napló                                                                         |
| Szabadszöveges számla        |                                                                                                                         | A **Szabadszöveges számla** oldalon kattintson a **Megnyitás az Excel** programban elemre (a Microsoft Office ikonra). |
| Tárgyi eszközök naplója     | Eszköz főkönyvbe, bankhoz, vevőhöz vagy szállítóhoz. A vállalatközi nem támogatott.                                               | Tárgyieszköz-napló                                                                     |
| Szállító kifizetési naplója   | Számla: Szállítói ellenszámla: Főkönyvi, banki vállalatközi támogatott.                                                 | Szállító kifizetési naplója                                                                  |
| Vevő kifizetési naplója | Számlák: Vevői ellenszámla: Főkönyvi, Banki vállalatközi támogatott.                                               | Vevő kifizetési naplója                                                                |
| Projektköltségnapló  | Számola: projekt, főkönyvi, vevői, szállítói ellenszámla: projekt, főkönyvi, vevői, szállítói vállalatközi támogatott. | Főkönyvinapló-kiadás (a projektvezetés és könyvelés részben)                       |

A sorok közzétételkor ellenőrzésre kerülnek annak érdekében, hogy biztosan megfeleljenek a pénzügyi naplókban beállított szabályoknak. A sorok közzététele után a felhasználók szerkeszthetik és fel is használhatja a bizonylatokat a Dynamics 365 Pénzügyben. 

Pénzügyi dimenziók sablonhoz történő hozzáadásához további módosításokra szükség. További információkért lásd: [Dimenziók hozzáadása Microsoft Excel sablonhoz](../../fin-ops-core/dev-itpro/financial/add-dimensions-excel-templates.md). Dimenziók az entitáshoz való hozzáadása után érhetővé válnak az Excel-tervezőben és hozzá lehet adni őket a sablonhoz.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
