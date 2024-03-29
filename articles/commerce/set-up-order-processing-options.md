---
title: Hívásközponti csatornák beállítása
description: Ez a cikk a hívásközponti rendeléseknek a használatával való feldolgozásával kapcsolatban tartalmaz tájékoztatást Dynamics 365 Commerce.
author: josaw1
ms.date: 02/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MCROrderParameters, MCRSalesTableOrderHistory, SalesOrderProcessingWorkspace
audience: Application User
ms.reviewer: josaw
ms.custom: 78973
ms.assetid: 09fca083-ac0d-4f30-baf2-bb00a626be12
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: c6d21385d956534c799af5b9e20a54c9970da368
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854871"
---
# <a name="set-up-call-center-channels"></a>Hívásközponti csatornák beállítása

[!include [banner](includes/banner.md)]

A vállalat több hívásközponti csatornát is meghatározhat a Dynamics 365 Commerce rendszerben. A hívásközponti csatornák konfigurálása a **Retail és Commerce** \> **Csatornák** \> **Hívásközpontok** \> **Összes hívásközpont** elemnél történik, és az adott jogi személyre jellemzők.

Új hívásközponti csatorna létrehozásakor rendszerszerűen hozzárendelnek egy üzemiegység-számot. Mivel a hívásközpontok üzemi egységekként jönnek létre, a felhasználók a hívásközponti csatornákat különböző Commerce funkciókhoz rendelhetik hozzá, ilyenek például a szortimentek, a katalógusok és az adott szállítási módok.

A hívásközponti csatornához be lehet állítani egy alapértelmezett raktárat. Ezután, amikor a csatornán értékesítési rendeléseket hoznak létre, az alapértelmezett raktár automatikusan megjelenik az értékesítési rendelés fejlécében, kivéve, ha egy másik raktár definiálva van a kiválasztott vevőhöz, amely ki van választva az értékesítési rendeléshez. Ebben az esetben a vevő raktára kerül az értékesítési rendelésre alapértelmezetten.

A hívásközpont funkcióinak használatához a felhasználókat hozzá kell csatolni egy hívásközponti csatornához. A felhasználók által létrehozott összes értékesítési rendelés automatikusan csatolódik a felhasználó hívásközponti csatornájához. Jelenleg egy felhasználó nem csatolódhat egyszerre több hívásközponti csatornához.

A hívásközponti csatornákhoz egy e-mail értesítési profilt is be lehet állítani. A profil határozza meg a hívásközponti csatornán keresztül rendeléseket leadó vevőknek történő e-mail-küldéskor használt e-mail-sablonok halmazát. Az e-mail-eseményindítók rendszereseményekre konfigurálhatók, például rendelés benyújtása vagy rendelés szállítása.

Az értékesítések helyes, hívásközponti csatornán keresztüli feldolgozása előtt ki kell javítani a [fizetési módokat](/dynamics365/unified-operations/retail/work-with-payments), és a szállítási módot meg kell adni a csatornához.

A hívásközponti csatornák szintjén be lehet állítani a többi alapértelmezett értékeket, amelyek azokhoz a pénzügyi dimenziókhoz kapcsolódnak, amelyek a csatorna által létrehozott rendelésekhez kapcsolandók.

## <a name="options-for-order-processing-behavior"></a>A rendelésfeldolgozási viselkedés beállításai

Három beállításnak egy hívásközpont konfigurációjában jelentős hatása van a szolgáltatásokra és funkciókra, amelyek rendelkezésre állnak az értékesítési rendelésekhez, amelyeket a hívásközponthoz hoznak létre: **rendeléskiegészítés engedélyezése**, **közvetlen értékesítés engedélyezése** és **rendelési árellenőrzés engedélyezése**.

### <a name="enable-order-completion"></a>Rendeléskiegészítés engedélyezése

A **Rendeléskiegészítés engedélyezése** hívásközponti csatorna beállításnak jelentős hatással van a csatornába bekerülő értékesítési rendelések rendelési folyamat feldolgozására. Ha ez a beállítás be van kapcsolva, minden értékesítési rendelésnek át kell esnie ellenőrzési szabályok készletén, mielőtt megerősítést kapnának. A szabályok futtatása a **Befejezés** gomb kiválasztásával történik, amely szerepel a műveleti ablakban az értékesítési rendelés oldalon. Értékesítési rendelések létrehozásakor, ha a **Rendeléskiegészítés engedélyezése** beállítás engedélyezve van, át kell esniük a rendelés befejezése folyamaton. Ez a folyamat megköveteli a kifizetés és a fizetés-ellenőrzési logika rögzítését. A fizetés kikényszerítése mellett a rendelés beküldése folyamat kiválthatja a [csalásellenőrzést](/dynamics365/unified-operations/retail/set-up-fraud-alerts), amelyet a rendszerben konfigurálhat. A fizetési vagy csalásellenőrzéseken sikertelen megrendelések várakoztatásra kerülnek, és nem adhatók ki további feldolgozásra (például kitárolás vagy szállítás), a várakoztatást okozó probléma megoldásáig.

