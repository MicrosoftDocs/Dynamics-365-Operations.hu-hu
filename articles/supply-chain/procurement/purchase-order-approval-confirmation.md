---
title: Beszerzési rendelések jóváhagyása és megerősítése
description: Ez a témakör ismerteti azokat az állapotokat, amiken keresztül megy a beszerzési rendelés létrehozás után, valamint a változáskezelés hatásait a beszerzési rendelésre.
author: kamaybac
ms.date: 04/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchOrderInReview, PurchOrderApproved, PurchOrderInDraft, PurchOrderAssignedToMe, VendPurchOrderJournalListPage, PurchTableWorkflowDropDialog, VendPurchOrderJournal
audience: Application User
ms.reviewer: kamaybac
ms.custom: 93143
ms.assetid: cd12a944-c52c-4579-a301-7abe1d237c72
ms.search.region: Global
ms.search.industry: ''
ms.author: dabourq
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 580095bacafe74c9e22aba47ca657e1cf42b3c6ae7929478a0d2f8bd241868f1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6780126"
---
# <a name="approve-and-confirm-purchase-orders"></a>Beszerzési rendelések jóváhagyása és megerősítése

[!include [banner](../includes/banner.md)]

Ez a témakör ismerteti azokat az állapotokat, amiken keresztül megy a beszerzési rendelés létrehozás után, valamint a változáskezelés hatásait a beszerzési rendelésre.

Miután a beszerzési rendelés létre lett hozva, lehet, hogy át kell esnie egy jóváhagyási folyamaton. Miután a szállító elfogadta a rendelést, a beszerzési rendelés állapota **Megerősítve** lesz.

## <a name="approval-of-purchase-orders"></a>A beszerzési rendelések jóváhagyása
Azok a beszerzési rendelések, amelyek nem használják a változáskezelést, azoknak az állapota létrehozás után **Jóváhagyva** lesz, míg a változáskezelést használó beszerzési rendelések létrehozás után **Vázlat** állapotúak. Az a beszerzési rendelés, amely az alaptervezés során egy tervezett rendelés megerősítéséből jön létre, azonnal **Jóváhagyva** állapotú lesz, a változáskezelési beállításoktól függetlenül. A beszerzési rendelés csak akkor hoz létre készlettranzakciót, ha eléri a **Jóváhagyva** állapotot. Ezért az a készlet nem lesz elérhető a foglalásoknál vagy jelöléseknél, amíg a rendelés nem lesz elfogadva.

Engedélyezheti a változáskezelést a beszerzési rendelésekhez a **Változáskezelés aktiválása** beállításával a **Beszerzési és forrásparaméterek** lapon. Ha a változáskezelés engedélyezve van, a beszerzési rendelésnek, elkészítés után, végig kell haladnia egy jóváhagyási munkafolyamaton. A Supply Chain Management rendelkezik olyan munkafolyamat-szerkesztővel, ami segít felállítani egy munkafolyamatot a jóváhagyási folyamathoz. Ez a munkafolyamat tartalmazhat szabályokat az automatikus jóváhagyáshoz, szabályokat, amelyek meghatározzák, hogy ki lesz hozzárendelve egy bizonyos beszerzési rendeléshez, valamint olyan szabályokat, amik eszkalálják azokat a munkafolyamatokat, amik már régóta jóváhagyásra várnak. A változáskezelési folyamatot engedélyezheti az összes szállítóhoz, vagy csak bizonyos szállítókhoz. Beállíthatja úgy is a folyamatot, hogy az minden beszerzési rendelés esetében felülírható legyen.

Ha a változáskezelés engedélyezve van, a beszerzési rendelések 6 jóváhagyási állapoton mennek keresztül, kezdve a **Vázlat** állapottól, a **Véglegesítve** állapotig. Miután egy rendelés jóvá lett hagyva, azoknak a felhasználóknak, akik módosítani szeretnék, a **Változtatás kérése** művelet kell használniuk.

