---
title: Hívásközponti rendelések létrehozása
description: Ez az eljárás bemutatja, hogy hogyan kereshet ki egy vevőt, hozhat létre egy új rendelést és kereshet rá egy termére, továbbá hogyan szedhet be kifizetést a vevőtől.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRCustomerService, SalesTable, MCRSourceIdTargetLookup, MCRSalesQuickQuote, MCRSalesOrderRecap, MCRCustPaymDialog, MCRCustPaymLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4867ad67dc570ab42420ba12fc7dc2da6b5ba503
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1548255"
---
# <a name="create-call-center-orders"></a>Hívásközponti rendelések létrehozása

[!include[task guide banner](../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogy hogyan kereshet ki egy vevőt, hozhat létre egy új rendelést és kereshet rá egy termére, továbbá hogyan szedhet be kifizetést a vevőtől. Az eljárás az USRT bemutatócéget használja, és az Értékesítési adminisztrátor számára készült. Előfeltételek: Az eljárást elvégző felhasználók a Hívásközpont felhasználóiként vannak beállítva, valamint a Gyári Féléves Katalógus közzététele megtörtént, legalább egy Forráskóddal.

1. Nyissa meg a következőt: Kiskereskedelem és kereskedelem > Vevők > Ügyfélszolgálat.
2. A Keresés szövegben mezőbe írja be a feltételeket a vevő kikereséséhez.
    * Ebben a példaeljárásban írja be: „karen”, majd nyomja meg a TAB billentyűt.  
3. Kattintson a Keresés gombra.
    * Mivel a bemutató adatsor csak egy „Karen” nevű vevőt tartalmaz, az ő kiválasztása automatikusan megtörténik.  
4. Kattintson az Új értékesítési rendelés gombra.
5. Bontsa ki vagy csukja össze az Értékesítési rendelés fejléce szakaszt.
6. Válassza ki a katalógus forráskódját.
    * Amennyiben nincsenek aktív Forráskódok, bezárhatja a Forrás mezőt, és kihagyhatja ezt a lépést.  
7. Kattintson az Új sor hozzáadása lehetőségre.
8. A Cikkszám mezőbe írja be írja be a cikk-keresési kifejezést.
    * Ebben a mintaeljárásban írja be a következő cikkszám-részletet: „8111”, majd nyomja meg a TAB billentyűt. Ekkor megjelenik a cikk-kereső ablak.  
9. Válassza ki az értékesítési rendeléshez hozzáadandó terméket.
10. Adja meg az értékesítési mennyiséget.
11. Kattintson az Új > lehetőségre.
12. Kattintson a Befejezés gombra a vevői fizetés rögzítéséhez.
13. Kattintson a Hozzáadás gombra.
    * A Hivatkozás hozzáadása a Kifizetések lapon található. Bontsa ki a Kifizetések lapot, ha össze van csukva.  
14. Válassza ki a fizetési módot.
    * Ebben az eljárásban válassza ki a készpénzfizetési módszert.  
15. Zárja be a lapot.
16. Írja be az összeget.
    * Ennél az eljárásnál írjon be egy olyan összeget, amely megegyezik a rendelési egyenleggel. Ez az Értékesítési rendelés összesítése oldalon látható, az összeg mezőtől balra. Ez lehetővé teszi, hogy teljesen kifizetett állapotban befejezze a rendelést.  
17. Kattintson az OK gombra.
18. Kattintson a Küldés hivatkozásra.

