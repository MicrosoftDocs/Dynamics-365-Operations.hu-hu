---
title: Szállítmány beállítása
description: Ez a cikk bemutatja a bejövő bizományosi készletfolyamatok használatát.
author: yufeihuang
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ConsignmentDraftReplenishmentOrderJournal, ConsignmentProductReceiptLines, ConsignmentReplenishmentOrder, ConsignmentVendorPortalOnHand, InventJournalOwnershipChange, InventOnHandItemListPage, PurchTable, PurchTablePart, PurchVendorPortalConfirmedOrders, DirPartyTable, EcoResTrackingDimensionGroup, InventJournalName, InventOwner, InventTableInventoryDimensionGroups, VendTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 220834
ms.assetid: 3c9d6de4-45d4-459a-aef7-0d9ad2c22b3a
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 0087abebccca107a094a40d3e2d5a5de330532af
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9014909"
---
# <a name="set-up-consignment"></a>Szállítmány beállítása

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja a bejövő bizományosi készletfolyamatok használatát.

A bizományosi árukészlet olyan készlet, amely a szállító tulajdonában van, de a tárolása az Ön telephelyén történik. Ha készen áll a felhasználására vagy a készlet használatára, átveszi a készlet tulajdonjogát. Ez a cikk arról tartalmaz tájékoztatást, hogyan lehet ténylegesen fogadni a szállító által birtokolt aktuális készletet a főkönyvi tranzakciók létrehozása nélkül, és hogyan lehet elindítani azt a termelési folyamatot, amelyben a szállító tulajdonában álló készlet ténylegesen lefoglalható. és hogyan lehet a nyersanyag tulajdonosát megváltoztatni annak érdekében, hogy fel lehessen dolgozni a felhasználást a termelési rendelés feldolgozása részeként. Arra vonatkozóan is vannak információk, hogy a szállítók hogyan követhetik figyelemmel a készletük felhasználását a szállítói együttműködési felületén.

## <a name="overview-of-the-consignment-process"></a>A szállítmányozási folyamat áttekintése

Ebben a példában az USMF vállalat szállítmányozási szerződést köt az US-104 szállítóval M9211CI nyersanyagra vonatkozóan.

1. A szállítmány feltöltési rendelését manuálisan készíti el egy személy az USMF-nél a várható igény alapján. A rendelést az USA-104 szállítói hozza létre, és a MS9211CI cikkhez hozzáadódik egy sor.
1. A szállító tájékoztatást kap a várható szállításról. Erre az alábbi három módszer egyikével kerül sor:
    - Valaki, aki az USMF-nél dolgozik, elküldi a rendelési adatokat a szállítónak.
    - A szállító figyelemmel követheti a várható, rendelkezésre álló készletet a szállítói együttműködés felhasználói felületén.
    - Valaki, aki az USMF-nél dolgozik, szűri az **aktuális készlet** lapján lévő adatokat, hogy csak az USA-104 szállító rekordjai jelenjenek meg, ahol a bevételezés állapota **Megrendelve**, majd ezeket az adatokat elküldi a szállítónak.
