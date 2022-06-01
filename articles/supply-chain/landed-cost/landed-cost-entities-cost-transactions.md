---
title: Költségtranzakció-entitások
description: Ez a témakör a költségtranzakció-entitásokkal kapcsolatban tartalmaz tájékoztatást, amelyek segítségével a költségek értékét fel lehet osztani egy költségterület tartalmára az apportiontion method kiválasztásával.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-27
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 41a9525cb766907b7de97f1e856a3b640d7718ac
ms.sourcegitcommit: 611202adaa080250636efabb3b3b32b850d92d04
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/28/2022
ms.locfileid: "8813166"
---
# <a name="cost-transaction-entities"></a>Költségtranzakció-entitások

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.28 -->

## <a name="apportionment"></a>Arányosítás

A partraszállítási költség lehetővé teszi egy költségterület (hajóút, szállítási tároló stb.) tartalmának felosztását az apportiontion módszer kiválasztásával. Az apportionment módszer az üzleti szabályokon alapuló automatikus költségek konfigurációjának részeként van beállítva. Hajóút létrehozása során ez a költség részeként jön létre.

### <a name="configure-the-apportionment-mapping-for-use-with-data-entities"></a>Az apportionment hozzárendelés konfigurálása adatentitásokkal való használatra

Ha egy költség külső forrásból – például szállítmányozóból – jön létre, akkor ez a külső forrás nem tudja megadni a költségérték arányának preferált módszerét. Az apportionment hozzárendelés meghatározza az egyes költségtípuskódok alapértelmezett felezési módját. Az apportionment **hozzárendelési táblát a Microsoft** apportionment hozzárendelési Dynamics 365 Supply Chain Management lapja alapján lehet elérni (**Partra kerül a \>\> költségszámítási beállítás apportionment hozzárendelése**).

Ha meg van adva egy hozzárendelési kombináció, és a költségtípus kódnak megfelelő költséget egy költségtranzakciós entitás használatával hoz létre, akkor a program a hozzárendelt felválasztó módszert használja az entitásnak megadott értékek helyett.

Ha a leképezési táblában nem található érték, de az entitás már megadott értéket, a rendszer a megadott értéket használja.

Ha a leképezési táblában vagy az entitásnak elküldött rekordban nem szerepel érték, a létrehozás sikertelen lesz.

### <a name="apportionment-mapping-itmapportionmentmapping"></a>Apportionment hozzárendelése (ITMApportionmentMapping)

Az apportionment mapping entitás (`ITMApportionmentMapping`) az apportionment mapping kapcsolatok létrehozására és a rekordok létrehozására és frissítésére ad lehetőséget.

| Név | Hozzárendelés | Adattípus | Kulcs | Kötelező |
|---|---|---|---|---|
| Arányosítási mód | ITMApportionmentMapping.ApportionmentMethod | Int | Nem | Nem |
| Költségtípus kódja | ITMApportionmentMapping.ShipCostTypeId | Nvarchar(20) | **Igen** | Nem |

## <a name="voyage-costs-itmcosttransvoyageentity"></a>Hajóút költségei (ITMCostTransVoyageEntity)

Az hajóút költségentitása (`ITMCostTransVoyageEntity`) az hajóút szintjén alkalmazott útköltség-tranzakciókat hoz létre. **·** **Az importálás során a rendszer az entitásban található kategória- és apportionment** metódusértékek alapján határozza meg, hogy a költség értéke hogyan lesz felszorzva az út teljes tartalmában.

| Név | Hozzárendelés | Adattípus | Kulcs | Kötelező |
|---|---|---|---|---|
| Arányosítási mód | ITMCostTrans.ApportionmentMethod | Int | Nem | Nem |
| Költségérték | ITMCostTrans.CostValue | Numerikus (32, 6) | Nem | Nem |
| Pénznem | ITMCostTrans.CurrencyCode | Nvarchar(3) | Nem | **Igen** |
| Sor száma | ITMCostTrans.LineNum | Numerikus (32, 16) | **Igen** | Nem |
| Kapcsolt költség típusa | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Nem | Nem |
| Minimális költség | ITMCostTrans.MinCostAmount | Numerikus (32, 6) | Nem | Nem |
| Kategória | ITMCostTrans.ShipCostCategory | Int | Nem | Nem |
| Költségtípus kódja | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Nem | Nem |
| Vállalat | ITMCostTrans.ShipDataArea | Nvarchar(4) | Nem | **Igen** |
| Út | ITMCostTrans.TransRecId | Nvarchar(20) | **Igen** | Nem |
| Cikkáfacsoport | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Nem | Nem |