| Jóváhagyási állapot | Leírás                                                                      | Változtatás kérése engedélyezve |
|-----------------|----------------------------------------------------------------------------------|---------------------------|
| Vázlat           | A beszerzési rendelés még csak vázlat, illetve nem lett benyújtva jóváhagyásra a beszerzési rendelés munkafolyamatában.     | Nem                        |
| Ellenőrzés alatt       | A beszerzési rendelés el lett küldve jóváhagyásra a beszerzési rendelés munkafolyamatában. Jóváhagyásra vár.       | Szám                        |
| Elutasítva        | A beszerzési rendelés el lett utasítva a jóváhagyási folyamat során.                                 | Szám                        |
| Engedélyezve        | A beszerzési rendelés jóvá lett hagyva.                                                             | Igen                       |
| Visszaigazolva       | A beszerzési rendelés megerősítve. A beszerzési rendelés nem erősíthető meg, amíg jóvá nem hagyták.        | Igen                       |
| Véglegesítve       | A beszerzési rendelés véglegesítve lett. Pénzügyileg lezárult, és már nem módosítható. | Nem                        |

## <a name="confirming-purchase-orders"></a>Beszerzési rendelések megerősítése
Azok a beszerzési rendelések, amik **Jóváhagyva** állapotúak, további lépéseken is áteshetnek, mielőtt meg lesznek erősítve. Például, ha egy beszerzési értesítést kell küldeni a szállítónak, hogy lekérdezze az árakat, kedvezményeket és a szállítási dátumokat. Ebben az esetben a beszerzési rendelést **Külső ellenőrzés alatt** állapotúra módosíthatja a **Beszerzési értesítő** művelet segítségével.

Azok a szállítók, akik a szállítói portált használják, áttekintheti a rendeléseket, majd jóváhagyhatják vagy elutasíthatják azokat. Ez alatt az áttekintési folyamat alatt a beszerzési rendelés **Külső ellenőrzés alatt** állapotú. A szállítói portál konfigurálható, így a szállítótól érkező visszaigazolás automatikusan megerősíti a rendelést a Supply Chain Management rendszerben. Másik megoldásként megerősíthet egy beszerzési rendelést manuálisan is, miután megkapta a megerősítést a szállítótól. Ha a szállító elutasítja a beszerzési rendelést, az elutasítás az indoklással, valamint a változtatási javaslattal kerül kézbesítésre. Ebben az esetben a beszerzési rendelés állapota továbbra is **Külső ellenőrzés alatt** lesz.

A pro-forma megerősítés generálására is van lehetőség, olyan megrendeléshez, amihez még nem készült aktuális megerősítés. Ez a beállítás olyan jelentést hoz létre, amit megoszthat a szállítóval. Ez nem hoz létre napló adatokat.

Miután a szállító jóváhagyta a megrendelést, a következő lépés a beszerzési rendelés vállaltként való rögzítése. Ez vagy a **Megerősítés**, vagy a **Megerősít** művelettel végezheti el. Mind a két művelet **Megerősítve** állapotra módosítja a megrendelést. A megrendelés megerősítése további két folyamatot indít el:

-   Létrejön egy napló, ami tárolja a rendszerben megerősítettek pontos másolatát. A megrendeléseket néha módosítani kell, ezért további naplók jönnek létre, miután a frissített rendelés megerősítést nyer. Ezek a naplók teszik lehetővé a korábbi verziójú megerősített megrendelés előzményének a megtekintését.
-   Létrejön a könyvelési felosztás, valamint rendelési és költségvetési ellenőrzések történnek, ha ez a funkció engedélyezve van. Ha valamelyik ellenőrzés sikertelen, megjelenhet egy hibaüzenet arról, hogy módosításokat kell végezni a beszerzési rendelésen, mielőtt újra megerősítik.

A szállító kérhet valamilyen biztosítást afelől, hogy a vásárlás ki lesz fizetve. A Kötelezettségeken belül több, különböző lehetőség is van a fizetés biztosítására. Például az **Előleg** művelet fenntart pénzalapot a beszerzési rendelés számára, valamint ez fel is van jegyezve a beszerzési rendelésnél.

