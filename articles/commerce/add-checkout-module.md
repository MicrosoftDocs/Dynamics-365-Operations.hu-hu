---
title: Fizetésmodul
description: Ez a témakör egy fizetésmodul egy laphoz való hozzáadásának és a kötelező tulajdonságok beállításának módját mutatja be.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4b810441fd25d41ee0893b119b4f7d91e7435d21
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697083"
---
# <a name="checkout-module"></a>Fizetésmodul

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör egy fizetésmodul egy laphoz való hozzáadásának és a kötelező tulajdonságok beállításának módját mutatja be.

## <a name="overview"></a>Áttekintés

A fizetésmodul egy speciális tároló, amely a rendelés létrehozásához szükséges összes modult tárolja. A fizetésmodulban szerepelhetnek olyan modulok, amelyek a szállítási címet, a szállítási módokat, a számlázási adatokat, a rendelési összesítéseket és a vevői rendeléshez kapcsolódó egyéb információkat kezelik. Lépésről lépésre bemutatja a folyamatot, amely során a vevő megadja a vásárláshoz szükséges összes információt.

A fizetésmodul a kosár azonosítója alapján jeleníti meg az adatokat. Ezt a kosárazonosítót a rendszer böngésző-cookie-ként menti. Egy kosárazonosító szükséges a fizetésmodul adatainak megjelenítéséhez, például a rendelésben szereplő cikkekhez, a teljes összeghez és az engedményekhez.

## <a name="checkout-module-properties"></a>Fizetésmodul tulajdonságai

A fizetésmodulon belül egy több modulból álló készlet található. A szélesség tulajdonsággal meghatározhatja, hogy a fizetésmodulban szereplő cikkek illeszkedjenek-e annak szélességhez, vagy ki kell tölteniük a képernyőt.

A fizetésmodul több helyet tartalmaz, például a **Fizetési információk** helyet, egy **Rendelésösszesítés** helyet és egy **Rendelés leadása** helyet. Minden hely olyan modulok egy csoportját támogatja, amelyek egy adott elrendezésben jelennek meg a lapon. Például a **Fizetési információk** hely tartalmazza az összes olyan modult, amely a fizetés elindításához szükséges, például a szállítási cím és a fizetési mód moduljait. A **Rendelésösszesítés** hely egy rendelés összesítését jeleníti meg, és támogatja a rendelés leadásának műveletét. A **Rendelés leadása** hely is támogatja a rendelésleadási műveletet. A rendelésleadási modulokat két helyen lehet megadni a különböző platformoktól érkező rendelések leadási folyamatának optimalizálásához.

### <a name="modules-that-can-be-used-in-the-checkout-module"></a>A fizetésmodulban használható modulok

