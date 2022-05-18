---
title: Beszerzési GYIK
description: Ez a témakör a Supply Chain Management beszerzési funkcióival kapcsolatban leggyakrabban feltett kérdésekre ad választ.
author: GalynaFedorova
ms.date: 05/31/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 718108447dcb5cec488b7fa626feb551808e8dd8
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8669348"
---
# <a name="procurement-faq"></a>Beszerzési GYIK

[!include [banner](../includes/banner.md)]

Ez a témakör a Supply Chain Management beszerzési funkcióival kapcsolatban leggyakrabban feltett kérdésekre ad választ.

## <a name="can-i-show-only-purchase-orders-that-i-created"></a>Megjeleníthetem a csak általam létrehozott beszerzési rendeléseket?

Ez a funkció jelenleg nem érhető el.

## <a name="can-i-reserve-inventory-and-create-transactions-against-registered-inventory-on-a-purchase-order"></a>Lefoglalhatók készletet és létrehozhatok tranzakciókat egy beszerzési rendelésen szereplő regisztrált készlettel szemben?

### <a name="issue-description"></a>Probléma leírása

A készletet továbbra is lefoglalhatja még akkor is, ha a cikkek *Regisztrált* állapotban vannak a beszerzési rendelésen. Más szóval a regisztrált készlettel szemben is lehet tranzakciókat létrehozni.

### <a name="reproduce-the-issue"></a>A hiba reprodukálása

A következő eljárás bemutatja a hiba reprodukálásának egyik módját.

1. Beszerzési rendelés létrehozása
2. Regisztrálja a beszerzési rendelés sorát.
3. Figyelje meg, hogy a regisztrált készlettel szemben foglalásokat vagy tranzakciókat lehet létrehozni.

### <a name="issue-resolution"></a>Probléma megoldása

Ez szándékosan van. A várakozás az, hogy a regisztrált cikkek fizikailag megérkeztek a raktárba vagy a készletbe, és így elérhetőek a foglalásra.

## <a name="can-i-find-the-user-who-canceled-a-purchase-order"></a>Megkereshetem azt a felhasználót, aki törölte a beszerzési rendelést?

Ezt az információt csak akkor követi nyomon a program, ha a beszerzési rendelésen alkalmazva van a változások követése. Ha változáskövetést használ, megtekintheti, hogy ki küldte be a módosítást (a visszavonást), és ki hagyta jóvá.

## <a name="why-cant-i-link-a-purchase-agreement-to-an-existing-purchase-order"></a>Miért nem lehet beszerzési szerződést meglévő beszerzési rendeléshez rendelni?

A beszerzési rendelés létrehozása során lehet beszerzési szerződést kapcsolni a beszerzési rendelés egy sorához. Ellenkező esetben a beszerzésirendelés-sorok nem társíthatók a beszerzési szerződés soraival.

## <a name="what-check-triggers-the-update-prices-and-discounts-entered-manually-or-external-document-message"></a>Milyen ellenőrzés váltja ki az „Manuálisan megadott árak és engedmények frissítése vagy külső dokumentum” üzenetet?

A szállítási dátum módosításakor a következő üzenet jelenik meg: „Manuálisan megadott árak és engedmények frissítése vagy külső dokumentum”. Ez az üzenet akkor jelenik meg, ha a szállítási dátum megváltozik, egy másik kereskedelmi vagy értékesítési szerződés lesz meghívva, és ez árváltozást okozhat. A szállítási dátum módosítása hatással lehet a raktári ütemezésekre és más kapcsolódó információkra is.

Az üzenet akkor jelenik meg, ha bármely dátum vagy más paraméter módosul. Az üzenet célja, hogy biztosan tisztában legyen azzal, a változtatások miatt előfordulhat az árak módosulása.

Az üzenet a kereskedelmi megállapodás értékelése (TAE) figyelmeztetés. A teljes leírást lásd: [Kereskedelmi szerződés értékelési irányelvei](/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).

## <a name="why-cant-i-post-more-than-one-invoice-for-a-purchase-order-line-that-has-category-based-items"></a>Miért nem tudok egynél több számlát feladni egy olyan beszerzésirendelés-sorhoz, amelyen kategória alapú cikkek szerepelnek?

A mennyiséget kötelező megadni, ha számlákat szeretne feladni. Ha tehát egy sor teljes mennyisége csak részlegesen lett kiszámlázva, akkor egy másik számlával nem számlázhatja a fennmaradó összeget.
