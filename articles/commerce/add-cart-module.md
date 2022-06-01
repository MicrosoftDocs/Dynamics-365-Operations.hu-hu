---
title: Kosármodul
description: Ez a témakör ismerteti a kosármodulok működését és bemutatja, hogyan tudjuk hozzáadni azokat az egyes webhelyekhez a Microsoft Dynamics 365 Commerce segítségével.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 962710f7b65c8d26b301b5034a89fc25476b6e0f
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780539"
---
# <a name="cart-module"></a>Kosármodul

[!include [banner](includes/banner.md)]

Ez a témakör ismerteti a kosármodulok működését és bemutatja, hogyan tudjuk hozzáadni azokat az egyes webhelyekhez a Microsoft Dynamics 365 Commerce segítségével.

A kosármodullal megjeleníthetők a kosárba tett cikkek, mielőtt az ügyfél a pénztárra lép. A modul a rendelés összegzését is megjeleníti, és lehetővé teszi, hogy a vevő hozzáadja vagy eltávolítsa a promóciós kódokat.

A kosár modul támogatja a bejelentkezett fizetést és a vendégfizetést. Támogatja a **Vissza a vásárláshoz** hivatkozást. A hivatkozáshoz vezető útvonalat a **Webhely-beállítások \> Bővítmények \> Útvonala** oldalon.

A kosár modul a kosár azonosítója alapján jeleníti meg az adatokat, ami a webhely teljes területén elérhető böngésző cookie. 

A következő kép a Fabrikam webhelyen használt kosároldal egy példáját jeleníti meg.

![Példa a Fabrikam webhelyén lévő kosármodulra.](./media/cart2.PNG)

A következő kép a Fabrikam webhelyen használt kosároldal egy példáját jeleníti meg. Ebben a példában egy sortételre kezelési díjat számolnak fel.

![Példa arra, amikor egy sortételre kezelési díjat számolnak fel.](./media/ecommerce-handling-fee.png)

## <a name="cart-module-properties-and-slots"></a>A kosármodul tulajdonságai és helyei

| Tulajdonság | Értékek | Leírás |
|----------------|--------|-------------|
| Fejléc | A fejléc szövege és a fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**) | A kosarának olyan címsor, mint például a "Bevásárlótáska" vagy a "Kosárban található termékek." |
| A nincs készleten állapottal kapcsolatos hibák megjelenítése | **Igaz** vagy **Hamis** | Ha ez a tulajdonság **Igaz** értékre van állítva, a kosár oldal a készlettel kapcsolatos hibákat fog jelezni. Azt ajánljuk Önnek, hogy állítsa ezt a tulajdonságot **igaz**-ra, ha a készlet ellenőrzés engedélyezve van az oldalon. |
| Szállítási költségek megjelenítések sorcikkeknél | **Igaz** vagy **Hamis** | Ha ez a tulajdonság **Igaz** értékre van állítva, akkor a kosár sortételei megmutatják a szállítás költségeit, amennyiben ez az információ elérhető. Ez a funkció nem támogatott a Fabrikam témában, mert a felhasználók a csak szállítást választják a fizetési folyamaton belül. Azonban ez a funkció más munkafolyamatokban is bekapcsolható, ha az alkalmazható az adott munkafolyamatban. |
| Elérhető promóciók megjelenítése| **Igaz** vagy **Hamis** | Ha ez a tulajdonság **Igaz**, a kosár a kosárban található cikkek alapján megjeleníti a rendelkezésre álló promóciókat. Ez a képesség a Dynamics 365 Commerce 10.0.16 kiadásban érhető el. |

## <a name="modules-that-can-be-used-in-a-cart-module"></a>A kosármodulban használható modulok

- **Szövegblokk** – Ez a modul a kosár modulban használható egyéni üzenetküldést támogatja. Az üzeneteket a tartalomkezelő rendszer (CMS) vezérli. Bármilyen üzenet megadható, például: „A rendeléssel kapcsolatos problémák esetén hívja az 1-800-Fabrikam számot”.
- **Áruházválasztó** – Ez a modul felsorolja azokat a közeli áruházakat, ahol a cikkek elérhetők és felvehetők. Ez lehetővé teszi a felhasználók számára, hogy a közelben levő üzleteket megtalálják. A modullal kapcsolatos további tudnivalókat lásd: [Üzletkiválasztó modul](store-selector.md).

## <a name="module-properties"></a>Modul tulajdonságai

A kosármodulok következő beállításai konfigurálhatók a **Webhelybeállítások \> Bővítmények** pontban:

- **Maximális mennyiség** – Ez a tulajdonság megadja az egyes cikkek kosárhoz adható maximális számát. Előfordulhat például, hogy egy kiskereskedő úgy dönt, hogy egyetlen tranzakcióban csak 10 terméket lehet értékesíteni.
- **Készlet** – A készletbeállítások alkalmazásával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Készletbeállítások alkalmazása](inventory-settings.md).
- **Vissza a vásárláshoz** – a tulajdonság a **Vissza a vásárláshoz** linkhez megadott útvonal meghatározására szolgál. Az útvonal a webhely szintjén konfigurálható, amely lehetővé teszi, hogy a kiskereskedők visszavigyék a vevőt a kezdőlapra vagy más lapjára.

> [!IMPORTANT]
> A Dynamics 365 Commerce 10.0.14-verzióban és a későbbiekben a kosárban szereplő cikkek a Commerce központ online áruházának online funkcionális profiljában megadott beállítások alapján kerülnek összesítésre. Ha további tájékoztatást szeretne arról, hogyan lehet létrehozni egy online funkcionális profilt, és be kell állítania az összesítéshez szükséges tulajdonságokat, akkor lásd: [online működési profil létrehozása](online-functionality-profile.md).

## <a name="commerce-scale-unit-interaction"></a>Commerce Scale Unit-interakció

A kosármodul a termék adatait a Commerce Scale Unit API-k használatával olvassa be. A böngésző cookie-jából származó kosárazonosító szolgál az összes termékadat beolvasására a Commerce Scale Unitról.

## <a name="add-a-cart-module-to-a-page"></a>Kosármodul felvétele egy oldalra

A kosármodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Lépjen a **Töredékek** pontra, és válassza az **Új** lehetőséget új töredék létrehozásához.
1. A Részlet **kiválasztása párbeszédpanelen** válassza ki a Bevásárlókocsi **modult**.
1. A **Töredék neve** pontban adja meg a **Kosár töredék** nevet, ezután válassza az **OK** lehetőséget.
1. Válassza ki **Kosár** helyet.
1. A jobb oldali tulajdonságok ablaktáblán válassza ki a ceruza szimbólumot, adja meg a címsor szövegét a mezőben, majd jelölje be a pipa jelet.
1. A Bevásárlókocsiban **válassza** ki a három pontból (**...**), majd válassza a Modul **hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **az** Üzletválasztó modult, majd kattintson az **OK gombra**.
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

[Átvételi információk modul](pickup-info-module.md)

[Rendelési részletek modul](order-confirmation-module.md)

[Ajándékutalvány modul](add-giftcard.md)

[Kiskereskedelmi csatornák készletelérhetőségének kiszámítása](calculated-inventory-retail-channels.md)

[Online funkcióprofil létrehozása](online-functionality-profile.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
