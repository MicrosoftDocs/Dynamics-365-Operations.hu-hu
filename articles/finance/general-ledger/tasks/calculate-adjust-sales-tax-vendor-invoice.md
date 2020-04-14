---
title: Szállítói számla áfatartalmának kiszámítása és kiigazítása
description: Ez a témakör bemutatja, hogyan lehet helyesbíteni az áfát egy szállítói számlán a Dynamics 365 Finance alkalmazásban.
author: twheeloc
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendInvoice, VendTableLookup, TaxTmpWorkTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2f3521f7bc56659fc6f7a6d47f581ddbfea16523
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3139967"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a>Szállítói számla áfatartalmának kiszámítása és kiigazítása

[!include [banner](../../includes/banner.md)]

Ez a témakör bemutatja, hogyan lehet helyesbíteni az áfát egy szállítói számlán. Ha az eredeti forrásbizonylat eltérő adóösszegeket jelenít meg számítva, akkor feladás előtt ezeket az összegeket módosíthatja. Ez a feladat az DEMF bemutatócéget használja.

1. Anavigációs ablaktáblán válassza a **Modulok > Kötelezettségek > számlák > Számlanapló** elemre.
2. Válassza az **Új** lehetőséget.
3. Az új sor **Név** mezőjében válasszon egy lehetőséget a legördülő menüből.
4. A Műveleti ablaktáblán válassza a **Sorok** elemet.
5. A **Számla** mezőben adja meg a kívánt értékeket.
6. Írjon be egy értéket a **Számla** mezőbe.
7. A **Hitelkeret** mezőben adjon meg egy számot.
8. Az **Ellenszámla** mezőben adja meg a kívánt értékeket.
9. Válassza az **Áfa** lehetőséget.
10. A **Teljes tényleges áfaösszeg** mezőbe írjon be egy számot.
11. A **Helyesbítés** lapon az áfaösszegek az áfakód szerint helyesbíthetők.
12. Válassza a **Tényleges visszaállítása a számított értékekből** lehetőséget.
13. Válassza ki az **OK** lehetőséget.
14. Válassza a **Mentés** lehetőséget.

