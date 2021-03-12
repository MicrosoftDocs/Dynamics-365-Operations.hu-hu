---
title: Termékadatok oldalainak áttekintése
description: Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 Commerce termékrészletek oldalairól (PDP-k).
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b0f50b4e7b78f4a5b9fe674a101476879923e10d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979828"
---
# <a name="product-details-pages-overview"></a>Termékadatok oldalainak áttekintése

[!include [banner](includes/banner.md)]

Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 Commerce termékrészletek oldalairól (PDP-k).

## <a name="overview"></a>Áttekintés

A PDP részletes információt nyújt a termékről, és a vevők számára lehetővé teszi a termékopciók például a méret, a stílus és a szín kiválasztását. A PDP-nek meg kell jelenítenie az összes olyan termékre vonatkozó információt, amely a vevőnek a beszerzési döntés meghozatalához szükséges.

A következő ábrán a PDP egy példája látható.

![Példa a termék részleteit tartalmazó oldalra](./media/pdp.PNG)

## <a name="header-and-footer-modules"></a>Fejléc- és láblécmodulok

A PDP felső részén egy fejléc jelenik meg, amely az összes termékkategóriát és az egyéb olyan oldalakt, amelyet a kereskedő azt szeretné, hogy böngésznének. A lap alján van egy lábléc, amely gyorshivatkozásokat tartalmaz a különböző témájú témákhoz, amelyek érdekesek lehetnek a vevők számára.

## <a name="buy-box-module"></a>Vásárlásmező-modul

A PDP legfontosabb modulja a vásárlásmező modul, amely a lap fő szakaszának első elemeként jelenik meg. A Vásárlásmező modul fontos termék adatait jeleníti meg, mint például a termék neve, a termék leírása, a termék ára, a termék képei és a termék minősítései.

A vásárlódoboz modul lehetővé teszi a vevő számára a termék opciók kiválasztását (például a méretet, a stílust és a színt), illetve azt, hogy a terméket hozzáadja a kosárhoz. Azt is lehetővé teszi, hogy a vevő online vásárolja meg a terméket, és vegye egy üzletben vegye át. A vásárlás online és az átvétel üzletben modul a Bing Maps alkalmazásprogramozási felületek (API-k) integrációját használja hogy megkeresse a közeli üzleteket vagy üzleteket egy másiik helye, amit az ügyfél meghatároz.

A vásárlódoboz modulhoz termékazonosító szükséges. Ez az azonosító az oldal kontextusából van származtatva. Ha egy vásárlómező modult egy olyan oldalhoz ad hozzá, amelyben a lap környezete nem tartalmaz termékazonosítót, akkor az az adatokat nem fogja helyesen megjeleníteni.

## <a name="product-specifications-module"></a>Termékleírások modul

A termékleírások modul a termékkel kapcsolatos további részletek megjelenítésére használható. Ezek a részletek a termékattribútumokból származnak a Commerce alkalmazásból. A termékspecifikációk modulja minden olyan attribútumot megjelenít, amelyben a **látható** tulajdonság **igaz** értékre van állítva. A termékattribútumok beolvasásához szükséges a termékazonosító.

## <a name="recommendations-module"></a>Ajánlatok modul

A PDP egyik fontos modulja az ajánlatok modul. Miközben a vevők böngészik a termékeket, további termék lehetőségeket kell megjeleníteni számukra, hogy megtalálják a megfelelő terméket, és megvásárolhassák azt. Ajánlások segítik a vevőket, hogy könnyen felfedezhessék a kapcsolódó tartalmakat, és folytathassák a vásárlást.

Különböző típusú ajánláslisták érhetők el:

- Az **Emberek ezt is szeretik** lista gépi tanuláson alapul. A többi vevő tranzakciós előzményeit használja a javaslatok biztosítására. Ezt a listát a javaslatok szolgáltatás hozza létre, és a „Vásárlók akik megvásárolták a következőket is megvásárolták…” listákhoz hasonlít. A lista létrehozásához egy termékazonosító szükséges.
- A Commerce termékeihez konfigurálható egy **Kapcsolódó** lista. Például egy barna bőr utazás kézitáskához, több bőr kézitáska, iletve más utzaásokhoz készült tásaki is konfigurálható a kapcsolódó listához. Más típusú kapcsolódó listák, például a **Tartozékok** és **Több ehhez hasonló** is konfigurálható a Commerce alkalmazásban. A lista létrehozásához egy termékazonosító szükséges. Ha tehát egy kezdőlaphoz adják hozzá, és a lap környezete nem tartalmaz termékazonosítót, akkor a lista üres lesz.
- Algoritmus alapján léterhozott ajánlási listák listák, például **Népszerű**, **Legnépszerűbb** és **Új** használhatók a PDP-ken. Annak ellenére, hogy ezek a listák nem közvetlenül kapcsolódnak a PDP termékeihez, egy másik módot kínálnak arra, hogy a vevők könnyebben megtalálják azokat a termékeket, amelyek érdekesek lehetnek számukra. Az ilyen típusú listákhoz nem szükséges termékazonosító. Ezek általános listák, amelyek a webhelyen tapasztalható különböző vásárlási szokások alapján jönnek létre.
- A Szerkesztői listák manuálisan válogatott listák. Előfordulhat például, hogy egy kiskereskedő úgy dönt, hogy manuálisan szeretné összeállítani a bemutatni kívánt termékek listáját.

## <a name="ratings-and-reviews-modules"></a>Értékelések és vélemények modulok

Három modul használható a vélemények megjelenítésére és hozzáadására:

- **Értékelések** – ez a modul a más vevők által adott értékeléseket és véleményeket listázza. A vevők rendezni és szűrni tudják a véleményeket. Ez a modul a vevők kedvelt vagy nem kedvelt értékelését, valamint a problémák jelentését is lehetővé teszi.
- **Értékelés írása** – ezzel a modullal a vevők saját értékelést írhatnak a termékhez.
- **Minősítési hisztogram**  – ez a modul tartalmaz egy olyan hisztogramot, amely egy termék minősítési tendenciáját jeleníti meg.

További részletekért lásd: [Minősítések és értékelések áttekintése](ratings-reviews-overview.md).

## <a name="marketing-modules"></a>Marketing modulok

Ha egy adott termék esetében a marketingtartalom egyedi, akkor a PDP-hez bármilyen marketingmodul hozzáadható. A marketingmodulokat egy PDP-hez a lap „gazdaggá tétele” révén lehet hozzáadni. A további tudnivalókat lásd [A termékoldal bővítése](enrich-product-page.md) lapon.

## <a name="additional-resources"></a>További erőforrások

[Kezdőlap áttekintése](quick-tour-home-page.md)

[Kosár és pénztár oldalainak áttekintése](quick-tour-cart-checkout.md)

[Fiókkezelési oldalak áttekintése](quick-tour-account-management.md)

[A termékoldal bővítése lap](enrich-product-page.md)
