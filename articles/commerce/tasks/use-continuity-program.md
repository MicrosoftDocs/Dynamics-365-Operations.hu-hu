---
title: Folytonos program használata
description: Ez az eljárás a folytonos program révén történő értékesítés és a kapcsolódó vevői rendelések feldolgozását mutatja be.
author: josaw1
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.industry: Retail
ms.search.form: MCRCustomerService, MCRCustSearch, SalesTable, MCRContinuityCustInfo, MCRCustPaymLookup, CreditCardTokenization, CreditCardLookup, MCRSalesOrderRecap
ms.openlocfilehash: 3736984a336b35b23b7060b2d98770912cc9ec6e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267404"
---
# <a name="using-continuity-program"></a>Folytonos program használata

[!include [banner](../includes/banner.md)]

Ez az eljárás a folytonos program révén történő értékesítés és a kapcsolódó vevői rendelések feldolgozását mutatja be. Az eljárás végrehajtásához a felhasználónak hívásközpont felhasználójaként kell beállítva lennie. Ez az eljárás az USRT bemutatócéget használja.

1. Nyissa meg a következőt: Commerce > Vevők > Ügyfélszolgálat.
2. A Keresés szövegben mezőbe írja be, hogy „Karen”, majd nyomja le a Tab billentyűt.
    * Megjelenik a Speciális keresés párbeszédpanel. Ha nem, kattintson a Keresés gombra a mező jobb oldalán.  
3. A listában jelölje meg a kiválasztott sort.
    * Elvileg csak egy sor látszik, amely a Karen Berg értéket tünteti fel. Jelölje ki a sort úgy, hogy rákattint a rács bal szélén látható pipa oszlopra.  
4. Kattintson a Kiválasztás lehetőségre.
5. Kattintson az Új értékesítési rendelés gombra.
    * Érdemes megjegyezni az értékesítési rendelés számát. Később szükség lesz rá az eljárás során.  
6. A Cikkszám mezőbe írja be, hogy „88000”, majd nyomja le a Tab billentyűt.
    * Ez egy folytonos cikk az USRT bemutatóadatok között.  
7. Kattintson a Befejezés gombra.
8. A Fizetési mód mezőbe írja be, hogy „Visa”.
9. Kattintson a Hitelkártya hozzáadása lehetőségre.
    * Ezen az oldalon adja meg a szükséges hitelkártyaadatokat.  
10. Kattintson az OK gombra.
11. Bontsa ki a Kifizetés szakaszt.
    * Hívásközponti rendelés elküldéséhez meg kell adni a rendeléshez tartozó kifizetéseket.  
12. Kattintson az OK gombra.
13. Kattintson a Küldés hivatkozásra.
    * Végzett az új folyamatos rendelés létrehozásával. Ezt követően két kötegelt eljárás futtatása következik, amelyek a folytonos rendelés feldolgozását végzik.  
14. Zárja be a lapot.
15. Ugorjon a Retail és Commerce > Folytonosság > Folytonos fizetések feldolgozása elemre.
16. A Folytonos cikk mezőbe írja be, hogy „88000”, és nyomja le a Tab billentyűt.
17. Kattintson az OK gombra.
18. Ugorjon a Retail és Commerce > Folytonosság > Folytonos gyermekrendelések létrehozása elemre.
    * Ezt a folyamat új értékesítési rendeléseket hoz létre a folyamatos programok beállításai alapján.  
19. A Folytonos cikk mezőbe írja be, hogy „88000”, és nyomja le a Tab billentyűt.
    * A „88000” egy folytonos cikk az USRT-bemutatóadatok között.  
20. Az Értékesítési rendelés mezőben adjon meg vagy válasszon ki egy értéket.
    * Adja meg az eljárás során korábban feljegyzett értékesítési rendelés számát. Ez minimálisra csökkenti az eljáráshoz szükséges feldolgozási időt. A Értékesítési rendelés mező kitöltése nem kötelező - bármely programhoz feldolgozható az összes megrendelés.  
21. Kattintson az OK gombra.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
