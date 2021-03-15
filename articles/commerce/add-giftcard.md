---
title: Ajándékutalvány-modul
description: Ez a témakör az ajándékutalvány-modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.openlocfilehash: d9626f33ced0433bc96ed58429e95d4f75af6508
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980382"
---
# <a name="gift-card-module"></a>Ajándékutalvány-modul

[!include [banner](includes/banner.md)]

Ez a témakör az ajándékutalvány-modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

Az ajándékutalvány egy gyakori fizetési mód, és az ajándékutalvány modulok használható az e-kereskedelmi tranzakciókban az ajándékutalványok elfogadására. Az ajándékutalvány modul támogatja a Dynamics 365, SVS és a Givex ajándékutalványokat. A SVS és a Givex ajándékutalványok a Adyen fizetési szolgáltatón keresztül válthatók be. A külső ajándékutalványok (például SVS és Givex) támogatásával kapcsolatos további tudnivalókat lásd: [Támogatás a külső ajándékutalványokhoz](./dev-itpro/gift-card.md).

> [!NOTE]
> A pénztári folyamat során történő SVS- és Givex-ajándékutalvány beváltásához nyújtott támogatás a Dynamics 365 Commerce 10.0.11-es kiadásban érhető el. 

Két ajándékutalvány-modul érhető el:

- **Ajándékutalvány** – Ez a modul a pénztár oldalon használható egy ajándékutalvány fizetőeszközként történő beváltására. 
- **Ajándékutalvány egyenlegének ellenőrzése** – Ez a modul bármilyen oldalon használható az ajándékutalvány egyenlegének ellenőrzésére. Ez a modul elérhető a Commerce alkalmazás 10.0.14 vagy újabb verziójában.

> [!NOTE]
> Az ajándékutalvány-egyenleget ellenőrző modul támogatása a Dynamics 365 Commerce 10.0.14-es kiadásában érhető el.

A következő kép egy Pénztár oldalon használt ajándékutalvány modul egy példáját jeleníti meg.

![Példa egy ajándékutalvány modulra](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a>Modul tulajdonságai

- **További mezők megjelenítése** – Ez a tulajdonság határozza meg, hogy milyen mezőket kell megjeleníteni az ajándékutalványokhozaz ajándékutalvány számán túl, amely alapértelmezés szerint mindig látható. Például egyes ajándékutalványok támogatják a személyes azonosítószám (PIN-kód) megjelenítését, mások a PIN-kód és a lejárati dátum megjelenítését. Másik lehetőségként a tulajdonság értéke „Nincs” lehet, amely csak az ajándékutalvány számát jeleníti meg, és további mezőket nem.

Támogatott értékek:
-   PIN-kód
-   Lejárat dátuma
-   PIN és lejárati dátum 
-   None

## <a name="site-settings-for-gift-card-modules"></a>Ajándékutalvány-modulok webhely-beállításai

A Commerce webhelykészítő **Webhelybeállítások \> Bővítmények** területén van egy ajándékutalvány-modul, amelynek neve **Támogatott ajándékutalvány-típus**. Ez a beállítás három értéket támogat:
- **Dynamics 365 ajándékutalvány** – Ha ezt a beállítást alkalmazza, akkor az ajándékutalvány modul csak a Dynamics 365 utalványok beváltását teszi lehetővé. Ez a beállítás csak az e-Commerce webhely bejelentkezett felhasználóinak esetében támogatott.
- **SVS és Givex ajándékutalványok** – Ha ezt a beállítást alkalmazza, akkor az ajándékutalvány modul csak a Givex és SVS utalványok beváltását teszi lehetővé. Ez a beállítás az e-Commerce webhely bejelentkezett és névtelen felhasználói esetében támogatott.
- **Dynamics 365, SVS és Givex ajándékutalványok** – Ha ezt a beállítást alkalmazza, akkor az ajándékutalvány modul a Dynamics 365, Givex és SVS utalványok beváltását teszi lehetővé. Ez a beállítás csak az e-Commerce webhely bejelentkezett felhasználóinak esetében támogatott.

> [!IMPORTANT]
> Ezek a beállítások a Dynamics 365 Commerce 10.0.11-es verziójában érhetők el, és csak akkor szükségesek, ha támogatásra van szüksége az SVS- vagy Givex-ajándékutalványok használatakor. Ha a Dynamics 365 Commerce egy korábbi verziójáról frissít, akkor manuálisan kell frissítenie az appsettings.json fájlt. Az appsettings.json fájlok frissítésével kapcsolatos tudnivalókat lásd az [SDK- és modulkönyvtár-frissítések](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file) témakörben. 

## <a name="add-a-gift-card-module-to-a-page"></a>Ajándékutalvány-modul felvétele egy oldalra

Az ajándékutalvány-modulnak a pénztár lapra történő hozzáadásával és a szükséges tulajdonságok beállításával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Fizetésmodul](add-checkout-module.md).

## <a name="additional-resources"></a>További erőforrások

[Kosármodul](add-cart-module.md)

[Kosárikon modul](cart-icon-module.md)

[Fizetésmodul](add-checkout-module.md)

[Fizetési modul](payment-module.md)

[Szállítási cím modul](ship-address-module.md)

[Szállítási lehetőségek modul](delivery-options-module.md)

[Átvételi információk modul](pickup-info-module.md)

[Rendelési részletek modul](order-confirmation-module.md)

[Támogatás külső ajándékutalványokhoz](./dev-itpro/gift-card.md)

[SDK- és modulkönyvtár-frissítések](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]