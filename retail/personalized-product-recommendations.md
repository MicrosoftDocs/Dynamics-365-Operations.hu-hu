---
title: "Személyre szabott termék-ajánlások áttekintése"
description: "Műveletek 365 Dynamics termék ajánlások egybeesik az értékesítés (POS) eszköz ponttal lehet megjeleníteni. Az ajánlások olyan elemek, amelyek a vevő lehet, hogy érdekli a Vásárlási előzmények, azok kívánságát lista elemeinek és más felhasználók online vásárolt cikkek és a tégla és habarcs üzletek alapján. Ajánlások a kiskereskedők nagy katalógusok, segítségre a vevő termék felderítési. Bemutató termékek szólnak, a vevő érdekeit, és a vevő szokásait, termék ajánlások Kiárusítás és kereszt-eladás kiskereskedők segíthet, és növelheti a vevői visszatartási. Műveletek 365 Dynamics termék ajánlások látja el árammal kognitív szolgáltatások és a Microsoft Azure gép tanulás."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: af1f4ba1ed5efe0e35d08d37d09e7ada4a4c1b7a
ms.lasthandoff: 03/31/2017


---

# <a name="personalized-product-recommendations-overview"></a>Személyre szabott termék-ajánlások áttekintése

Műveletek 365 Dynamics termék ajánlások egybeesik az értékesítés (POS) eszköz ponttal lehet megjeleníteni. Az ajánlások olyan elemek, amelyek a vevő lehet, hogy érdekli a Vásárlási előzmények, azok kívánságát lista elemeinek és más felhasználók online vásárolt cikkek és a tégla és habarcs üzletek alapján. Ajánlások a kiskereskedők nagy katalógusok, segítségre a vevő termék felderítési. Bemutató termékek szólnak, a vevő érdekeit, és a vevő szokásait, termék ajánlások Kiárusítás és kereszt-eladás kiskereskedők segíthet, és növelheti a vevői visszatartási. Műveletek 365 Dynamics termék ajánlások látja el árammal kognitív szolgáltatások és a Microsoft Azure gép tanulás.

<a name="scenarios"></a>Esetek
---------

Az alábbi esetekben POS termék ajánlások engedélyezettek. Felhő POS vagy Modern POS (MPOS) rendelkezésre áll.

1.  A a **termékadatok** oldalon:

-   Ha az üzletekhez társítása látogatások egy **termékadatok** oldalra, ha megnézzük az előző tranzakciók különböző csatornákon keresztül az ajánlás motor javasol további elemek, amelyek várhatóan együtt lehet megvásárolni.
-   Ha a tároló hozzárendelése vevő hozzáadása a tranzakcióhoz, és majd látogatások egy **termékadatok** lap, az ajánlás motor a vevői tranzakciók előzményeinek segítségével személyre szabott javaslatokat tesz.

[![proddetails](./media/proddetails.png)](./media/proddetails.png)

2.  A a **tranzakció** oldalon:

-   Az ajánlás motor cikkeket a kosárba cikkek teljes listája alapján javasol.
-   Ha a tároló hozzárendelése vevő hozzáadása a tranzakcióhoz, az ajánlás motor segítségével a vevői tranzakciók előzményeinek és az elemek közül a kosár személyes javaslatokat tesz.

**Megjegyzés:** javaslatok megjelenítése a **tranzakció** lap, a kiskereskedő kell frissíteni a képernyő-elrendezésén Dynamics 365 műveletekhez. A **ajánlások** vezérlő kell elveti a a **tranzakció** oldalon. [![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

3.  A a **vevő adatai** oldalon:
    -   Az ajánlás motor javasol cikkeket a felhasználói Azonosítót és a vevő kívánja lista alapján.

[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)

## <a name="configure-dynamics-365-for-operations-to-enable-pos-recommendations"></a>Műveletek engedélyezése POS ajánlások Dynamics 365 beállítása
Termék ajánlások beállításához tegye a következőket kell.

1.  Győződjön meg arról, hogy a megfelelő jelölt **jogi személy**.
2.  Keresse meg **tároló entitás**, jelölje be **kiskereskedelmi értékesítése**, és kattintson a **frissítési**. ** ** Ez az operatív adatbázisból bemutató adatokat (vagy az adatok) használja, és helyezze át a tároló entitás.
3.  Választható lehetőség: Javaslatok megjelenítése a tranzakciók képernyőn, Ugrás ** képernyő-elrendezés, **a képernyő-elrendezés, indítsa el a **képernyő-elrendezés tervezője**,** ** majd helyezze az elemet a ** ajánlások vezérlő ** ahol szükséges.
4.  Keresse fel **kiskereskedelmi paraméterek**, válassza **gép-tanulás**, jelölje be ** Igen ** alatt **javaslatok engedélyezése POS**.
5.  POS javaslatok megtekintéséhez futtassa a globális konfigurációs feladat **1110**. POS képernyő-elrendezés tervezője végzett módosítások tükrözéséhez csatorna konfigurációs feladat futtatása **1070**.

## <a name="how-does-it-work"></a>[]()Hogyan működik?
Frissítésekor a **tároló entitás** egység, a következő műveletek végrehajtása történik.

-   A kognitív szolgáltatások által megkövetelt adatokat a Dynamics 365 műveletek működési adatbázis kivonjuk, és az entitás üzlethez.
-   Az adatok tisztítható ADA tevékenységek részeként struktúra parancsfájlok segítségével az adatok által Azure Data Factory (ADF) szolgál. Blob-tároló kitisztítanak adatokat tárolja.
-   Blob-tároló adatai egy ajánlás modell vonat a kognitív szolgáltatások API-t használja.

Ha bekapcsolja a **engedélyezése a ajánlásokról** és a konfigurációs feladatok futtatása, a következő műveletek végrehajtása történik.

-   Az API kivételezni és a Dynamics 365 műveletek működési adatbázis, AOS a Web.config és is a kiskereskedelmi kiszolgálón tárolt minta hitelesítő adatai és Azonosítóját.
-   Modell hitelesítő adatai és Azonosítóját is elérhetők a CRT úgy, hogy a hívások termék ajánlások felhő POS és MPOS online módban is lehet alkalmazkodni.


<a name="see-also"></a>Lásd még
--------

[Ajánlások vezérlő hozzáadása a POS eszközök tranzakció lap](add-recommendations-control-pos-screen.md)


