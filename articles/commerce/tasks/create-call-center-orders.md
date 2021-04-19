---
title: Hívásközponti rendelések létrehozása
description: Ez az eljárás bemutatja, hogy hogyan kereshet ki egy vevőt, hozhat létre egy új rendelést és kereshet rá egy termére, továbbá hogyan szedhet be kifizetést a vevőtől.
author: josaw1
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MCRCustomerService, SalesTable, MCRSourceIdTargetLookup, MCRSalesQuickQuote, MCRSalesOrderRecap, MCRCustPaymDialog, MCRCustPaymLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8d8dc9e19ecd6b835569ba80563bce33134895cb
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791655"
---
# <a name="create-call-center-orders"></a>Hívásközponti rendelések létrehozása

[!include [banner](../includes/banner.md)]

Ez az eljárás bemutatja, hogy hogyan kereshet ki egy vevőt, hozhat létre egy új rendelést és kereshet rá egy termére, továbbá hogyan szedhet be kifizetést a vevőtől. Az eljárás az USRT bemutatócéget használja, és az Értékesítési adminisztrátor számára készült. Előfeltételek: Az eljárást elvégző felhasználók a Hívásközpont felhasználóiként vannak beállítva, valamint a Gyári Féléves Katalógus közzététele megtörtént, legalább egy Forráskóddal.

1. Nyissa meg a következőt: **Kiskereskedelem és kereskedelem \> Ügyfelek \> Ügyfélszolgálat**.
2. A **Keresés szövegben** mezőbe írja be a feltételeket a vevő kikereséséhez.
    * Ebben a példaeljárásban írja be: „karen”, majd nyomja meg a **TAB** billentyűt.  
3. Válassza a Keresés lehetőséget.
    * Mivel a bemutató adatsor csak egy „Karen” nevű vevőt tartalmaz, az eredmény kiválasztása automatikusan megtörténik.  
4. Válassza ki az **Új értékesítési rendelés** lehetőséget.
5. Bontsa ki vagy csukja össze az **Értékesítési rendelés** fejléce szakaszt.
6. Válassza ki a katalógus forráskódját.
    * Amennyiben nincsenek aktív Forráskódok, kihagyhatja ezt a lépést.  
7. Válassza a **Sor hozzáadása** lehetőséget.
8. A **Cikkszám** mezőbe írja be írja be a cikk-keresési kifejezést.
    * Ebben a mintaeljárásban írja be a következő cikkszám-részletet: „8111”, majd nyomja meg a TAB billentyűt. Ezzel a művelettel megjelenik a cikk-kereső ablak.  
9. Válassza ki az értékesítési rendeléshez hozzáadandó terméket.
10. Adja meg az értékesítési mennyiséget.
11. Válassza a **Létrehozása** lehetőséget.
12. Kattintson a **Befejezés** gombra a vevői fizetés rögzítéséhez.
13. Válassza a **Hozzáadás** lehetőséget.
    * A Hivatkozás hozzáadása a Kifizetések lapon található. Bontsa ki a Kifizetések lapot, ha össze van csukva.  
14. Válassza ki a fizetési módot.
    * Ebben az eljárásban válassza ki a készpénzfizetési módszert.  
15. Zárja be a lapot.
16. Írja be az összeget.
    * Ennél az eljárásnál írjon be egy olyan összeget, amely megegyezik a rendelési egyenleggel. Ez az Értékesítési rendelés összesítése oldalon látható, az összeg mezőtől balra. Ez a művelet lehetővé teszi, hogy teljesen kifizetett állapotban befejezze a rendelést.  
17. Válassza ki az **OK** lehetőséget.
18. Válassza a **Beküldés** lehetőséget.

## <a name="additional-resources"></a>További erőforrások

[Tranzakciós e-mailek testreszabása szállítási mód szerint](../customize-email-delivery-mode.md)

[Szállítási mód módosítása a pénztárban](../pos-change-delivery-mode.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]