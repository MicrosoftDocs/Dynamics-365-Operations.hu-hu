---
title: Termékbevételezés összevetése a beszerzési rendelésekkel
description: Ez a témakör bemutatja a termékek átvettként történő regisztrálására vonatkozó különböző opciókat.
author: kamaybac
ms.date: 11/15/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, VendPackingSlipJournalListPage, VendPackingSlipJournal
audience: Application User
ms.reviewer: kamaybac
ms.custom: 93113
ms.assetid: d4ec3e86-fce2-4546-911b-e0acf64c8887
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 413b4c96f5ee4a3a698847ce6329773a65a712ad
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188317"
---
# <a name="product-receipt-against-purchase-orders"></a>Termékbevételezés összevetése a beszerzési rendelésekkel

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja a termékek átvettként történő regisztrálására vonatkozó különböző opciókat.

A termékbevételezés azon megrendelt termékek dokumentálása, melyek leszállításra kerültek, ezáltal a beszerzésirendelés-sorok készen állnak a kiszámlázásra történő feldolgozásra. Bizonyos esetekben a termékek előregisztráción esnek át, ahol a szállítótól a termékek átadása előtt további információk kerülnek dokumentálásra. Amikor a termékek megérkeznek, először **Regisztrált** megjelölést kapnak. A termékek ezután további folyamatokon eshetnek át, mint pl. a minőségellenőrzés, mielőtt véglegesen **Átvett** megjelölést kapnak.

## <a name="preregistration-asn"></a>Előregisztráció (ASN)
A szállítók információkat közölhetnek a szállításra váró termékekről. Ebben az esetben a termékeket úgy is előregisztrálhatja, hogy azok még nem érkeztek meg. A termékek előregisztrálásával lerövidítheti a cikkregisztráció és a bevételezés folyamatát. A szállítók elektronikusan, az Előzetes kiszállítási értesítés (ASN - Advance Shipment Notice) segítségével is közölhetnek információt, ami a rendszerben automatikusan tárolásra kerül. Az ASN-ben megadott adatok tartalmazzák a szállításra váró termékek mennyiségét, és a szállítás dátumát. Az ASN továbbá egyéb információkat, mint pl. a köteg- és sorszámokat is tartalmazhat. Az ASN regisztrációja a **Szállításkezelés** modulban történik.

## <a name="registration"></a>Nyilvántartás
A termékbevételezési regisztráció gyakran a raktár érkeztetési területén történik. Kézi készülék segítségével akár érkeztetési naplók keresztül végezhetők el. Másik megoldásként a termékbevételezést manuálisan is regisztrálhatja a **Beszerzési megrendelés** oldalon található **Regisztráció** művelet használatával. A termék mindkét esetben **Regisztrált** megjelölést kapnak. Vegye figyelembe, hogy ez nem azonos a termék **Átvett** jelölésével.  

A raktárban átvett termékek minőségellenőrzésen is áteshetnek, mielőtt a készletbe kerülnek. Minőségi rendelések vagy a karanténutasítások használhatók minőségellenőrzés elvégzéséhez. Ha a minőségi rendelés kerül használatra, a folyamat konfigurálható úgy, hogy bizonyos termékeket foglalással visszatartson, amíg azokat át nem vizsgálják. Karanténutasítások használatakor a vizsgálandó termékeket ellenőrzésre egy másik raktárba szállítják. Ez a raktár a karanténraktár. Mindkét minőségellenőrzési folyamat során megtörténhet, hogy néhány termék kiselejtezésre kerül, mert nem felelnek meg a minőségi elvárásoknak, vagy mert a minőségellenőrzési folyamat egy adott minta vagy termék megsemmisülésével jár.

## <a name="product-receipt"></a>Termékbevételezés
A termékek beszerzési rendelésen történő **Átvett** státuszúként történő megjelölése leggyakrabban a **Beszerzési rendelések** oldalon található **Termékbevételezés** művelettel történik. A **Termékbevételezés** feladása oldalon számos beállítás található az átvettként könyvelt mennyiségre vonatkozóan. A **Mennyiség** mezőt beállíthatja például a következőkre: **Megrendelt mennyiség**, **Átveendő mennyiség**. Másik megoldásként, raktári érkeztetési folyamat során ez a mező gyakran kaphatja a **Regisztrált mennyiség** beállítást. Minden egyes **Átvett** megjelöléssel ellátott rendeléssor mennyiségeit módosíthatja a diszkrepanciáknak, mint pl. az alul- vagy túlszállításnak megfelelően. A termékbevételezés során meg kell adnia a termékbevételezési azonosítót, ami általában a megegyezik a szállító által biztosított szállítószámmal. Ez az azonosító szükséges a könyveléshez, mert így auditok vagy ellenőrzések során a szállítólevelek összeegyeztethetők a ténylegesen átvett mennyiségekkel, a számba vett készlettel vagy kiadással.  