## <a name="shipping-container-costs-itmcosttransshippingcontainerentity"></a>Szállítási tároló költségei (ITMCostTransShippingContainerEntity)

A szállítási tároló költségentitása (`ITMCostTransShippingContainerEntity`) létrehozza a szállítási tárolónak a szállítási tároló szintjén alkalmazott költségeit. **·** **Az importálás során a rendszer a kategória és az apportionment** metódus értékeit használja fel, amelyek az entitásban szerepelnek annak meghatározására, hogy hogyan van felszorzva a költség értéke a szállítási tároló tartalmában.

Az **Összesítés**, **Láb** **és Csatolt szakasz** **mezők olyan rekordokra vonatkoznak, amelyekben a Költségterület** *érték Szállítási tároló*. Emiatt nem nak olyan entitások, amelyek más költségterületeken vannak.

| Név | Hozzárendelés | Adattípus | Kulcs | Kötelező |
|---|---|---|---|---|
| Összesítés | ITMCostTrans.AggregatedCost | Int | Nem | Nem |
| Arányosítási mód | ITMCostTrans.ApportionmentMethod | Int | Nem | Nem |
| Költségérték | ITMCostTrans.CostValue | Numerikus (32, 6) | Nem | Nem |
| Pénznem | ITMCostTrans.CurrencyCode | Nvarchar(3) | Nem | **Igen** |
| Sor száma | ITMCostTrans.LineNum | Numerikus (32, 16) | **Igen** | Nem |
| Kapcsolt költség típusa | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Nem | Nem |
| Kapcsolt szakasz | ITMCostTrans.LinkLegId | Nvarchar(20) | Nem | Nem |
| Minimális költség | ITMCostTrans.MinCostAmount | Numerikus (32, 6) | Nem | Nem |
| Szállítási tároló | ITMCostTrans.TransRecId | Nvarchar(20) | **Igen** | Nem |
| Kategória | ITMCostTrans.ShipCostCategory | Int | Nem | Nem |
| Költségtípus kódja | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Nem | Nem |
| Vállalat | ITMCostTrans.ShipDataArea | Nvarchar(4) | Nem | **Igen** |
| Út | ITMCostTrans.TransRecId | Nvarchar(20) | **Igen** | Nem |
| Szakasz | ITMCostTrans.ShipLegId | Nvarchar(20) | Nem | Nem |
| Cikkáfacsoport | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Nem | Nem |

## <a name="folio-costs-itmcosttransfolioentity"></a>Pénzügyi költségek (ITMCostTransFomissEntity)

A pénzügyi tranzakció költségentitása (`ITMCostTransFolioEntity`) a pénzügyi szintjének megfelelő költségtranzakció-rekordokat hoz létre. **·** **Az importálás során a rendszer az entitásban található kategória- és apportionment** metódusértékek alapján határozza meg, hogy a költség értéke hogyan lesz felszorzva az egyes költségeket a levél tartalmában.

| Név | Hozzárendelés | Adattípus | Kulcs | Kötelező |
|---|---|---|---|---|
| Arányosítási mód | ITMCostTrans.ApportionmentMethod | Int | Nem | Nem |
| Költségérték | ITMCostTrans.CostValue | Numerikus (32, 6) | Nem | Nem |
| Pénznem | ITMCostTrans.CurrencyCode | Nvarchar(3) | Nem | **Igen** |
| Sor száma | ITMCostTrans.LineNum | Numerikus (32, 16) | **Igen** | Nem |
| Kapcsolt költség típusa | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Nem | Nem |
| Minimális költség | ITMCostTrans.MinCostAmount | Numerikus (32, 6) | Nem | Nem |
| Kategória | ITMCostTrans.ShipCostCategory | Int | Nem | Nem |
| Költségtípus kódja | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Nem | Nem |
| Vállalat | ITMCostTrans.ShipDataArea | Nvarchar(4) | Nem | **Igen** |
| Ívlap | ITMCostTrans.TransRecId | Nvarchar(20) | **Igen** | Nem |
| Cikkáfacsoport | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Nem | Nem |

