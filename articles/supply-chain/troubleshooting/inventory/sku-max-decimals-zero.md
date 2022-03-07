---
title: A készlettárolási egységre vonatkozó tizedesjegyek maximális száma 0
description: 'Készlettranzakció vagy készletfoglalás feladása során a következő hibaüzenet jelenik meg: "A termékraktározási egységnél a tizedesjegyek maximális száma 0."'
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 9dec198e2d77efd2253c80e14d15791cc37f88e1
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476591"
---
# <a name="maximum-number-of-decimals-for-the-stock-keeping-unit-is-0"></a>A készlettárolási egységre vonatkozó tizedesjegyek maximális száma 0


## <a name="symptoms"></a>Tünetek

Amikor készlettranzakciót vagy készletfoglalást próbál feladni, a következő hibaüzenet jelenik meg:

> A készlettárolási egységre vonatkozó tizedesjegyek maximális száma 0.

Ez a probléma akkor fordul elő, ha a készlettranzakció mennyisége olyan tizedesértékként van megadva, amely a mező által támogatott pontosság szintje alatti. Például egy készlettranzakcióhoz *0,5* mennyiséget adott meg, de csak egész számok támogatottak. Ezért az értéknek *1-nek* kell lennie *0,5* helyett.

## <a name="resolution"></a>Megoldás

1. Futtassa a következő parancsfájlt az SQL Server-példányon a készlettranzakciók mennyiségének kerekítéséhez. Ez a parancsfájl korrigálja az **inventTrans** táblában található értékeket.

    ```sql
    update it set it.QTY = round(it.qty, decimalPrecisionValue) from inventtrans it where it.DATAAREAID='XXXX' and it.PARTITION=XXXXXX and it.qty <> round(it.qty, decimalPrecisionValue) and exists (select 'x' from INVENTTABLEMODULE a, unitofmeasure b where  a.unitid =b.SYMBOL and a.partition=it.partition and a.PARTITION=b.PARTITION and  MODULETYPE =0 and  b.DECIMALPRECISION=decimalPrecisionValue and a.DATAAREAID='XXXX' and a.ITEMID =it.ITEMID and it.DATAAREAID=a.DATAAREAID)
    ```

1. Futtassa az adott anyagon az aktuális konzisztencia-ellenőrzést, ha a **hibajavítás** beállítás be van kapcsolva. Ez az ellenőrzés korrigálja az **inventSum** táblában található értékeket.

> [!IMPORTANT]
> Kifejezetten ajánljuk, hogy a környezetnek megfelelően körültekintően szerkessze a parancsfájlt, tesztelje tesztkörnyezetben, majd ellenőrizze az így kapott adatokat, mielőtt éles környezetben futtatja a parancsfájlt.
