---
title: Fizetési modul
description: Ez a témakör ismerteti a fizetési modult, és bemutatja, hogyan konfigurálhatjuk őket a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
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
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 894ac35973927c193d6e9c54e326daefb8a3f4a5
ms.sourcegitcommit: 765056b5dc1d0a8c27e56ff2cbd310ad3349ff09
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/20/2020
ms.locfileid: "4055381"
---
# <a name="payment-module"></a>Fizetési modul

[!include [banner](includes/banner.md)]

Ez a témakör ismerteti a fizetési modult, és bemutatja, hogyan konfigurálhatjuk őket a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A fizetési modul lehetővé teszi a vásárlóknak a rendelések fizetését hitelkártyával vagy bankkártyával. A fizetés integrációját ehhez a modulhoz a Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz alkalmazás biztosítja. A fizetési összekötő telepítésével és konfigurálásával kapcsolatos további információkért lásd: [Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz](dev-itpro/adyen-connector.md).

A fizetési modul fizetési információt szolgáltat, amit az Adyen a HTML szövegközi keret (iframe) által biztosít. A fizetési modul kölcsönhatásba lép a Commerce Scale Unit egységgel, hogy kinyerje az Adyen szolgáltatásból az információkat. A Commerce Scale Unit egységgel való interakció részeként a fizetési modul engedélyezi a számlázási címének információit, mind az iframe-en keresztül szolgáltatva, mind egy külön modulon keresztül. A Fabrikam témában a számlázási cím külön modulban jelenik meg. Ez a mód több formázási rugalmasságot engedélyez, mert a cím sorok megadhatók, így azok a szállítási cím soraihoz hasonlóan jelennek meg.

A fizetési modul lehetővé teszi a bejelentkezett vásárlóknak menteni a fizetési információikat. A fizetési információk és számlázási címek mentésre és kezelésre kerülnek az Adyen fizetési összekötőn keresztül.

A fizetési modul fedez minden egyes rendelési változtatást, melyek nem kerülnek fedezésre hűségpontok által vagy ajándékutalványokkal. Ha a rendelés összegét teljes mértékben fedezik a hűségpontok és/vagy ajándékutalványok, a fizetési modul elrejtésre kerül, és a vásárló enélkül is leadhatja rendelését.

Az Adyen fizetési összekötő támogatja az erős vevőhitelesítést (SCA) is. Az Európai Unió (EU) Pénzforgalmi szolgáltatási irányelvek 2.0 (PSD2.0) megköveteli, hogy az online vásárlók hitelesítve legyenek az online vásárlási tapasztalataikon kívül is, amikor egy elektronikus fizetési módot használnak. A fizetési folyamat során a vásárlók átirányításra kerülnek a saját bankolási oldalukra. Ezután, a hitelesítés után a program visszairányítja őket a Commerce fizetési folyamathoz. Ezalatt az átirányítás alatt az információ, amit egy vásárló megadott a fizetési folyamatban (például szállítási cím, szállítási lehetőségek, ajándékutalvány információ, hűségadatok) láthatók maradnak. Mielőtt bekapcsolhatná ezt a funkciót, a fizetési összekötő konfigurálva kell legyen az SCA-hoz a Commerce headquartersben. További tudnivalókért lásd: [Erős vevőhitelesítés az Adyen használatával](adyen_redirect.md).

> [!NOTE]
> Az Adyen payment összekötő esetében a kifizetési modul iframe modulja csak akkor jeleníthető meg, ha hozzáadja az Adyen URL-címet a webhely engedélyezési listájához. A lépés végrehajtásához adja hozzá az **\*.adyen.com** címet az oldala tartalmi biztonsági házirendjének **child-src** , **connect-src** , **img-src** , **script-src** és **style-src** direktíváihoz. További információ: [Tartalomra vonatkozó biztonsági irányelv kezelése](manage-csp.md). 

A következő ábrán egy példa látható az ajándékutalvány-, a hűség- és a fizetési modulokra a fizetési oldalon.

![Példa az ajándékutalvány, a hűség- és a fizetési modulokra a fizetési oldalon](./media/ecommerce-payments.PNG)

## <a name="payment-module-properties"></a>Fizetési modul tulajdonságai

| Tulajdonság neve | Értékek | Leírás |
|---------------|--------|-------------|
| Fejléc | A címsor szövege | Egy választható címsor a fizetési modulhoz. |
| Az iframe magassága | Képpontok | Az iframe magassága képpontokban. A magasság növelhető, ha szükséges. |
| Számlázási cím megjelenítése | **Igaz** vagy **Hamis** | Ha ez a tulajdonság **Igaz** értékre van állítva, akkor a számlázási cím az Adyen által lesz szolgáltatva, a fizetési modul iframe-jében. Ha ez **Hamis** értékre van állítva, akkor a számlázási cím nem az Adyen által lesz szolgáltatva, és a Commerce-felhasználónak konfigurálnia kell egy modult, hogy az mutassa a számlázási címét a fizetési oldalon. |
| Fizetés stílus felülbírálása | Stíluslapok (CSS) kód | Mivel a fizetési modul az iframe-en keresztül van szolgáltatva, véges számú formázási képesség áll rendelkezésre. Elérhet néhány formázási lehetőséget ennek a tulajdonságnak a használatával. A webhelystílusok felülírásához be kell illesztenie a CSS-kódot a tulajdonság értékeként. A webhely CSS -építő felülbírálásai és a stílusok nem vonatkoznak erre a modulra. |

## <a name="billing-address"></a>Számlázási cím

A fizetési modul lehetővé teszi a vevőknek, hogy egy számlázási címet biztosítsanak a fizetési információikhoz. Ez azt is lehetővé teszi számukra, hogy szállítási címüket számlázási címként használhassák, hogy ezzel is könnyebbé és gyorsabbá tegyék a fizetési folyamatot. Ha a **Számlázási cím megjelenítése** tulajdonság **Hamis** értékre van állítva, akkor fizetési modult be kell állítani a fizetési oldalon.

## <a name="add-a-payment-module-to-a-checkout-page-and-set-the-required-properties"></a>Adjon meg egy fizetési modult a kifizetési oldalhoz, és állítsa be a kötelező tulajdonságokat

A fizetésimodul csak a kifizetési modulhoz adható hozzá. A fizetési modul konfigurálásával és a kifizetési oldalhoz való hozzáadásával kapcsolatos további tudnivalókért lásd: [Fizetési modul](add-checkout-module.md).

## <a name="additional-resources"></a>További erőforrások

[Kosármodul](add-cart-module.md)

[Kosárikon modul](cart-icon-module.md)

[Fizetésmodul](add-checkout-module.md)

[Szállítási cím modul](ship-address-module.md)

[Szállítási lehetőségek modul](delivery-options-module.md)

[Rendelési részletek modul](order-confirmation-module.md)

[Ajándékutalvány modul](add-giftcard.md)

[Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz](dev-itpro/adyen-connector.md)

[Erős vevőhitelesítés (SCA) az Adyen segítségével](adyen_redirect.md)