## <a name="purchase-order-costs-itmcosttranspurchaseentity"></a>Beszerzési rendelés költségei (ITMCostTransPurchaseEntity)

A beszerzési rendelés költségentitása (`ITMCostTransPurchaseEntity`) olyan költségtranzakciókat hoz létre, amelyek a beszerzői rendelés fejlécére vonatkoznak. **·** **Az importálás során a rendszer az entitásban található kategória- és apportionment** metódusértékek alapján határozza meg, hogy a költség értéke hogyan lesz felszorzva az egyes költségeket a levél tartalmában.

| Név | Hozzárendelés | Adattípus | Kulcs | Kötelező |
|---|---|---|---|---|
| Arányosítási mód | ITMCostTrans.ApportionmentMethod | Int | Nem | Nem |
| Költségérték | ITMCostTrans.CostValue | Numerikus (32, 6) | Nem | Nem |
| Pénznem | ITMCostTrans.CurrencyCode | Nvarchar(3) | Nem | **Igen** |
| Sor száma | ITMCostTrans.LineNum | Numerikus (32, 16) | **Igen** | Nem |
| Kapcsolt költség típusa | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Nem | Nem |
| Minimális költség | ITMCostTrans.MinCostAmount | Numerikus (32, 6) | Nem | Nem |
| Beszerzési rendelés | ITMCostTrans.TransRecId | Nvarchar(20) | **Igen** | Nem |
| Kategória | ITMCostTrans.ShipCostCategory | Int | Nem | Nem |
| Költségtípus kódja | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Nem | Nem |
| Vállalat | ITMCostTrans.ShipDataArea | Nvarchar(4) | Nem | **Igen** |
| Cikkáfacsoport | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Nem | Nem |

## <a name="item-costs-itmcosttransitementity"></a>Cikk-költségek (ITMCostTransItemEntity)

A cikk költségentitása (`ITMCostTransItemEntity`) a cikkszintre vonatkozó költségtranzakciókat hoz létre. Ez az entitás a beszerzésirendelés-sorokban található cikkekre vonatkozik. A költség értékét a program teljes egészében a sorra alkalmazza.

A **Helyesbítés összege** és **az** Értékkorrekció mező a sor szintű költségterületekre vonatkozik. Emiatt nem nak olyan entitások, amelyek más költségterületeken vannak.

| Név | Hozzárendelés | Adattípus | Kulcs | Kötelező |
|---|---|---|---|---|
| Kiigazítás összege | ITMCostTrans.AdjustmentAmount | Numerikus (32, 6) | Nem | Nem |
| Költségérték | ITMCostTrans.CostValue | Numerikus (32, 6) | Nem | Nem |
| Pénznem | ITMCostTrans.CurrencyCode | Nvarchar(3) | Nem | **Igen** |
| Sor száma | ITMCostTrans.LineNum | Numerikus (32, 16) | **Igen** | Nem |
| Kapcsolt költség típusa | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Nem | Nem |
| Minimális költség | ITMCostTrans.MinCostAmount | Numerikus (32, 6) | Nem | Nem |
| Beszerzési rendelés | ITMCostTrans.TransRecId | Nvarchar(20) | **Igen** | Nem |
| Beszerzésirendelés-sor száma | ITMCostTrans.TransRecId | Nvarchar(20) | **Igen** | Nem |
| Kategória | ITMCostTrans.ShipCostCategory | Int | Nem | Nem |
| Költségtípus kódja | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Nem | Nem |
| Vállalat | ITMCostTrans.ShipDataArea | Nvarchar(4) | Nem | **Igen** |
| Cikkáfacsoport | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Nem | Nem |
| Érték kiigazítása | ITMCostTrans.ValueAdjustmentMethod | Int | Nem | Nem |

## <a name="transfer-line-costs-itmcosttranstransferlineentity"></a>Sorköltségek átvitele (ITMCostTransTransferLineEntity)

Az átátviteli sor költségentitása (`ITMCostTransTransferLineEntity`) olyan költségtranzakciókat hoz létre, amelyek az átátviteli rendelési sor szintjére vonatkoznak. Ezeknek a költségeknek az értékét a program teljes egészében az átrendelési sorra alkalmazza.

A **Helyesbítés összege** és **az** Értékkorrekció mező a sor szintű költségterületekre vonatkozik. Emiatt nem nak olyan entitások, amelyek más költségterületeken vannak.

