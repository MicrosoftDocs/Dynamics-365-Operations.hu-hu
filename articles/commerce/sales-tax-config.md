---
title: Az online rendelések áfájának konfigurálása
description: Ez a témakör áttekintést nyújt a különböző online rendeléstípusok áfacsoportjának kiválasztásáról a Dynamics 365 Commerce alkalmazásban.
author: gvrmohanreddy
manager: AnnBe
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: gmohanv
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 8df939c1a566fb63bc53e455cc6c2aa85956ac79
ms.sourcegitcommit: 583801af75c50915ea5ffc60e831fb617d045533
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2021
ms.locfileid: "5853811"
---
# <a name="configure-sales-tax-for-online-orders"></a>Az online rendelések áfájának konfigurálása

[!include [banner](includes/banner.md)]

Ez a témakör áttekintést nyújt a különböző online rendeléstípusok áfacsoport-kiválasztásáról, cél alapú vagy vevői számla alapú adóbeállításokkal. 

Előfordulhat, hogy azt szeretné, hogy az e-kereskedelmi csatornája támogassa az olyan lehetőségeket, mint a kézbesítés vagy az online rendelések felvétele. Az áfa alkalmazhatósága az online ügyfelek által kiválasztott beállításon alapul. 

## <a name="destination-based-taxes-for-online-orders"></a>Online rendelések célon alapuló adói

A vevői címekre szállítandó online rendelésekre kivetett adókat általában a cél határozza meg. Minden áfacsoport rendelkezik egy kiskereskedelmi célalapú adókonfigurációval, amelyben a vállalkozás hierarchikus formában definiálhatja a céladatokat, például a megye vagy régió, az állam, a megye és a város értékét.

### <a name="orders-delivered-to-customer-address"></a>Vevői címre szállított rendelések

Online rendelés leadásakor a Commerce adómotor a rendelés minden sorcikk szállítási címét használja, és megkeresi az áfacsoportokat a megfelelő célalapú adózási feltételekkel. Például egy olyan online rendelés esetén, amelynek sorcikkének szállítási címe San Franciscóban (Kalifornia) van, az adómotor megkeresi Kalifornia áfacsoportját és áfakódját, majd ennek megfelelően kiszámítja az adót minden sorra vonatkozóan.

### <a name="order-pick-up-in-store"></a>Rendelésfelvétel az üzletben

Az üzletbeli vagy a járdaszéli felvétellel megadott csomagfelvételeket megadó rendeléssorok esetén a kiválasztott átvételi áruház adócsoportja lesz alkalmazva. Az áfa beállításáról az [Üzletek egyéb adóbeállításainak megadása](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores) című témakörben talál további tudnivalókat.

## <a name="customer-account-based-taxes-for-online-orders"></a>Online rendelések vevői számlán alapuló adói

Előfordulhat olyan üzleti helyzet, amikor áfacsoportot szeretne beállítani a Commerce központjában meghatározott vevői számla alapján. A központnak két helye van, ahol a vevői számlához be lehet állítani az áfa beállítását. Ezek eléréséhez először menjen ide: **Kiskereskedelem és kereskedelem \> Vevők \> Minden vevők**, majd ki kell választania egy vevőt.

A központnak két helye van, ahol a vevői számlához be lehet állítani az áfa beállítását:

- **Áfacsoport** a vevő adatai lap **Számla és szállítás** gyorslapján. 
- **Áfa** az **Általános** gyorslapján a **Cím kezelése** lapnak. Ha a vevő adatai lapról szeretne eljutni ide, válasszon ki egy címet a **Címek** gyorslapon, majd válassza a **Speciális** lehetőséget.

