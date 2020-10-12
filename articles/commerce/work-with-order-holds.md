---
title: Hívásközpont rendeléseinek várakoztatása - beállítás és használat
description: Ez a témakör a várakoztatott rendelések használatát ismerteti a Dynamics 365 Commerce rendszerben.
author: josaw1
manager: AnnBe
ms.date: 05/14/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: MCRHoldCodeTable, MCRSalesTableOrderHistory, MCRHoldCodeTrans, MCROrderEventSetup, MCROrderEventTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: b11dd48ac629910a82b4d5bfdf9889809b0d829d
ms.sourcegitcommit: 54da65a7da0efd4f0d9760c5b14ff785b28751c4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/22/2020
ms.locfileid: "3830123"
---
# <a name="configure-and-work-with-call-center-order-holds"></a>Hívásközpont rendeléseinek várakoztatása – konfigurálás és használat

[!include [banner](includes/banner.md)]

Ez a témakör azokat a rendelésvárakoztatási funkciókat ismerteti, amelyek a Dynamics 365 Commerce alkalmazásban találhatók a hívásközpont rendeléseihez.

## <a name="configuring-call-center-order-holds"></a>Hívásközpont rendeléseinek várakoztatása - konfigurálás

A hívásközpont rendelésvárakoztatási funkcióinak használatához először definiálnia kell a várakoztatási kódokat. Felhasználó által definiált - az üzlet szükségletei szerinti - várakoztatási kódok létrehozásához lépjen ide: **Értékesítés és marketing**\>**Beállítási**\>**Értékesítési rendelések**\>**Rendelésvárakoztatási kódok**. Tetszés szerint megjelölheti a várakoztatási kódok egyikét alapértelmezett várakoztatási kódként; ehhez állítsa az **Értékesítési rendelés alapértelmezése** lehetőséget **Igenre**. Ezt a várakoztatási kódot használja a rendszer mindig, amikor egy értékesítési rendelést várakoztatnak. Ha egy értékesítési rendeléshez készlet van lefoglalva, és a foglalásokat automatikusan el kell távolítani, ha a rendelést valamilyen meghatározott oknál fogva várakoztatják, a **Készletfoglalások eltávolítása** lehetőséget állítsa **Igenre** az okkódoknál.

Ahhoz, hogy meghatározza annak a megjegyzésnek a típusát, amelyet a rendszer rögzít, amikor a felhasználók - akik egy értékesítési rendelést várakoztatnak - opcionálisan beírnak egy megjegyzést, lépjen ide: **Kinnlevőségek**\>**Beállítás**\>**Kinnlevőségek paraméterei**, majd az **Értékesítés beállítása** gyorslapon, az **Általános** fülön végezze el a **Megjegyzés típusa** mező beállítását. A **Várakoztatott értékesítési rendelés állapota** mezőben jelölje ki azt a színt, amellyel a várakoztatott értékesítési rendelések kiemelésre kerülnek, amikor megjelennek az **Ügyfélszolgálat** oldalon.

Opcionális várakoztatási okkódok létrehozásához lépjen ide: **Retail és Commerce**\>**Csatorna beállítása**\>**Infókódok**. Ezeket az infókódokat másodlagos okkódokként lehet használni a fő várakoztatási kód további meghatározásához. Okkód-készlet létrehozásához válassza ki az **Új** lehetőséget, majd jelölje be az **Alkódok** lehetőséget a további okok listájának meghatározásához. Ahhoz, hogy valamely definiált infókódot a hívásközponti csatornához rendeljen, lépjen ide: **Retail és Commerce**\>**Csatornák**\>**Hívásközpontok**\>**Összes hívásközpont**. Az **Általános** gyorslapon állítsa be a **Várakoztatási kód** mezőt.

## <a name="putting-orders-on-hold"></a>Rendelések várakoztatása

Azokat a rendeléseket, amelyeket a hívásközpont felhasználói hoznak létre a háttérirodai Commerce programban, manuálisan lehet várakoztatni, vagy – konkrét helyzetekben – automatikusan.

