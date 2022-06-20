---
title: Adó-összetevők beállítása a TDS-adótípusra
description: Ez a cikk bemutatja, hogy hogyan lehet adóelőleg-összetevőket beállítani a forrásnál levont adó (TDS) adótípushoz. Azt is elmagyarázza, hogyan kell meghatározni az egyes TDS-összetevők TDS-ének kiszámításához használt küszöbértéket.
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
ms.openlocfilehash: df2eb10ce9e372bb1e984f6ae1a2e889bbd90ad0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871157"
---
# <a name="set-up-tax-components-for-the-tds-tax-type"></a>Adó-összetevők beállítása a TDS-adótípusra

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogy hogyan lehet adóelőleg-összetevőket beállítani a forrásnál levont adó (TDS) adótípushoz. A TDS komponensek a TDS, felár, PE-Cess, és SHE Cess. Ez a témakör azt is bemutatja, hogyan lehet meghatározni az egyes TDS-összetevők TDS-számításában használt küszöbértéket. Ezenkívül meghatározhat egy kivételi küszöbértéket, amelyet az egyes TDS-összetevők TDS-ének kiszámítására használhat.

A TDS-összetevők beállításához kövesse az alábbi lépéseket.

1. Lépjen az **Adó \> Beállítás \> Adóelőleg \> Adóelőleg-összetevők** részhez.

    [![Adóelőleg-összetevők oldal.](./media/apac-ind-TDS-9.png)](./media/apac-ind-TDS-9.png)

2. Az **Adótípus** mezőben válassza ki a **TDS** lehetőséget a TDS adótípus adóelőleg-komponenseinek beállításához.
3. Jelölje be a műveleti ablakban az **Új** lehetőséget az új sor létrehozásához.
4. Az **Adóelőleg összetevő** mezőben adjon nevet a TDS összetevőnek.
5. Az **Adóelőleg-összetevő csoport** mezőben válassza ki azt a TDS-adóelőleg-összetevő csoportot, amelyhez a TDS összetevőt csatolja.
6. Az **Általános** gyorslapon a **Leírás** mezőben adja meg a TDS-összetevő leírását.
7. A műveletpanelen válassza ki a **Küszöbérték** lehetőséget a **Küszöbérték** oldal megnyitásához, hogy meghatározza azt a küszöbértéket, amely a TDS-összetevő TDS--ének számításához használatos.
8. A **Kzedő dátum** és a **Befejező dátum** mezők segítségével határozza meg azt az időszakot, amelyre a küszöbérték vonatkozik.
9. Adja meg az **Általános** gyorslapon a **Küszöbérték** mezőben azt a küszöbérték-összeget, amely a TDS összetevő TDS-ének számításához használatos. Az adó levonása csak akkor történik meg a forrásnál, ha a számla halmozott összege túllépi a küszöbértéket.

    Ha például a küszöbérték összege 10 000, akkor a TDS számítása az összesített számlaösszeg után történik, amely meghaladja a 10 000-et (tehát10 001 vagy több).

10. A **Kivételi Küszöbérték** mezőben azt a kivételi küszöbérték-összeget adja meg, amely a TDS összetevő TDS-ének számításához használatos. A számlasor adójának levonása csak akkor történik meg a forrásnál, ha a számla halmozott összege túllépi a kivételi küszöbértéket.

    Ha például a kivétel küszöbérték összege 5000, akkor a TDS számítása egy adott számlasor alapján történik, ha a számlasor összege meghaladja az 5000-et (vagyis, ha 5001 vagy több).

    [![Küszöbérték oldal.](./media/apac-ind-TDS-10.png)](./media/apac-ind-TDS-10.png)

    > [!NOTE]
    > A kivételi küszöbérték összegének kisebbnek vagy egyenlőnek kell lennie a küszöbérték összegével.
    >
    > A rendszer akkor is levonja a tranzakció adóját, ha a tranzakció összege túllépi a kivételi küszöbértéket, még akkor is, ha a számla halmozott összege nem lépi túl a **Küszöbérték** mezőben megadott küszöbértéket.

11. A **Küszöbérték** lap bezárásával térjen vissza **Adóelőleg-összetevők** lapra.
12. A Műveleti panelen a **Másolás** gombra kattintva nyissa meg az **Adóelőleg-összetevők másolása** párbeszédpanelt, hogy átmásolhassa az egyik TDS-összetevő csoporthoz beállított TDS-összetevőket egy másik TDS-összetevő csoportba.
13. A **Forrás** mezőben válassza ki azt a TDS-összetevő csoportot, amelyből másolni kell a TDS-összetevőket. A **Cél** mezőben válassza ki az adóelőleg összetevő csoportot, amelybe másolni kell a TDS-összetevőket.

    > [!NOTE]
    > A TDS-összetevőcsoportokhoz csatolt általános TDS-összetevők másolása nem történt meg.

14. Ha az **Adóelőleg-összetevők** lapon válassza az **OK lehetőséget a TDS-összetevők másolásához a másik TDS-összetevő csoportra az Adóelőleg-összetevők** oldalon.

    [![Adóelőleg-összetevők másolása párbeszédpanel.](./media/apac-ind-TDS-11.png)](./media/apac-ind-TDS-11.png)

15. Zárja be a lapot.
