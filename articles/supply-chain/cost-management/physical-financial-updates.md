---
title: Pénzügyi és fizikai frissítések
description: Ez a cikk áttekintést nyújt arról, hogy milyen típusú tranzakciók növelik vagy csökkentik a készletmennyiséget.
author: JennySong-SH
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTrans, InventTransVoucher
audience: Application User
ms.reviewer: kamaybac
ms.custom: 75023
ms.assetid: 128340e1-c573-48e6-b835-6c350d8dd0fb
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 345f07e7ba55f567c9956539241c080db958c848
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895844"
---
# <a name="physical-and-financial-updates"></a>Pénzügyi és fizikai frissítések

[!include [banner](../includes/banner.md)]

Ez a cikk áttekintést nyújt arról, hogy milyen típusú tranzakciók növelik vagy csökkentik a készletmennyiséget. 

A készlettranzakciók fizikailag és pénzügyileg is frissíthetőek a Dynamics 365 Supply Chain Management rendszerben. Egyes fizikai és pénzügyi tranzakciótípusok növelik a készlet mennyiségét, míg mások csökkentik.

## <a name="physical-increases"></a>Fizikai növekedések
Fizikai tranzakció feladásakor a tranzakciórekord állapota **Beérkezett**. A következő tranzakciók tekintendők fizikai mennyiségnövekedésnek:

-   Beszerzési rendelés – bevételezés
-   Értékesítési rendelés – csomagjegyzék – visszáru
-   Termelési rendelés készként jelentése
-   Termelési rendelés – kitárolási lista mellékterméke

## <a name="financial-increases"></a>Pénzügyi növekedések
Pénzügyi bevételezési tranzakció feladásakor a mennyiséget növelő tranzakciórekord állapota **Beszerezve**. A következő tranzakciók tekintendők pénzügyi mennyiségnövekedésnek:

-   Szállítói számla
-   Visszáru értékesítési rendelése – számla
-   Termelési megrendelés költségszámítása
-   Pozitív mennyiségű készletnaplók, például mozgás-, eredmény- és leltárnaplók, anyagjegyzékek és átmozgatás

## <a name="transactions-that-increase-quantity"></a>Mennyiséget növelő tranzakciók
A mozgóátlagon alapuló önköltségi ár mennyiséget növelő tranzakciók feladása. A cikkhez kiszámított mozgóátlagon alapuló önköltségi ár a pénzügyileg követett egyes készletdimenziók tranzakcióinak költségén alapul. A mozgóátlagos önköltségi árakkal kapcsolatos további tudnivalókat lásd: [Mozgóátlagon alapuló önköltségi árak](running-average-cost-price.md).

## <a name="transactions-that-decrease-quantity"></a>Mennyiséget csökkentő tranzakciók
A számított mozgóátlagon alapuló önköltségi ár használt a mennyiséget csökkentő tranzakció feladásakor, függetlenül attól, mely készletmodell van társítva a készlethez. A mennyiséget csökkentő tranzakció a feladás előtt korábban nem lehetett megjelölve egy másik tranzakcióhoz. Ha a fizikai tényleges készlet negatívvá válik, a készletköltség használt, amely meg van határozva a cikkhez a **Cikk** oldalon. 

> [!NOTE]
> Ha engedélyezve van a többhelyes funkció, ez a költség ehelyett az a készletköltség lesz, amely a helyhez van meghatározva az **Alapértelmezett rendelésbeállítások** képernyőn.

## <a name="physical-issues-vs-financial-issues"></a>Pénzügyi kiadások és a tényleges kiadások
Fizikai kiadási tranzakció feladásakor a tranzakciórekord állapota **Levonva**. A következő tranzakciók tekintendők fizikai kiadásnak:

-   Termelési rendelés – kitárolásilista-napló
-   Értékesítési rendelés - csomagjegyzék
-   Beszerzési rendelés – csomagjegyzék – visszáru

Pénzügyi tranzakció feladásakor a tranzakciórekord állapota **Eladva**. A következő tranzakciók tekintendők pénzügyi kiadásnak:

-   A termelési rendelések befejezése
-   Értékesítési rendelés - számla
-   Szállítói számlaforgalom
-   Negatív mennyiségű készletnaplók, például mozgás-, eredmény- és leltárnaplók, anyagjegyzékek és átmozgatás

A mozgóátlagon alapuló önköltségi ár mennyiséget csökkentő tranzakciók feladása. Így a készletzárás folyamata a cikk készletmodellben kiválasztott készletértékelési módszer alapján a kiadási tranzakciókat a bevételezési tranzakciókkal szemben egyenlíti ki.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]