Rendelésbevitel során, de a rendelés benyújtása és a megerősítés előtt előfordulhat, hogy a hívásközpont felhasználói manuálisan akarnak egy rendelést várakoztatni, és megakadályozni, hogy az kiadásra kerüljön a raktárba további feldolgozásra. Például a vevő, aki leadja a rendelést még nem áll készen annak véglegesítésére, vagy a rendelés feldolgozásához szükséges alapvető adatok nem állnak rendelkezésre.

A rendelésbeviteli oldalon a hívásközpont felhasználója várakoztatott állapotúra állíthat egy rendelést a **Rendelések várakoztatása** lehetőséggel, a rendelésbeviteli menü **Értékesítési rendelés** lapján. Másik lehetőségként a felhasználó kiválaszthatja a **Várakoztatás** menüelemet az **Értékesítési rendelés összesítése** oldalon, amely akkor jelenik meg, amikor a felhasználó kiválasztja a **Kész** lehetőséget a hívásközpont értékesítési rendelésén.

Mindkét esetben megjelenik a **Rendelések várakoztatása** lap. A felhasználó ezután kiválaszthatja az **Új** lehetőséget a rendelés várakoztatásának létrehozásához. A **Várakoztatási kód** mezőben a felhasználónak ki kell választania azt a kódot, amely a legjobban leírja a várakoztatás okát. Az **Okkód** mezőben a felhasználó tetszés szerint kiválaszthat egy további okkódot, hogy a várakoztatáshoz egy második szintű leírást is biztosítson.

A **Megjegyzések** gyorslapon, a **Várakoztatási megjegyzések** mezőben a felhasználó további, szabad szöveges megjegyzéseket adhat meg, hogy kiegészítő háttérinformációkat vagy adatokat biztosítson a várakoztatással kapcsolatban. Ezek a megjegyzések segíthetnek más felhasználóknak, akik később áttekintik a várakoztatott rendelést vagy dolgoznak vele.

Miután a várakoztatási adatokat bevitték és mentették, a felhasználó bezárhatja a **Rendelések várakoztatása** oldalt. A felhasználó ekkor visszakerül az értékesítési rendelés beviteli lapjára. Ha nincs szükség további műveletekre az értékesítési rendelésnél, a felhasználó bezárhatja az értékesítési rendelés beviteli lapját.

Ha a **Rendeléskiegészítés engedélyezése** megjelölés be van kapcsolva a hívásközponti csatornában, nem kell kifizetést alkalmazni egy rendeléshez, amely várakoztatott állapotban van. Ezzel szemben a nem várakoztatott értékesítési rendelések esetében a felhasználók nem hagyhatják az értékesítési rendelés beviteli lapját üresen mindaddig, amíg nem kerül sor fizetés alkalmazására. Természetesen a fizetés el kell végezni, mielőtt a rendelés várakoztatása fel lesz oldva.

