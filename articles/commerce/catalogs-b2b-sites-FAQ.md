---
title: Commerce-katalógusok B2B-hez – GYIK
description: Ez a cikk a katalógusokkal kapcsolatos gyakori kérdésekre ad Microsoft Dynamics 365 Commerce választ.
author: ashishmsft
ms.date: 05/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: af69c3d27142a961049470dd1292ffbc3d8387a9
ms.sourcegitcommit: 6616b969afd6beb11a79d8e740560bf00016ea7f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/17/2022
ms.locfileid: "9027368"
---
# <a name="commerce-catalogs-for-b2b-faq"></a>Commerce-katalógusok B2B-hez – GYIK

[!include [banner](includes/banner.md)]

Ez a cikk a vállalat által Microsoft Dynamics 365 Commerce [használt (B2B) katalógusokkal kapcsolatban leggyakrabban feltett kérdésekre ad választ](catalogs-b2b-sites.md).

## <a name="why-cant-i-configure-a-catalog-specific-navigation-hierarchy-or-see-an-option-to-associate-a-customer-hierarchy"></a>Miért nem lehet katalógusspecifikus navigációs hierarchiát konfigurálni, vagy látni egy vevői hierarchia társítási beállítását?

Győződjön meg arról, hogy **engedélyezve van a Több katalógus használatának engedélyezése a kiskereskedelmi** **csatornákon** szolgáltatás a Commerce Headquarters Szolgáltatáskezelési munkaterületén. Ezenkívül győződjön meg róla, hogy a környezetben a Commerce 10.0.27-es vagy újabb verziója van használatban.

## <a name="can-i-view-the-catalog-specific-hierarchy-and-enrich-category-pages-in-commerce-site-builder"></a>Megtekinthet katalógusspecifikus hierarchiát, és bővítheti a kategóriaoldalakat a Commerce webhelyszerkesztőben?

Igen, a Commerce webhelyszerkesztő **webhely**-szerkesztője, akik hozzáférnek a webhelyszerkesztő Termékek laphoz, kiválaszthat egy katalógust, és megtekintheti a katalógusspecifikus hierarchiát. A Termékek **lapon** a felhasználók a katalógus egy adott kategóriájához tartozó kategóriaoldalt is bővíthetnek. A további tudnivalókat lásd: [Kategória céloldalának bővítése](enrich-category-page.md). Ha egy katalógusra jellemző bővítő hierarchiát szeretne, akkor azt ajánljuk, hogy az adott katalógushoz egyedi és egyedi navigációs hierarchiát használjon.

## <a name="can-a-b2b-shopper-purchase-from-multiple-catalogs-in-a-single-checkout"></a>Egy B2B vásárló egyetlen pénztárban több katalógusból is vásárolhat?

Igen, egy pénztárban több katalógusból is lehet beszerzést tenni. A B2B üzletkötők a bevásárlókocsiban található katalógus-jelzővel határozzák meg, hogy mely cikkek hozzáadása a katalógushoz.

## <a name="if-a-b2b-shopper-purchases-the-same-item-from-different-catalogs-what-is-the-expected-behavior"></a>Ha egy B2B vásárló ugyanazt a cikket különböző katalógusok alapján vásárolja meg, milyen viselkedést vár?

Annak ellenére, hogy egy adott felhasználónak adott időpontban több katalógushoz lehet hozzáférése, az elvárás az, hogy az ilyen katalógusok termékei kölcsönösen kizárják egymást. Más szóval, ideális esetben ugyanaz a termék nem lehet egynél több katalógus része egy adott felhasználó számára.

Ha azonban olyan helyzet áll elő, amelyben ugyanaz a termék több katalógushoz tartozik, a rendszer az adott termékhez több kosársort tart fenn. Minden katalógushoz külön sor lesz. A pénztárnál nem egyesíti két különböző katalógus ugyanazon termékét.

