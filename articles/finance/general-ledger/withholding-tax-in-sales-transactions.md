---
title: Adóelőleg az értékesítési tranzakciókban
description: Ez a témakör a kiválasztott vevők adóelőleg-számításának elkerülésére vonatkozó lépéseket sorolja fel. Azon vevők esetében, akik a kifizetéseikben adóelőleget határoznak meg, hozzárendelheti az alapértelmezett adóelőleg-csoportot.
author: roschlom
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 8e11ce10faa9b450b6f36a856b34b06b4ee1838d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842344"
---
# <a name="withholding-tax-in-sales-transactions"></a>Adóelőleg az értékesítési tranzakciókban

Ez a témakör a kiválasztott vevők adóelőleg-számításának elkerülésére vonatkozó lépéseket sorolja fel. Azon vevők esetében, akik a kifizetéseikben adóelőleget határoznak meg, hozzárendelheti az alapértelmezett **Adóelőleg-csoport** lehetőséget a **Vevők** oldalon. 

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