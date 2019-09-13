---
title: Eszközök számlálóinak automatikus frissítése
description: Ez a témakör az Eszközkezelésben használt eszközszámlálók automatikus frissítését ismerteti.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 97e6912cd37d6f82d8bf022141f04645a3364ee1
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875700"
---
# <a name="automatic-update-of-asset-counters"></a>Eszközök számlálóinak automatikus frissítése

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Az előző részben le van írva az eszközök számlálóinak manuális regisztrálása. Az eszközök számlálóinak beállítását a [Számlálók](../setup-for-objects/counters.md) írják le.

A számlálók értékei automatikusan is frissíthetők a termelési regisztrációk alapján, a termelési órák vagy termelési mennyiségek alapján. Ez az **Eszköz számlálóinak frissítése** során történik. Egy vagy több eszköz frissítéséhez egy paramétert, a **Kezdő dátumot**kell beszúrni. Ez a paraméter határozza meg a termelési regisztrációk kezdő dátumát (az órákat vagy a termelt mennyiséget), vagyis azt a kezdő dátumot, amikor a számlálók értékét frissíteni kell.

Minden olyan eszköz, amely egy erőforráshoz van rendelve *és* amelyekhez eszközszámláló van beállítva, amely a gyártott mennyiség vagy termelési óra alapján történő frissítésre van beállítva, az automatikus frissítés része lesz, és létrejönnek az új számlálók értékei.

A termelési mennyiségen alapuló számlálók, a megfelelő mennyiség és a regisztrált hibás mennyiség a számlálásban szerepel. Ha a termelt mennyiséghez használt egység eltér a számlálóban használt egységtől, akkor a program átváltja a mennyiséget a számláló egységével.

A fent említettek szerint az automatikus számlálók a termelési regisztrációk alapján frissíthetők. Ennélfogva az eszköznek, amelynél automatikusan szeretné frissíteni a számlálókat, egy erőforráshoz (gép) kell tartoznia. A következő leírások áttekintést nyújtanak a termelési rendelések beállításáról és feldolgozásáról (a **Gyártásvezérlés** modulban), amelyek az eszköz számlálóinak automatikus frissítéséhez használatosak az **Eszközkezelés** modulban.

Ha az erőforrásban a gyártott mennyiségek vagy a termelési órák regisztrálva vannak, akkor frissítheti a kapcsolódó eszköz számlálóit.

1. Kattintson az **Eszközkezelés** > **Időszakos** > **Eszközök** > **Eszköz számlálóinak frissítése** lehetőségre.

2. A **Kezdő dátum** mezőben válassza ki az automatikus frissítés kezdő dátumát.

>[!NOTE]
>Az ebben a mezőben szereplő dátum a „folyamatban lévő munka” dátuma innen: **Útvonal-tranzakciók** (**Gyártásvezérlés** > **Lekérdezések és jelentések** > **Termelés** > **Útvonal-tranzakciók** > **Tényleges dátum** mező).

3. Ha ki szeretne választani adott eszközt, eszköztípust vagy erőforrást az automatikus frissítéshez, kattintson a **Belefoglalandó rekordok** gyorslap **Szűrő** elemére, és végezz el a megfelelő kiválasztásokat.

4. Ha szükséges, a **Futtatás a háttérben** gyorslapon szükség szerint kötegelt feladatként is beállíthatja az automatikus frissítést.

![1. ábra](media/12-work-orders.png)

5. Kattintson az **OK** gombra. Amikor az automatikus eszközszámláló-frissítés megtörtént, az eszközhöz kapcsolódó számláló-regisztrációk láthatók itt: **Eszközökszámlálók** (**Eszközkezelés** > **Közös** > **Eszközök** > **Minden eszköz** > eszköz kiválasztása > **Számlálók** gomb).

Az **Eszköz számlálóinak összegei** részben áttekintést kaphat az összes eszközhöz tartozó összes számlálótípus legutóbbi regisztrálásairól. Kattintson az **Eszközkezelés** > **Lekérdezések** > **Eszközök** > **Eszköz összesített érték** elemre. A nézet nagyon hasonló az **Eszközszámlálók** elemhez, de nem lehet hozzáadni és szerkeszteni a regisztrációkat itt: **Eszköz összesített érték**. Csak áttekintésre szolgál.

![2. ábra](media/13-work-orders.png)


- Továbbra is lehetőség van arra, hogy manuális számlálóregisztrációkat hozzon létre az automatikusan frissített számlálótípusokhoz. A további tudnivalókat lásd: „Eszközök számlálóinak manuális frissítése”.
- Egy másik számlálóhoz kapcsolódó számlálókat is beállíthat, ami azt jelenti, hogy a számláló frissítésekor a program automatikusan frissíti a kapcsolódó számlálókat is. A kapcsolódó számlálók beállításáról itt talál további információt: [Számlálók](../setup-for-objects/counters.md).
