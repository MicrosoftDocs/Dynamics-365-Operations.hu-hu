---
title: Adóelőleg a beszerzési tranzakciókban
description: Az adóelőleg fizetésére kötelezett szállítók esetén az alapértelmezett **Adóelőleg-csoport** lehetőséget a **Minden szállító** oldalon rendelheti hozzá.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 06997e2d6b47d867e014a7d493d91015c78a5e04
ms.sourcegitcommit: 630a0b3f800f36ced49b79156dd52132904fef75
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2021
ms.locfileid: "5060744"
---
# <a name="withholding-tax-in-purchase-transactions"></a>Adóelőleg a beszerzési tranzakciókban

Az adóelőleg fizetésére kötelezett szállítók esetén az alapértelmezett **Adóelőleg-csoport** lehetőséget a **Minden szállító** oldalon rendelheti hozzá.

1. Lépjen ide: **Navigáció ablaktábla > Modulok > Kötelezettségek > Szállítók > Minden beszállító**.

2. Kattintson a megfelelő Szállítói számlára, és válassza a **Szerkesztés** gombot.

3. A **Számlázás és szállítás** lapon állítsa az **Adóelőleg számítása** mezőt **Igen** értékre.

   > [!NOTE] 
   > Az adóelőleg számítása nem történik meg, ha az adatok között nincs bekapcsolva az **Adóelőleg számítása** lehetőség.

4. Válasszon egy adóelőleg-csoportot az **Adóelőleg-csoport** pontban.

5. Kattintson a **Mentés** gombra.

Az adóelőleg-köteles cikkekhez/szolgáltatásokhoz hozzárendelheti a **Kiadott termékek** alapértelmezett **Cikk adóelőleg-csoport** funkciót.

1. Kattintson ide: **Navigációs ablaktábla > Modulok > Termékinformációk kezelése > Termékek > Kiadott termékek**.

2. Kattintson a megfelelő Cikkszámra, és válassza a **Szerkesztés** gombot.

3. A **Beszerzés** lapon kattintson az **Adóelőleg számítása** elemre.

   > [!NOTE] 
   > Az adóelőleg számítása nem történik meg, ha az **Adóelőleg számítása** nem **Igen** értékre van beállítva ehhez a cikkhez a **Kiadott termék** oldal **Beszerzés** lapján.

4. Válasszon egy cikk adóelőleg-csoportot a **Cikk-adóelőlegek csoportja** listában.

5. Kattintson a **Mentés** gombra.

Az adóelőleg-csoportok és cikk-adóelőlegek csoportjai a következő lapokon rendelhetők hozzá: 

- **Beszerzési rendelés**
- **Szállítói számla**
- **Számlanapló**

**Beszerzési rendelések** és/vagy **Függőben levő szállítói számlák** létrehozásakor a sorokba az alapértelmezett adóelőleg-csoport és cikk-adóelőlegek csoportja kerül. A **Szállítói számla naplója** pontban átválthat az **Adóelőleg számítása** elemre, és a napló **Általános** lapján kiválaszthatja a **Cikk-adóelőlegek csoportja** lehetőséget.

Az adóelőleg ideiglenes összege elérhető a **Beszerzési rendelés** oldal **Összegek** lapján, a **Helyesbített adóelőleg** mezőben.

![Az adóelőleg szerepel a beszerzési rendelésen](media/withholding-tax-adjusted.png)

Az adóelőleg számítása a **Szállítói kifizetési napló** alapján történik. Az alkalmazandó adóelőlegkódokat és a tényleges adóelőleg-összegeket manuálisan módosíthatja a **Tranzakciók kiegyenlítése** oldal **Adóelőleg** lapján.

![Az adóelőleg manuálisan módosítható a Tranzakciók kiegyenlítése oldalon](media/withholding-tax-vendor-payment-tab.png)

A származtatott adóelőleg összege le lesz vonva a szállítói kifizetésből, és a rendszer feladja az **Adóelőleg számlája** ponthoz egy kapcsolódó bizonylaton.

![Kapcsolódó bizonylatot megjelenítő adóelőlegszámla](media/withholding-tax-adjusted.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]