---
title: 'A TDS-paraméterek beállítása:'
description: Ez a témakör bemutatja, hogy hogyan lehet beállítani a paramétereket a forrásnál levont adó (TDS) funkció aktiválásához a megadott tranzakciókban. Ez a lépés szükséges Forrásnál levont adó funkció használatához.
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
ms.openlocfilehash: b74a1ab6d0f17367fc16f795e1b28ff5d0c5508e
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6358242"
---
# <a name="set-the-tds-parameters"></a>A TDS-paraméterek beállítása:

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogy hogyan lehet beállítani a paramétereket a forrásnál levont adó (TDS) funkció aktiválásához a megadott tranzakciókban. Ez a lépés szükséges Forrásnál levont adó funkció használatához.

1. Menjen a **Főkönyv \> Főkönyv beállítás \> Főkönyv paraméterei** pontra.
2. A **Közvetlen adók** lapon a **Forrásnál levont adó** szakaszban állítsa a **TDS aktiválása** lehetőséget **Igen** beállításra a TDS funkció, valamint az ahhoz használt lapok és mezők aktiválásához.
3. Állítsa a **Számla** lehetőséget **Igen** értékre, hogy aktiválja a számla szintjén az adószámításhoz és -levonáshoz használt mezőket.
4. Állítsa a **Fizetés** lehetőséget **Igen** értékre, hogy aktiválja a fizetés szintjén az adószámításhoz és -levonáshoz használt mezőket.

    [![Közvetlen adók lap.](./media/apac-ind-TDS-1.png)](./media/apac-ind-TDS-1.png)

5. A **Számsorozatok** lapon keresse meg azt a sort, amelyben a **Hivatkozás** mezőben **Adóelőleg-fizetés** van beállítva. A **Számsorozat kódja** mezőben a sorhoz válasszon ki egy számsorozat-kódot. A számsorozatkód segítségével bizonylatszámokat lehet létrehozni az időszakos TDS kiegyenlítési folyamathoz.

    > [!NOTE]
    > Az időszakos TDS-elszámolási folyamat futtatásához lépjen az **Adó \> Nyilatkozatok \> Adóelőleg \> Adóelőleg-fizetés** lehetőségre.

    [![Számsorozatok lap.](./media/apac-ind-TDS-2.png)](./media/apac-ind-TDS-2.png)

6. Zárja be a lapot.
