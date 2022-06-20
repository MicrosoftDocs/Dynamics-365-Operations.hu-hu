---
title: 'A TDS-paraméterek beállítása:'
description: Ez a témakör bemutatja, hogyan lehet beállítani a paramétereket a forrásnál levont adó aktiválásához a megadott tranzakciókban. Ez a lépés szükséges Forrásnál levont adó funkció használatához.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 3390cad6979858fbff73769d0d25132ba18a2157
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8865613"
---
# <a name="set-the-tds-parameters"></a>A TDS-paraméterek beállítása:

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan lehet beállítani a paramétereket a forrásnál levont adó aktiválásához a megadott tranzakciókban. Ez a lépés szükséges Forrásnál levont adó funkció használatához.

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