Ha a **Rendeléskiegészítés engedélyezése** beállítás engedélyezve van a hívásközponti csatornán, ha sorban szereplő cikkek vannak egy értékesítési rendelésben megadva, és a csatorna felhasználója megpróbál zárni, vagy az értékesítési rendelés képernyőt elhagyni anélkül, hogy először kiválasztja a **Befejezés** lehetőséget, a rendszer kikényszeríti a rendeléskiegészítést az értékesítésirendelés-összegzés lap megnyitásával és annak a megkövetelésével, hogy a felhasználó megfelelően küldje be az űrlapot. Ha a rendelés megfelelően nem küldhető a fizetéssel együtt, a felhasználó használhatja a [rendelés visszatartva](/dynamics365/unified-operations/retail/work-with-order-holds) funkciót a rendelés várakoztatottra állításához. Ha a felhasználó megpróbálja érvényteleníteni a rendelést, megfelelően kell érvénytelenítenie vagy az érvénytelenítés, vagy a törlés funkcióval, attól függően, amit lehetővé teszi a felhasználó biztonsága.

Ha a **Rendeléskiegészítés engedélyezése** beállítás engedélyezve van a hívásközponti csatornán, a **Fizetési állapot** mezőt a rendszer nyomon követi a rendelésen. A rendszer kiszámítja a **Fizetési állapot** értékét, amikor benyújtják az értékesítési rendelést. A rendszer csak a jóváhagyott kifizetési állapotú rendeléseket engedi végighaladni a további rendelésfeldolgozási lépéseken, például a kitárolás és a szállítás lépésén. Ha a kifizetéseket elutasítja a rendszer, a **ne dolgozza fel** jelző engedélyezve lesz a részletes rendelésállapotnál, és ez várakozó állapotba helyezi a rendelést a fizetési probléma megoldásáig.

Ezenkívül, ha a **Rendeléskiegészítés engedélyezése** beállítás engedélyezve van, amikor a felhasználó az értékesítési rendeléseket létrehozza és sortétel beviteli módban van, a **Forrás** mező rendelkezésre áll a fő értékesítési rendelés fejlécében. A **Forrás** mező szolgál egy [katalógus forráskód](/dynamics365/unified-operations/retail/call-center-catalogs) rögzítésére a közvetlen marketing eladási forgatókönyvek esetén. Ez a kód ezután különleges árak vagy promóciók hajtóereje lehet.

Akkor is, ha a **Rendeléskiegészítés engedélyezése** beállítás ki van kapcsolva, a felhasználók továbbra is alkalmazhatnak egy forráskódot egy értékesítési rendelésre. Azonban ehhez meg kell nyitni az értékesítési rendelés fejlécének részleteit a **Forrás** mező eléréséhez. Ez azt jelenti, hogy néhány további kattintással szükség. Ugyanez vonatkozik az olyan funkciókra, mint a szállítás befejeződött és a sürgős rendelések. Ezek a funkciók a hívásközpontban létrehozott összes rendeléshez elérhetők. Ugyanakkor, ha a **Rendeléskiegészítés engedélyezése** beállítás engedélyezve van, a felhasználók megtekinthetik ezeknek a szolgáltatásoknak a konfigurációját az eladási fejlécben, amíg a sorbeviteli nézetben vannak. Nem kell megnyitniuk az értékesítési rendelés fejlécének részletes információit a megfelelő beállítások és mezők megkereséséhez.

> [!NOTE]
> **Ha engedélyezve van aCsatorna csatorna Commerce** rendeléskifizetési szolgáltatása, **·** **·** **\>\> a Kiskereskedelmi és Commerce Csatornák hívásközpontja általános gyorsgombjával rejtve marad a Rendeléskiegészítés engedélyezése hívásközpont.**

### <a name="enable-direct-selling"></a>Közvetlen értékesítés engedélyezése

Ha a **Közvetlen értékesítés engedélyezése** beállítás engedélyezve van a hívásközponti csatornák esetében, a felhasználók kihasználhatják a Commerce felül- és keresztértékesítési funkcióinak előnyeit. Ebben az esetben előugró ablakok jelennek meg a rendelésbevitel során, és egyéb termékeket javasolnak a hívásközpont felhasználója számára, amelyeket felajánlhat a vevőnek. A termékek, amelyeket a program felajánl, az értékesítésirendelés-sorban éppen megrendelt terméken alapulnak. Jelenleg a felül- és keresztértékesítési javaslatok a cikkek szintjén vannak beállítva, a termékek vagy katalógusok esetében. Ha a **Közvetlen értékesítés engedélyezése** beállítás ki van kapcsolva a hívásközponti csatornákra, előugró ablakok nem jelennek meg a rendelésbevitel során, még akkor sem, ha egy érvényes felül- és keresztértékesítés meg van adva egy rendelés alatt álló cikkre.

