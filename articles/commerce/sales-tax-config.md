---
title: Az online rendelések áfájának konfigurálása
description: Ez a témakör áttekintést nyújt a különböző online rendeléstípusok áfacsoportjának kiválasztásáról a Dynamics 365 Commerce alkalmazásban.
author: gvrmohanreddy
manager: AnnBe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: 56621bb9658b71551c7312aa47812903914bc888
ms.sourcegitcommit: da17648c296b22d517eadb2f71c7803672e5648d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/19/2021
ms.locfileid: "5031789"
---
# <a name="configure-sales-tax-for-online-orders"></a>Az online rendelések áfájának konfigurálása

[!include [banner](includes/banner.md)]

Ez a témakör áttekintést nyújt a különböző online rendeléstípusok áfacsoportjának kiválasztásáról. 

Előfordulhat, hogy az e-kereskedelmi csatornája támogatni szeretné az olyan lehetőségeket, mint a kézbesítés vagy az online rendelések felvétele. Az áfa alkalmazhatósága az online felhasználók által kiválasztott beállításon alapul. Amikor a webhely egyik ügyfele úgy dönt, hogy online vásárol egy cikket, és egy címre szállíttatja, az áfa meghatározása a vevő szállítási címéhez tartozó adócsoport beállításától függ. Amikor egy vevő úgy dönt, hogy egy megvásárolt cikket vesz fel egy üzletben, az áfa meghatározása a felvételi üzlet adócsoportjának beállítása alapján történik. 

## <a name="orders-shipped-to-a-customer-address"></a>Vevői címre szállított rendelések 

A vevői címekre szállítandó online rendelésekre kivetett adókat általában a cél határozza meg. Minden áfacsoport rendelkezik egy kiskereskedelmi célalapú adókonfigurációval, amelyben a vállalkozás hierarchikus formában definiálhatja a céladatokat, például a megye/régió, az állam, a megye és a város értékét. Online rendelés leadásakor a Commerce adómotor a rendelés minden sorcikk szállítási címét használja, és megkeresi az áfacsoportokat a megfelelő célalapú adózási feltételekkel. Például egy olyan online rendelés esetén, amelynek sorcikkének szállítási címe San Franciscóban (Kalifornia) van, az adómotor megkeresi Kalifornia áfacsoportját és áfakódját, majd ennek megfelelően kiszámítja az adót minden sorra vonatkozóan.  

## <a name="customer-based-tax-groups"></a>Vevőalapú adócsoportok

A Commerce központban két helyen van konfigurálva vevőadó-csoportok:

- **Vevő profilja**
- **A vevő szállítási címe**

### <a name="if-a-customers-profile-has-a-tax-group-configured"></a>Ha egy vevő profiljához be van állítva egy adócsoport

Előfordulhat, hogy a központban lévő vevői profilrekordhoz konfigurálva van egy áfacsoport, azonban az online rendelések esetében a vevő profiljában beállított áfacsoportot az adómotor nem fogja használni. 

### <a name="if-a-customers-shipping-address-has-a-tax-group-configured"></a>Ha egy vevő szállítási címéhez be van állítva egy adócsoport

Ha a vevő szállítási cím rekordjánál adócsoport van konfigurálva, és egy online rendelést (vagy sorelemet) szállítanak a vevő szállítási címére, akkor a vevő címrekordjában beállított adócsoportot az adómotor fogja használni az adószámítási célokra.

#### <a name="configure-a-tax-group-for-a-customers-shipping-address-record"></a>Adócsoport konfigurálása egy vevő szállítási cím rekordjához

Ha egy vevő szállítási cím rekordjának adócsoportját szeretné konfigurálni a Commerce-központban, kövesse az alábbi lépéseket.

1. Nyissa meg az **Összes ügyfél** lehetőséget, és válassza ki a kívánt ügyfelet. 
1. A **Címek** gyorslapon válassza ki a kívánt címet, majd válassza a **További beállítások \> Speciális** lehetőséget. 
1. A **Címek kezelése** oldal **Általános** lapján szükség szerint állítsa be az áfaértékét.

> [!NOTE]
> Az adócsoport a rendelési sor szállítási címe alapján van definiálva, és a célalapú adók az adócsoportnál vannak konfigurálva. További információ: [Online áruházak adóinak beállítása cél alapján](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination) című témakörben olvashat.

## <a name="order-pickup-in-store"></a>Rendelésfelvétel az üzletben

Az üzletbeli vagy a járdaszéli felvétellel megadott csomagfelvételeket megadó rendeléssorok esetén a kiválasztott átvételi áruház adócsoportja lesz alkalmazva. Az adócsoport adott üzlethez való konfigurálásáról az [Üzletek egyéb adóbeállításainak megadása](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores) című témakörben talál további tudnivalókat.

> [!NOTE]
> Amikor egy rendelési sort üzletben való átvételekor, a vevői cím adóbeállításait (ha be van állítva) az adómotor figyelmen kívül hagyja, és az átvételi üzlet adókonfigurációját alkalmazza. 

## <a name="additional-resources"></a>További erőforrások

[Áfa áttekintése](https://docs.microsoft.com/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=/dynamics365/commerce/toc.json) 

[Áfaszámítási módok a Kiindulás mezőben](https://docs.microsoft.com/dynamics365/finance/general-ledger/sales-tax-calculation-methods-origin-field?toc=/dynamics365/commerce/toc.json) 

[Áfa-hozzárendelés és felülbírálások](https://docs.microsoft.com/dynamics365/supply-chain/procurement/tasks/sales-tax-assignment-overrides?toc=/dynamics365/commerce/toc.json) 

[Teljesösszeg- és intervallumszámítási opciók áfakódokhoz](https://docs.microsoft.com/dynamics365/finance/general-ledger/whole-amount-interval-options-sales-tax-codes?toc=/dynamics365/commerce/toc.json) 

[Adómentesség számítása](tax-exempt-price-inclusive.md) 



[!INCLUDE[footer-include](../includes/footer-banner.md)]