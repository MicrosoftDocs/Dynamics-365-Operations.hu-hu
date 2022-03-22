---
title: Az adóelőlegelemek kifizetési időszakainak beállítása TDS adótípushoz
description: Ez a témakör elmagyarázza, hogyan lehet beállítani az elszámolási időszakokat a forrásnál levont adó (TDS) elszámolási időszakaihoz.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 92c7c8f0df3e6acde7cd9b1299f799ace35ca6a86c801a0a333321c56d8502eb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6778140"
---
# <a name="set-up-withholding-tax-settlement-periods-for-the-tds-tax-type"></a>Az adóelőlegelemek kifizetési időszakainak beállítása TDS adótípushoz

[!include [banner](../includes/banner.md)]

Ez a témakör elmagyarázza, hogyan lehet beállítani az elszámolási időszakokat a forrásnál levont adó (TDS) elszámolási időszakaihoz.

1. Ugorjon az **Adó \> Közvetett adók \> Adóelőleg \> Adóelőleg-kiegyenlítési időszakok** elemre.

    [![Adóelőleg-kiegyenlítési időszakok oldala.](./media/apac-ind-TDS-13.png)](./media/apac-ind-TDS-13.png)

2. Az **Adótípus** mezőben válassza ki a **TDS** lehetőséget a TDS adótípus adóelőleg kiegyenlítési időszakainak beállításához.
3. Új sor létrehozásához válassza az **Új** elemet.
4. A **Kiegyenlítési időszak** mezőbe írja be a TDS kiegyenlítési időszak nevét.
5. Adjon meg egy leírást a **Leírás** mezőben.
6. Az **Adóelőleg hatósága** mezőben válassza ki azt a TDS-hatóságot, amelyhez a TDS elszámolási időszakot határozza meg.
7. Az **Általános** gyorslapon az **Időszak intervalluma** mezőben válassza ki a TDS elszámolási időszak időszak-intervallumának típusát.
8. Az **Egységek száma** mezőben adja meg az időszaki intervallumtípus egységeinek számát.
9. Az **Időszakok** gyorslapon a **Kezdő dátum** mezőben válassza ki a TDS elszámolási időszak kezdő dátumát. Válassza ki a befejező dátumot a **Befejező dátum** mezőben.
10. Ha egy meglévő időszakra egy későbbi TDS-elszámolási időszakot szeretne létrehozni az időszakintervallum és az időszakegységek alapján, válassza az **Új időszak** lehetőséget.
11. Az adott elszámolási időszakra vonatkozó időszakos TDS-elszámolás részleteinek megtekintéséhez válassza az **Adóelőlegfizetés** lehetőséget az **Adóelőlegfizetés** oldal megnyitásához.

    > [!NOTE]
    > Az időszakos TDS-elszámolási folyamat futtatásához lépjen a **Főkönyv \> Időszakos \> Adóelőleg \> Adóelőleg-fizetés** lehetőségre.

    [![Adóelőlegfizetés oldal.](./media/apac-ind-TDS-15.png)](./media/apac-ind-TDS-15.png)

12. Zárja be a lapot.
