---
title: A Pénztár nem szállítói kiszállítási módjainak elrejtése
description: Ez a témakör egy olyan konfigurációs beállítást tartalmaz, amellyel megakadályozhatja, hogy a nem szállítmányozói szállítási módok megjelenjenek a kiválasztásra ha a szállítási rendelések létrehozása a pénztár (POS) alkalmazásban történik.
author: hhainesms
manager: annbe
ms.date: 10/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhainesms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 09ea83b3336b208f8af0a91025c2e6c50d64c385
ms.sourcegitcommit: 574309903f15eeab7911091114885b5c7279d22a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/24/2019
ms.locfileid: "2659021"
---
# <a name="hide-non-carrier-delivery-modes-from-the-shipping-options-in-pos"></a>A Pénztár nem szállítói kiszállítási módjainak elrejtése

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör egy olyan konfigurációs beállítást tartalmaz, amely elérhető a pénztár (POS) alkalmazás számára. Ez a beállítási lehetőség megváltoztatja a szállítási mód kiválasztásának működését, ha a kiszállítási rendeléseket a pénztárban hozzák létre.

Amikor a felhasználók vevői szállítási rendeléseket hoznak létre a pénztárban, ki tudják választani a szállítmány szállítási módját. Ez a funkció elérhető attól függetlenül, hogy a teljes rendelést leszállítják, vagy csak a kiválasztott sorokat.

Alapértelmezés szerint az a párbeszédpanel, amelyen a szállítási mód be kiválasztható, az összes érvényes szállítási módot megmutatja egy csatorna, egy tétel és egy szállítási cím kombinációja számára. Ezeket a szállítási módokat a **Szállítási módok** oldalon a Retail Headquarters helyen (**Értékesítési és marketing \> Beállítás \> Elosztás \> Kiszállítási módok**) határozzák meg. A „nem szállítmányozó” szállítási módok (például **Carryout** vagy **Felvétel**) is megjelenhetnek a párbeszédpanelem kiválasztásra.

Egy olyan funkció lett azonban hozzáadva, amely lehetővé teszi a nem szállítmányozói szállítási módok elrejtését a párbeszédpanelen. Ha be kívánja kapcsolni ezt a funkciót, akkor a **Vevői paraméterek** oldalon a **Vevői rendelések** lapon állítsa be, hogy a **Csak szállítmányozói módbeállításai megjelenítése kiszállítási rendelésekhez** beállítást **Igen** értékre. Miután bekapcsolta ezt a funkciót, és futtatja a megfelelő elosztási feladatokat a csatorna-adatbázisba történő szinkronizáláshoz, nem fognak megjelenni a nem szállítmányozó szállítási módok a kiválasztáshoz a pénztári szállítmányok létrehozási folyamata során.
