---
title: Tervezett rendelések megtekintése, kezelése és jóváhagyása
description: Ez a témakör a tervezett rendelések a Tervezésoptimalizálásban történő megtekintésével, kezelésével és jóváhagyásával kapcsolatban tartalmaz tájékoztatást.
author: ChristianRytt
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 94ecd623d445e23cc41829c51429e4783daa49f9
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6355973"
---
# <a name="view-manage-and-approve-planned-orders"></a>Tervezett rendelések megtekintése, kezelése és jóváhagyása

[!include [banner](../../includes/banner.md)]

Ez a témakör a tervezett rendelések a Tervezésoptimalizálásban történő megtekintésével, kezelésével és jóváhagyásával kapcsolatban tartalmaz tájékoztatást.

## <a name="view-and-manage-planned-orders"></a><a name="view-planned-orders"></a>Tervezett rendelések megtekintése és kezelése

A tervezett rendelések bármely tervezett rendelési listaoldalon megtekinthetők és kezelhetők. A munkához használni kívánt tervezett rendelések típusától függően lépjen a következő helyek egyikére:

- Alaptervezés \> Munkaterületek \> Alaptervezés
- Alaptervezés \> Alaptervezés \> Tervezett rendelések
- Gyártásvezérlés \> Termelési rendelések \> Tervezett termelési rendelések
- Beszerzés és forrás \> Beszerzési rendelés \> Tervezett beszerzési rendelések
- Készletnyilvántartás \> Bejövő rendelések \> Tervezett átmozgatások
- Készletnyilvántartás \> Kimenő rendelések \> Tervezett átmozgatások

## <a name="view-and-edit-the-status-of-planned-orders"></a>A tervezett rendelések állapotának megtekintése és szerkesztése

Az egyes tervezett rendelések **Állapot** mezőjével nyomon követheti az előrehaladást, illetve módosíthatja a tervezett rendelések feldolgozásának módját. A következő **Állapot** értékek érhetők el:

- **Feldolgozatlan** – Amikor az alaptervezés tervezett rendeléseket készít, akkor ezt az állapotot kapják. Az ilyen állapotú tervezett rendeléseket a program a következő tervezés futtatásakor törli.
- **Befejeződött** – Ez az állapot azt jelzi, hogy a tervezett rendelést befejezték. Ha úgy dönt, hogy nem erősíti meg a tervezett rendelést, akkor manuálisan is módosíthatja az állapotát *Befejeződött* értékre. Ne feledje, hogy a rendszer a *Feldolgozatlan* és a *Befejezett* állapotot ugyanúgy kezeli.
- **Jóváhagyva** – Ez az állapot azt jelzi, hogy a tervezett rendelést jóváhagyták megerősítésre. Ha meg szeretné határozni a tervezett rendelést, akkor a *Jóváhagyott* állapotra módosítható. Ha meg szeretné tartani a tervezett rendelésen történt módosításokat, vagy ha egy tervezett rendelés megerősítését tervezi, módosítsa a tervezett rendelés állapotát *Jóváhagyott* értékre. Az alaptervezés rögzítettnek és várható készletnek minősíti a *Jóváhagyott* állapotú tervezett rendeléseket. Ezért ezek nem módosulnak és nem törlődnek a későbbi alaptervezési futások során. A viselkedés elérése érdekében a tervezési logika átmásolja a *Jóváhagyott* állapotú tervezett rendeléseket a régi terv verzióból az új terv verzióba az alaptervezés során. Ne felejtse el, hogy a *Jóváhagyott* állapotú tervezett rendelések csak az adott alaptervben számítanak ellátásnak.

Ha egyetlen tervezett rendelés állapotát kell módosítani, [nyissa meg a tervezett rendelések listaoldalát](#view-planned-orders), nyissa meg a rendelést, majd hajtsa végre a következő lépések valamelyikét:

- Az **Általános** gyorslapon módosítsa az **Állapot** mező értékét.
- A Művelet ablaktábla **Tervezett rendelés** lapjának **Feldolgozás** csoportjában válassza az **Állapot módosítása** elemet.
- A rendelés jóváhagyottként való megjelöléséhez válassza a **Jóváhagyás** lehetőséget a Műveletpanelen.

Ha egyszerre több tervezett rendelés állapotát is módosítani szeretné, [nyissa meg a tervezett rendelések listaoldalát](#view-planned-orders), jelölje be mindegyik módosítani kívánt rendelés jelölőnégyzetét, majd hajtsa végre a következő lépések valamelyikét:

- A Művelet ablaktábla **Tervezett rendelés** lapjának **Feldolgozás** csoportjában válassza az **Állapot módosítása** elemet.
- A rendelések jóváhagyottként való megjelöléséhez válassza a **Jóváhagyás** lehetőséget a Műveletpanelen.

## <a name="approve-planned-orders"></a>Tervezett rendelések jóváhagyása

A tervezett rendelések jóváhagyása nem kötelező lépés a megerősített rendelés egy tervezett rendelésből való létrehozásának folyamatában.

A következő ábra bemutatja, hogy hogyan lehet a jóváhagyási munkafolyamat megvalósításához használni az egyes tervezett rendelésekhez hozzárendelt **Állapot** értéket. A jóváhagyási folyamat megvalósításához manuálisan módosítsa az egyes tervezett rendelések **Állapot** értékét az előző szakaszban leírtaknak megfelelően.

![Tervezett rendelés folyamata.](media/approved-planned-orders-1.png)

> [!TIP]
> Javasoljuk, hogy hagyja jóvá a módosított tervezett rendeléseket. Ellenkező esetben a rendszer figyelmen kívül hagyja a módosításokat, és felülírja őket a következő tervezési futtatás során.

## <a name="additional-resources"></a>További erőforrások

- [Biztosra tervezett rendelések](planned-order-firming.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
