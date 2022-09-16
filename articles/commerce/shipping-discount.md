---
title: Szállítási engedmény
description: Ez a témakör ismerteti a szállítási engedményekkel használható lehetőségeket Microsoft Dynamics 365 Commerce és az alkalmazásukhoz szükséges beállításokat.
author: ShalabhjainMSFT
ms.date: 08/23/2020
ms.topic: overview
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2019-01-31
ms.openlocfilehash: 74cfe5246ad72cbdedd0ed4e3b3394bf7277919e
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473850"
---
# <a name="shipping-discount"></a>Szállítási engedmény

[!include [banner](includes/banner.md)]

Ez a témakör ismerteti a szállítási engedményekkel használható lehetőségeket Microsoft Dynamics 365 Commerce és az alkalmazásukhoz szükséges beállításokat.

Az ingyenes vagy engedményes szállítás az egyik olyan tényező, amely hatással van a vevők online beszerzési döntésre. Ha tranzakciónként növelniük kell a bevételüket, sok kiskereskedők ingyenes szállítási juttatással motiválják a vevőket a bevásárlókocsi méretének növelésére.

A Commerce rendszer olyan szállítási engedményre képes, amely lehetővé teszi a kiskereskedők számára, hogy meghatározott szállítási módra engedményt állítsanak be a szállítási költségekre, ha a tranzakcióban minősített cikkek teljes értékesítési összege megfelel bizonyos feltételeknek. A szállítási engedményre való képességre példa egy ilyen helyzetre: "Egy vagy több $50 költsen el, hogy egynapos ingyenes szállítást kap."

## <a name="prerequisites"></a>Előfeltételek

A Commerce rendszer speciális [automatikus díjakat biztosít a szállítási engedményre.](/dynamics365/unified-operations/retail/omni-auto-charges) Ahhoz, hogy a szállítási engedmény működjön, **·** **·** **engedélyeznie kell a Speciális automatikus költségek használata konfigurációt a Commerce Headquarters Commerce** paraméterek oldalának Vevői rendelések lapján. A kiskereskedők a speciális automatikus díjak funkcióval különféle költségeket állíthatnak be, például kezelés, telepítés és kivezetés.

A szállítási engedmény csak a szállítási költségekre vonatkozik. Ezért egy kiskereskedőnek meg kell adnia, hogy mely költségek a szállítási költségek. A szállítási költségek a Commerce Headquarters **\>\>** szolgáltatásBan való megadásához kattintson a Csatornabeállítás költségei kódjára, **·** **és** a kívánt költségekhez állítsa a Szállítási költség beállítást Igen gombra.

![Költség megadása szállítási költségként.](./media/Specify_shipping_charge.png)

## <a name="configuration"></a>Konfiguráció

A szállítási engedményre való képesség többszintű, és csak a **Százalékos** engedmény számítástípust támogatja. Szállítási engedmény beállítására a Commerce Headquarters **\> az Árképzés és engedmények – Szállítási küszöbérték engedménye beállításnál indul el**. Ezt követően meghatározhatja, hogy az engedmény melyik szállítási módra vonatkozik, meghatározhat egy vagy több összeghatárt, és beállíthatja az egyes küszöbértékek engedményszázalékát. A kategóriák és termékek listáját is beállíthatja minősített cikkként. Ily módon csak a tranzakcióban ezeknek a cikkeknek az értékesítési összegét számolja le a rendszer, amikor az árkalkprogram kiértékeli, hogy a tranzakció végösszege eléri-e a küszöbértéket.

> [!NOTE]
> A többi engedménytípustól eltérően a szállítási engedmény nem hoz létre engedménysorokat. Ehelyett közvetlenül szerkeszti a szállítási költséget, és a költség leírásában hozzáfűzi az engedmény nevét.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