> [!TIP]
> Online vevői rendelések esetén, ha csak a célon alapuló adókat szeretné alkalmazni, és a vevői számlán alapuló adókat szeretné elkerülni, győződjön meg arról, hogy az **Áfacsoport** mező üres a vevői adatok lap **Számla és szállítás** gyorslapján. Annak érdekében, hogy az online csatornával regisztráló új vevők ne örököljék az áfacsoport beállításait az alapértelmezett vevő- vagy vevőcsoport-beállításoktól, győződjön meg arról, hogy az online csatorna alapértelmezett vevőbeállításai és vevőcsoport-beállításai (**Kiskereskedelem és kereskedelem \> Vevők \> Vevőcsoportok**) is üresen maradnak az **Áfacsoport** mezőben.

## <a name="determine-destination-based-tax-or-customer-account-based-tax-applicability"></a>Célon alapuló adó vagy vevői számla alapú adó alkalmazhatóságának meghatározása 

A következő táblázat bemutatja, hogy a célon alapuló adók és a vevői számla alapú adók online rendeléseknél vannak-e alkalmazva. 

| Vevőtípus | Szállítási cím                   | Vevő > Számla és szállítás > Áfacsoport? | A központ vevői számláján található cím? | Vevői cím > Speciális >Általános > Áfacsoport?                                              | Áfacsoport alkalmazva      |
|---------------|------------------------------------|-----------------------------------------------------|-----------------------------------|--------------------------------------------------------------------------------------------------------|------------------------------|
| Vendég         | Manhattan, New York                      | Nem (üres)                                                | Nem (üres)                              | Nem (üres)                                                                                                   | New York (célon alapuló adók) |
| Bejelentkezve.     | Austin, Texas állam                          | Nem (üres)                                             | Igen                               | None<br/><br/>Online csatornán keresztül hozzáadott új cím.                                                            | Texas (célon alapuló adók) |
| Bejelentkezve.     | San Fransisco, California (átvétel az üzletben) | Igen (New York)                                            | Nem alkalmazható                              | Nem alkalmazható                                                                                                    | California (célon alapuló adók) |
| Bejelentkezve.     | Houston, Texas                         | Igen (New York)                                            | Igen                               | Igen (New York)<br/><br/>Online csatornán keresztül hozzáadott új cím és a vevőkódtól örökölt áfacsoport. | New York (vevői számla alapú adók)  |
| Bejelentkezve.     | Austin, Texas állam                          | Igen (New York)                                            | Igen                               | Igen (New York)<br/><br/>Online csatornán keresztül hozzáadott új cím és a vevőkódtól örökölt áfacsoport. | New York (vevői számla alapú adók)  |
| Bejelentkezve.     | Sarasota, Florida                       | Igen (New York)                                            | Igen                               | Igen (Washington)<br/><br/>Manuálisan állítsa át a WA beállításra.                                                                          | Washington (vevői számla alapú adók)  |
| Bejelentkezve.     | Sarasota, Florida                       | Nem (üres)                                                | Igen                               | Igen (Washington)<br/><br/>Manuálisan állítsa át a WA beállításra.                                                                          | Washington (vevői számla alapú adók)  |

## <a name="additional-resources"></a>További erőforrások

[Online áruházak adóinak beállítása cél alapján](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination)

[Áfa áttekintése](https://docs.microsoft.com/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=/dynamics365/commerce/toc.json) 

[Áfaszámítási módok a Kiindulás mezőben](https://docs.microsoft.com/dynamics365/finance/general-ledger/sales-tax-calculation-methods-origin-field?toc=/dynamics365/commerce/toc.json) 

[Áfa-hozzárendelés és felülbírálások](https://docs.microsoft.com/dynamics365/supply-chain/procurement/tasks/sales-tax-assignment-overrides?toc=/dynamics365/commerce/toc.json) 

[Teljesösszeg- és intervallumszámítási opciók áfakódokhoz](https://docs.microsoft.com/dynamics365/finance/general-ledger/whole-amount-interval-options-sales-tax-codes?toc=/dynamics365/commerce/toc.json) 

[Adómentesség számítása](tax-exempt-price-inclusive.md) 



[!INCLUDE[footer-include](../includes/footer-banner.md)]