## <a name="when-a-b2b-shopper-is-shopping-is-there-any-validation-for-catalog-availability"></a>Amikor egy B2B vásárló vásárol, van érvényesség-ellenőrzés a katalógus elérhetőségére?

Igen. A B2B üzletkötő csak akkor léphet tovább a pénztárba, ha a kosárban lévő összes cikk érvényes katalógusból van. Ha a bevásárlókocsiba tartozó cikkek lejárt vagy visszavont katalógusok, azok törlődnek, és a felhasználó értesítést kap.

## <a name="during-the-shopping-experience-are-search-and-product-discovery-including-related-and-recommended-product-collections-catalog-specific"></a>A vásárlás során a keresés és a termékfedezés (beleértve a kapcsolódó és ajánlott termékgyűjteményeket) katalógusspecifikus?

Igen. Ha egy felhasználó kiválaszt egy adott katalógust, akkor az egész bevásárlókocsi katalógusspecifikus lesz. Ez az utazás olyan termékelemzési tapasztalatokat foglal magában, mint például a keresési javaslatok, a keresési eredmények, a kategóriaeredmények, a finomítók, az árképzés, az attribútumok és a javasolt termékek (például új, legjobb eladási, trendek, gyakran vásárolt együtt és kapcsolódó termékek).

## <a name="can-a-b2b-shopper-purchase-from-the-default-assortment-catalogid0"></a>Lehet egy B2B vásárlót az alapértelmezett szortimentből (catalogID=0)?

Nem, a B2B vásárló nem vásárolhat az alapértelmezett szortimentből. A szortiment csak névtelen böngészésre szolgál. Ha egy B2B üzletkötőnél hiányoznak a katalógus-hozzárendelések (az adminisztrációtól függőben lévő frissítések), nem láthatják az ő által kiválasztható katalógusokat, és nem lesz látható kategóriahierarchia.

## <a name="can-marketing-content-be-curated-for-a-product-that-is-specific-to-a-catalog"></a>A marketingtartalmak egy katalógushoz tartozó termékhez összesíthet?

Jelenleg a termékgazdagítás csak a telephely és csatorna szintjén támogatott. Más szóval, ha egy terméket bővít, akkor az több katalógus között meg lesz osztva, és az adott termék megfelelő termék részletező lapja (PDP) ugyanúgy jelenik meg az adott webhely összes katalógusában.

## <a name="is-catalog-support-available-for-both-b2b-and-business-to-consumer-b2c-online-channels"></a>Elérhető a katalógustámogatás a B2B és a 2C online csatornák számára?

A Commerce katalógusok jelenleg csak B2B csatornákkal való munkára szolgálnak.

## <a name="can-we-set-up-catalog-specific-upsellcross-sell-items"></a>Be lehet állítani katalógusspecifikus cikk-értékesítéseket/kereszteladásokat?

Jelenleg csak a kapcsolódó termékek funkciói támogatottak. A hívásközpontok számára ugyanakkor elérhetők a további és a kereszteladásos cikk-konfigurációk.

A következő funkciók csak hívásközpontok esetén is támogatottak:

- Katalógus forráskódja
- Forrás- és válaszkulcsok használata a költségek és a válaszmértékek nyomon követésére
- Katalógusspecifikus rendelés- és cikk-parancsfájlok
- Katalógusoldal-elemzés
- Katalóguskérések
- Részletfizetések
- Ingyenes termékek forráskódok alapján

## <a name="can-we-use-catalog-source-codes-for-b2b-orders-through-the-e-commerce-portal"></a>Használhat katalógus forráskódokat a B2B rendelésekhez az e-commerce portálon keresztül?

Nem. A katalógus forráskódok csak hívásközponti csatornáknál támogatottak.

## <a name="additional-resources"></a>További erőforrások

[Commerce-katalógusok létrehozása B2B webhelyekhez](catalogs-b2b-sites.md)

[Commerce-katalógusok B2B-testreszabásokra vonatkozó bővíthetőségi hatása](catalogs-b2b-sites-dev.md)
