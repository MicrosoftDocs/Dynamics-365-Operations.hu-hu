---
title: Adózásrészletezési információk elrejtése a rendelésösszesítésekben
description: Ez a témakör azt ismerteti, hogyan lehet elrejteni az adó-lebontást a bevásárlókocsi, a pénztár, a rendelés-visszaigazolás és a rendelés részleteit tartalmazó lapok sorrendjének összegzésében Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 05/17/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-03-28
ms.openlocfilehash: fe1f6c5875444f4f91ee1dfb01b3fdaa527c52e5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8881790"
---
# <a name="hide-tax-breakup-information-in-order-summaries"></a>Adózásrészletezési információk elrejtése a rendelésösszesítésekben

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ez a témakör azt ismerteti, hogyan lehet elrejteni az adó-lebontást a bevásárlókocsi, a pénztár, a rendelés-visszaigazolás és a rendelés részleteit tartalmazó lapok sorrendjének összegzésében Microsoft Dynamics 365 Commerce.

Alapértelmezés szerint az Dynamics 365 Commerce adó-lebontást a bevásárlókocsi, a pénztár, a rendelés-visszaigazolás és a rendelés részleteit tartalmazó lapok rendelési összegzésében jeleníti meg. A Commerce rendszer 10.0.27-es verziójának kiadásában a Commerce Webhelyszerkesztő egy olyan beállítást is tartalmaz, amellyel elrejtheti az adó-lebontást a rendelés összegzésében.

A következő ábra két rendelési összegzés példáját mutatja be. Az első az adó-lebontást mutatja, a második elrejti.

![Példák olyan bevásárlókocsikra, amelyekben az adóra vonatkozó információk megjelennek és rejtve vannak.](media/prices-include-sales-tax-e-Commerce.png)

> [!NOTE]
> - **A** rendelési összegzésekben az adó-lebontást el lehet rejteni, csak akkor érhető el, ha az e-commerce **csatorna** Árak tartalmazzák az áfa beállítását a Commerce Headquarters Igen beállításánál a **Retail és Commerce \> Channels \> Minden \>** üzletben. 
> - Alapértelmezés szerint a Helyszerkesztőben **engedélyezve van az Adók lebontva** megjelenítése a rendelésösszegzésben beállítás.

## <a name="hide-tax-breakup-information-in-order-summaries"></a>Adózásrészletezési információk elrejtése a rendelésösszesítésekben

A következő lépések szerint rejtheti el az adó-lebontó adatokat a rendelés összegzésében.

1. A Commerce webhelyszerkesztőben menjen a frissíteni kívánt webhelyre.
1. Ugrás a **Webhelybeállítások \> Bővítmények** pontra.
1. Törölje a jelölést **az Adók lebontva megjelenítése jelölőnégyzetből a rendelés összegző** jelölőnégyzetében.

A rendelésösszegzések adó-lebontó információinak a megjelenítése érdekében jelölje be **az Adók felszaördítésének megjelenítése jelölőnégyzetet**.  

A következő ábra az adók **lebontva megjelenítése a webhelyszerkesztőben kijelölt** és be kijelölt rendelésösszegzési jelölőnégyzetben látható.

![Adó-lebontás megjelenítése a helyszerkesztő rendelésösszegzési beállításában.](media/prices-include-sales-tax-e-Commerce-site-settings.png)

> [!NOTE]
> Ha testreszabott rendelés-összegző modulokat használ, és nem szeretné örökölni a Commerce rendszer 10.0.27-es vagy újabb verziójának "Az adó-lebontás információinak elrejtése a rendelésösszegzések" funkciót, [akkor az egyedi rendelésösszegző modulok használata esetén a rendelésösszegzés részösszegzése](troubleshoot/summary-taxes-custom-modules-10.0.27.md#resolution) nem tartalmazza a költségek adóit.

## <a name="additional-resources"></a>További erőforrások

[Áfa áttekintése](/finance/general-ledger/indirect-taxes-overview)

[Az online rendelések áfájának konfigurálása](sales-tax-config.md)

[Hibakeresés: Az online rendelések adójának számítása hibás.](troubleshoot/tax-miscalculated-online-order.md)
