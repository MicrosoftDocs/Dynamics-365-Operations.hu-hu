---
title: E-kereskedelmi digitális ajándékutalványok
description: Ez a témakör azt mutatja be, hogyan működnek a digitális ajándékutalványok a Microsoft Dynamics 365 Commerce e-kereskedelmi megvalósítása során. Áttekintést nyújt a fontos konfigurációs lépésekről is.
author: anupamar-ms
manager: annbe
ms.date: 12/15/2020
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
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 5a88bef72e13b7b0d948bfd7617cb1dbbcd9ce49
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982666"
---
# <a name="e-commerce-digital-gift-cards"></a>E-kereskedelmi digitális ajándékutalványok

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ez a témakör azt mutatja be, hogyan működnek a digitális ajándékutalványok a Microsoft Dynamics 365 Commerce e-kereskedelmi megvalósítása során. Áttekintést nyújt a fontos konfigurációs lépésekről is.

A Dynamics 365 Commerce rendszerben a digitális ajándékutalványok vásárlása ugyanúgy működik, mint a rendszerben az egyéb termékek vásárlása. Nincs szükség további modulok konfigurálására. Ha a kosárhoz több ajándékutalványt adnak hozzá, a rendszer az ajándékutalvány-cikkeket nem egyetlen értékesítési sorban összesíti. Erre a viselkedésre azért van szükség, mert minden értékesítési sort külön ajándékutalvány-szám alapján számláz a rendszer.

A digitális ajándékutalványok vásárlása a Dynamics 365 Commerce 10.0.16-os és későbbi verzióiban támogatott.

A következő ábra példaként mutatja be egy digitális ajándékutalvány esetében a termék részleteit tartalmazó oldalt (PDP) a Fabrikam e-kereskedelmi webhelyén.

![Példa digitális ajándékutalvány termék részleteit tartalmazó oldalára a Fabrikam e-kereskedelmi webhelyén](./media/GiftcardPDP.PNG)

## <a name="turn-on-the-digital-gift-card-feature-in-commerce-headquarters"></a>A digitális ajándékutalvány funkció bekapcsolása a Commerce központi felületén

Ahhoz, hogy a digitális ajándékutalványok beszerzési folyamata működjön a Dynamics 365 Commerce rendszerben, a Commerce központi felületén be kell kapcsolni az **Ajándékutalvány vásárlása az e-kereskedelem funkción** nevű funkciót. A funkciót a **Funkciókezelés** munkaterületen találja meg a Commerce központi felületén.

![Funkciókezelés munkaterület a Commerce központi felületén](./media/Featureflag.PNG)

## <a name="configure-a-digital-gift-card-in-commerce-headquarters"></a>Digitális ajándékutalvány konfigurálása a Commerce központi felületén

A digitális ajándékutalvány típusú termékeket a Commerce központi felületén kell konfigurálni. A folyamat hasonlít a többi termékhez kapcsolódó folyamathoz. Az alábbi fontos lépések azonban csak a megvásárolható ajándékutalványok konfigurációjára vonatkoznak. A termékek létrehozásával és konfigurálásával kapcsolatos további tudnivalókért lásd: [Új termék létrehozása a Commerce szolgáltatásban](create-new-product-commerce.md).

