---
title: Felhőalapú keresés – áttekintés
description: Ez a témakör a felhőalapú keresésről ad áttekintést a következőben:Microsoft Dynamics 365 Commerce
author: ashishmsft
ms.date: 02/28/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.assetid: ''
ms.openlocfilehash: ed80ff42ea5c6e6a904ea2855953d006f66aad37
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273666"
---
# <a name="cloud-powered-search-overview"></a>Felhőalapú keresés – áttekintés

[!include [banner](includes/banner.md)]

Ez a témakör a felhőalapú keresésről ad áttekintést a következőben:Microsoft Dynamics 365 Commerce

A termék felderíthetővé tételével biztosíthatja, hogy a vevők gyorsan és egyszerűen megtalálják a termékeket a kategóriák böngészésével, kereséssel és szűréssel. A kiskereskedők úgy gondolja, hogy a termékfeloldás elsődleges eszköz a vevőknek a csatornákon keresztüli kommunikációjához, amelyet a felhőskálaegység (SCALE UNIT) ellát, például az e-commerce és a point of sale (POS).

A vevők megszokták a webes keresőmotorok, a kifinomult e-kereskedelmi webhelyek, a közösségi alkalmazások, a keresőkifejezések gépelésekor megjelenő automatikus javaslatok, a jellemzőalapú navigáció és a kiemelés szinte azonnali reakcióidejét. Ha az ügyfelek nem tudják gyorsan megtalálni azt a terméket, amit egy e-commerce üzletben keresnek, akkor nem fognak másik e-kereskedelmi üzletbe lépni.

A Commerce rendszer felhőalapú termékkövetéssel segíti a kiskereskedőket a felhasználói visszatartások és átváltások számának növelésében a csatornákon keresztül.

A Commerce keresési tapasztalat jobb lehetőségeket kínál a kiskereskedők számára a jobb termékkereskedhetőség érdekében. Ugyanakkor ezek a funkciók az e-commerce forgalomhoz szükséges skálázhatóságot és teljesítményt is biztosítják.

## <a name="browse-and-search"></a>Böngészés és keresés

A keresés relevanciája és teljesítménye kulcsfontosságú tényező a többcsatornás élményben, mivel a termékek felderítése elsősorban az információ lekérésére és a tartalom navigálására szolgáló keresési funkció alapján történik. A hatékony és hatásos böngészési és keresési élmény növeli a konverziót.

A következő ábra a jellemző böngészési és keresési funkciók egy példáját mutatja be.

![Keresés céloldala.](./media/SearchLanding.png)

## <a name="faceted-navigation-and-choice-summary"></a>A jellemzőalapú navigáció és a választási lehetőségek összegzése 

A jellemzőalapú navigálás révén a vevők könnyebben böngészhetik a tartalmat, ha megadják azokat a finomítók számára, amelyek egy kifejezéskészlet kifejezéseihez kötődnek. Ha egy vevő kiválasztott és alkalmazott finomítókat, akkor megjelenik a választási lehetőségek összesítése. 

A jellemzőalapú navigáció segítségével különböző finomítók állíthatók be a kifejezéskészlet különböző kifejezéseihez anélkül, hogy további oldalakat kellene létrehoznia. 

A következő ábra egy példát mutat be, ahol a jellemzőalapú navigálás kerül felhasználásra egy keresésben.

![Választási lehetőségek összegzése.](./media/ChoiceSummary.png)

## <a name="immersive-autosuggest"></a>Modern automatikus ajánlások

A jelenlegi automatikus visszacsatlott funkció azokat a kulcsszavakat jeleníti meg, amelyek az egyező kulcsszó keresését indítják. A Commerce rendszer új fejlesztései miatt a vevők gyakran még a beírás befejezése előtt is fel tudják fedezni a termékekre mutató hivatkozásokat.

A Commerce ezenkívül támogatja a különböző kategóriák kulcsszó-egyezésekkel kapcsolatos funkcióit is. Ez a funkció lehetővé teszi a vevők számára, hogy megtekintsék az egyező kulcsszavak számát a kategóriákban, és más kategóriákban keressenek egy kifejezést.

A következő ábra egy példát mutat be, ahol a modern automatikus javaslat van használatban.

![Modern automatikus ajánlások.](./media/ImmersiveAutoSuggestUX.png)

## <a name="sort"></a>Rendezés

A rendezési funkció lehetővé teszi a vevők számára a kategóriaeredmények rendezését, keresését és tallózását, valamint az eredmények finomítását például az ár, a terméknév és a termékszám alapján. Ha engedélyezi a termékajánlásokat [a](product-recommendations.md) környezetben, akkor a vevők speciális rendezési feltételek, például új, legjobb eladási és trend szerint is rendezheti az eredményeket.


> [!NOTE]
> Ezek a felhőalapú keresési funkciók a 10.0.8 verziótól érhetők el. Győződjön meg róla, hogy van "True" **értékű bejegyzés a Commerce Parameters és a Configuration Parameters > "ProductSearch.UseAzureSearch" paraméterben**. 
![A felhőalapú keresés konfigurációs paraméterei.](./media/CloudPoweredSearchConfigurationParameters.png)
>A Commerce SSK 9.35+ Dynamics 365 Commerce verzióban és 10,0,20 kiadásban speciális rendezési beállítások, például új, bestsing és trendek érhetők el.  


## <a name="additional-resources"></a>További erőforrások

[Az alapértelmezett kategória-céloldal és keresési találatoldal áttekintése](category-search-page-overview.md)

[SEO-metaadatok kezelése](manage-seo-metadata.md)


[!INCLUDE [footer-include](../includes/footer-banner.md)]