A hívásközpont felhasználói ezenkívül a valamilyen okból gyanús rendeléseket manuálisan is várakoztathatják csalás miatt. A rendelések automatikusan is várakoztathatók, amikor egyezést mutatnak az aktív csalási feltételekkel és szabályokkal. További tájékoztatás az ilyen típusú rendelés várakoztatásának kapcsolatban itt található [csalásellenőrzési figyelmeztetések beállítása](https://docs.microsoft.com/dynamics365/unified-operations/retail/set-up-fraud-alerts).

## <a name="viewing-and-managing-orders-that-are-on-hold"></a>Várakoztatott rendelések megtekintése és kezelése

### <a name="viewing-hold-information-for-a-single-sales-order"></a>Egyetlen értékesítési rendelés várakoztatási adatainak megtekintése

Az **Ügyfélszolgálat** lapon a felhasználók vizuálisan azonosíthatják a várakoztatott rendeléseket, mert a rendelési sorok egy adott színben jelennek meg. Ezt a színt a **Várakoztatott értékesítési rendelés állapota** mező határozza meg a **Kinnlevőségek paraméterei** oldalon.

> [!NOTE]
> Ha a sort kiválasztják a lapon, a kiemelés színe nem látható.

A felhasználók megtekinthetik egy értékesítési rendelés részletes állapotadatait is, amelyből megtudhatják, hogy az várakoztatva van-e. A részletes állapotadatok a **Minden értékesítési rendelés** vagy az **Ügyfélszolgálat** oldalon érhetők el. Ha egy megrendelés várakoztatott állapotban van, be van állítva hozzá a **Feldolgozni tilos** megjelölés, és a **Részletes állapot** mezőben a **Várakoztatott** vagy **Csalásvárakoztatás** állapot látható az adott esettől függően.

Az egyes rendelési várakoztatások részletes adatainak megtekintéséhez a felhasználó megnyithatja a **Rendelés várakoztatása** lap részletes nézetét az **Ügyfélszolgálat** lapon, a kiválasztott rendelésre vonatkozó **Lehetőségek** menü segítségével. A felhasználók ezt a nézetet a **Minden értékesítési rendelés** lapon is elérhetik; ehhez ki kell jelölni a **Várakoztatott rendelések** menüelemet az **Értékesítési rendelés** lapon.

### <a name="viewing-all-orders-that-are-on-hold"></a>Az összes várakoztatott rendelés megtekintése

A manuális vagy automatikus várakoztatású összes rendelés megtekintéséhez lépjen ide: **Retail és Commerce**\>**Vevők**\>**Várakoztatott rendelések**.

A **Várakoztatott rendelések** munkaterület tartalmaz egy listát minden olyan rendelésről, amely várakoztatott állapotban van manuális vagy csalásivárakoztatási műveletek következtében. A lapon rendelkezésre álló szokásos szűrési és rendezési lehetőségek segítségével a felhasználók olyan nézeteket hozhatnak létre, amelyek lehetővé teszik, hogy bizonyos - a felelősségi körükbe tartozó - várakoztatási kódokkal dolgozzanak vagy azokat kezeljék. A **Várakoztatott rendelések** munkaterület azt is jelzi, hogy a rendelés hány napja várakozik. Ezek az információk segítenek a felhasználóknak a várólista prioritásának meghatározásában.

A várakoztatott rendelések részletesebb nézetének megtekintéséhez a felhasználók rákattinthatnak a menü **Rendelés várakoztatása** lehetőségére. Ez a nézet tájékoztatást ad a vevőről, valamint a rendeléshez, a vevőhöz vagy a várakoztatási művelethez fűzött esetleges megjegyzésekről. A nézet az automatikus várakoztatás okával kapcsolatban is tartalmaz részleteket, ha a rendelést azért állították várakoztatott állapotba, mert egyezést mutatott egy csalásellenőrzési szabállyal.

A **Várakoztatott rendelések** oldal listanézete és részletes nézete segítségével a felhasználók megtekinthetik vagy szerkeszthetik a rendeléshez kapcsolódó információkat, például a kifizetéseket, végösszegeket és feljegyzéseket.

A **várakoztatási pénztár** lapon lévő lehetőségek akkor lehetnek hasznosak, ha a vállalat több felhasználója egyidejűleg dolgozik a várakoztatási listával. A **Kivétel** lehetőség bejelölésével a felhasználók jelezhetik, hogy a várakoztatott rendelés áttekintésén és ellenőrzésén dolgoznak. Ezzel a módszerrel más felhasználók nem veszítenek időt azzal, hogy ugyanazt a munkát próbálják elvégezni. A **Várakoztatott rendelések** lap részletes nézetének segítségével a felhasználók megtekinthetik a kivétel dátumára és idejére vonatkozó információkat, valamint azt, hogy melyik felhasználó vette ki a várakoztatott bejegyzést.

Miután egy várakoztatott bejegyzést kivesznek, a kivételt csak az a felhasználó törölheti, aki a kivételt végezte. Ez a korlátozás megakadályozza meg, hogy a felhasználók olyan bejegyzéseket vegyenek elő, amelyen más felhasználók már dolgoznak. Ahhoz, visszategyen egy rendelést a várólistára, hogy azzal más felhasználók is dolgozhassanak, a felhasználónak, aki kivette a bejegyzést, ki kell választania a **Kivétel törlése** lehetőséget.

> [!NOTE]
> A várakoztatás nem kerül feloldásra, amikor a kivételt törlik.

Bizonyos esetekben, például amikor egy felhasználó betegszabadságon van vagy már nem dolgozik a vállalatnál, előfordulhat, hogy az ennek a felhasználónak kivett bejegyzéseket egy másik felhasználóhoz kell hozzárendelni. A bejegyzéseket egy vezető adhatja át a **Kivétel felülbírálása** lehetőség segítségével.

## <a name="releasing-orders-that-are-on-hold"></a>Az összes várakoztatott rendelés feloldása

A **Várakoztatott rendelések** oldal listanézetén és részletes nézetén egyaránt a **Várakoztatás törlése** lap tartalmazza azokat a beállításokat, amelyek segítségével törölhető egy rendelés várakoztatása. A **Várakoztatások törlése** lehetőség segítségével lehet kivenni a rendelést a kiválasztott várakoztatási kódból.

A hívásközpont rendeléseihez fizetésre van szükség. Ezért a várakoztatás nem teljesen törölhető, ha a rendeléshez nem alkalmaztak fizetést. A **Hívásközponti paraméterek** oldalon, a **Várakoztatás** lapon, győződjön meg róla, hogy a **Küldés törléskor** paraméter be van kapcsolva. Ennek a beállításnak a segítségével garantálható, hogy a törölt várakoztatás után a rendelés a megfelelő sorrendben megy végig a megrendelési műveleteken a kifizetés ellenőrzéséhez és engedélyezéséhez. Ha a kifizetések hiányoznak, a felhasználó hibaüzenetet kap, és a várakoztatási kód nem törlődik.

Ha a **Küldés törléskor** paraméter nincs beállítva, a felhasználóknak ki kell választania a **Törlés és küldés** beállítást a **Várakoztatás törlése** menüben; ezzel biztosítja, hogy a rendelés végigmegy az összes szükséges kifizetési ellenőrzésen. Ha a rendelés benyújtása sikertelen, amikor a **Rendeléskiegészítés engedélyezése** megjelölés van kapcsolva a hívásközponti csatornán, akkor a rendelés várakoztatott állapota megszűnik, de a **Tilos feldolgozni** megjelölés megmarad. Ennek megfelelően a rendelés nem kerül kiadásra a raktárba, amíg nem kerül sor a megfelelő kifizetések alkalmazására és ellenőrzésére.

Ha felhasználók törölni akarják a várakoztatást, de további módosításokat akarnak végezni a rendelésen, mielőtt az kiadásra kerül további feldolgozásra, kiválaszthatják a **Törlés és módosítás** lehetőséget. Ez a beállítás eltávolítja a várakoztatási kódot, és megnyitja az értékesítési rendelés részleteit, hogy a felhasználók további módosításokat végezhessenek a rendelésen. A felhasználók ugyancsak alkalmazhatják a kifizetést és benyújthatják az értékesítési rendelést, hogy az végigmenjen a fizetés-ellenőrzési logika lépésein, amikor a **Rendeléskiegészítés engedélyezése** megjelölés be van kapcsolva a hívásközponti csatornán.

## <a name="reporting-options"></a>Jelentési funkciók

Ahhoz, hogy jelentést készítsen a várakoztatott rendelésekről a dátumtartomány, várakoztatási kód vagy egyéb kapcsolódó feltételek alapján, lépjen ide: **Retail és Commerce**\>**Lekérdezések és jelentések**\>**Hívásközponti jelentések**\>**Rendelésvárakoztatási jelentések**.
