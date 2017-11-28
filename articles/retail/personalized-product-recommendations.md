---
title: "Személyre szabott termékajánlatok áttekintése"
description: "Ez a témakör a Dynamics 365 for Retail pénztár (POS) eszközön megjeleníthető termékajánlásaival kapcsolatban rendelkezik információval."
author: ashishmsft
manager: AnnBe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Operations, Core
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 64f0a9a44b97a9980f8d1b76ff158f1ac9cbc114
ms.openlocfilehash: 942d6225a46b108ea39d3b8e4376b644c128ae6d
ms.contentlocale: hu-hu
ms.lasthandoff: 11/14/2017

---

# <a name="personalized-product-recommendations-overview"></a>Személyre szabott termékajánlatok áttekintése

[!include[banner](includes/banner.md)]


> [!NOTE]
> Ez a funkció jelenleg csak védőfali és termelési (magas rendelkezésre állási) telepítési topológiákban érhető el. 

A Dynamics 365 for Retail rendszerben a termékajánlásokat meg lehet jeleníteni a pénztár (POS) eszközön. Az ajánlások olyan elemek, amelyek érdekelhetik a vevőt a vásárlási előzmények alapján, a kívánságlistájukon levő elemek alapján, illetve olyan elemek alapján, amelyeket más felhasználók vásároltak meg online vagy hagyományos üzletekben. A nagy katalógussal dolgozó kiskereskedők esetében az ajánlások segítenek a vevőknek a termékek felderítésében. A vevő érdeklődésének és vásárlási szokásainak megfelelően célzott termékek bemutatásával a termékajánlások segíthetik a kiskereskedőket az értéknövelő, valamint a keresztértékesítésben, és növelhetik a vevők megtartását. A Dynamics 365 for Retail rendszerben a termékajánlásokat a kognitív szolgáltatás és a Microsoft Azure gépi tanulás szolgálja ki.


<a name="scenarios"></a>Esetek
---------

Az alábbi POS-esetekben engedélyezettek a termékajánlások. A felhő POS vagy a modern POS (MPOS) esetében állnak rendelkezésre.

1.  A **Termékadatok kezelése** oldalon:

-   Ha az üzlet alkalmazottja megnyitja valamelyik **Termékadatok** oldalt, amikor az előző tranzakciókat nézi meg különböző csatornákat lefedve, az ajánlások motor további elemeket javasol, amelyek várhatóan együtt fognak megvásárolni.
-   Ha az üzlet alkalmazottja hozzáad egy vevőt a tranzakcióhoz, majd látogat egy **Termékadatok** lapot, az ajánlások motor a vevői tranzakciók előzményeinek segítségével személyre szabott ajánlásokat tesz.

[![proddetails](./media/proddetails.png)](./media/proddetails.png)

2.  A **Tranzakció** oldalon:

-   Az ajánlások motor a kosárban levő cikkek teljes listája alapján cikkeket javasol.
-   Ha az üzlet alkalmazottja hozzáad egy vevőt a tranzakcióhoz, az ajánlások motor a vevői tranzakciók előzményeinek segítségével, valamint a kosárban levő cikkel alapján személyes ajánlásokat tesz.

> [!NOTE]
> Javaslatok megjelenítéséhez a **Tranzakció** lapon a kiskereskedőnek frissítenie kell a képernyő-elrendezést Dynamics 365 for Retail rendszerben. Az **Ajánlások** vezérlőt rá kell húzni a **Tranzakció** oldalra. [![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

3.  A **Vevő adatai** oldalon:
    -   Az ajánlások motor a felhasználói azonosító és a vevő kívánságlistáján levő cikkek alapján cikkeket javasol.

[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)

## <a name="configure-dynamics-365-for-retail-to-enable-pos-recommendations"></a>A Dynamics 365 for Retail rendszer konfigurálása a POS-ajánlások engedélyezésére
A termékajánlások beállításához a következőket kell tenni:

1.  Győződjön meg arról, hogy a megfelelő **Jogi személy** választotta ki.
2.  Keresse meg az **Entitástár** elemet, jelölje be a **Kiskereskedelmi értékesítés** lehetőséget, és kattintson a **Frissítés** elemre. Ezzel a bemutatóadatokat (vagy a saját adatait) használja az üzemi adatbázisból, és áthelyezi őket az entitástárba.
3.  Választható lehetőség: Javaslatok megjelenítéséhez a tranzakciók képernyőn, menjen a **Képernyőelrendezés** lehetőséghez, válassza ki a képernyőelrendezést, indítsa el a **Képernyő-elrendezés tervezőjét**, majd helyezze az **ajánlások** vezérlőjét oda, ahová szükséges.

4.  Keresse fel a **Kiskereskedelmi paraméterek** elemet, válassza **Gépi tanulás** elemet, jelölje be az **Igen** lehetőséget **POS-ajánlások engedélyezése** alatt.
5.  A javaslatok megtekintéséhez a POS-on, futtassa az **1110** globális konfigurációs feladatot. A POS képernyő-elrendezés tervezőjén végzett módosítások megjelenítéséhez futtassa az **1070** csatorna konfigurációs feladatot.

## <a name="how-does-it-work"></a>[]()Hogyan működik?
Az **Entitástár** entitás frissítésekor a következő műveletek végrehajtása történik.

-   A kognitív szolgáltatások által megkövetelt formátumban a rendszer kivonja az adatokat a Dynamics 365 for Retail működési adatbázisából, és elküldi őket az entitástárba.
-   Az adatokat az Azure Data Factory (ADF) használja fel az adatok tisztításához Hive-parancsfájlok használatával, az ADF-tevékenységek részeként. A megtisztított adatokat blobtároló tárolja.
-   A blobtároló adatait a kognitív szolgáltatások API használja egy ajánlási modell betanításához.

Ha bekapcsolja az **Ajánlások engedélyezése** elemet, és elvégzi a konfigurációs feladatok futtatását, a következő műveletek végrehajtása történik.

-   A modell hitelesítő adatokat és az azonosítót a rendszer az API segítségével szerzi meg, majd a Dynamics 365 for Retail működési adatbázisában tárolja, az AOS web.config állományában, illetve a kiskereskedelmi kiszolgálón is.
-   A modell hitelesítő adatok és az azonosító hozzáférhetők a CRT számára, hogy ki lehessen szolgálni a felhő POS és az MPOS felől online módban érkező termékajánlás-lehívásokat.


<a name="see-also"></a>Lásd még
--------

[Ajánlások vezérlő hozzáadása egy POS-eszköz tranzakció lapján](add-recommendations-control-pos-screen.md)




