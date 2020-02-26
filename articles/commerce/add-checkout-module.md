---
title: Fizetésmodul
description: Ez a témakör egy fizetésmodul egy laphoz való hozzáadásának és a kötelező tulajdonságok beállításának módját mutatja be.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: 3805c0faabc8afc3decffb924b7f25332ff1ab16
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025390"
---
# <a name="checkout-module"></a>Fizetésmodul


[!include [banner](includes/banner.md)]

Ez a témakör egy fizetésmodul egy laphoz való hozzáadásának és a kötelező tulajdonságok beállításának módját mutatja be.

## <a name="overview"></a>Áttekintés

A fizetésmodul egy speciális tároló, amely a rendelés létrehozásához szükséges összes modult tárolja. Lépésről lépésre bemutatja a folyamatot, amely során a vevő megadja a vásárláshoz szükséges összes információt. A szállítási cím, a szállítási mód és a számlázási adatok rögzítése történik. Ezenkívül a rendelés összesítését és a vevői rendeléshez kapcsolódó egyéb információkat is tartalmaz.

A fizetésmodul a kosár azonosítója alapján jeleníti meg az adatokat. Ezt a kosárazonosítót a rendszer böngésző-cookie-ként menti. Egy kosárazonosító szükséges a fizetésmodul adatainak megjelenítéséhez, például a rendelésben szereplő cikkekhez, a teljes összeghez és az engedményekhez.

## <a name="checkout-module-properties"></a>Fizetésmodul tulajdonságai

A fizetési modul a rendelés összesítését jeleníti meg, és biztosítja a rendelés elküldésére szolgáló funkciókat. A rendelés elküldése előtt szükséges összes ügyféladat összegyűjtéséhez további modulokat kell a fizetési modulhoz adni. Ezért a kiskereskedők rugalmasan hozzáadhatnak egyéni modulokat a fizetési folyamathoz, vagy szükség szerint kizárhatnak modulokat.

### <a name="modules-that-can-be-used-in-the-checkout-module"></a>A fizetésmodulban használható modulok

