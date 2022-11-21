---
title: 'Előlegek itt: Dynamics 365 Commerce'
description: Ez a témakör áttekintést nyújt a következőben található előlegtranzakciók feldolgozásával kapcsolatos adatokról:Microsoft Dynamics 365 Commerce
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2021-06-28
ms.openlocfilehash: 8262470f83481ef8840857a52948c0833d8b278e
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780200"
---
# <a name="prepayments-in-dynamics-365-commerce"></a>Előlegek itt: Dynamics 365 Commerce

[!include[banner](../includes/banner.md)]

Ez a témakör áttekintést nyújt a következőben található előlegtranzakciók feldolgozásával kapcsolatos adatokról:Microsoft Dynamics 365 Commerce

Dynamics 365 Commerce A <a0/<a0/a Kinnlevőségek vagy Commerce rendszer a következő kifizetési típusok előlegtranzakcióit dolgozza fel:

- **Vevői számla letétfizetése** – a vevő letétet fizet a pénztárnál (POS). A Commerce előlegtranzakcióként dolgozza fel a letéti kifizetést. Amikor feladja a tranzakciót, létrejön egy kifizetési napló, és feladja azt a **Commerce** Headquarters Naplóbizonylat lapján. A **Kifizetési napló lap Előlegnapló-bizonylat** **jelölőnégyzete** automatikusan be van jelölve. A további tudnivalókat, [köztük a cél régióra vonatkozó előleg- és adóspecifikus információkat lásd a Globalizációs erőforrások – Ország-/területspecifikus súgótartalomban](/dynamics365/fin-ops-core/dev-itpro/lcs-solutions/country-region?context=%2Fdynamics365%2Fcontext%2Ffinance#countryregion-specific-help-content).
- **Letétet letétet vevői rendelés –** a vevő létrehoz egy vevői rendelést a POS-terminálon. A vevő a Commerce Headquarters **(Commerce rendszer** vevői paraméterei) vevői rendelési lapján beállított alapértelmezett letéti százalék alapján kifizetheti a **\> rendelés letétját**. A Commerce rendszer előlegtranzakcióként dolgozza fel a vevői rendelés letéti kifizetését. Amikor feladja a tranzakciót, létrejön egy kifizetési napló, és azt feladja a Naplóbizonylat **lapon**. A **Kifizetési napló lap Előlegnapló-bizonylat** **jelölőnégyzete** automatikusan be van jelölve. A kifizetés ki van egyenlítve, és a vevői számla automatikusan ki lesz bocsátva, amikor a rendelést fel- vagy szállítják.
- **Hívásközponti értékesítési rendelés** – a hívásközponti ügyfélszolgálati munkatárs a vevő nevében létrehoz egy értékesítési rendelést, **·** **és** a fizetés rögzítésekor az előleg attribútuma Igen lesz.

A Commerce rendszer a következő feladatokat végzi el előleg feldolgozása érdekében:

- **Vevői számlás letéti** kifizetés feldolgozása – a vevő által a bank által befizetett letét egy olyan szolgáltatás használatával kerül átvitelre a Commerce rendszerbe, amely az adatokat szinkronizálja. A Commerce rendszer létrehoz egy kiskereskedelmi kifizetési tranzakciót a kifizetéshez. Amikor feladja a kiskereskedelmi tranzakciót, egy készpénznaplót vagy egy vevői kifizetési naplót ad fel a rendszer. A **Commerce Headquarters** **·** **Naplóbizonylat** lapján található Előlegnapló-bizonylat jelölőnégyzet automatikusan be van jelölve a kifizetési naplóhoz. Az előlegek nem feldolgozhatóak, ha a kifizetés összege negatív.
- **Vevői rendelés vagy letétet** fizető értékesítési rendelés feldolgozása – a vevő a vevői rendeléshez szükséges letétet a Commerce Data Exchange Következő használatával fizeti ki: Real-time Service. A Commerce rendszer a vevő által használt fizetési módtól függően vagy vevői kifizetési naplót, vagy készpénznaplót hoz létre. A **Commerce Headquarters alkalmazás** **·** **automatikusan** be van jelölve a Naplóbizonylat lap Kifizetés lapján található Előlegnapló-bizonylat jelölőnégyzet a naplóhoz. Ha egy vevő többféle fizetési módot használ a részleges kifizetések fizetésére, a Commerce az alkalmazott fizetési módnak megfelelő részleges kifizetést dolgozza fel.

Hitelkártyák, illetve a hitelkártyás fizetési módokat szolgáló digitális fizetőeszközök esetén a Commerce a sikeres engedélyezés után egy "rögzítési" kérést küld. (Az alapokat az értékesítési rendelés számlázása előtt rögzítik.)

Vevői rendelés érvénytelenítése esetén az előleg összegét visszatéríti a rendszer, és a letét összegére visszatérítési naplót ad fel. A visszatérítési összeg számítása és feladása a visszatérítési kifizetés feladott feladott fizetési módja alapján történik. A Commerce rendszer érvénytelenítési díjat alkalmazhat a **Commerce Headquarters Commerce paraméterek** lapján megadott százalék alapján.

Vevői rendelés visszáruja esetén a rendszer létrehoz egy visszárurendelést és egy visszatérítési kifizetési naplót. A visszárurendelés feladása során a Commerce az eredeti tranzakcióhoz használt fizetési módnak megfelelően vevői kifizetési naplót vagy készpénznaplót hoz létre.