## <a name="changing-purchase-orders"></a>Beszerzési rendelés megváltoztatása
Bizonyos esetekben lehet, hogy meg kell változtatni egy beszerzési rendelést, miután elérte a **Jóváhagyott** vagy a **Megerősítve** állapotot.

Ha a beszerzési rendelés a változás-kezelési folyamat segítségével lett létrehozva, a rendelés visszahívásával eszközölhet változtatásokat, valamint ha a rendelés már jóvá lett hagyva, akkor a **Változtatás kérése** művelettel teheti ezt meg. Ebben az esetben a megrendelés visszakerül **Vázlat** állapotba, és ezután módosíthatja a rendelést. Miután befejezte a módosításokat, benyújthatja a beszerzési rendelést újbóli jóváhagyásra. A **Beszerzési rendelések ismételt jóváhagyási szabálya** irányelv segítségével a **Beszerzési irányelvek** oldalon beállíthatja azokat a változtatásokat, ami miatt újbóli jóváhagyásra van szükség

Miután a megrendelt mennyiség egy része már ki lett szállítva, nem változtathatja meg a rendelés mennyiségét, amikor a beszerzési rendelés **Vázlat** állapotban van. Ugyanakkor módosíthatja a **Fennmaradó szállítása** mennyiséget annak a beszerzési rendelésnek a sorában, amely **Vázlat** állapotban van.

Miután egy rendelés meg lett erősítve, nem törölheti azt. Azonban érvénytelenítheti a teljes vagy a fennmaradó mennyiséget, feltéve, hogy a mennyiség még nem lett átvéve vagy számlázva. Ezután a **Véglegesítés** művelet segítségével megakadályozhatja a további feldolgozást. 


## <a name="canceling-purchase-orders"></a>Beszerzési rendelések érvénytelenítése

A beszerzési rendelést a fejléc **Érvénytelenítés** műveletével lehet érvényteleníteni.

Ha a mennyiség részben regisztrálva, bevételezve vagy számlázva van, akkor csak a fennmaradó nem regisztrált, bevételezett vagy számlázott maradék mennyiséget lehet érvényteleníteni. Ezt követően a rendelési mennyiség ennek megfelelően csökkentve lesz. Amikor a sorban szereplő mennyiség frissítve van, az állapot is frissül. Például a sorban szereplő eredeti mennyiség 5, és 3 érkezik be. Ebben az esetben csak kettőt lehet érvényteleníteni. A sor ezután a **Fogadott** állapotra módosul.

Ha szállítási maradékot ad hozzá a rendelési sorhoz, és az meghaladja a rendelési sorban szereplő mennyiséget, akkor az **Érvénytelenítés** művelet nem érvényteleníti a felesleges mennyiséget. Helyette a sor **Nyitott rendelés** állapotú marad, mert a fennmaradó mennyiség még rajta van. Például a sorban szereplő eredeti mennyiség 5, és szállítási maradék 7. Ha a rendelést érvénytelenítették, akkor öt érvénytelenítve van, és a 2 marad, amint az látható a készlettranzakciók között.

Ha érvényteleníteni szeretné vonni a beszerzésirendelés-sorban szereplő teljes mennyiséget, érvénytelenítse a sorban szereplő szállítási maradék mennyiségét is. Ezt követően a sor **Visszavonva** állapotra frissül.

Ha egy beszerzési rendelés változáskezelés alatt van, akkor bármilyen változtatást, például a rendelés érvénytelenítését vagy a szállítás fennmaradó részét be kell nyújtani a munkafolyamat-rendszernek, és jóvá kell hagyni a folyamat befejezése előtt, és a készlettranzakciók frissíthetők érvénytelenítettre.

## <a name="additional-resources"></a>További erőforrások

[Beszerzési rendelések áttekintése](purchase-order-overview.md)

[Beszerzési rendelések létrehozása](purchase-order-creation.md)

[Termékbevételezés összevetése a beszerzési rendelésekkel](product-receipt-against-purchase-orders.md)

[Szállítói számlák áttekintése](../../finance/accounts-payable/vendor-invoices-overview.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]