- **Szállítási cím** – Ez a modul lehetővé teszi a vevő számára, hogy megadja vagy kiválassza a rendelés szállítási címét. Ha a vevő be van jelentkezve, akkor a rendszer a vevő korábban mentett címeit jeleníti meg. A vevő ezután választhatja ezekből a címekből. A vevő új címet is hozzáadhat. A szállítási cím a rendelésben szereplő összes szállítandó cikkhez használatos. Nem lehet testreszabni az egyes sortételekhez. A szállítási címek formátumai országonként vagy régiónként definiálhatók, és ez a modul érvényesíti az ország-/régióspecifikus szabályokat. Bár a modul nem biztosít címellenőrzést, a címellenőrzés személyre szabással megvalósítható. Ha a rendelés csak azokat a cikkeket tartalmazza, amelyek az üzletben kerülnek felvételre, akkor a program automatikusan elrejti ezt a modult.
- **Szállítási lehetőségek** – Ez a modul lehetővé teszi a vevő számára, hogy kiválasszon egy szállítási módot a rendeléshez. A szállítási lehetőségek a szállítási címen alapulnak. Ha a szállítási cím módosul, akkor a szállítási módokat újra le kell kérdezni. Ha a rendelés csak azokat a cikkeket tartalmazza, amelyek az üzletben kerülnek felvételre, akkor a program automatikusan elrejti ezt a modult.
- **Fizetési szakasz tárolója** – Ez a modul egy olyan tároló, amelyben több modult is elhelyezhet egy szakasz létrehozásához a fizetési folyamaton belül. Például az összes fizetéshez kapcsolódó modult elhelyezheti ebben a tárolóban, hogy egy szakaszként jelenjenek meg. Ez a modul csak a folyamat elrendezését érinti.
- **Ajándékutalvány** – Ez a modul lehetővé teszi a vevők számára, hogy egy ajándékutalvány segítségével fizessenek egy rendelést. Csak a Microsoft Dynamics 365 Commerce ajándékutalványok használatát támogatja. Egy vagy több ajándékutalvány alkalmazható egy rendelésre. Ha az ajándékutalvány egyenlege nem fedi le a kosárban szereplő összeget, akkor az ajándékutalvány egy másik fizetési móddal kombinálható. Ajándékutalványok csak akkor válthatók be, ha a vevő be van jelentkezve.
- **Hűségpontok** – Ez a modul lehetővé teszi, hogy a vevő a hűségpontok felhasználásával fizessen egy rendelést. A rendelkezésre álló pontok és lejáró pontok összesítését biztosítja, és lehetővé teszi a vevő számára, hogy kiválassza a beváltani kívánt pontok számát. Ha a vevő nincs bejelentkezve vagy nem tagja a hűségprogramnak, illetve a kosár teljes összege 0 (nulla), akkor a rendszer automatikusan elrejti ezt a modult.
- **Hitelkártya** – Ez a modul lehetővé teszi a vevők számára, hogy egy hitelkártyával fizessenek egy rendelést. Ha a kosarat hűségpontokkal vagy ajándékutalvánnyal fedezik, vagy a kosár teljes összege 0 (nulla), akkor a rendszer automatikusan elrejti ezt a modult. A hitelkártyás integrációt a Adyen fizetési összekötő biztosítja. További tájékoztatás az összekötő használatáról: [Adyen fizetési összekötő](https://).
- **Számlázási cím** – Ez a modul lehetővé teszi a vevő számára a számlázási adatok megadását. Ezt az információt az Adyen a hitelkártyaadatokkal együtt dolgozza fel. Ez a modul egy olyan beállítást tartalmaz, amely lehetővé teszi a vevők számára a számlázási cím szállítási címként történő használatát.
- **Kapcsolattartási adatok** – Ez a modul lehetővé teszi a vevő számára, hogy megadja vagy módosítsa a rendeléshez tartozó kapcsolattartási adatokat (e-mail-cím).
- **Rendelés leadása** – Ez a modul lehetővé teszi, hogy a vevő leadjon egy megrendelést.
- **Tartalomgazdag blokk** – Ez a modul minden olyan üzenetküldést tartalmaz, amelyet a tartalomkezelő rendszer (CMS) vezérel. Például tartalmazhatja a következő üzenetet: „A rendeléssel kapcsolatos problémák esetén hívja az 1-800-FABRIKAM számot”. 
- **Rendelésösszesítés** – Ez a modul egy rendelés költségrészletezését jeleníti meg.
- **Rendelés sortételei** – Ez a modul a rendelésbe foglalandó cikkek összesítését jeleníti meg.

## <a name="retail-server-interaction"></a>Kiskereskedelmi kiszolgálói interakció

A legtöbb fizetési információt (például a szállítási címet és a szállítási módot) a kosár tárolja, és a rendelés részeként kerül feldolgozásra. Az egyetlen kivételt a hitelkártyával kapcsolatos adatok jelentik. Ezeket az adatokat a rendszer közvetlenül az Adyen fizetési összekötő használatával dolgozza fel. A kifizetés engedélyezve van, de nem kerül felszámításra.

## <a name="add-a-checkout-module-to-a-new-page-and-set-the-required-properties"></a>Fizetésmodul hozzáadása egy laphoz és a kötelező tulajdonságok beállítása

A fizetésmodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Lépjen a **Töredék \> Új töredék** lehetőségre, és adja meg az új töredéknek a **Fizetési töredék** nevet.
1. Adjon hozzá egy fizetési modult a töredékhez.
1. Adjon hozzá egy fejlécet a fizetési modulhoz.
1. A **Fizetési információk** helyen adja meg a szállítási címet, a szállítási módokat, a fizetési szakasz tárolóját és a kapcsolattartási adatok modult. A **Fizetési információk** helyen most négy szakasznak kell lennie.
1. A fizetési szakasz tároló moduljában adjon hozzá ajándékutalvány, hűségpontok és hitelkártya modulokat. Így biztosíthatja, hogy az összes fizetési mód együtt jelenjen meg egy szakaszban.
1. A **Rendelésösszesítés** helyen adja hozzá a rendelésösszesítés, hirdetésleadás és tartalomgazdag blokk modulokat.
1. A tartalomgazdag blokk modulban adja hozzá a következő szöveget: **A rendeléssel kapcsolatos kérdés esetén hívja az 1-800-FABRIKAM számot**.
1. A **Rendelés leadása** helyen adjon hozzá egy rendelésleadási modult.
1. Válassza a **Mentés** lehetőséget. Előfordulhat, hogy egyes modulok nem jelennek meg az előnézetben, mert nem rendelkeznek kosárkontextussal.
1. Adja be a töredéket, és tegye közzé.
1. Hozzon létre egy olyan sablont, amely az új fizetési töredéket használja.
1. Hozzon létre egy olyan fizetési oldalt, amely az új sablont használja.

## <a name="additional-resources"></a>További erőforrások

[Kezdő csomag áttekintése](starter-kit-overview.md)

[Tárolómodul](add-container-module.md)

[Vásárlásmező modul](add-buy-box.md)

[Kosármodul](add-cart-module.md)

[Rendelésmegerősítés modul](order-confirmation-module.md)

[Fejlécmodul](author-header-module.md)

[Láblécmodul](author-footer-module.md)
