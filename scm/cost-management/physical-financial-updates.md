---
title: "Pénzügyi és fizikai frissítések"
description: "Ez a témakör áttekintést ad a készlet mennyiségét növelő vagy csökkentő tranzakciók típusairól."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventTrans, InventTransVoucher
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 75023
ms.assetid: 128340e1-c573-48e6-b835-6c350d8dd0fb
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: d68006c756f6b29804cad1d05db9ced2bd33897d
ms.lasthandoff: 03/31/2017


---

# <a name="physical-and-financial-updates"></a>Pénzügyi és fizikai frissítések

[!include[banner](../includes/banner.md)]


Ez a témakör áttekintést ad a készlet mennyiségét növelő vagy csökkentő tranzakciók típusairól. 

A készlettranzakciók fizikailag és pénzügyileg is frissíthetőek a Microsoft Dynamics 365 for Operations rendszerben. Egyes fizikai és pénzügyi tranzakciótípusok növelik a készlet mennyiségét, míg mások csökkentik.

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
A mozgóátlagon alapuló önköltségi ár mennyiséget növelő tranzakciók feladása. A Dynamics 365 for Operations kiszámítja a cikkhez a mozgóátlagon alapuló önköltségi árat, amely a pénzügyileg követett egyes készletdimenziók tranzakcióinak költségén alapul. A mozgóátlagos önköltségi árakkal kapcsolatos további tudnivalókat lásd: [Mozgóátlagon alapuló önköltségi árak](running-average-cost-price.md).

## <a name="transactions-that-decrease-quantity"></a>Mennyiséget csökkentő tranzakciók
A Dynamics 365 for Operations a számított mozgóátlagon alapuló önköltségi árat használja, a mennyiséget csökkentő tranzakció feladásakor, függetlenül attól, mely készletmodell van társítva a készlethez. A mennyiséget csökkentő tranzakció a feladás előtt korábban nem lehetett megjelölve egy másik tranzakcióhoz. Ha a fizikai tényleges készlet negatívvá válik, a Dynamics 365 for Operations azt a készletköltséget használja, amely meg van határozva a cikkhez a **Cikk** oldalon. **Megjegyzés:** Ha engedélyezve van a többhelyes funkció, ez a költség ehelyett az a készletköltség lesz, amely a helyhez van meghatározva az **Alapértelmezett rendelésbeállítások** képernyőn.

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



