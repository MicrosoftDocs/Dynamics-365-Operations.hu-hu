---
title: "Beszerzési rendelések áttekintése"
description: "Ez a cikk a beszerzési rendelések általános ismertetését tartalmazza és további hivatkozásokat a beszerzési rendelés különböző szakaszaihoz kapcsolódó cikkekhez ."
author: FrankDahl
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 93083
ms.assetid: e9b7bc5b-1d7e-4ec2-97be-d655274b0613
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: d01ef1c496c7c79795d9d740ee755e84434dfdf1
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---

# <a name="purchase-order-overview"></a>Beszerzési rendelések áttekintése

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

Ez a cikk a beszerzési rendelések általános ismertetését tartalmazza és további hivatkozásokat a beszerzési rendelés különböző szakaszaihoz kapcsolódó cikkekhez .

A beszerzési rendelés áruk vagy szolgáltatások vásárlásáról szóló, a szállítóval kötött megállapodást jelképező dokumentum. A dokumentum szintén segít nyomon követni a rendelés felé készült termékbevételezéseket és később a szállító által a rendelés felé kiállított számlák könyvelését.  

A **Beszerzési rendelések** oldal tartalmazza a rendelkezésre álló rendelések áttekintését, és lehetővé teszi a rendelések módosítását. Amikor megnyit egy beszerzési rendelést, választhatja a **Fejléc** nézetet, amely olyan információkat tartalmaz, amelyek az egyes beszerzési rendeléseknek csak egyszer lett megadva, mint például a szállítói adatok. Másik lehetőségként választhatja a **Sorok** nézetet, ahol a a rendelési sorokat módosíthatja. Általában váltunk a két nézet között a beszerzési megrendelések módosítása közben. A költségek nem jelennek meg közvetlenül a **Beszerzési rendelések** oldalon, hanem a menükből nyithatók meg a rendelési fejlécen és sorokon keresztül.  

Számos jelentésben találhat információt a Beszerzési rendelésekről, termékbevételezésekről és szállítói számlákról. Ezek a jelentések megtalálhatók a **beszerzés és forrás** és **kötelezettségek** modulok.  

A **Beszerzési rendelés előkészítése** és a **Beszerzési rendelés bevételezése és követése** munkaterületek lehetővé teszik a beszerzési rendelések megtekintését a feldolgozás különböző állapotaiban. A végrehajtandó műveletekről is összegzést nyújtanak. A **Beszerzési rendelés készítése** munkaterület a beszerzési rendelés létrehozására és ellenőrzésére, jóváhagyására és a szállító visszaigazolására összpontosít. A **Beszerzési rendelés bevételezése és követése** munkaterület összpontosít a cikkek vagy szolgáltatások beérkezésének feldolgozására a beszerzési rendelés ellenében. Ez magában foglalja a listákat, amelyek segítségével megtekinthetők a lejárt nyugták, vagy amelyek hamarosan aktuálisak lesznek a szállító általi szállításra. Ezeket a munkaterületeket nem a raktárban végzett kapcsolódó bevételezési tevékenységek végrehajtásához használják. Ezeket a tevékenységeket a **Készletgazdálkodás** és a **Raktárkezelés** modulok oldalainak használatával hajtják végre. Szállítói számlák feldolgozását a **Szállítói számla bevitele** munkaterület használatával kell elvégezni és a kifizetéseket a **Szállítói kifizetések** munkaterület használatával kell elvégezni.  

A következő cikkek áttekintést adnak a beszerzési rendelés különböző szakaszairól:

-   [Beszerzési rendelés létrehozása](purchase-order-creation.md)
-   [Beszerzési rendelés jóváhagyása és visszaigazolása](purchase-order-approval-confirmation.md)
-   [Beszerzési rendelés - termékbevételezés](product-receipt-against-purchase-orders.md)
-   [Szállítói számlák áttekintése](../../financials/accounts-payable/vendor-invoices-overview.md)

## <a name="types-of-purchase-orders"></a>Beszerzési rendelések típusai
Háromféle BR van. A beszerzési rendelés létrehozásakor meg kell adnia a típusát. Beállíthatja az új rendelések alapértelmezett rendelési típusát a **Beszerzési és forrásparaméterek** oldalon.

