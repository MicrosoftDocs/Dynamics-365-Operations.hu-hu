---
title: Adó-lebontó adatok elrejtése a rendelés összegzésében
description: Ez a témakör azt írja le, hogyan lehet elrejteni az adó-lebontást a bevásárlókocsi, a pénztár, a rendelés-visszaigazolás és a rendelés részletező oldalait tartalmazó rendelési összefoglalókban Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 04/21/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-03-28
ms.openlocfilehash: 9890b5cd92f8c07e6feabb26f4fdd076cb7a02bc
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/27/2022
ms.locfileid: "8648133"
---
# <a name="hide-tax-breakup-information-in-order-summaries"></a>Adó-lebontó adatok elrejtése a rendelés összegzésében

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ez a témakör azt írja le, hogyan lehet elrejteni az adó-lebontást a bevásárlókocsi, a pénztár, a rendelés-visszaigazolás és a rendelés részletező oldalait tartalmazó rendelési összefoglalókban Microsoft Dynamics 365 Commerce.

Alapértelmezés szerint az Dynamics 365 Commerce adó-lebontást a bevásárlókocsi, a pénztár, a rendelés-visszaigazolás és a rendelés részleteit tartalmazó lapok rendelési összegzésében jeleníti meg. A Commerce rendszer 10.0.27-es verziójának kiadásában a Commerce Webhelyszerkesztő egy olyan beállítást is tartalmaz, amellyel elrejtheti az adó-lebontást a rendelés összegzésében.

A következő ábra két rendelési összegzés példáját mutatja be. Az első az adó-lebontást mutatja, a második elrejti.

![Példák olyan bevásárlókocsikra, amelyekben az adóra vonatkozó információk megjelennek és rejtve vannak.](media/prices-include-sales-tax-e-Commerce.png)

> [!NOTE]
> - **A** rendelési összegzésekben az adó-lebontást el lehet rejteni, csak akkor érhető el, ha az e-commerce **csatorna** Árak tartalmazzák az áfa beállítását a Commerce Headquarters Igen beállításánál a **Retail és Commerce \> Channels \> Minden \>** üzletben. 
> - Alapértelmezés szerint a Helyszerkesztőben **engedélyezve van az Adók lebontva** megjelenítése a rendelésösszegzésben beállítás.

## <a name="hide-tax-breakup-information-in-order-summaries"></a>Adó-lebontó adatok elrejtése a rendelés összegzésében

A következő lépések szerint rejtheti el az adó-lebontó adatokat a rendelés összegzésében.

1. A Commerce webhelyszerkesztőben menjen a frissíteni kívánt webhelyre.
1. Ugrás a **Webhelybeállítások \> Bővítmények** pontra.
1. Törölje a jelölést **az Adók lebontva megjelenítése jelölőnégyzetből a rendelés összegző** jelölőnégyzetében.

A rendelésösszegzések adó-lebontó információinak a megjelenítése érdekében jelölje be **az Adók felszaördítésének megjelenítése jelölőnégyzetet**.  

A következő ábra az adók **lebontva megjelenítése a webhelyszerkesztőben kijelölt** és be kijelölt rendelésösszegzési jelölőnégyzetben látható.

![Adó-lebontás megjelenítése a helyszerkesztő rendelésösszegzési beállításában.](media/prices-include-sales-tax-e-Commerce-site-settings.png)

## <a name="additional-resources"></a>További erőforrások

[Áfa áttekintése](/finance/general-ledger/indirect-taxes-overview)

[Az online rendelések áfájának konfigurálása](sales-tax-config.md)

[Hibakeresés: Az online rendelések adójának számítása hibás.](troubleshoot/tax-miscalculated-online-order.md)
