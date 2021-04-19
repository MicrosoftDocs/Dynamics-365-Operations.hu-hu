---
title: Pénzügyi és fizikai frissítések
description: Ez a témakör áttekintést ad a készlet mennyiségét növelő vagy csökkentő tranzakciók típusairól.
author: AndersGirke
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
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 88432b9a5e564f9e81892e0bb379f95ff40d6c9d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842153"
---
# <a name="physical-and-financial-updates"></a>Pénzügyi és fizikai frissítések

[!include [banner](../includes/banner.md)]

Ez a témakör áttekintést ad a készlet mennyiségét növelő vagy csökkentő tranzakciók típusairól. 

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