A beszerzési megrendeléseket olyan termékekre is ki lehet állítani, amelyeket nem szándékoznak készletbe venni, viszont ugyanúgy költségnek számítanak. Ebbe a kategóriába tartoznak azok a rendelési sorok, ahol a termékeket **Nem raktározott** jelöléssel látják el a készletmodell-csoportjukban, valamint azok a sorok, amelyek beszerzési kategóriákat használnak. Ebben az esetben a cikkek lehet, hogy nem mennek keresztül a raktárban az érkezési regisztráción és a termékbevételezésen. Ehelyett a **Termékbevételezés** művelettel a bevételezést közvetlenül a beszerzési rendelésen rögzítik, és a bevételezés nem a regisztrált, hanem a megrendelt mennyiség alapján történik.  

Beszerzésirendelés-sorokat hozhat létre ott, ahol az **Új rögzített eszköz** opció be van kapcsolva. Ez a beállítás jelzi, hogy ezt a beszerzést rögzített eszközként, és nem készletként kell kezelni. Ebben az esetben a konfigurált fix készletmeghatározási szabályok határozzák meg, hogy egy termék vagy kategória megvásárlása átlép-e bizonyos küszöbértékeket, és, hogy emiatt azt fix eszközkezeléssel eszközként kell-e kezelni. Beszerzést létező, fix eszközre is ki lehet állítani. Ebben az esetben az összeg a megfelelő mennyiségre módosítható.  

Több rendelést és bevételezési feldolgozást is kiválaszthat együttesen, az összes rendelésre. Ezt a módszert ritkán használják, de hasznos lehet, ha a beszállító egy összetett rendelést egy adagként szállít le. Létezik egy funkció az összesítő frissítések létrehozására a beszerzések alatti termékbevételezés során. Az összesítő frissítésekkel a szállítótól több, mint egy beszerzési rendelésre vonatkozóan egyetlen szállítólevél is feladható.  

A beszerzési rendelések értékesítési rendelésekből is létrehozhatók, ahol a **Közvetlen szállítás** opciót kiválasztották. Közvetlen kiszállítás esetén a termékek nem az Ön raktárába, hanem közvetlenül a szállítótól a fogyasztóhoz kerülnek kiszállításra. Ebben az esetben a bevételezést közvetlenül a beszerzési rendelésen rögzítik. A bevételezés végrehajtható automatikusan, pl. a szállítóval folytatott elektronikus adatcserével (EDI - Electronic Data Interchange). Amennyiben a beszerzési rendelés vállalatok közötti beszerzési rendelés, a Supply Chain Management használatával a kiszállításkor választhatja bevételezés automatizálását a vállalatok közötti értékesítési rendelésen. A termékek közvetlen kiszállítás esetén is készletként kerülnek elszámolásra, annak ellenére, hogy fizikailag nem voltak a raktárban. Ezért, amikor a termékbevételezés rögzítésre kerül a beszerzési rendelésen, az értékesítési rendelés automatikusan egy szállítólevéllel frissül, így a készlet változásainak végösszege 0 (nulla). Közvetlen kiszállítás esetén nem szükséges az előregisztráció. Amennyiben raktárkezelésre alkalmas raktárakat használ, a rendszámtábla-regisztráció helyett virtuális raktárat is megadhat. Ezt a raktárat a **Közvetlen kiszállítási raktár** mezőben megadhatja a terméken. 

Miután a termékbevételezés megtörtént a beszerzési rendelésen, a beszerzési rendelés állapota **Átvett** lesz, így jelölve, hogy a rendeléshez tartozó számla feldolgozható. A már átvett termékekre vonatkozó részleteket megtekintheti a **Termékbevételezési naplók** oldalon.  

Ezt az oldalt a **Bevételezés** műveletcsoportból, a **Beszerzési** rendelés oldalon érheti el. Ezek az információk a naplókban tartalmazzák a mennyiségekre, dátumokra, és dimenziókra vonatkozó adatokat.

## <a name="additional-resources"></a>További erőforrások

[Beszerzési rendelések áttekintése](purchase-order-overview.md)

[Beszerzési rendelések létrehozása](purchase-order-creation.md)

[Beszerzési rendelések jóváhagyása és megerősítése](purchase-order-approval-confirmation.md)

[Szállítói számlák áttekintése](../../finance/accounts-payable/vendor-invoices-overview.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]