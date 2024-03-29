---
title: Eszközök számlálóinak automatikus frissítése
description: Ez a témakör ismerteti az eszközszámlálók automatikus frissítését az Eszközkezelésben.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8ea84259eb8f12becdcf008ed9222a44b2626a0d
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016217"
---
# <a name="automatic-update-of-asset-counters"></a>Eszközök számlálóinak automatikus frissítése

[!include [banner](../../includes/banner.md)]

Az eszközök számlálóinak manuális regisztrálásával kapcsolatos tudnivalókat lásd: [Eszközszámlálók manuális frissítése](../work-orders/manual-update-of-asset-counters.md). Az eszközszámlálók beállításával kapcsolatos további információkat lásd: [Számlálók](../setup-for-objects/counters.md).

A számlálók értékei automatikusan is frissíthetők a termelési regisztrációk alapján, a termelési órák vagy termelési mennyiségek alapján (ez a gyártott mennyiség). Ez a frissítés az **Eszközök frissítése** lapon történik. Egy vagy több eszköz frissítéséhez egy paramétert, a **Kezdő dátumot** kell beállítani. Ez a paraméter a termelési regisztrációk (termelési órák vagy termelési mennyiségek) kezdődátumát határozza meg. Más szóval azt a dátumot határozza meg, amikortól a számlálók értékét frissíteni kell.

Minden olyan eszköz, amely egy erőforráshoz van rendelve *és* amelyekhez eszközszámláló van beállítva, amely a gyártott mennyiség vagy termelési óra alapján történő frissítésre van beállítva, az automatikus frissítés része lesz. Új számlálóértékek jönnek létre.

A termelési mennyiségen alapuló számlálók esetében a számlálás mind a jó mennyiséget, mind a regisztrált hibás mennyiséget tartalmazza. Ha a termelési mennyiséghez használt egység eltér a számlálóban használt egységtől, akkor a program átváltja a mennyiséget a számláló egységének megfelelőre.

A fent említettek szerint az automatikus számlálók a termelési regisztrációk alapján frissíthetők. Ennélfogva az eszköznek, amelynél automatikusan szeretné frissíteni a számlálókat, egy erőforráshoz (gép) kell tartoznia. Ha az erőforrásban a gyártott mennyiségek vagy a termelési órák regisztrálva vannak, akkor frissítheti a kapcsolódó eszköz számlálóit.

1. Válassza az **Eszközkezelés** > **Időszakos** > **Eszközök** > **Eszköz számlálóinak frissítése** lehetőséget.

2. A **Kezdő dátum** mezőben válassza ki az automatikus frissítés kezdő dátumát.

    >[!NOTE]
    >Az ebben a mezőben szereplő dátum a „folyamatban lévő munka” dátuma innen: **Útvonal-tranzakciók** (**Gyártásvezérlés** > **Lekérdezések és jelentések** > **Termelés** > **Útvonal-tranzakciók** > **Tényleges dátum** mező).

3. A **Szerepeltetni kívánt rekordok** gyorslapon kiválaszthatja az automatikus frissítés konkrét eszközeit, eszköztípusait vagy erőforrásait. Válassza a **Szűrő** elemet, és végezze el a kapcsolódó kiválasztásokat.

4. A **Futtatás a háttérben** gyorslapon szükség szerint kötegelt feladatként is beállíthatja az automatikus frissítést.

    Az alábbi ábra az **Eszköszámlálók frissítése** párbeszédablak egy példáját mutatja be.

    ![1. ábra](media/12-work-orders.png)

5. Válassza ki az **OK** lehetőséget. 

Az automatikus eszközszámláló-frissítést követően megtekintheti a az eszközhöz kapcsolódó számlálóregisztrációkat az **Eszköz számlálók** oldalon. Válassza **ki az Eszközkezelés** > **– Összes** > **eszköz** eszközt, jelölje ki az eszközt, **·** **majd válassza ki a Számlálókat a műveletpanel Eszköz lapján, a Megelőző** **csoportban.**

Az **Eszköz összesített értéke** oldalon áttekintést kaphat az összes eszközhöz készített összes számlálótípus legutóbbi regisztrálásairól. Válassza az **Eszközkezelés** > **Lekérdezések** > **Eszközök** > **Eszköz összesített érték** elemet. Ez a lap hasonlít az **Eszközök számlálók** lapjára, de regisztrációkat nem lehet regisztrációkat hozzáadni és szerkeszteni. Csak áttekintésre szolgál.

Az alábbi ábra az **Eszközök összesített értéke** oldal egy példáját mutatja be.

![2. ábra](media/13-work-orders.png)

Vegye figyelembe az alábbiakat:

- Továbbra is lehetősége van arra, hogy manuális számlálóregisztrációkat hozzon létre az automatikusan frissített számlálótípusokhoz. A további tudnivalókat lásd: [Eszközök számlálóinak manuális frissítése](../work-orders/manual-update-of-asset-counters.md).

- Lehetőség van egy másik számlálóhoz kapcsolódó számlálók beállítására is. Ebben az esetben a számláló frissítését követően a kapcsolódó számlálók frissítése is egyidőben megtörténik. Az számlálók beállításával kapcsolatos további információkat lásd: [Számlálók](../setup-for-objects/counters.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]