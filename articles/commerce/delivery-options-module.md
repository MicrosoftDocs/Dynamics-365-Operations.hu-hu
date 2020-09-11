---
title: Szállítási lehetőségek modul
description: Ez a témakör ismerteti a szállítási lehetőségek modult, és bemutatja, hogyan konfigurálhatjuk őket a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 08/05/2020
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
ms.openlocfilehash: 60449e9492c8e831b4ec6b2896f1ab471ef9d499
ms.sourcegitcommit: ae0843763a8b6b232bb71db326fab28605ac6c53
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2020
ms.locfileid: "3661206"
---
# <a name="delivery-options-module"></a>Szállítási lehetőségek modul

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ez a témakör ismerteti a szállítási lehetőségek modult, és bemutatja, hogyan konfigurálhatjuk őket a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A szállítási lehetőségek modulok lehetővé teszik a vevők számára, hogy kiválaszthassanak egy szállítási módot, mint például a szállítást vagy a felvételt online rendeléseikhez. A szállítási mód megadásához szállítási cím szükséges. Ha a szállítási cím megváltozik, a szállítási lehetőségek újra lekérésre kell kerüljenek. Ha a rendelés csak olyan cikkeket tartalmaz, melyek az üzletben átvehető, ez a modul automatikusan elrejtésre kerül.

A szállítási módok konfigurálásával kapcsolatos tudnivalókért lásd: [Online csatorna-beállítások](channel-setup-online.md) és a [Szállítási módok beállításai](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

Minden szállítási módhoz kapcsolódó költség is tartozhat. Az online áruházakhoz tartozó költségek konfigurálásával kapcsolatos bővebb tájékoztatásért lásd: [Többcsatornás speciális automatikus költségek](omni-auto-charges.md).

A Commerce 10.0.13-es verziójában a szállítási lehetőségek modul frissítése megtörtént, így az támogatja a **Fejlécköltségek  arányosítás nélkül** és a **Sorköltségként történő szállítás** funkciókat. Ha az arányosítás ki van kapcsolva, a várakozás szerint az e-Commerce munkafolyamat nem fogja engedélyezni a vegyes módú szállítást a cikkekre a kosárban (ez azt jelenti, hogy néhány cikk szállításra lesz kiválasztva, néhány pedig felvételre). A **Fejlécköltségek arányosítás nélkül** funkcióhoz szükséges a **Konzisztens szállítási mód kezelésének engedélyezése a csatornában** jelölő be kell legyen kapcsolva a Commerce headquartersben. Ha a jelölő be van kapcsolva, szállítási díjak kapcsolódhatnak mind a fejléc szinten, mind a sor szinten, függően a Commerce headquarters beállításaitól.

A Fabrikam téma támogatja a kevert módú szállítást, ahol egyes cikkek szállításra vannak kiválasztva, a másikak pedig felvételre. Ebben a módban a szállítási költségek arányosításra kerülnek minden cikkre, amelyek a kiszállítás szállítási móddal kerülnek feladásra. A vegyes szállítási mód működéséhez először konfigurálnia kell a **Fejlécköltségek arányosítással** funkciót a Commerce headquartersben. A konfigurációval kapcsolatos további információkét lásd: [Fejlécköltségek arányosítása az egyező értékesítési sorokhoz](pro-rate-charges-matching-lines.md).

Ha egy sortételhez szállítási költségek tartoznak, azok megjelenítésre kerülnek a kosár sorban cikkenként. Ez a funkció megköveteli, hogy a **Szállítási költségek megjelenítése a sortételeken** lehetőség be legyen kapcsolva mind a kosármodulon, mind a fizetési modulon. A további tudnivalókért lásd: [Kosármodul](add-cart-module.md)és [Fizetési modul ](add-checkout-module.md).

A következő ábra bemutat egy példát egy szállítási lehetőségek modulról egy fizetési oldalon.

![Példa egy szállítási lehetőségek modulra egy fizetési oldalon](./media/ecommerce-deliveryoptions.PNG)

## <a name="delivery-options-module-properties"></a>Szállítási lehetőségek modul tulajdonságai

| Tulajdonság | Értékek | Leírás |
|----------|--------|-------------|
| Fejléc | A fejléc szövege és a fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**) | A szállítási lehetőségek modul választható címsora. |
| Egyéni CSS-osztály neve | Szöveg | Egy testreszabott Cascading Style Sheets (CSS) osztály neve, arra használatos, hogy mutassa ezt a modult, ha alkalmazható. |
| Szállítási mód beállítás szűrése | **Szűrés mellőzése** vagy **Nem-szállítási módok** | Egy értéknek, amely meghatározza a szállítási lehetőségek modult, ki kell szűrnie minden nem-szállítási módot. |

## <a name="add-a-delivery-options-module-to-a-checkout-page-and-set-the-required-properties"></a>Adjon hozzá egy szállítási lehetőségek modult a fizetési oldalhoz és állítsa be a kötelező tulajdonságokat

A szállítási lehetőségek modul csak a pénztár modulhoz adható hozzá. A szállítási lehetőségek modul konfigurálásával és a fizetési oldalhoz való hozzáadásával kapcsolatos bővebb információkét lásd: [Fizetési modul](add-checkout-module.md).

## <a name="additional-resources"></a>További erőforrások

[Kosármodul](add-cart-module.md)

[Fizetésmodul](add-checkout-module.md)

[Fizetési modul](payment-module.md)

[Szállítási cím modul](ship-address-module.md)

[Rendelési részletek modul](order-confirmation-module.md)

[Ajándékutalvány modul](add-giftcard.md)

[Online csatorna-beállítások](channel-setup-online.md)

[Többcsatornás speciális automatikus költségek](omni-auto-charges.md)

[Fejlécköltségek arányosítása az egyező értékesítési sorokhoz](pro-rate-charges-matching-lines.md)

[Szállítási módok beállítása](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)
