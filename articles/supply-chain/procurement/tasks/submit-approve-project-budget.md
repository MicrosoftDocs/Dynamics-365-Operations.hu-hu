---
title: Projekt-költségvetési munkafolyamat létrehozása és elküldése
description: Ez az eljárás bemutatja, hogyan hozhatja létre és nyújthatja be a költségvetést a projekthez.
author: GalynaFedorova
ms.date: 11/22/2021
ms.topic: article
ms.search.form: ProjProjectsListPage, ProjTable, ProjBudget, WorkflowSubmitDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e554fb578371f52f665ef348d6fa81fd27196a9e
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671028"
---
# <a name="create-and-submit-a-project-budget-workflow"></a>Projekt-költségvetési munkafolyamat létrehozása és elküldése

[!include [banner](../../includes/banner.md)]

Projektköltségvetés létrehozásakor megadhatja a projekt becsült bevételeit és költségeit, és az értékekkel szabályozhatja a tényleges projekttranzakciókat. A projekt költségvetéséhez az összes eredeti költségvetésnek és verziónak végig kell mennie egy projekt-munkafolyamaton jóváhagyásra. A munkafolyamat növeli a költségvetés fölötti ellenőrzést, és módosítási előzményrekordot hoz létre. A projekt [létrehozása után](/dynamicsax-2012/appuser-itpro/create-a-project) a következő eljárás szerint hozhatja létre és küldheti el a költségvetést.

1. Ugrás a **ModulesProject** > **management and accountingProjectsAll** > **·** > **projektekhez**.
1. A projektlistáról válassza ki a projektet.
1. A projekt részletes lapján válassza a Terv **lapot**.
1. A Költségvetés **csoportban** válassza a Projekt költségvetése **lehetőséget**.
1. Adja meg a következő adatokat az **Általános** gyorslapon:
   - A Leírás **mezőbe** írjon be egy értéket.
   - Válassza ki a lehetőséget az eredeti **költségvetéshez**.
   - Válassza a fennmaradó költségvetés **beállítását**.
1. Bontsa ki **a Költségek** gyorsét, és válassza az Új **lehetőséget**. Ezután állítsa be a következő beállításokat:
   - Válassza ki a tranzakciótípus **beállítását**.
   - Válasszon egy megfelelő **kategóriát**.
   - Írjon be egy értéket az eredeti **költségvetésbe**.
1. Bontsa ki **a Bevételek** gyorsét, és válassza az Új **lehetőséget**. Ezután állítsa be a következő beállításokat:
   - Válassza ki a tranzakciótípus **beállítását**.
   - Válasszon egy **kategóriát**.
   - Adja meg az eredeti költségvetés **értékét**.
1. Válassza a **Mentés** lehetőséget.
1. Munkafolyamat **küldésének \> kiválasztása**
1. Az Eredeti költségvetési **munkafolyamat áttekintése - Küldés** lapon írjon be egy megjegyzést, és válassza a **Küldés** **lehetőséget**.
