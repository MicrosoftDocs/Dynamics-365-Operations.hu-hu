---
title: A beszerzés integrálása a Supply Chain Management és a Field Service között
description: Ez a témakör azt ismerteti, hogy hogyan támogatja a kettős írású integráció a beszerzési rendelések létrehozását és frissítéseit a Supply Chain Management és a Field Service szolgáltatásból.
author: RichardLuan
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: rhaertle
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-11-11
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 2c27f06524b91f91d95ef4b901740e7761232c28
ms.sourcegitcommit: a202bf67c3c2c054e2a47cb7b3145cb7c0ee635e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/25/2021
ms.locfileid: "5941109"
---
# <a name="integrate-procurement-between-supply-chain-management-and-field-service"></a>A beszerzés integrálása a Supply Chain Management és a Field Service között

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

A Microsoft Dynamics 365 Supply Chain Management hatékony beszerzési funkciókat biztosít. A Dynamics 365 Field Service hasonló funkciókat kínál, amelyek támogatják a szolgáltatási folyamattal összefüggő beszerzési folyamatokat. Ennek a két alkalmazásnak a funkcióit kettős írással integrálja a rendszer, és az így létrejövő keresztfunkcionális felhasználási esetek engedélyezése táblaleképezésekkel, megoldáslogikával, nézetekkel és képernyők használatával történik.

Ez az integráció támogatja a beszerzési rendelések létrehozását, illetve a legtöbb esetben mindkét alkalmazásból származó frissítéseket. A Supply Chain Management ugyanakkor szabályozza az árképzést, a címeket és a termékbevételezést. Számos hatékony, keresztfunkcionális felhasználási eset engedélyezve van olyan szervezetek számára, amelyek mind a Field Service, mind a Supply Chain Management szolgáltatást használják. Az ilyen esetek lehetővé teszik a beszerzések kezdeményezését és nyomon követését mindkét rendszerben.

A következő ábra bemutatja a táblákat mindkét rendszerben, és azt, hogy hogyan vannak leképezve egymáshoz. A Field Service szolgáltatásban lévő beszerzési rendelések egy *számlasorra* hivatkoznak, míg a Supply Chain Management szolgáltatásban *szállítói* sorra. Az integráció megoldásához a kettős írás hivatkozással kapcsolja össze a *szállítói* sorokat a *számlasorokkal*. További információ: [Integrált szállítói alapadat](vendor-mapping.md).

![Beszerzés-leképezések](media/scm-field-service-tables.png)

## <a name="prerequisites"></a>Előfeltételek

A Supply Chain Management szolgáltatás Field Service szolgáltatással történő integrálásához telepítenie kell a következő összetevőket:

- A Field Service 8.8.31.60 vagy újabb verziója, átfogó beszerzési rendelési integráció érdekében
- Supply Chain Management 10.0.14 vagy újabb verzió
- Kettős írás a OneFSSCM megoldás futtatásához

## <a name="installation-guidelines"></a>Telepítési útmutató

### <a name="prerequisites"></a>Előfeltételek

