---
title: "Jóváhagyása és a beszerzési rendelések megerősítése"
description: "Ez a cikk ismerteti azokat az állapotokat, amiken keresztül megy a beszerzési rendelés létrehozás után, valamint a változáskezelés hatásait a beszerzési rendelésre."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PurchTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 93143
ms.assetid: cd12a944-c52c-4579-a301-7abe1d237c72
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: b16092454e9637e628c8481bc471d86cf3be7bf6
ms.lasthandoff: 03/31/2017


---

# <a name="approve-and-confirm-purchase-orders"></a>Jóváhagyása és a beszerzési rendelések megerősítése

Ez a cikk ismerteti azokat az állapotokat, amiken keresztül megy a beszerzési rendelés létrehozás után, valamint a változáskezelés hatásait a beszerzési rendelésre.

Miután a beszerzési rendelés létre lett hozva, lehet, hogy át kell esnie egy jóváhagyási folyamaton. Miután a szállító elfogadta a rendelést, a beszerzési rendelés állapota **Megerősítve** lesz.

## <a name="approval-of-purchase-orders"></a>A beszerzési rendelések jóváhagyása
Azok a beszerzési rendelések, amelyek nem használják a változáskezelést, azoknak az állapota létrehozás után **Jóváhagyva** lesz, míg a változáskezelést használó beszerzési rendelések létrehozás után **Vázlat** állapotúak. Az a beszerzési rendelés, amely az alaptervezés során egy tervezett rendelés megerősítéséből jön létre, azonnal **Jóváhagyva** állapotú lesz, a változáskezelési beállításoktól függetlenül. A beszerzési rendelés csak akkor hoz létre készlettranzakciót, ha eléri a **Jóváhagyva** állapotot. Ezért az a készlet nem lesz elérhető a foglalásoknál vagy jelöléseknél, amíg a rendelés nem lesz elfogadva.  

Engedélyezheti a változáskezelést a beszerzési rendelésekhez a **Változáskezelés aktiválása** beállításával a **Beszerzési és forrásparaméterek** lapon. Ha a változáskezelés engedélyezve van, a beszerzési rendelésnek, elkészítés után, végig kell haladnia egy jóváhagyási munkafolyamaton. A Microsoft Dynamics 365 for Operations rendszer rendelkezik olyan munkafolyamat-szerkesztővel, ami segít felállítani egy munkafolyamatot a jóváhagyási folyamathoz. Ez a munkafolyamat tartalmazhat szabályokat az automatikus jóváhagyáshoz, szabályokat, amelyek meghatározzák, hogy ki lesz hozzárendelve egy bizonyos beszerzési rendeléshez, valamint olyan szabályokat, amik eszkalálják azokat a munkafolyamatokat, amik már régóta jóváhagyásra várnak. A változáskezelési folyamatot engedélyezheti az összes szállítóhoz, vagy csak bizonyos szállítókhoz. Beállíthatja úgy is a folyamatot, hogy az minden beszerzési rendelés esetében felülírható legyen.  

Ha a változáskezelés engedélyezve van, a beszerzési rendelések 6 jóváhagyási állapoton mennek keresztül, kezdve a **Vázlat** állapottól, a **Véglegesítve** állapotig. Miután egy rendelés jóvá lett hagyva, azoknak a felhasználóknak, akik módosítani szeretnék, a **Változtatás kérése** művelet kell használniuk.

| Jóváhagyási állapot | Leírás                                                                      | Változtatás kérése engedélyezve |
|-----------------|----------------------------------------------------------------------------------|---------------------------|
| Vázlat           | A beszerzési rendelés még csak vázlat, illetve nem lett benyújtva jóváhagyásra a beszerzési rendelés munkafolyamatában.     | Szám                        |
| Ellenőrzés alatt       | A beszerzési rendelés el lett küldve jóváhagyásra a beszerzési rendelés munkafolyamatában. Jóváhagyásra vár.       | Szám                        |
| Elutasítva        | A beszerzési rendelés el lett utasítva a jóváhagyási folyamat során.                                 | Szám                        |
| Engedélyezve        | A beszerzési rendelés jóvá lett hagyva.                                                             | Igen                       |
| Visszaigazolva       | A beszerzési rendelés megerősítve. A beszerzési rendelés nem erősíthető meg, amíg jóvá nem hagyták.        | Igen                       |
| Véglegesítve       | A beszerzési rendelés véglegesítve lett. Pénzügyileg lezárult, és már nem módosítható. | Szám                        |

