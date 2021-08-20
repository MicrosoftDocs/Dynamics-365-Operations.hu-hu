---
title: Beszerzési rendelések hibaelhárítása
description: Ez a témakör azt mutatja be, hogyan lehet javítani a beszerzési rendelések használata során felmerülő problémákat.
author: SmithaNataraj
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 963a2363ee7cdca6ed25be805e69eeb41331b6f4773c1c59da903fda68ba570b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744750"
---
# <a name="troubleshoot-purchase-orders"></a>Beszerzési rendelések hibaelhárítása

Ez a témakör azt mutatja be, hogyan lehet javítani a beszerzési rendelések használata során felmerülő problémákat.

## <a name="an-action-can-be-completed-only-after-the-line-number-is-fully-distributed"></a>Egy művelet csak akkor hajtható végre, ha a sorszám teljesen ki van osztva.

Ez a hiba a beszerzési rendelések felosztásakor jelentkező ellentmondás miatt fordulhat elő.

A hiba blokkolásának feloldásához és a beszerzési rendelés *Vázlat* állapotra állításához nyissa meg a **Beszerzés és forrás \> Időszakos feladatok \> Tisztítás \> Beszerzési rendelés felosztásának visszaállítása** lehetőséget. A további tudnivalókat lásd a következő blogbejegyzésben: [Beszerzésirendelés-felosztási hibák megoldása a Dynamics 365 Supply Chain Management-alkalmazásban](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="when-purchase-orders-are-imported-through-data-management-purchase-order-line-numbers-dont-follow-the-increment-that-defined-in-system-parameters"></a>Amikor a beszerzési rendeléseket adatkezelés útján importálja, a beszerzésirendelés-sorok száma nem követi a rendszer paraméterei között megadott növekményt.

### <a name="issue-description"></a>Probléma leírása

Alapértelmezés szerint a az automatikusan generált sorszámok a beszerzésirendelés-sorokhoz, amelyek a *Beszerésirendelés-sorok V2* adatentitáson keresztül vannak importálva, nem használják a rendszer számnövekményét, ami a rendszerparaméterekben van meghatározva. Ha kézzel hoz létre egy beszerzési rendelést, és a felhasználói felületen (UI) keresztül ad hozzá sorokat, akkor a program a sorszámokat helyesen növeli. Az Adatkezelési keretrendszer (DMF) használata esetén azonban nem megfelelőek a növekmények.

Ez a probléma azért fordulhat elő, mert amikor DMF keresztül importál sorokat, ha a sorok száma még nincs hozzárendelve az importált entitáshoz, akkor a rendszer a DMF metódusát használja a hozzárendelésekhez. Ez a módszer mindig eggyel növeli a sorszámokat.

### <a name="issue-workaround"></a>Probléma megoldása

Ügyeljen arra, hogy a kívánt sorszámok már meg legyenek adva az adatelem sorszám mezőiben a beszerzésirendelés-sorok importálásakor. Ebben az esetben a DMF nem írja felül a sorszámokat.

## <a name="a-default-tax-group-and-a-default-cash-discount-arent-filled-in-from-the-invoice-account"></a>Egy alapértelmezett adócsoport és egy alapértelmezett készpénzfizetési engedmény nem kerül kitöltésre a számlázási fiókból.

Ha olyan számlázási fiókot használ, amely eltér a vevői számlától, akkor egy alapértelmezett áfacsoport és egy alapértelmezett készpénzfizetési engedmény nem lesz kitöltve a számlázási fiókból a beszerzési rendelés létrehozásakor.

Ez szándékosan van. Az adócsoport, készpénzfizetési engedmények és egyéb áradatok alapértelmezett értékei a vevői fiókon, nem pedig a számlázási fiókon alapulnak.

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a>A beszerzési rendelés visszaigazolásakor egy „Objektumhivatkozás nincs beállítva” hiba vagy „Kivétel történt a meghívás célja felől” kivétel jelenik meg szállítói számla feladása során.

Ez a hiba a beszerzési rendelések felosztásakor jelentkező ellentmondás miatt fordulhat elő.

A hiba blokkolásának feloldásához és a beszerzési rendelés *Vázlat* állapotra állításához nyissa meg a **Beszerzés és forrás \> Időszakos feladatok \> Tisztítás \> Beszerzési rendelés felosztásának visszaállítása** lehetőséget. A további tudnivalókat lásd a következő blogbejegyzésben: [Beszerzésirendelés-felosztási hibák megoldása a Dynamics 365 Supply Chain Management-alkalmazásban](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a>Egy vagy több könyvelési felosztás túlzottan fel van osztva, vagy nincsen eléggé felosztva.

### <a name="issue-description"></a>Probléma leírása

A következő hibaüzenet jelenik meg: „Egy vagy több könyvelési felosztás túlzottan fel van osztva, vagy nincsen eléggé felosztva.”

### <a name="issue-resolution"></a>Probléma megoldása

Ez a hiba a beszerzési rendelések felosztásakor jelentkező ellentmondás miatt fordulhat elő.

A hiba blokkolásának feloldásához és a beszerzési rendelés *Vázlat* állapotra állításához nyissa meg a **Beszerzés és forrás \> Időszakos feladatok \> Tisztítás \> Beszerzési rendelés felosztásának visszaállítása** lehetőséget. A további tudnivalókat lásd a következő blogbejegyzésben: [Beszerzésirendelés-felosztási hibák megoldása a Dynamics 365 Supply Chain Management-alkalmazásban](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

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

## <a name="purchase-orders-dont-reflect-the-language-settings-of-the-legal-entity"></a>A beszerzési rendelések nem veszik figyelembe a jogi személy nyelvi beállításait.

### <a name="issue-description"></a>Probléma leírása

A beszerzési rendelésen szereplő terméknév a rendszer nyelvén jelenik meg a beszerzési rendelés létrehozásához használt jogi személyhez megadott nyelv helyett.

### <a name="reproduce-the-issue"></a>A hiba reprodukálása

A következő eljárás bemutatja a hiba reprodukálásának egyik módját.

1. A rendszer nyelvét állítsa *EN-US* (amerikai angol) értékre.
1. Győződjön meg róla, hogy van olyan termék, ahol az *EN-US* és *DE* (német) nyelvek vannak fenntartva a termék név fordításaihoz.
1. Jogi személy nyelvét módosítsa *DE* értékre.
1. A jogi személyben, ahol a nyelv beállítása *DE* hozzon létre egy beszerzési rendelés, ami tartalmazza a terméket.
1. Figyelje meg, hogy a termék neve továbbra is az angol nyelven jelenik meg (a rendszer nyelvén).

### <a name="issue-resolution"></a>Probléma megoldása

Ez szándékosan van. A beszerzési rendeléseken a termék mindig a rendszer nyelvén jelenik meg. A beszerzési rendelés nyelvét a rendszer a visszaigazolási napló létrehozásakor használja.

## <a name="the-approved-vendor-list-by-product-entity-doesnt-allow-the-effective-date-to-be-changed"></a>Az Engedélyezett szállító lista a termék entitása nem teszi lehetővé a hatályos dátum módosítását.

### <a name="issue-description"></a>Probléma leírása

A termék olyan engedélyezett szállítóval rendelkezik, amely például 2018. január 11-i (*01/11/2018*) érvényességi dátummal és a *Soha* lejárati dátummal rendelkezik. Ha a hatályosság dátumát 2018. január 10-re (*01/10/2018*) vagy 2018. január 12-re (*01/12/2018*) szeretné módosítani, akkor a következő hibaüzenet jelenik meg:

> Nem hozható létre rekord az Engedélyezett szállítói listán (PdsApproveVendorList). A „Lejárat” értéknek nagyobbnak kell lennie, mint a „Hatályos” értéknek.

### <a name="issue-resolution"></a>Probléma megoldása

Csak addig hosszabbíthatja meg azt az időszakot, ameddig a szállítót jóváhagyták. Az alábbi szabályokat kell betartani:

- Ha azt szeretné, hogy a program a hatályossági dátumot a szállítóhoz tartozó létező rekordoknál (időszakok) korábbira módosítsa, akkor az új időszak lejárati dátumának korábban kell lennie a meglévő rekordok összes lejárati dátumával.
- Ha módosítani szeretné a lejárati dátumot úgy, hogy az később legyen, mint a meglévő időszakok, akkor az érvényességi dátumnak a legkésőbbi lejárati dátum után kell lennie minden meglévő rekordban.
- Ha csökkenteni szeretné a szállító számára jóváhagyott teljes időszakot, akkor törölnie kell vagy módosítania kell a meglévő rekordokat. Azt is megteheti, hogy az Importálás során a **csonkolás** kapcsolót használja. Ez a kapcsoló törli a táblából a jóváhagyott szállítókhoz tartozó összes meglévő rekordot.

A probléma leírásában ismertetett példa esetében, amikor a rekord érvényességi dátuma *01/11/2018* érvényességi dátuma és a lejárati dátuma *Soha*, importálhat egy olyan új rekordot, amelynek érvényességi dátuma *01/10/2018*, és a lejárati dátuma *Soha*. Az időszakot azonban nem lehet csökkenteni úgy, hogy az érvényességi dátumot *01/12/2018* értékre módosítja az adatkezelési folyamaton keresztül. Ezt a módosítást a felhasználói felületen keresztül kell elvégeznie.

## <a name="after-i-change-the-delivery-address-on-a-purchase-order-header-the-delivery-name-isnt-synced"></a>A beszerzési rendelés fejlécében szereplő szállítási cím módosítása után a szállítási név nincs szinkronizálva.

### <a name="issue-description"></a>Probléma leírása

Egy beszerzési rendelés fejlécében szereplő cím olyan címre módosul, amely nem a szállítási cím. Bár a cím frissítve van a beszerzési rendelésen, a szállítási név nem frissül a frissített cím alapján.

### <a name="issue-resolution"></a>Probléma megoldása

Ez szándékosan van. A kiválasztott cím besorolása szállítási cím kell legyen. Ellenkező esetben a szállítási név nem módosul a kiválasztott cím alapján.

## <a name="can-i-find-the-user-who-canceled-a-purchase-order"></a>Megkereshetem azt a felhasználót, aki törölte a beszerzési rendelést?

Ezt az információt csak akkor követi nyomon a program, ha a beszerzési rendelésen alkalmazva van a változások követése. Ha változáskövetést használ, megtekintheti, hogy ki küldte be a módosítást (a visszavonást), és ki hagyta jóvá.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]