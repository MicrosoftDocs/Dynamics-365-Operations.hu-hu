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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: c06dfa697e3e0eab7a7f4183da9f178af818a6d7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206160"
---
# <a name="hide-non-carrier-delivery-modes-from-the-shipping-options-in-pos"></a>A Pénztár nem szállítói kiszállítási módjainak elrejtése


[!include [banner](includes/banner.md)]

Ez a témakör egy olyan konfigurációs beállítást tartalmaz, amely elérhető a pénztár (POS) alkalmazás számára. Ez a beállítási lehetőség megváltoztatja a szállítási mód kiválasztásának működését, ha a kiszállítási rendeléseket a pénztárban hozzák létre.

Amikor a felhasználók vevői szállítási rendeléseket hoznak létre a pénztárban, ki tudják választani a szállítmány szállítási módját. Ez a funkció elérhető attól függetlenül, hogy a teljes rendelést leszállítják, vagy csak a kiválasztott sorokat.

Alapértelmezés szerint az a párbeszédpanel, amelyen a szállítási mód be kiválasztható, az összes érvényes szállítási módot megmutatja egy csatorna, egy tétel és egy szállítási cím kombinációja számára. Ezeket a szállítási módokat a **Szállítási módok** oldalon a Központban (**Értékesítési és marketing \> Beállítás \> Elosztás \> Kiszállítási módok**) határozzák meg. A „nem szállítmányozó” szállítási módok (például **Carryout** vagy **Felvétel**) is megjelenhetnek a párbeszédpanelem kiválasztásra.

Egy olyan funkció lett azonban hozzáadva, amely lehetővé teszi a nem szállítmányozói szállítási módok elrejtését a párbeszédpanelen. Ha be kívánja kapcsolni ezt a funkciót, akkor a **Commerce paraméterek** oldalon a **Vevői rendelések** lapon állítsa be, hogy a **Csak szállítmányozói módbeállítások megjelenítése kiszállítási rendelésekhez** beállítást **Igen** értékre. Miután bekapcsolta ezt a funkciót, és futtatja a megfelelő elosztási feladatokat a csatorna-adatbázisba történő szinkronizáláshoz, nem fognak megjelenni a nem szállítmányozó szállítási módok a kiválasztáshoz a pénztári szállítmányok létrehozási folyamata során.


[!INCLUDE[footer-include](../includes/footer-banner.md)]