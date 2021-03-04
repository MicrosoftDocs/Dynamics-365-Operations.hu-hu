---
title: Kosárikon modul
description: Ez a témakör a kosárikon modullal foglalkozik, és bemutatja, hogy hogyan lehet azt hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ebc5cfa490a4c8538fd081aced0844ed01d63a26
ms.sourcegitcommit: 12d271bb26c7490e7525d9b4bbf125cdc39fef43
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/07/2020
ms.locfileid: "4413021"
---
# <a name="cart-icon-module"></a>Kosárikon modul

[!include [banner](includes/banner.md)]

Ez a témakör a kosárikon modullal foglalkozik, és bemutatja, hogy hogyan lehet azt hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A kosárikon-modul a lap fejlécében a kosárat jelenti, és a kosárban található cikkek számát jeleníti meg. A kosárikon modul a kosár összegzését (más néven minikosár) is megjelenít ,ha fölé viszik az egérmutatót. A minikosár anélkül jeleníti meg a kosárban található cikkek összegzését a felhasználó számára, hogy a meg kellene nyitnia a kosár lapját. Ezenkívül azt is lehetővé teszi a felhasználó számára, hogy közvetlenül a pénztár lapjára ugorjon, ha elégedett az összesítéssel. Ez csökkenti az oldalnavigációk számát és gyorsabban teszi a fizetést. 

> [!NOTE]
> A kosárikon modul támogatása a Dynamics 365 Commerce 10.0.11-es kiadásában érhető el.

A következő képen egy példa látható a kosárikon modulra, amely egy minikosarat jelenít meg a Fabrikam címsorban.

![Példa egy kosárikon modulra](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a>Modul tulajdonságai

- **Mini-kosár megjelenítése** – Ha ennek értéke igaz, ez a tulajdonság lehetővé teszi a kosár összesítésének (mini kosár) megjelenítését, ha a kosár ikonja fölé viszik az egérmutatót. Ez a funkció csak az asztali nézet portjain használható.

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