Ha a **Közvetlen értékesítés engedélyezése** beállítás engedélyezve van, a parancsfájlok és képek szolgáltatások is be vannak kapcsolva az értékesítésirendelés-bevitel oldalon. Ebben az esetben a lap jobb oldalán információs panel érhető el rendelésbevitel során. Ez a panel parancsfájlokat jeleníthet meg, amelyek az általános rendelésbeviteli eljáráshoz, a katalógus alkalmazott forráskódjához vagy az éppen rendelt cikkekhez kapcsolódó parancsfájlokhoz kapcsolódnak. Ezenkívül a képek panelen is megjelenhet az éppen rendelt cikkekhez kapcsolódó termékkép, ha megadtak egy képet a termék beállításakor a cikkhez.

### <a name="enable-order-price-control"></a>Rendelési árellenőrzés engedélyezése

Ha a **Rendelési árellenőrzés engedélyezése** beállítás engedélyezve van, csak az engedéllyel rendelkező felhasználó módosíthatja a cikk eladási árát a rendelésbevitel során. A módosításoknak a meghatározott tűréshatáron belül kell lenniük. A felhasználóknak, akik nem rendelkeznek megfelelő jogosultságokkal, ehelyett be kell nyújtaniuk az árváltozás igénylését. A kérelem ezután fel lesz dolgozva a rendszer ellenőrzési és jóváhagyási munkafolyamataiban.

## <a name="channel-users"></a>Csatorna felhasználói

A hívásközponti csatornák definiálásakor a csatornafelhasználókat hozzá kell rendelnie a hívásközponthoz. Ellenkező esetben a hívásközpont nem használható a rendszerben. Amikor a felhasználó bejelentkeznek a Commerce alkalmazásba, és értékesítési rendeléseket vagy visszárurendeléseket visznek be egy rendelésbevitelhez kapcsolódó lapon, a felhasználói azonosítójukat veti össze a program a hívásközponti csatornák konfigurációjával. Ha egy felhasználó egy adott hívásközponti csatornához van csatolva, a rendelések, amelyeket a felhasználó hoz létre, öröklik a csatorna alapértelmezett jellemzőit és értékeit.

Alapértelmezés szerint az **Értékesítés** jelző az értékesítési rendelés fejlécében be van kapcsolva a hívásközpont felhasználói által létrehozott minden megrendelésre. A rendelések ezután élvezhetik a rendszer kereskedelemspecifikus ár- és promóciófunkcióinak előnyeit.


Azok a felhasználók, akik nem kapcsolódnak hívásközponti csatornához, Microsoft Dynamics a 365 Pénzügy általános rendelésbeviteli funkcióit használják. Az ilyen felhasználók által az értékesítési rendelés bevitele képernyőről bevitt rendelések nem lesznek rendszeresen Commerce megrendelésként azonosítva. Emellett ezek a rendelések, amelyeket ezek a felhasználók visznek be, nem tartoznak a rendelés teljesítésére vonatkozó szabályok feldolgozása, az árképzéslogika vagy más rendelés-ellenőrzések hatálya alá, amelyeket a hívásközponti csatorna konfigurálásánál és a hívásközponti rendszerparaméterekben lehet meghatározni.

A hívásközponti csatornák konfigurálása és a csatorna felhasználóinak megadása után, a kívánt rendszerviselkedés garantálásának elősegítésére érdekében ellenőrizze, hogy az összes szükséges hívásközponti paraméter meg van határozva itt: **Retail és Commerce** \> **Csatorna beállítása** \> **Hívásközpont beállítása** \> **Hívásközponti paraméterek**. Győződjön meg arról, hogy kapcsolódó számsorozatok is meg vannak határozva.

> [!NOTE]
> A hívásközpont funkciójának használatához engedélyezni kell a **Több célhely** konfigurációs kulcsát. Ez a konfigurációs kulcs megtalálható a **Kereskedelem konfiguráció** kulcsai között a **Rendszerfelügyelet**\> **Beállítás** \> **Licenckonfiguráció** alatt. Ez a hívásközpont funkciók miatt szükséges, amelyek az értékesítésirendelés-sor szintjén konfigurált kézbesítési cím alapján különböző érvényesítéseket hajtanak végre. 



[!INCLUDE[footer-include](../includes/footer-banner.md)]
