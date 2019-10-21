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
ms.openlocfilehash: a68e0df78516875168d977f78adf023887b2362d
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186279"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a>Szállítói számla áfatartalmának kiszámítása és kiigazítása

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