- **Szállítási cím** – Ez a modul lehetővé teszi a vevő számára, hogy megadja vagy kiválassza a rendelés szállítási címét. Ha a vevő be van jelentkezve, akkor a rendszer a vevő korábban mentett címeit jeleníti meg. A vevő ezután választhatja ezekből a címekből. A vevő új címet is hozzáadhat. A szállítási cím a rendelésben szereplő összes szállítandó cikkhez használatos. Nem lehet testreszabni az egyes sortételekhez. A szállítási címek formátumai országonként vagy régiónként definiálhatók, és ez a modul érvényesíti az ország-/régióspecifikus szabályokat. Bár a modul nem biztosít címellenőrzést, a címellenőrzés személyre szabással megvalósítható. Ha a rendelés csak azokat a cikkeket tartalmazza, amelyek az üzletben kerülnek felvételre, akkor a program automatikusan elrejti ezt a modult.
- **Szállítási lehetőségek** – Ez a modul lehetővé teszi a vevő számára, hogy kiválasszon egy szállítási módot a rendeléshez. A szállítási lehetőségek a szállítási címen alapulnak. Ha a szállítási cím módosul, akkor a szállítási módokat újra le kell kérdezni. Ha a rendelés csak azokat a cikkeket tartalmazza, amelyek az üzletben kerülnek felvételre, akkor a program automatikusan elrejti ezt a modult.
- **Fizetési szakasz tárolója** – Ez a modul egy olyan tároló, amelyben több modult is elhelyezhet egy szakasz létrehozásához a fizetési folyamaton belül. Például az összes fizetéshez kapcsolódó modult elhelyezheti ebben a tárolóban, hogy egy szakaszként jelenjenek meg. Ez a modul csak a folyamat elrendezését érinti.
- **Ajándékutalvány** – Ez a modul lehetővé teszi a vevők számára, hogy egy ajándékutalvány segítségével fizessenek egy rendelést. Csak a Microsoft Dynamics 365 Commerce ajándékutalványok használatát támogatja. Egy vagy több ajándékutalvány alkalmazható egy rendelésre. Ha az ajándékutalvány egyenlege nem fedi le a kosárban szereplő összeget, akkor az ajándékutalvány egy másik fizetési móddal kombinálható. Ajándékutalványok csak akkor válthatók be, ha a vevő be van jelentkezve.
- **Hűségpontok** – Ez a modul lehetővé teszi, hogy a vevő a hűségpontok felhasználásával fizessen egy rendelést. A rendelkezésre álló pontok és lejáró pontok összesítését biztosítja, és lehetővé teszi a vevő számára, hogy kiválassza a beváltani kívánt pontok számát. Ha a vevő nincs bejelentkezve vagy nem tagja a hűségprogramnak, illetve a kosár teljes összege 0 (nulla), akkor a rendszer automatikusan elrejti ezt a modult.
- **Fizetés** – Ez a modul lehetővé teszi a vevők számára, hogy egy hitelkártyával fizessenek egy rendelést. Ha a kosarat hűségpontokkal vagy ajándékutalvánnyal fedezik, vagy a kosár teljes összege 0 (nulla), akkor a rendszer automatikusan elrejti ezt a modult. A hitelkártyás integrációt ehhez a modulhoz a Adyen fizetési összekötő biztosítja. További tájékoztatás az összekötő használatáról: [Dynamics 365 Adyen fizetési összekötő](dev-itpro/adyen-connector.md).
- **Számlázási cím** – Ez a modul lehetővé teszi a vevő számára a számlázási adatok megadását. Ezt az információt az Adyen a hitelkártyaadatokkal együtt dolgozza fel. Ez a modul egy olyan beállítást tartalmaz, amely lehetővé teszi a vevők számára a számlázási cím szállítási címként történő használatát.
- **Kapcsolattartási adatok** – Ez a modul lehetővé teszi a vevő számára, hogy megadja vagy módosítsa a rendeléshez tartozó kapcsolattartási adatokat (e-mail-cím).
- **Szövegblokk** – Ez a modul minden olyan üzenetküldést tartalmaz, amelyet a tartalomkezelő rendszer (CMS) vezérel. Például tartalmazhatja a következő üzenetet: „A rendeléssel kapcsolatos problémák esetén hívja az 1-800-Fabrikam számot”. 

## <a name="commerce-scale-unit-interaction"></a>Commerce Scale Unit-interakció

A legtöbb fizetési információt (például a szállítási címet és a szállítási módot) a kosár tárolja, és a rendelés részeként kerül feldolgozásra. Az egyetlen kivételt a hitelkártyával kapcsolatos adatok jelentik. Ezeket az adatokat a rendszer közvetlenül az Adyen fizetési összekötő használatával dolgozza fel. A kifizetés engedélyezve van, de nem kerül felszámításra.

## <a name="add-a-checkout-module-to-a-new-page-and-set-the-required-properties"></a>Fizetésmodul hozzáadása egy laphoz és a kötelező tulajdonságok beállítása

A fizetésmodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Lépjen a **Töredék \> Új töredék** lehetőségre, és adja meg az új töredéknek a **Fizetési töredék** nevet.
1. Adjon hozzá egy fizetési modult a töredékhez.
1. Adjon hozzá egy fejlécet a fizetési modulhoz.
1. Adja meg a szállítási címet, a szállítási módokat, a fizetési szakasz tárolóját és a kapcsolattartási adatok modult. 
1. A fizetési szakasz tároló moduljában adjon hozzá ajándékutalvány, hűségpontok és fizetési modulokat. Így biztosíthatja, hogy az összes fizetési mód együtt jelenjen meg egy szakaszban.
1. Mentse a töredéket, és tekintse meg az előnézetét. Előfordulhat, hogy egyes modulok nem jelennek meg az előnézetben, mert nem rendelkeznek kosárkontextussal.
1. Fejezze be a töredék szerkesztését, és tegye közzé.
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