1. A készlet leszállításra kerül az USA-104-től az USMF-nek.
1. Amikor az anyag megérkezik az USMF-hez, a szállítmány feltöltési rendelése frissül a termékbevételezéssel. Csak a szállító által birtokolt készlet tényleges mennyisége kerül rögzítésre. Nem jönnek főkönyvi tranzakciók, mert a készlet tulajdonosa továbbra is a szállító.
1. A szállító figyeli a tényleges, aktuális készlet frissítését a **Szállítmány aktuális készlete** lapon.
1. Most, hogy a tényleges készlet rendelkezésre áll, a termelési folyamat lefoglalja a szállító által birtokolt készletet, és elindítja a termelési rendelést azokra a késztermékekre vonatkozóan, amelyek felhasználják a M9211CI nyersanyagot.
1. Az aznapi termelés során felhasználandó, lefoglalt nyersanyagok tulajdonosa az US-104-ről az USMF-re változik. Ez a készlet tulajdonosának megváltozását vezető napló segítségével történik. Ez a folyamat olyan beszerzési rendeléseket hoz létre, ahol a **Származás** mező értékének beállítása **Szállítmány**.
1. A szállító figyeli a felhasználást (tulajdonjog-változás) a **Szállítmány-készletből érkezett áruk** oldalon, és kiállít egy számlát a két vállalat közötti megállapodások alapján.
1. A termelési folyamat felhasználja a nyersanyagot termelési kitárolási listán keresztül. A tényleges foglalás automatikusan frissül, és jelzi, hogy az aktuális készlet az USMF birtokában van.
1. Az US-104 által kiadott számla feldolgozásra kerül azon beszerzési rendelésekkel összevetve, amelyek automatikusan jöttek létre, amikor a készlettulajdonos-változási napló feldolgozásra került. A felhasznált készletre vonatkozó kifizetés megtörténik az US-104 szállítónak.

Az USMF további ismétlődő folyamatokat végez:

- A szállító által birtokolt készletnek a különböző raktárok közötti fizikai mozgatásának feldolgozása átviteli napló segítségével történik.
- A tényleges, rendelkezésre álló készlet egy **Cikkleltár** napló segítségével frissül. A leltárt a szállító is használhatja az aktuális készlet frissítésére, ha rendelkezik ehhez engedéllyel.

Az US-104 szállító figyelemmel követheti a frissítéseket a **Szállítmány aktuális készlete** oldal segítségével.

## <a name="consignment-replenishment-orders"></a>Bizományosi feltöltési rendelések

A szállítmány feltöltési rendelése olyan dokumentum, amely egy szállító által, bizonyos dátumintervallumon belül leszállítani kívánt készlettranzakciók kérésére és nyomon követésére szolgál. Ez megrendelt készletmennyiségeket létrehozásával történik. Általában ennek alapja az adott termékre vonatkozó előrejelzés és tényleges igény. A szállítmány feltöltési rendelése alapján leszállított készlet a szállító tulajdonában marad. Csak a termékeknek a fizikai átvételhez kapcsolódó birtokbavételének frissítése kerül rögzítésre, és ennek megfelelően nincsenek frissítések a főkönyvi tranzakciókban.

A **Tulajdonos** dimenzió segítségével lehet különválasztani azokat az információkat, melyek alapján megállapítható, hogy melyik készlet tulajdonosa a szállító, és melyiknek a fogadó jogi személy. A szállítmányfeltöltési megrendelési sorok állapota **Nyitott rendelés** mindaddig, amíg a sorok teljes mennyisége nincs leszállítva vagy érvénytelenítve. Amikor a teljes mennyiség leszállításra vagy érvénytelenítésre kerül, az állapot **Kész** értékre változik. A szállítmány feltöltési rendeléséhez kapcsolódó, tényleges, aktuális készletet egy regisztrálási folyamat és egy termék-bevételezési frissítési folyamat segítségével lehet rögzíteni. A regisztrációt a cikk érkeztetési eljárásának segítségével vagy a rendeléssorok manuális frissítésével lehet elvégezni. A termék-bevételezési frissítési folyamatot használják, a termékbevételezési naplóban létrejön egy rekord, amellyel nyugtázni lehet az áruk átvételét a szállítók számára.

[![Bizományosi feltöltési rendelések.](./media/consignment-replenishment-order.png)](./media/consignment-replenishment-order.png)

## <a name="inventory-ownership-change-journal"></a>Készlettulajdonos-változás naplója

A **készlettulajdonos-változási** napló arra szolgál, hogy rögzítse, amikor a bizományosi készlet tulajdonosa a szállítóról a felhasználó jogi személyre változik. Várhatóan nem jönnek létre készlettranzakciók a naplóhoz kapcsolódóan. Mint bármely készletnapló esetében ezt is azonosítani kell egy készletnapló-névvel. Ezeknek a neveknek a létrehozása a **készletnapló-nevek** lapon történik, és a **naplótípust** **tulajdonos módosítása** értékre kell állítani.

