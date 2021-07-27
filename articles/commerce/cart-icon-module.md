---
title: Kosárikon modul
description: Ez a témakör a kosárikon modullal foglalkozik, és bemutatja, hogy hogyan lehet azt hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
ms.date: 07/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e0238e9d464fc1d44cbc5091638ac7270d5b6ae3
ms.sourcegitcommit: 7e976059118938b0089e40bef948029a8c088b38
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/09/2021
ms.locfileid: "6479304"
---
# <a name="cart-icon-module"></a>Kosárikon modul

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ez a témakör a kosárikon modullal foglalkozik, és bemutatja, hogy hogyan lehet azt hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

A kosárikon-modul a lap fejlécében a kosárat jelenti, és a kosárban található cikkek számát jeleníti meg. A kosárikon modul a kosár összegzését (más néven minikosár) is megjelenít ,ha fölé viszik az egérmutatót. A minikosár anélkül jeleníti meg a kosárban található cikkek összegzését a felhasználó számára, hogy a meg kellene nyitnia a kosár lapját. Ezenkívül azt is lehetővé teszi a felhasználó számára, hogy közvetlenül a pénztár lapjára ugorjon, ha elégedett az összesítéssel. Ez csökkenti az oldalnavigációk számát és gyorsabban teszi a fizetést. 

A következő képen egy példa látható a kosárikon modulra, amely egy minikosarat jelenít meg a Fabrikam címsorban.

![Példa egy kosárikon modulra.](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a>Modul tulajdonságai

- **Mini-kosár megjelenítése** – Ha ennek értéke igaz, ez a tulajdonság lehetővé teszi a kosár összesítésének (mini kosár) megjelenítését, ha a kosár ikonja fölé viszik az egérmutatót. Ez a funkció csak az asztali nézet portjain használható.

## <a name="module-properties-in-the-adventure-works-theme"></a>Modultulajdonságok a Adventure Works témában

Az Adventure Works témában a kosárikon modulja két további helyet tartalmaz a minikosár számára. Ezek a helyek moduldefiníciós bővítményként vannak belefoglalva.

- **Promóciók az üres bevásárlókocsiban** – Ez a hely szövegterület-modult fogad. Ha üres a kosár, megjelenik a megadott szövegterület-modul. A szövegterület-modul promóciókhoz, marketingtartalmakhoz és kategóriaoldalakra mutató hivatkozásokhoz használható, hogy segítsen a vevőknek folytatni a vásárlást.
- **Promóciós tartalom** – Ez a hely promóciók – például „100 dollár feletti rendelés esetén ingyenes a szállítás” – megjelenítéséhez használható. A promóciós tartalomhelyen szövegterület- és képlistamodulok használhatók.

A következő képen egy olyan kosárikonmodul látható az Adventure Works témában, amely promóciós tartalmat jelenít meg a minikosárban.

![Példa egy kosárikonmodulra az Adventure Works témában](./media/AW_minicart.PNG)

> [!IMPORTANT]
> Az Adventure Works témahelyei a Dynamics 365 Commerce 10.0.20-as kiadásában érhetők el.

## <a name="add-a-cart-icon-module-to-a-page"></a>Kosárikon modul felvétele egy oldalra

Egy kosárikon modul hozzáadásához lásd: [Fejléc modul](author-header-module.md).

## <a name="additional-resources"></a>További erőforrások

[Kosármodul](add-cart-module.md)

[Fizetésmodul](add-checkout-module.md)

[Fizetési modul](payment-module.md)

[Szállítási cím modul](ship-address-module.md)

[Szállítási lehetőségek modul](delivery-options-module.md)

[Átvételi információk modul](pickup-info-module.md)

[Rendelési részletek modul](order-confirmation-module.md)

[Ajándékutalvány modul](add-giftcard.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
