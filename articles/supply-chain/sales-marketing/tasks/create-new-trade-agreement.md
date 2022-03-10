---
title: Új kereskedelmi szerződés létrehozása
description: Ez az eljárás bemutatja, hogyan hozhat létre egy kereskedelmi megállapodást, amelyben regisztrálhat egy új termékeladási árat, amelyben egy adott vevővel megállapodott.
author: Henrikan
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TradeNonStockedConversion, TradeNonStockedConversionChangeWizard, TradeNonStockedConversionCheckWorksheet, TradeNonStockedConversionWizard, TradeNonStockedRegister
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a16a39d95605900be0fa1e339b8cd0755ba85189
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573417"
---
# <a name="create-a-new-trade-agreement"></a>Új kereskedelmi szerződés létrehozása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan hozhat létre egy kereskedelmi megállapodást, amelyben regisztrálhat egy új termékeladási árat, amelyben egy adott vevővel megállapodott. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja. Saját adatok használatakor az útmutató használatának megkezdése előtt győződjön meg róla, hogy a Kereskedelmi megállapodások napló neve létezik, ahol az Alapértelmezett viszony az "Ár (eladási)".

## <a name="create-and-post-a-new-trade-agreement-journal"></a>Hozzon létre és tegyen közzé egy új kereskedelmi megállapodási naplót

1. Ugorjon a **Navigációs lap > Modulok >Értékesítés és marketing > Árak és engedmények > Kereskedelmi megállapodási naplók** elemre.
2. Kattintson az **Új** elemre.
3. A **Név** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. Keresse meg és jelölje ki a kívánt rekordot a listán.
5. A **Művelet panelen** kattintson a **Sorok** elemre.
6. A **Fiókkód** mezőben válassza ki a „Tábla” lehetőséget.
    
    Ebben a példában egy konkrét vevő árát frissíti, ami azt jelenti, hogy meg kell adnia egy Táblát. Ha a termék listaárát frissítené, az „Összeset” kellene kiválasztania, úgy, hogy az új ár legyen érvényes az összes vevőre. Ha különböző árakat különböztet meg az egyes vevői szegmensek között, akkor válassza a Csoportot. A Csoport kiválasztásához be kell állítania a Vevői árcsoportokat.  

7. A **Fiókválasztás** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
8. Keresse meg és jelölje ki a kívánt rekordot a listán.
9. A **Cikk-kód** mezőben válassza ki a „Tábla” lehetőséget.
    
    Ha "Ár (eladási)" típusú kereskedelmi megállapodást ír be, akkor csak a "Tábla" elemet válassza ki a **Cikk-kód** mezőben. Ennek oka az, hogy az ár abszolút érték, és nem lehet azonos egy termékcsoport összes termékére.
    
10. A **Cikk-viszony** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
11. A listában válassza ki a szerződésben szerepeltetni kívánt terméket. Jegyezze meg, hogy mely termék van kijelölve.  
12. Adja meg a minimum mennyiséget a **Kezdőérték** mezőben.
    - Ha a vevőnek egy minimális mennyiséget kell rendelnie, mielőtt új ár igényelhetne, akkor meg kell adnia a mennyiséget itt.  
    - Adjon meg egy értéket a **Címzett** mezőben, hogy megadja a maximális mennyiséget, amely felett a megállapodási ár nem lesz érvényes. Ha több mennyiségi szünet alapján ajánl árakat és engedményeket, adja meg az egyes mennyiségi határértékeket egy minimális és maximális mennyiségként a **Kezdő** és a **Befejező** mezőkben.
13. Az **Összeg devizában mezőben** adjon meg egy árat.
14. A **Részletek** szakaszban, a **Kezdő dátum** mezőben adjon meg egy dátumot, amelytől kezdve érvényes lesz a szerződés.
15. Kattintson a **Mentés** gombra.
16. Kattintson az **Érvényesítés** gombra.
17. Kattintson a **Kijelölt sorok érvényesítése** pontra.
18. Kattintson az **OK** gombra.
19. Kattintson a **Bejegyzés** lehetőségre.
20. Kattintson az **OK** gombra.

## <a name="view-trade-agreements-for-a-product"></a>Termékkel kapcsolatos kereskedelmi megállapodások megtekintése

1. Kattintson ide: **Navigációs ablaktábla > Modulok > Termékinformációk kezelése > Termékek > Kiadott termékek**.
2. A listában keresse meg és válassza ki a terméket, amelynek éppen frissítette az árát.
3. A **Művelet panelen** kattintson az **Értékesítés** elemre.
4. Kattintson a **Kereskedelmi megállapodások megtekintése** pontra.
    
    Tekintse át az imént létrehozott ármegállapodás részletes adatait.

5. Zárja be a lapot.

## <a name="additional-resources"></a>További erőforrások

### <a name="whitepaper"></a>Tanulmány

További tudnivalókért töltse le a következő (az AX 2012 támogatásához készült, de még a Dynamics 365 Supply Chain Management esetében is érvényes) tanulmányt

- [Kereskedelmi megállapodások](https://download.microsoft.com/download/0/2/9/02972c8b-0159-4936-a3ef-1e64252b2d2f/TradeAgreementsInAX.pdf)

### <a name="community-blogs"></a>Közösségi blogok

- [Értékesítési árak a Dynamics 365 for Finance and Operations szolgáltatásban](https://financefunction.tech/2018/11/14/sales-prices-in-dynamics-365-for-finance-and-operations/#sales_price_in_trade_agreements)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]