Csak olyan készlettranzakciók jönnek létre, amelyek a feladott naplóhoz kapcsolódnak. Mikor kerül feladásra a napló?

- A szállító által birtokolt készlet kiadása egy **Eladva** állapotú **Tulajdonos módosítása** hivatkozással történik.
- Megtörténik az aktuális készlet érkeztetése felhasználást végző jogi személyhez egy termékbevételezéssel frissített készlettranzakcióval, a beszerzési rendelésen. Ezzel a rendelés állapotát **Beérkezettre** állítja. A szállítmányhoz használt beszerzési rendelések **Származás** mezőjének beállítása **Szállítmány**.

A szállítmány beszerzési rendelésének soraiban szereplő mennyiséget nem lehet frissíteni a rendelés létrehozása után.

[![Készlettulajdonos változásnaplója.](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)

## <a name="vendor-collaboration-in-consignment-processes"></a>Szállítói együttműködés a szállítmányozási folyamatokban.

Ha az Ön szállítói a szállítói együttműködési felületet használják, ezt arra is felhasználhatják, hogy nyomon kövessék az Ön telephelyén lévő készlet felhasználását. A szállítói együttműködés felülete három oldallal rendelkezik a bejövő szállítmány folyamatához kapcsolódóan:

- **Beszerzési rendelések** **szállítmány-készlet felhasználása** - a szállítmányozási folyamat alapján megváltozott tulajdonjoghoz kapcsolódó beszerzési rendelés adatainak részleteit tünteti fel.
- **Szállítmány-készletből érkező termékek** - olyan cikkekről és mennyiségekről mutat információkat, amelyek termékbevételezése frissült a tulajdonjog megváltozásának folyamata során.
- **Az aktuális szállítmány készlete** - olyan szállítmányelemekről mutat információkat, amelyek várhatóan leszállításra kerülnek, és olyan cikkekről, amelyek már ténylegesen rendelkezésre állnak a vevő telephelyén.

A szállítóknak a szállítói együttműködés használatára való beállításával kapcsolatos további tudnivalókat lásd [a Szállítói együttműködési felhasználók kezelése csoportban](../procurement/manage-vendor-collaboration-users.md).

## <a name="inventory-owners"></a>Készlettulajdonosok

Fizikai bejövő bizományosi készlet rögzítéséhez meg kell határozni a szállító-tulajdonost. Ez a **készlettulajdonos** oldalon történik. Ha bejelöli a **szállítói számlát**, ezzel létrehozza a **Név** és **Tulajdonos** mezők alapértelmezett értékeit. Az a **tulajdonos** mezőben lévő érték látható a szállító számára, ezért érdemes úgy módosítani, hogy a szállítói számla nevei ne legyenek könnyen felismerhetők külső felhasználók számára. A **tulajdonos** mezőt lehet módosítani, de csak addig a pontig, amikor menti a **készlettulajdonos** rekordot. A **Név** mezőt a rendszer automatikusan beírja annak a félnek a neve alapján, akihez a szállítói számla hozzá van rendelve, és ez nem módosítható.

[![Készlettulajdonosok.](./media/inventory-owners.png)](./media/inventory-owners.png)

## <a name="tracking-dimension-group"></a>Nyomonkövetésidimenzió-csoport

A bizományosi folyamatokban használandó cikkeket társítani kell egy **nyomon követési dimenziócsoporttal**, ahol a **tulajdonos** dimenzió értéke **aktív**. A tulajdonos dimenzió esetében a **leltár** és a **pénzügyi készlet** opció mindig ki van választva. A **fedezeti terv dimenziónként** soha nincs bejelölve.

[![Nyomonkövetésidimenzió-csoport.](./media/tracking-dimension-group.png)](./media/tracking-dimension-group.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
