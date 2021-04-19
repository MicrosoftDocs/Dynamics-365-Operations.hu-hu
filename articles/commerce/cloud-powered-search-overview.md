---
title: Felhőalapú keresés – áttekintés
description: Ez a témakör áttekintést nyújt a felhőalapú keresésről a Microsoft Dynamics 365 Commerce alkalmazásban.
author: ashishmsft
ms.date: 06/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b5182df9d45a3b5d2572a5b6b391c924ef23bf9a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800421"
---
# <a name="cloud-powered-search-overview"></a>Felhőalapú keresés – áttekintés

[!include [banner](includes/banner.md)]

Ez a témakör áttekintést nyújt a felhőalapú keresésről a Microsoft Dynamics 365 Commerce alkalmazásban.

A termék felderíthetővé tételével biztosíthatja, hogy a vevők gyorsan és egyszerűen megtalálják a termékeket a kategóriák böngészésével, kereséssel és szűréssel. A kiskereskedők a termékfelderítésre elsődleges eszközként tekintenek az ügyfélinterakciókhoz összes kereskedelmi csatornán.

A vevők megszokták a webes keresőmotorok, a kifinomult e-kereskedelmi webhelyek, a közösségi alkalmazások, a keresőkifejezések gépelésekor megjelenő automatikus javaslatok, a jellemzőalapú navigáció és a kiemelés szinte azonnali reakcióidejét. Ha a vevők nem találnak meg elég gyorsan egy terméket egy e-kereskedelmi áruházban, akkor habozás nélkül váltani fognak egy másik e-kereskedelmi áruházra.

A felhőalapú termék-felderíthetőség a Dynamics 365 Commerce alkalmazásban segít a kiskereskedőknek a vásárlók megtartásának és a konverziós rátának a növelésében az összes csatornán, mind az e-kereskedelmi csatornákat, mind a pénztár (POS) csatornákat beleértve.

A Dynamics 365 Commerce keresési élmény továbbfejlesztett képességekkel rendelkezik, amelyek segítenek a kiskereskedők számára a jobb termék-felderíthetőség elérésében. Ezek a képességek egyidejűleg az e-kereskedelmi forgalomhoz szükséges méretezhetőséget és teljesítményt is biztosítják.

## <a name="browse-and-search"></a>Böngészés és keresés

A keresés relevanciája és teljesítménye kulcsfontosságú tényező a többcsatornás élményben, mivel a termékek felderítése elsősorban az információ lekérésére és a tartalom navigálására szolgáló keresési funkció alapján történik. A hatékony és hatásos böngészési és keresési élmény növeli a konverziót.

A következő ábra a jellemző böngészési és keresési funkciók egy példáját mutatja be.

![Keresés céloldala](./media/SearchLanding.png)

## <a name="faceted-navigation-and-choice-summary"></a>A jellemzőalapú navigáció és a választási lehetőségek összegzése 

A jellemzőalapú navigálás révén a vevők könnyebben böngészhetik a tartalmat, ha megadják azokat a finomítók számára, amelyek egy kifejezéskészlet kifejezéseihez kötődnek. Ha egy vevő kiválasztott és alkalmazott finomítókat, akkor megjelenik a választási lehetőségek összesítése. 

A jellemzőalapú navigáció segítségével különböző finomítók állíthatók be a kifejezéskészlet különböző kifejezéseihez anélkül, hogy további oldalakat kellene létrehoznia. 

A következő ábra egy példát mutat be, ahol a jellemzőalapú navigálás kerül felhasználásra egy keresésben.

![Választási lehetőségek összegzése](./media/ChoiceSummary.png)

## <a name="immersive-autosuggest"></a>Modern automatikus ajánlások

A jelenlegi automatikus ajánlások funkció csak azokat a kulcsszavakat jeleníti meg, amelyek a megfelelő kulcsszó keresését jelenítik meg. Az új fejlesztések miatt a Dynamics 365 Commerce vevői gyakran a gépelés befejeződése előtt felfedezhetik a termékekre mutató hivatkozásokat.

Dynamics 365 Commerce támogatja a kulcsszavas egyeztetések működését is a különböző kategóriákban. Ez a funkció lehetővé teszi a vevők számára, hogy megtekintsék az egyező kulcsszavak számát a kategóriákban, és más kategóriákban keressenek egy kifejezést.

A következő ábra egy példát mutat be, ahol a modern automatikus javaslat van használatban.

![modern automatikus ajánlások](./media/ImmersiveAutoSuggestUX.png)

## <a name="sort"></a>Rendezés

A Dynamics 365 Commerce továbbfejlesztett rendezésével a vevők rendezhetnek, kereshetnek és böngészhetnek a keresési találatok között, valamint finomíthatják azokat ár, terméknév és termékszám szerint. A vevők az eredményeket úgy is rendezhetik, hogy a termék új, a legnépszerűbb vagy újonnan hozzáadott-e.

>[!NOTE]
>Ezek a felhőalapú keresési funkciók a 10.0.8 verziótól érhetők el. Ellenőrizze, hogy a **Kereskedelmi paraméterek > Konfigurációs paraméterek** között van-e egy bejegyzés a következőhöz: „ProductSearch. UseAzureSearch 'igaz' értékre állítva”. 
![A felhőalapú keresés konfigurációs paraméterei](./media/CloudPoweredSearchConfigurationParameters.png)

## <a name="additional-resources"></a>További erőforrások

[Alapértelmezett kategória-céloldal és keresési találatoldal áttekintése](category-search-page-overview.md)

[SEO-metaadatok kezelése](manage-seo-metadata.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
