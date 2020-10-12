---
title: Kosármodul
description: Ez a témakör a kosármodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d9a15f85838849796d6ce4674712636251c75bf3
ms.sourcegitcommit: 97ceb24f191161ca601e0889a539df665834ac3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/16/2020
ms.locfileid: "3818275"
---
# <a name="cart-module"></a>Kosármodul

[!include [banner](includes/banner.md)]

Ez a témakör a kosármodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A kosármodullal megjeleníthetők a kosárba tett cikkek, mielőtt az ügyfél a pénztárra lép. A modul a rendelés összegzését is megjeleníti, és lehetővé teszi, hogy a vevő hozzáadja vagy eltávolítsa a promóciós kódokat.

A kosár modul támogatja a bejelentkezett fizetést és a vendégfizetést. Támogatja a **Vissza a vásárláshoz** hivatkozást. A hivatkozáshoz vezető útvonalat a **Webhely-beállítások \> Bővítmények \> Útvonala** oldalon.

A kosár modul a kosár azonosítója alapján jeleníti meg az adatokat, ami a webhely teljes területén elérhető böngésző cookie. 

A következő kép a Fabrikam webhelyen használt kosároldal egy példáját jeleníti meg.

![Példa egy gyár webhelyén lévő kosármodulra](./media/cart2.PNG)

A következő kép a Fabrikam webhelyen használt kosároldal egy példáját jeleníti meg. Ebben a példában egy sortételre kezelési díjat számolnak fel.

![Példa arra, amikor egy sortételre kezelési díjat számolnak fel](./media/ecommerce-handling-fee.png)

## <a name="cart-module-properties-and-slots"></a>A kosármodul tulajdonságai és helyei

| Tulajdonság | Értékek | Leírás |
|----------------|--------|-------------|
| Fejléc | A fejléc szövege és a fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**) | A kosarának olyan címsor, mint például a "Bevásárlótáska" vagy a "Kosárban található termékek." |
| A nincs készleten állapottal kapcsolatos hibák megjelenítése | **Igaz** vagy **Hamis** | Ha ez a tulajdonság **Igaz** értékre van állítva, a kosár oldal a készlettel kapcsolatos hibákat fog jelezni. Azt ajánljuk Önnek, hogy állítsa ezt a tulajdonságot **igaz**-ra, ha a készlet ellenőrzés engedélyezve van az oldalon. |
| Szállítási költségek megjelenítések sorcikkeknél | **Igaz** vagy **Hamis** | Ha ez a tulajdonság **Igaz** értékre van állítva, akkor a kosár sortételei megmutatják a szállítás költségeit, amennyiben ez az információ elérhető. Ez a funkció nem támogatott a Fabrikam témában, mert a felhasználók a csak szállítást választják a fizetési folyamaton belül. Azonban ez a funkció más munkafolyamatokban is bekapcsolható, ha az alkalmazható az adott munkafolyamatban. |

## <a name="modules-that-can-be-used-in-a-cart-module"></a>A kosármodulban használható modulok

- **Szövegblokk** – Ez a modul a kosár modulban használható egyéni üzenetküldést támogatja. Az üzeneteket a tartalomkezelő rendszer (CMS) vezérli. Bármilyen üzenet megadható, például: „A rendeléssel kapcsolatos problémák esetén hívja az 1-800-Fabrikam számot”.
- **Áruházválasztó** – Ez a modul felsorolja azokat a közeli áruházakat, ahol a cikkek elérhetők és felvehetők. Ez lehetővé teszi a felhasználók számára, hogy a közelben levő üzleteket megtalálják. A modullal kapcsolatos további tudnivalókat lásd: [Üzletkiválasztó modul](store-selector.md).

## <a name="module-properties"></a>Modul tulajdonságai

A kosármodulok következő beállításai konfigurálhatók a **Webhelybeállítások \> Bővítmények** pontban:

- **Maximális mennyiség** – Ez a tulajdonság megadja az egyes cikkek kosárhoz adható maximális számát. Előfordulhat például, hogy egy kiskereskedő úgy dönt, hogy egyetlen tranzakcióban csak 10 terméket lehet értékesíteni.
- **Készlet** – A készletbeállítások alkalmazásával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Készletbeállítások alkalmazása](inventory-settings.md).
- **Vissza a vásárláshoz** – a tulajdonság a **Vissza a vásárláshoz** linkhez megadott útvonal meghatározására szolgál. Az útvonal a webhely szintjén konfigurálható, amely lehetővé teszi, hogy a kiskereskedők visszavigyék a vevőt a kezdőlapra vagy más lapjára.

## <a name="commerce-scale-unit-interaction"></a>Commerce Scale Unit-interakció

A kosármodul a termék adatait a Commerce Scale Unit API-k használatával olvassa be. A böngésző cookie-jából származó kosárazonosító szolgál az összes termékadat beolvasására a Commerce Scale Unitról.

## <a name="add-a-cart-module-to-a-page"></a>Kosármodul felvétele egy oldalra

A kosármodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Lépjen a **Töredékek** pontra, és válassza az **Új** lehetőséget új töredék létrehozásához.
1. Az **Új töredék** párbeszédpanelen válassza ki a **Kosár** modult.
1. A **Töredék neve** pontban adja meg a **Kosár töredék** nevet, ezután válassza az **OK** lehetőséget.
1. Válassza ki **Kosár** helyet.
1. A jobb oldali tulajdonságok ablaktáblán válassza ki a ceruza szimbólumot, adja meg a címsor szövegét a mezőben, majd jelölje be a pipa jelet.
1. A **Kosár** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Áruházválasztó** modult, majd kattintson az **OK** gombra.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a töredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.
1. Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a sablon nevét.
1. A Vázlatablakban válassza ki a **Törzs** helyét, válassza a három pont (**…**) majd válassza a **Töredék hozzáadása** elemet.
1. A **Töredék kiválasztása** párbeszédpanelen válassza ki a **Kosártöredék** nevű töredékét, majd kattintson az **OK** gombra.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.
1. A **Sablon kiválasztása** párbeszédpanelen válassza ki a létrehozott sablont, adjon meg egy oldalnevet, majd kattintson az **OK** gombra.
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.
1. Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

## <a name="additional-resources"></a>További erőforrások

[Kosárikon modul](cart-icon-module.md)

[Fizetésmodul](add-checkout-module.md)

[Fizetési modul](payment-module.md)

[Szállítási cím modul](ship-address-module.md)

[Szállítási lehetőségek modul](delivery-options-module.md)

[Rendelési részletek modul](order-confirmation-module.md)

[Ajándékutalvány modul](add-giftcard.md)

[Kiskereskedelmi csatornák készletelérhetőségének kiszámítása](calculated-inventory-retail-channels.md)