- Amikor a digitális ajándékutalványokat konfigurál az **Új termék** párbeszédpanelben, állítsa a **Terméktípus** mezőt **Szolgáltatás** beállításra. (A párbeszédpanel megnyitásához nyissa meg a következőt: **Kiskereskedelem és kereskedelem \> Termékek és kategóriák \> Termékek kategória szerint**, és válassza az **Új** lehetőséget.) A **Szolgáltatás** típusú termékek esetében a rendszer nem ellenőrzi az elérhető készletet a rendelés leadása előtt. További információ: [Új termék létrehozása](create-new-product-commerce.md#create-a-new-product).
- A **Commerce paraméterek** oldal **Feladás** lapján az **Ajándékutalvány-termék** mezőt **Digitális ajándékutalvány** értékre kell állítani – ezt az alábbi ábra mutatja. Ha a termék külső ajándékutalvány, a további tudnivalókat lásd a [Támogatás külső ajándékutalványokhoz](./dev-itpro/gift-card.md) oldalon.

    ![Ajándékutalvány-termék mező a Commerce központi felületén](./media/PostGiftcard.png)

- Ha az ajándékutalványnak több előre definiált összeget (például $25, $50, vagy $100) kell támogatnia, akkor az előre megadott összegek beállításához a **Méret** dimenziót kell használni. Minden előre definiált összeg egy variáns lesz. További információ: [Termékdimenziók](https://docs.microsoft.com/dynamics365/supply-chain/pim/product-dimensions?toc=/dynamics365/retail/toc.json).
- Ha az ügyfélnek képesnek kell lennie arra, hogy egyéni összeget adjon meg egy ajándékutalványhoz, először állítson be egy olyan variánst, amely lehetővé teszi az egyéni összeg megadását. Ezután nyissa meg a terméket a **Kiadott termékek ebben a kategóriában** oldalon, majd a **Commerce** gyorslapon állítsa az **Ár beírása billentyűvel** mezőt **Be kell írni az új árat** mezőjére – ezt az alábbi ábra mutatja. Ez a beállítás gondoskodik arról, hogy a vevők megadjanak egy árat, amikor PDP-n böngészik a terméket.

    ![Ár beírása billentyűvel a Commerce központi felületén](./media/KeyInPrice.png)

- A digitális ajándékutalványok szállítási módját **Elektronikus** beállításra kell állítani. A **Szállítási módok** oldalon (**Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Szállítási módok**) a listaablakban válassza ki az **Elektronikus** szállítási mód beállítást, majd adja hozzá a digitális ajándékutalvány-terméket a **Termékek** gyorslap rácsához, amint azt az alábbi ábra mutatja. További információkért lásd: [Szállítási módok beállítása](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

    ![Digitális ajándékutalvány-termékek a Commerce központi felületének Szállítási mód oldalán](./media/ElectronicMode.PNG)

- Győződjön meg arról, hogy létrehozott egy online funkcióprofilt, és az társítva van a Commerce központi felületén lévő online áruházához. A funkcióprofilban állítsa a **Termékek összesítése** lehetőséget **Igen** beállításra. Ez a beállítás gondoskodik arról, hogy az ajándékutalványok kivételével minden cikket összesítsen a rendszer. További tájékoztatás: [Online funkcióprofil létrehozása](online-functionality-profile.md).
- Annak érdekében, hogy az ajándékutalvány kiszámlázása után a vevők e-mailt kapjanak, hozzon létre egy új e-mailes értesítési típust az **E-mailes értesítési profilok** oldalon, és állítsa az **E-mailes értesítés típusa** mezőt **Ajándékutalvány kiállítása** értékre. További információt az [E-mailes értékesítési profil beállítása](email-notification-profiles.md) című témakörben talál.

## <a name="add-product-images-to-the-commerce-site-builder-media-library"></a>Termékképek hozzáadása a Commerce webhelykészítő médiakönyvtárához

A digitális ajándékutalvány-termékek termékképét hozzá kell adni a Commerce webhelykészítő Médiakönyvtárához. Győződjön meg arról, hogy az ajándékutalvány-képfájlok fájlneve a webhely termékképekre vonatkozó elnevezési konvenciót kövesse. További tudnivalókért lásd: [Képek feltöltése](dam-upload-images.md).

## <a name="configure-a-custom-amount-for-a-digital-gift-card-in-commerce-site-builder"></a>Digitális ajándékutalványok egyéni összegének konfigurálása a Commerce webhelykészítőben

Ha egy digitális ajándékutalvány úgy van beállítva, hogy egyéni összeget engedélyezzen, ezt a viselkedést engedélyezni kell a webhely PDP-iben használt [vásárlásmező moduljaiban](add-buy-box.md) is. A vásárlásmező modul lehetővé teszi az egyéni összegek konfigurálását. Meghatározhatja az egyéni összegekre engedélyezett minimális és maximális összegeket is.

A Commerce webhelykészítőben a digitális ajándékutalványok egyéni összegét a következő lépésekkel konfigurálhatja.

1. Lépjena webhely PDP-in használt vásárlásmező modulra. Ez a vásárlásmező modul töredékként, sablonként vagy egy oldalon is megvalósítható.
1. Válassza ki a **Szerkesztés** opciót.
1. A jobb oldali tulajdonságok panelen jelölje be az **Egyéni ár engedélyezése** jelölőnégyzetet.
1. Opcionális: Az egyéni összegek minimális és maximális összegének meghatározásához írja be a **Minimális ár** és a **Maximális ár** alatti összegeket.
1. Válassza a **Szerkesztés befejezése** parancsot, majd válassza a **Közzététel** elemet.

## <a name="additional-resources"></a>További erőforrások

[Vásárlásmező-modul](add-buy-box.md)

[Pénztármodul](add-checkout-module.md)

[Kosármodul](add-cart-module.md)

[Új termék létrehozása a Commerce szolgáltatásban](create-new-product-commerce.md)

[Szállítási módok beállítása](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[Termékdimenziók](https://docs.microsoft.com/dynamics365/supply-chain/pim/product-dimensions?toc=/dynamics365/retail/toc.json)

[E-mail-értesítési profil beállítása](email-notification-profiles.md)

[Online funkcióprofil létrehozása](online-functionality-profile.md)

[Támogatás külső ajándékutalványokhoz](./dev-itpro/gift-card.md)
