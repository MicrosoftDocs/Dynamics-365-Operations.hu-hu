---
title: Adóelőleg az értékesítési tranzakciókban
description: Ez a cikk a kiválasztott vevők adóelőleg-számításának elkerülésére vonatkozó lépéseket sorolja fel. Azon vevők esetében, akik a kifizetéseikben adóelőleget határoznak meg, hozzárendelheti az alapértelmezett adóelőleg-csoportot.
author: kailiang
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 75a7fc62c1d493007f3aa88a723465828c557df7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8910084"
---
# <a name="withholding-tax-in-sales-transactions"></a>Adóelőleg az értékesítési tranzakciókban

Ez a cikk a kiválasztott vevők adóelőleg-számításának elkerülésére vonatkozó lépéseket sorolja fel. Azon vevők esetében, akik a kifizetéseikben adóelőleget határoznak meg, hozzárendelheti az alapértelmezett **Adóelőleg-csoport** lehetőséget a **Vevők** oldalon. 

1. Lépjen a **Navigáció ablaktábla > Modulok > Kintlévőségek > Ügyfelek > Minden ügyfél** lehetőségre.

2. Kattintson a megfelelő vevői számlára, és válassza a **Szerkesztés** gombot.

3. A **Számlázás és szállítás** lapon állítsa az **Adóelőleg számítása** mezőt **Igen** értékre.

   > [!NOTE] 
   > Az adóelőleg számítása nem történik meg, ha a törzsadatokban erre a vevőre vonatkozóan nincs bekapcsolva az **Adóelőleg számítása** lehetőség.

4. Válasszon egy adóelőleg-csoportot az **Adóelőleg-csoport** pontban.

5. Kattintson a **Mentés** gombra.

Az adóelőleg-köteles cikkekhez/szolgáltatásokhoz hozzárendelheti a **Kiadott termékek** alapértelmezett **Cikk adóelőleg-csoport** funkciót.

1. Kattintson ide: **Navigációs ablaktábla > Modulok > Termékinformációk kezelése > Termékek > Kiadott termékek**.

2. Kattintson a megfelelő Cikkszámra, és válassza a **Szerkesztés** gombot.

3. Az **Értékesítés** lapon kattintson az **Adóelőleg számítása** elemre.

   > [!NOTE] 
   > Az adóelőleg számítása nem történik meg, ha az **Adóelőleg számítása** nem **Igen** értékre van beállítva ehhez a cikkhez a **Kiadott termék** oldal **Értékesítés** lapján.

4. Válasszon egy Cikk adóelőleg-csoportot a **Cikk-adóelőlegek csoportja** listában.

5. Kattintson a **Mentés** gombra.

Az adóelőleg-csoportok és cikk adóelőleg-csoportok az **Értékesítési rendelés** oldalon rendelhetők hozzá: 

Új értékesítési rendelés létrehozásakor az alapértelmezett adóelőleg-csoport és cikk adóelőleg-csoport lesz az értékesítésirendelés-sorok alapértelmezett bejegyzése.

Az adóelőleg számítása és feladása a **Vevői kifizetési napló** alapján történik. Az alkalmazandó adóelőlegkódot és a tényleges adóelőleg-összeget manuálisan módosíthatja a **Tranzakciók kiegyenlítése** oldal **Adóelőleg** lapján.

A kiszámított adóelőleg összege le lesz vonva a vevői kifizetésből, és a rendszer feladja az **Adóelőleg ellenszámla** számlához egy kapcsolódó bizonylaton.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
