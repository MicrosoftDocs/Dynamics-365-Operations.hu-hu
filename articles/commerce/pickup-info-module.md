---
title: Átvételi információ modul
description: Ez a témakör leírja a felvételi információs modult, és bemutatja, hogyan lehet hozzáadni a pénztároldalakhoz Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 11/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-09021
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: ad877a0c018093fe97f0aa8ac213357c0520a1c9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892597"
---
# <a name="pickup-information-module"></a>Átvételi információ modul

[!include [banner](includes/banner.md)]

Ez a témakör leírja a felvételi információs modult, és bemutatja, hogyan lehet hozzáadni a pénztároldalakhoz Microsoft Dynamics 365 Commerce.

Az átvételi információk modul egy fizetési modulban használható a rendelésfelvételi információk megjelenítéséhez. Az ügyfelek megtekinthetik a rendelkezésre álló felvételi dátumokat és időközöket, majd kiválaszthatják a megfelelő időpontot a rendelés felvételéhez. Például egy vevő választhat, hogy március 21-én 15:00 órakor vesz fel egy rendelést a San Francisco-i üzletből.

A megfelelő üzletek felvételi időközeit a Commerce központjában kell konfigurálni. További információért lásd: [Időközök létrehozása és frissítése a vevői átvételhez](dev-itpro/pickup-timeslots.md).

Ha egy felvételi információs modul jön létre a pénztár oldalon, de nincs időköz meghatározva a csomagfelvételre kiválasztott üzlethez, a modul információkat jelenít meg, de a felhasználó nem tud időközöket kiválasztani. Az időközök nem kötelezőek, és nem kell rendelést leadniuk.

Ha több cikket választ ki több üzletben történő felvételhez, a felvételi információs modul lehetővé teszi a felhasználó számára, hogy minden üzlethez válasszon egy idősávot, feltéve, hogy rendelkezésre állnak időközök.

> [!NOTE]
> Az időközök és a fizetési felvételi információs modul támogatása a Dynamics 365 Commerce 10.0.15-ös és újabb verzióban érhető el.

A következő ábra egy példát mutat be az idősáv kiválasztására a felvételi információs modulon keresztül a pénztár oldalon.

![Példa egy átvételi információk modulra egy fizetési oldalon.](./dev-itpro/media/Curbside_timeslot_eCommerce.PNG)

## <a name="module-properties"></a>Modul tulajdonságai

- **Címsor** – Adja meg a modul címsora.

## <a name="show-time-slot-information-after-an-order-is-placed"></a>Időközadatok megjelenítése a megrendelés után

A megrendelés elküldése után a kiválasztott idősávra vonatkozó információk megtekinthetők a [rendelés-visszaigazolási modulban](order-confirmation-module.md) és a [rendelés részletei modulban](account-management.md#order-details-page). Mindkét modul rendelkezik az **Időközadatok megjelenítése** tulajdonsággal. Mielőtt a rendelési folyamat során megmutathatják a kijelölt időközt, a tulajdonságot **Igaz** értékre kell állítani.

## <a name="add-a-checkout-pickup-information-module-to-a-page"></a>Fizetési átvételi információk modul hozzáadása egy fizetési oldalhoz

Az átvételi információk modulnak a pénztár laphoz való hozzáadásával és a szükséges tulajdonságok beállításával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Fizetési modul](add-checkout-module.md).

A következő ábra egy e-kereskedelmi fizetési oldalt mutat be, amely időközöket tartalmaz a sorelemek átvételéhez.

![Egy e-kereskedelmi fizetési oldal példája, amely időközöket tartalmaz a sorelemek átvételéhez.](./dev-itpro/media/Curbside_timeslot_eCommerce_checkoutsummary.PNG)

## <a name="additional-resources"></a>További erőforrások

[Időközök létrehozása és frissítése a vevői átvételhez](dev-itpro/pickup-timeslots.md)

[Pénztármodul](add-checkout-module.md)

[Rendelésmegerősítési modul](order-confirmation-module.md)

[Rendelési részletek modul](account-management.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]