- **Kettős írás** – a további tudnivalókat lásd: [kettős írás kezdőlapja](dual-write-home-page.md#dual-write-setup).
- **Dynamics 365 Field Service** – További információ: [A Dynamics 365 Field Service telepítése](/dynamics365/field-service/install-field-service#step-1-install-dynamics-365-field-service).

Ha engedélyezve van a Microsoft Dataverse szolgáltatásban, a kettős írás és a Field Service több megoldásréteget is bevezet, amelyek új metaadatokkal, képernyőkkel, nézetekkel és logikával bővítik a környezetet. Ezek a megoldások bármilyen sorrendben engedélyezhetők, bár általában az itt megadott sorrendben kell telepíteni őket:

1. **Field Service Common** – a Field Service Common szolgáltatás akkor van telepítve, ha a Field Service telepítve van a környezetben.
2. **Field Service (Anchor)** – a Field Service (Anchor) szolgáltatás akkor van telepítve, ha a Field Service telepítve van a környezetben. 
3. **Supply Chain Management Extended** – a Supply Chain Management Extended szolgáltatás automatikusan telepítve van, ha környezetben engedélyezve van a kettős írás. 
4. **OneFSSCM-megoldás** – a OneFSSCM megoldást automatikusan telepíti az a megoldás (Field Service vagy Supply Chain Management), amelyiket legutóbb telepítették.

    - Ha a Field Service már telepítve van a környezetben, és ön engedélyezi a kettős írást, amely a Supply Chain Management Extended szolgáltatást telepíti, akkor a OneFSSCM telepítve van.
    - Ha a Supply Chain Management Extended már telepítve van a környezetben, és ön telepíti a Field Service szolgáltatást, akkor a OneFSSCM telepítve van.

## <a name="initial-synchronization"></a>Kezdeti szinkronizálás

Új beszerzési rendelések létrehozásához és a meglévő beszerzési rendelésekkel való munkához szinkronizálni kell a hivatkozási adatokat a Supply Chain Management és a Dataverse között. A kezdeti írási funkcióval lehet észlelni a táblakapcsolatokat, és megtalálni azokat a táblákat, amelyeket engedélyeznie kell egy adott leképezéshez.

Szinkronizálnia kell a következő táblákat:

- Terméksablonok

    A kezdeti írás futtatásakor a szükséges táblák teljes listája megjelenik. Az alábbiakban példák láthatók a sablonokra:

    - Minden termék
    - Kiadott termékek V2
    - Dataverse kiadott egyedi termékek

- Helyek
- Raktárak
- Beszerzési kategóriák sablonjai

    Az alábbiakban példák láthatók a sablonokra:

    - Beszerzési kategóriák
    - Pro
    - Termékkategória hierarchiája
    - Termékkategóriák hozzárendelései

- Szállítósablonok, például A2 szállító
- Kapcsolattartó-sablonok, például Dataverse V2 kapcsolattartók
- Dolgozói sablonok, például Dolgozó

A táblák szinkronizálása biztosítja, hogy a Supply Chain Management összes dokumentuma (beszerzési rendelések és termékbevételezések) elérhetővé váljon a Dataverse szolgáltatásban.

### <a name="account-and-vendor-tables"></a>Számla- és szállítói táblák

A Field Service szolgáltatásban található beszerzési rendelések a Számlatáblán alapulnak a szállítók nyomon követése érdekében. Emiatt a beszerzési rendelések Dataverse táblái számlákat használnak a szállítók nyomon követésére. Ennek a fő különbségnek a figyelembevétele érdekében aktiválni kell a következő négy munkafolyamatot, hogy a számlák és szállítók szinkronban legyenek: 

- Szállítók létrehozása a Számlák táblában
- Szállítók létrehozása a Szállítók táblában
- Szállítók frissítése a Számlák táblában
- Szállítók frissítése a Szállítók táblában

Ha a OneFSSCM telepítve van, mivel mind a Field Service, mind a Supply Chain Management Extended szolgáltatás telepítve van, ezek a munkafolyamatok automatikusan aktiválva vannak. Ha a Field Service nincs telepítve, de integrálni szeretné a beszerzési rendelési táblákat a l Dataverse szolgáltatással, aktiválnia kell ezeket a munkafolyamatokat. Mindkét esetben – hacsak nem kezdi elölről – előfordulhat, hogy a beszerzési rendelések létrehozása előtt meg kell győződnie arról, hogy minden szállítót számlaként hoztak létre a Dataverse szolgáltatásban. Ellenkező esetben hibák lépnek fel.

### <a name="initial-synchronization"></a>Kezdeti szinkronizálás

Ha az összes előfeltétel meg van adva, és mindkét rendszerben elérhetővé szeretné tenni a létező beszerzési rendeléseket és termékbevételezéseket, akkor el kell végeznie a következő sablonok kezdeti szinkronizálását:

- Beszerzési rendelés V2 fejléce
- CDS beszerzési rendelés sora
- CDS beszerzésirendelés-sor részleges törlése
- Beszerzési rendelés – bevételezés
- Beszerzési rendelés – bevételezési termék

## <a name="mappings-with-logic"></a>Leképezések logikával

A beszerzési integráció a következő logikával bővíti ki a termékleképezést, hogy a Dataverse terméktáblájában helyesen legyen beállítva a **Field Service Terméktípus** oszlopa:

- Ha a **Terméktípus** beállítása *Termék* és a **Cikkmodellcsoport, Raktározott termék** *Igaz*, a **Field Service terméktípus** *Készlet* értékre van beállítva.
- Ha a **Terméktípus** beállítása *Termék* és a **Cikkmodellcsoport, Raktározott termék** *Hamis*, a **Field Service terméktípus** *Nem készlet* értékre van beállítva.
- Ha a **Terméktípus** *Szolgáltatás* értékre van beállítva, akkor a **Field Service terméktípus** szintén *Szolgáltatás* értékre van beállítva.

Ezenkívül a Dataverse olyan logikát is tartalmaz, amely a szállítókat a kapcsolódó számláikhoz képezi le. Ez a logika beállítja az alapértelmezett számlához tartozó szállítói számlát. Létrehozás esetén a kiszolgálóoldali beépülő modul logikája beállítja a számlához kapcsolódó szállítói számlát a számlához kapcsolódó szállítóból. A szállító hivatkozik arra a számlaszámra, amelyet ennek az értéknek a beállításához használnak.

## <a name="supported-scenarios"></a>Támogatott esetek

- A Dataverse felhasználók beszerzési rendeléseket hozhatnak létre és frissíthetnek. A folyamatot és az adatokat azonban a Supply Chain Management vezérli. A Supply Chain Management eszközben a beszerzési rendelés oszlopainak frissítésére vonatkozó megszorítások akkor alkalmazandók, amikor a Field Service szolgáltatásból frissítések érkeznek. Ha például már véglegesített egy beszerzési rendelést, azt nem frissítheti. 
- Ha a beszerzési rendelést a Supply Chain Management változáskezelése vezérli, a Field Service felhasználója csak akkor tudja frissíteni a beszerzési rendelést, ha a Supply Chain Management jóváhagyási állapota *Piszkozat*.
- Több oszlopot csak a Supply Chain Management tud kezelni, és ezek nem frissíthetők a Field Service szolgáltatásban. A nem frissíthető oszlopokról a termék leképezési tábláiban olvashat bővebben. Az egyszerűség kedvéért a legtöbb ilyen oszlop csak olvashatóra van állítva a Dataverse lapokon. 

    Az árinformációk oszlopait például a Supply Chain Management kezeli. A Supply Chain Management olyan kereskedelmi megállapodásokkal rendelkezik, amelyek a Field Service számára előnyös lehet. oszlopok, úgymint az **Egységár**, **Engedmény** és **Nettó összeg** csak a Supply Chain Management szolgáltatásból származhatnak. Annak érdekében, hogy az ár szinkronizálva legyen a Field Service szolgáltatással, a **Szinkronizálás** szolgáltatást kell használnia a **Beszerzési rendelés** és **Beszerzési rendelés terméke** oldalakon a Dataverse szolgáltatásban, amikor beszerzési rendelési adatokat ad meg. További tájékoztatás: [Szinkronizálás a Dynamics 365 Supply Chain Management beszerzési adatokkal igény szerint](#sync-procurement).

- Az **Összegek** oszlop csak a Field Service mezőben érhető el, mert a Supply Chain Management szolgáltatásban nem érhetők el a beszerzési rendelés naprakész összesítései. A Supply Chain Management összegének számítása több olyan paraméter alapján történik, amelyek nem érhetők el a Field Service szolgáltatásban.
- Azok a beszerzésirendelés-sorok, amelyekben csak beszerzési kategória van megadva, vagy amelyekben a megadott termék *Szolgáltatás* terméktípus vagy Field Service terméktípus, csak a Supply Chain Management szolgáltatásban kezdeményezhetők. A program ekkor szinkronizálja a sorokat a Dataverse szolgáltatással, és megjelennek a Field Service szolgáltatásban.
- Ha csak a Field Service szolgáltatás van telepítve, a Supply Chain Management nem, akkor a **Raktár** oszlop kötelező a beszerzési rendelésen. Ha azonban a Supply Chain Management telepítve van, akkor erre a követelményre csak akkor van szükség, ha az Supply Chain Management bizonyos helyzetekben nem ad meg raktárat a beszerzési rendelés soraihoz.
- A termékbevételezéseket (a Dataverse szolgáltatásban: beszerzési rendelésbevételezések) a Supply Chain Management kezeli, és nem lehet létrehozni a Dataverse szolgáltatásban, ha a Supply Chain Management telepítve van. A Supply Chain Management szolgáltatásból származó termékbevételezések szinkronizálása a Supply Chain Managementből a Dataverse szolgáltatásba történik.
- A szállítási hiány engedélyezve van a Supply Chain Management szolgáltatásban. A OneFSSCM megoldás hozzáadja a logikát, így amikor a termékbevételezési sor (vagy a Dataverse szolgáltatásban beszerzési rendelés bevételezési terméke) létrejön vagy frissül, egy készletnaplósor jön létre a Dataverse szolgáltatásban, amely korrigálja a szállítási hiány helyzeteinek fennmaradó rendelési mennyiségét.

## <a name="unsupported-scenarios"></a>Nem támogatott esetek

- A Field Service megakadályozza, hogy sorokat adjon hozzá egy visszavont beszerzési rendeléshez a Supply Chain Management szolgáltatásban. Megoldásként módosíthatja a beszerzési rendelés rendszerállapotát a Field Service szolgáltatásban, majd az új sort hozzáadhatja a Field Service vagy a Supply Chain Management szolgáltatáshoz.
- Bár a beszerzési sorok hatással vannak mindkét rendszer készletszintjére, ez az integráció nem gondoskodik a készletnek a Supply Chain Management és a Field Service szolgáltatás közötti korrigálásáról. Mind a Field Service, mind a Supply Chain Management szolgáltatásban vannak más folyamatok is, amelyek frissítik a készletszinteket. Ezek a folyamatok kívül esnek a beszerzés hatókörén.

## <a name="status-management"></a>Állapotkezelés

A Field Service szolgáltatásban a beszerzési rendelések állapota eltér a Supply Chain Management szolgáltatásban lévő állapotoktól.

### <a name="field-service-purchase-order-and-purchase-order-product-statuses"></a>A Field Service beszerzési rendelése és a beszerzési rendelés termékállapotai

| Fejléc – Rendszerállapot | Fejléc – Jóváhagyási állapot | Cikk állapota |
|---|---|---|
| <ul><li>Piszkozat</li><li>Elküldve</li><li>Érvénytelenített</li><li>Termék bevételezve</li><li>Számlázva</li></ul> | <ul><li>Null</li><li>Engedélyezve</li><li>Elutasítva</li></ul> | <ul><li>Függőben</li><li>Bevételezve</li><li>Érvénytelenített</li></ul> |

### <a name="supply-chain-management-purchase-order-and-purchase-order-line-statuses"></a>A Supply Chain Management beszerzési rendelése és beszerzési rendelésének sorállapotai

A sor jóváhagyási állapotai csak akkor aktívak, ha van sormunkafolyamat.

| Fejléc - dokumentumok állapota | Fejléc – Jóváhagyási állapot | Sor állapota | Sorjóváhagyási állapot |
|---|---|---|---|
| <ul><li>Nyitott rendelés (utánrendelés)</li><li>Bevételezve</li><li>Számlázva</li><li>Érvénytelenített</li></ul> | <ul><li>Piszkozat</li><li>Ellenőrzés alatt</li><li>Engedélyezve</li><li>Elutasítva</li><li>Külső ellenőrzés alatt</li><li>Visszaigazolva</li><li>Véglegesítve</li></ul> | <ul><li>Nyitott rendelés (utánrendelés)</li><li>Bevételezve</li><li>Számlázva</li><li>Érvénytelenített</li></ul> | <ul><li>Nincs elküldve</li><li>Ellenőrzés alatt</li><li>Engedélyezve</li><li>Elutasítva</li></ul> |

Az állapotoszlopok a következő szabályokat alkalmazzák:

- A Supply Chain Management állapota nem frissíthető a Field Service szolgáltatásból. Bizonyos esetekben azonban a Field Service szolgáltatásban a beszerzési rendelés állapota frissül, ha a Supply Chain Management szolgáltatásban módosul.
- Ha a Supply Chain Management szolgáltatásban egy beszerzési rendelés változáskezelés alatt áll, és a változás feldolgozása folyamatban van, a jóváhagyási állapot *Piszkozat* vagy *Ellenőrzés alatt*. Ebben az esetben a Field Service szolgáltatás jóváhagyási állapota *Null* lesz.
- Ha a Supply Chain Management szolgáltatásban a beszerzési rendelés jóváhagyási állapota *Jóváhagyva*, *Külső ellenőrzés alatt*, *Megerősítve* vagy *Véglegesített*, akkor a Field Service szolgáltatásban a beszerzési rendelés jóváhagyási állapota *Jóváhagyott* lesz.
- Ha a Supply Chain Management szolgáltatásban a beszerzési rendelés jóváhagyási állapota *Elutasítva*, akkor a Field Service szolgáltatásban a beszerzési rendelés jóváhagyási állapota *Elutasítva* lesz.
- Ha a Supply Chain Management dokumentumfejlécének állapota *Nyitott rendelés (Utánrendelés)* állapotra módosul, és a Field Service beszerzési rendelésének állapota *Piszkozat* vagy *Visszavonva*, akkor a Field Service szolgáltatás beszerzési rendelésének állapota *Elküldve* állapotúra változik.
- Ha a Supply Chain Management szolgáltatásban a dokumentumfejléc állapota *Visszavonva* állapotra módosul, és a Field Service mezőben található beszerzési rendelés bevételezési termékei nincsenek a beszerzési rendeléshez társítva (beszerzési rendelési termékeken keresztül), a Field Service szolgáltatás rendszerállapota *Visszavonva* állapotú lesz.
- Ha a Supply Chain Management szolgáltatásban a beszerzésirendelés-sor állapota *Visszavonva*, a Field Service szolgáltatásban a beszerzési rendelés termékállapota *Visszavonva* állapotúra lesz beállítva. Továbbá ha a Supply Chain Management szolgáltatásban a beszerzési rendelés sorának állapota *Visszavonva* állapotról *Utánrendelésre* módosul, akkor a Field Service szolgáltatásban a beszerzési rendelés termékének állapota *Függőben*.

## <a name="sync-with-the-supply-chain-management-procurement-data-on-demand"></a><a id="sync-procurement"></a>Szinkronizálás a Supply Chain Management beszerzési adatokkal igény szerint

A Supply Chain Management olyan beszerzési adatokat tartalmaz, amelyek a kereskedelmi megállapodások, engedmények és más olyan helyzetek kezelésére használhatók, amelyek a Supply Chain Management szolgáltatásban másodlagos folyamatokon alapulnak. A beszerzési motor összetett szabályokat használ egy adott rendelés legjobb árának megállapításához. Ha kettős írást használ, akkor az adatok nem mindig szinkronizálódnak a két környezet között, különösen olyan helyzetekben, amikor a sort létrehozták vagy frissítették a  Dataverse szolgáltatásból, és a Supply Chain Management szolgáltatásban követési folyamatokat vált ki.

## <a name="sync-the-procurement-data-from-supply-chain-management"></a>Beszerzési adatok szinkronizálása a Supply Chain Management szolgáltatásból

1. A Dataverse szolgáltatásban ugorjon a **Készlet \> Beszerzési rendelés** lehetőségre.
2. Válassza az **Új** lehetőséget egy új beszerzési rendelés létrehozásához, vagy válasszon egy sort a meglévő beszerzési rendelések listájához.
3. Beszerzési rendelésből vagy beszerzésirendelés-sorból.
4. A műveleti ablaktáblán válassza a **Szinkronizálás** lehetőséget.

A program a Supply Chain Management által megosztott összes, a Dataverse és a Field Service szolgáltatásban megtalálható oszlopot szinkronizálja.

A következő helyzetekben használhatja a **Szinkronizálás** funkciót:

- Ha ugyanannak a sornak több egymást követő változtatását is végrehajtotta a Dataverse szolgáltatásból, futtassa a **Szinkronizálás** funkciót.
- Ha nem biztos benne, hogy egy változtatás lehet-e a második egymást követő módosítás a Dataverse szolgáltatásból, akkor érdemes lehet a **Szinkronizálás** funkciót futtatni.
- Ha hibaüzenetet kap egy értéknek a Supply Chain Management szolgáltatásból való frissítéséről, futtassa a **Szinkronizálás** funkciót, majd próbálja meg újra a frissítést a Dataverse szolgáltatásban.

## <a name="cancelling-the-posting-process"></a>A feladási folyamat visszavonása

Ha a feldolgozás során megszakították a termékbevételezés feladási folyamatát, előfordulhat, hogy a kettős írás létrehoz egy termékbevételezési sort a Dataverse szolgáltatásban, a Supply Chain Management szolgáltatásban azonban nem. Ez a helyzet azért fordul elő, mert a kettős írás nem támogatja az elosztott tranzakciókat.

## <a name="templates"></a>Sablonok

A beszerzésekkel kapcsolatos dokumentumok integrálásához a következő sablonok állnak rendelkezésre.

| Ellátásilánc-kezelés | Field Service | Leírás |
|---|---|---|
| Beszerzési rendelés V2 fejléce | msdyn\_Purchaseorders | Ez a tábla a beszerzési rendelés fejlécének megfelelő oszlopokat tartalmazza. |
| Beszerzésirendelés-sor entitás | msdyn\_PurchaseOrderProducts | Ez a tábla a beszerzési rendelés sorainak megfelelő sorokat tartalmazza. A termékszám a szinkronizáláshoz használható. Ez a termékraktározási egységként (SKU) azonosítja a terméket, a termékdimenziókkal együtt. A Dataverse szolgáltatással történő termékintegrációval kapcsolatos további tudnivalókat lásd: [Egyesített termékkel kapcsolatos tapasztalat](product-mapping.md). |
| Termékbevételezések fejléce | msdyn\_purchaseorderreceipts | Ez a tábla azokat a termékbevételezési fejléceket tartalmazza, amelyek a Supply Chain Management szolgáltatásban a termékbevételezés feladása során jönnek létre. |
| Termékbevételezési sor | msdyn\_purchaseorderreceiptproducts | Ez a tábla azokat a termékbevételezési sorokat tartalmazza, amelyek a Supply Chain Management szolgáltatásban a termékbevételezés feladása során jönnek létre. |
| Beszerzés rendelési sora – részben törölt entitás | msdyn\_purchaseorderproducts | Ez a tábla az olyan beszerzésirendelés-sorokról tartalmaz információkat, amelyek részben törölve vannak. A Supply Chain Management szolgáltatásban a beszerzésirendelés-sorok csak akkor törölhetők részlegesen, ha a beszerzési rendelést megerősítették vagy jóváhagyták, a változáskezelés bekapcsolt állapota esetén. A sor megtalálható a Supply Chain Management adatbázisban, és **Törölve** jelöléssel van ellátva. Mivel a Dataverse nem tartalmazza a részleges törlés koncepcióját, fontos, hogy ezek az adatok szinkronizálva legyenek a Dataverse szolgáltatással. Ily módon a Supply Chain Management szolgáltatásban részlegesen törölt sorok automatikusan törölhetők a Dataverse szolgáltatásból. Ebben az esetben a sorok Dataverse szolgáltatásból történő törlésének logikája a Supply Chain Management Extended szolgáltatásában található. |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Currency](includes/productreceiptheader-msdyn-purchaseorderreceipts.md)]

[!include [Currency](includes/productreceiptline-msdyn-purchaseorderreceiptproducts.md)]

[!include [Currency](includes/purchaseorderheadersv2-msdyn-purchaseorders.md)]

[!include [Currency](includes/purchaseorderlinesoftdeletedtable-msdyn-purchaseorderproducts.md)]

[!include [Currency](includes/purchaseorderlinetable-msdyn-purchaseorderproducts.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