| Név | Hozzárendelés | Adattípus | Kulcs | Kötelező |
|---|---|---|---|---|
| Kiigazítás összege | ITMCostTrans.AdjustmentAmount | Numerikus (32, 6) | Nem | Nem |
| Költségérték | ITMCostTrans.CostValue | Numerikus (32, 6) | Nem | Nem |
| Pénznem | ITMCostTrans.CurrencyCode | Nvarchar(3) | Nem | **Igen** |
| Sor száma | ITMCostTrans.LineNum | Numerikus (32, 16) | **Igen** | Nem |
| Kapcsolt költség típusa | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Nem | Nem |
| Minimális költség | ITMCostTrans.MinCostAmount | Numerikus (32, 6) | Nem | Nem |
| Kategória | ITMCostTrans.ShipCostCategory | Int | Nem | Nem |
| Költségtípus kódja | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Nem | Nem |
| Vállalat | ITMCostTrans.ShipDataArea | Nvarchar(4) | Nem | **Igen** |
| Átmozgatási rendelés | ITMCostTrans.TransRecId | Nvarchar(20) | **Igen** | Nem |
| Átrendelt rendelési sor száma | ITMCostTrans.TransRecId | Nvarchar(20) | **Igen** | Nem |
| Cikkáfacsoport | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Nem | Nem |
| Érték kiigazítása | ITMCostTrans.ValueAdjustmentMethod | Int | Nem | Nem |

### <a name="transaction-table"></a>Tranzakciós tábla

A költségtranzakció-rekord egy költségterülethez kapcsolódik egy tranzakciótábla számának () hozzárendelése révén`TransTableId`. Ha meghatározott táblaazonosító számok szükségesek, akkor az entitások felosztása ezen értékek alapján történik, így az egyes költségterületekkel kapcsolatban létezik entitás.

A tranzakciós tábla értéke (`TransTableId`) implicit a költségtranzakciós entitás kiválasztása során.

### <a name="calculated-fields"></a>Számított mezők

A következő mezők nem érhetők el beszúrás vagy frissítés során, ha költségtranzakciós entitást használnak, mivel ezek a mezők csak akkor vannak beállítva, ha a hajórekordon bizonyos műveleteket is figyelembe használnak:

- **Becsült költség** – ez a mező akkor van beállítva, amikor az hajóútra (beszerzési rendelésre) vonatkozó számlát vagy áthozatot ad fel.
- **Becsült költség pénzneme** – ez a mező akkor van beállítva, amikor az hajóútra (beszerzési rendelésre) vagy az átadásra vonatkozó számlát feladnak.
- **Tényleges költség** – ez a mező a szállítói számla feladott feladott költségében van beállítva. A költséghez van társítva.

### <a name="find-auto-costs"></a>Automatikus költségek keresése

Az **egyes költségterületekkel** (hajóút, szállítási tároló stb.) elérhető Automatikus költségek megkeresása gomb segítségével frissítheti az adott költségterület költségtranzakcióit a konfigurációs táblák adataiból. Amikor egy költségterülethez kiválasztja a gombot, a rendszer törli az adott költségterület meglévő költségeit, és az automatikus költségbeállítási táblák aktuális konfigurációja alapján új rekordokat hoz létre.

Az adatentitás használatával létrehozott költségtranzakció-rekordok importáltként vannak megjelölve. Ezek a rekordok nem **törlődnek**, ha az Automatikus költségek megkerese lehetőséget választja, mivel nem lesznek újra létrehozva az automatikus költségbeállítási táblákból. Az importáltként megjelölt költségtranzakció-rekordokat azonban továbbra is lehet törölni.

### <a name="linked-fields"></a>Csatolt mezők

Minden költségtranzakció ugyanannak a költségterületnek egy másik rekordhoz társítható. Ezt a társítást a Csatolt költségtípus **mezőben lehet** létrehozni. Lehetővé teszi a költségérték másik költség százalékában való számítását.

A **Csatolt költségtípus** mező csak akkor érvényesíthető, ha a hivatkozott rekordot előbb feldolgozta a rendszer, vagy ha már létezik a táblában. Ugyanez a követelmény vonatkozik a Hivatkozott **szakasz** mezőre is, amely csak a szállítási tároló költségterületének költségeihez használatos.