| Beszerzési rendelési típusa        | Leírás                                                                                                                                                                                                                                                                           |
|----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Napló        | Ezzel a típussal rendelés tervezetet hozhat létre. Ez a típus nincs hatással a raktári mennyiségekre és nem hoz létre készlettranzakciókat. A beszerzési rendelés naplósorai nem lesznek az alapütemezés részei.                                                                                                       |
| Beszerzési rendelés | Ezt a típust akkor használja beszerzési rendelések létrehozására, ha a szállító visszaigazolta a rendeléseket és a rendelések bevételezése és a számlázása a szállító kifizetése előtt feldolgozásra került. Ez a beszerzési rendelés típus a leggyakoribb.                                                                          |
| Visszaküldött rendelés | Ezt a típust használja, ha cikkeket küld vissza a szállítónak. Ennél a rendeléstípusnál a szállító által adott visszáru-jóváhagyási szám (Return Materials Authorization – RMA) megadása szükséges. Az visszáru-jóváhagyási számot az beszerzési rendelés **Általános** lapján adhatja meg. A rendeléssoroknak negatív mennyiségekkel kell rendelkeznie. |

## <a name="purchase-order-statuses"></a>Beszerzési rendelés állapotai
A beszerzési rendelések számos állapotmezőt tartalmaznak, melyek a rendelés állapotát jelölik. Ezek a mezők a rendelés **Fejléc** nézetén láthatók, és néhány közülük az összes rendelési rács áttekintésében is látható. Az **Állapot** mező a rendelés mennyiségeinek állapotát jeleníti meg. A következő értékek állnak rendelkezésre:

-   **Nyissa meg a rendelés** – Rendelések jöttek létre, mennyiségek megrendelve .
-   **Bevételezve** – Néhány mennyiség bevételezésre került, de a számlázásuk még nem történt meg.
-   **Számlázva** – A rendelés teljes mennyisége számlázva. **Megjegyzés:** Ha egy rendelés *részben* számlázva lett, sem a **Beérkezett** állapot, sem a **Számlázott** állapot megfelelő. Ezért a rendelés állapota még mindig **Nyitott rendelés**.
-   **Visszavonva** – Egy rendelés megerősítést nyert, de később visszavonták. Ezért ez az állapot azt jelzi, hogy már nincsenek nyitott mennyiségek megrendelve.

A **Dokumentum állapota** a mező segíti a rendelés állapotának gyors áttekintését a feldolgozott dokumentumok vonatkozásában. A rendelés legutoljára elkészült dokumentumának állapotát mutatja. A következő értékek állnak rendelkezésre:

-   **Nincs** – Még nincs dokumentum feldolgozva a rendeléshez.
-   **Beszerzési értesítő** – Egy beszerzési értesítést hozott létre, és a rendelés visszajelzést vár a szállítótól.
-   **Beszerzési rendelés** – A rendelés visszaigazolásának feldolgozása megtörtént.
-   **Termékbevételezés** – A rendelés termékbevételezésének feldolgozása megtörtént.
-   **Számla** – Egy számla a rendeléshez lett könyvelve.

A **Jóváhagyási állapot** mező akkor használatos, ha egy beszerzési rendelés halad át az ellenőrzési folyamaton vagy a munkafolyamaton. A következő értékek állnak rendelkezésre:

-   **Tervezet**, **Ellenőrzés alatt**, és **Elutasítva** – ezeket az állapotokat csak akkor használják, ha jóváhagyási munkafolyamatot használnak a beszerzési rendeléshez.
-   **Jóváhagyva** – Ez az állapot a befejezett munkafolyamat-jóváhagyással rendelkező rendelésekhez van társítva. Jóváhagyási munkafolyamat használata nélkül létrehozott rendelések állapota azonnal **Jóváhagyva** lesz.
-   **Külső ellenőrzés alatt** – Ez az állapot olyan esetekben használatos, amikor egy beszerzési értesítést küldenek a szállítónak, hogy a beszerzési rendelésen szereplő feltételeket megerősíthesse. Ez az állapot is használatban van a folyamat során, amelyet a **Megerősítés kérés** művelet kezdeményez. Ehhez a folyamathoz a szállítónak meg kell erősítenie a Beszerzési rendelés feltételeit a rendszerhez való kapcsolódással és a rendelés megerősítésének vagy elutasításának regisztrálásával.
-   **Megerősített** – Ez az állapot a rendelés megerősítése után kerül hozzárendelésre. Általában ez az állapot van hozzárendelve a rendelés utolsó jóváhagyási állapotához.


<a name="additional-resources"></a>További erőforrások
--------

[Beszerzési rendelés létrehozása](purchase-order-creation.md)

[Beszerzési rendelés jóváhagyása és visszaigazolása](purchase-order-approval-confirmation.md)

[Beszerzési rendelés - termékbevételezés](product-receipt-against-purchase-orders.md)

[Szállítói számlák áttekintése](../../financials/accounts-payable/vendor-invoices-overview.md)