## <a name="confirming-purchase-orders"></a>Beszerzési rendelések megerősítése
Azok a beszerzési rendelések, amik **Jóváhagyva** állapotúak, további lépéseken is áteshetnek, mielőtt meg lesznek erősítve. Például, ha egy beszerzési értesítést kell küldeni a szállítónak, hogy lekérdezze az árakat, kedvezményeket és a szállítási dátumokat. Ebben az esetben a beszerzési rendelést **Külső ellenőrzés alatt** állapotúra módosíthatja a **Beszerzési értesítő** művelet segítségével.  

Azok a szállítók, akik a szállítói portált használják, áttekintheti a rendeléseket, majd jóváhagyhatják vagy elutasíthatják azokat. Ez alatt az áttekintési folyamat alatt a beszerzési rendelés **Külső ellenőrzés alatt** állapotú. A szállítói portál konfigurálható, így a szállítótól érkező visszaigazolás automatikusan megerősíti a rendelést a Dynamics 365 for Operations rendszerben. Másik megoldásként megerősíthet egy beszerzési rendelést manuálisan is, miután megkapta a megerősítést a szállítótól. Ha a szállító elutasítja a beszerzési rendelést, az elutasítás az indoklással, valamint a változtatási javaslattal kerül kézbesítésre. Ebben az esetben a beszerzési rendelés állapota továbbra is **Külső ellenőrzés alatt** lesz.  

A pro-forma megerősítés generálására is van lehetőség, olyan megrendeléshez, amihez még nem készült aktuális megerősítés. Ez a beállítás olyan jelentést hoz létre, amit megoszthat a szállítóval. Ez nem hoz létre napló adatokat.  

Miután a szállító jóváhagyta a megrendelést, a következő lépés a beszerzési rendelés vállaltként való rögzítése. Ez vagy a **Megerősítés**, vagy a **Megerősít** művelettel végezheti el. Mind a két művelet **Megerősítve** állapotra módosítja a megrendelést. A megrendelés megerősítése további két folyamatot indít el:

-   Létrejön egy napló, ami tárolja a rendszerben megerősítettek pontos másolatát. A megrendeléseket néha módosítani kell, ezért további naplók jönnek létre, miután a frissített rendelés megerősítést nyer. Ezek a naplók teszik lehetővé a korábbi verziójú megerősített megrendelés előzményének a megtekintését.
-   Létrejön a könyvelési felosztás, valamint rendelési és költségvetési ellenőrzések történnek, ha ez a funkció engedélyezve van. Ha valamelyik ellenőrzés sikertelen, megjelenhet egy hibaüzenet arról, hogy módosításokat kell végezni a beszerzési rendelésen, mielőtt újra megerősítik.

A szállító kérhet valamilyen biztosítást afelől, hogy a vásárlás ki lesz fizetve. A Kötelezettségeken belül több, különböző lehetőség is van a fizetés biztosítására. Például az **Előleg** művelet fenntart pénzalapot a beszerzési rendelés számára, valamint ez fel is van jegyezve a beszerzési rendelésnél.

## <a name="changing-purchase-orders"></a>Beszerzési rendelés megváltoztatása
Bizonyos esetekben lehet, hogy meg kell változtatni egy beszerzési rendelést, miután elérte a **Jóváhagyott** vagy a **Megerősítve** állapotot.  

Ha a beszerzési rendelés a változás-kezelési folyamat segítségével lett létrehozva, a rendelés visszahívásával eszközölhet változtatásokat, valamint ha a rendelés már jóvá lett hagyva, akkor a **Változtatás kérése** művelettel teheti ezt meg. Ebben az esetben a megrendelés visszakerül **Vázlat**állapotba, és ezután módosíthatja a rendelést. Miután befejezte a módosításokat, benyújthatja a beszerzési rendelést újbóli jóváhagyásra. A **Beszerzési rendelések ismételt jóváhagyási szabálya** irányelv segítségével a **Beszerzési irányelvek** oldalon beállíthatja azokat a változtatásokat, ami miatt újbóli jóváhagyásra van szükség  

Miután a megrendelt mennyiség egy része már ki lett szállítva, nem változtathatja meg a rendelés mennyiségét. Azonban módosíthatja a **Fennmaradó szállítása** sorban szereplő mennyiséget. Ezután a **Véglegesítés** művelet segítségével érvénytelenítheti a sorokat és megakadályozhatja a további feldolgozást. 

Miután egy rendelés meg lett erősítve, nem törölheti azt. Azonban érvénytelenítheti a teljes vagy a fennmaradó mennyiséget, feltéve, hogy a mennyiség még nem lett átvéve vagy számlázva.

<a name="see-also"></a>Lásd még
--------

[Purchase order overview](purchase-order-overview.md)

[Purchase order creation](purchase-order-creation.md)

[Beszerzési rendelés - termékbevételezés](product-receipt-against-purchase-orders.md)

[Szállítói számlák áttekintése](/dynamics365/operations/financials/accounts-payable/vendor-invoices-overview)


