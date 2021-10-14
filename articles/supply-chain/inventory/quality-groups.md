---
title: Cikkminőségi csoportok
description: Ez a témakör azt írja le, hogyan lehet a termékek logikai csoportosítására cikkminőségi csoportokat használni és létrehozni, hogy a minőségi rendelések automatikus létrehozásához minőségi rendeléseket lehessen hozzárendelni.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestQualityGroup, InventTestItemQualityGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f7a4932c561c052bec1eb0094a390e315b9b1bb
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580912"
---
# <a name="item-quality-groups"></a>Cikkminőségi csoportok

[!include [banner](../includes/banner.md)]

A minőségi csoport a cikkekre vonatkozó közös tesztkövetelményeket képvisel. Ez a témakör azt írja le, hogyan lehet a termékek logikai csoportosítására cikkminőségi csoportokat használni és létrehozni, hogy a minőségi rendelések automatikus létrehozásához minőségi rendeléseket lehessen hozzárendelni.

A minőségi csoporthoz rendelt cikkeket, illetve a cikkhez rendelt minőségi csoportokat lehet beállítani, módosítani és megtekinteni, ehhez menjen a **Készletkezelés \> Beállítás \> Minőségi csoportok** részhez. Miután a **Tesztcsoportok** oldalon definiálta a tesztkövetelményeket, meghatározhatja a minőségi rendelések automatikus létrehozásának szabályait. A folyamat egyszerűsítése érdekében az egyes cikkekhez tartozó szabályokat Ön nem határozza meg. Ehelyett egy minőségi csoportra vonatkozó szabályokat definiálhatunk a **Minőségi társítások** oldalon.

## <a name="example-of-an-item-quality-group"></a>Példa egy cikkminőségi csoportra

Egy gyártóvállalat több nyersanyagot is vásárol, amelyeknél a beérkezéskor szükséges vizsgálatokra ugyanazok a tesztkövetelmények vonatkoznak. Ezért a vállalat definiál egy minőségi csoportot, majd hozzárendeli a nyersanyagokhoz társított cikkszámokat a csoporthoz. Később a vállalat egy új típusú nyersanyagot vásárol, amelyre az előzőekkel azonos tesztkövetelmények vonatkoznak. Ahelyett, hogy az új anyagra új tesztkövetelményeket állítana be, a vállalat hozzáadja az új anyag cikkszámát a meglévő minőségi csoporthoz.

Ugyanez a vállalat olyan cikkeket is gyárt, amelyek gyártási tesztjeire ugyanazok a követelmények érvényesek, és olyan cikkeket is szállít, amelyek szállítás előtti tesztjeire ugyanolyan követelmények vonatkoznak. Ezért a vállalat két további minőségi csoportot határoz meg, majd a megfelelő cikkszámokat hozzárendeli az egyes minőségi csoportokhoz.

## <a name="create-a-quality-group"></a>Minőségi csoport létrehozása

Minőségi csoport létrehozásához kövesse az alábbi lépéseket.

1. Ugorjon a **Készletkezelés \> Beállítás \> Minőség-ellenőrzés \> Minőségi csoportok** elemre.
1. A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz. Ezután új sorhoz állítsa be a következő mezőket:

    - **Minőségi csoport** – Adja meg a minőségi csoport egyedi azonosítóját vagy nevét.
    - **Leírás** – Adja meg a minőségi csoport részletes leírását.

1. Zárja be a lapot.

## <a name="manually-add-items-to-a-quality-group"></a>Cikkek manuális hozzáadása egy minőségi csoporthoz

A következő lépések követésével adhat hozzá cikkeket manuálisan egy minőségi csoporthoz.

1. Ugorjon a **Készletkezelés \> Beállítás \> Minőség-ellenőrzés \> Minőségi csoportok** elemre.
1. Annak a minőségi csoportnak a kiválasztása, amelybe cikkeket szeretne felvenni.
1. A Művelet ablaktáblán kattintson a **Cikkek** elemre.
1. A **Cikkek a minőségi csoportokban** oldalon a műveleti ablaktáblán válassza az **Új** elemet sor rácshoz adásához. Ezután az új sorhoz állítsa be a **Cikkszám** mezőt a hozzáadni kívánt cikkszámhoz.
1. Ismételje meg az előző lépést minden olyan cikkel, amit hozzá szeretne még adni.
1. Zárja be a lapokat.

## <a name="add-multiple-items-to-a-quality-group"></a>Több cikk hozzáadása egy minőségi csoporthoz

A következő lépések követésével adhat hozzá több cikkeket egy minőségi csoporthoz.

1. Ugorjon a **Készletkezelés \> Beállítás \> Minőség-ellenőrzés \> Minőségi csoportok** elemre.
1. Annak a minőségi csoportnak a létehozása vagy kiválasztása, amelybe cikkeket szeretne felvenni.
1. A Művelet ablaktáblán kattintson a **Cikkek hozzáadása** elemre.
1. A **Lekérdezés** párbeszédpanelen adja meg a hozzáadni kívánt cikkek szűrési feltételét. Szűrheti például egy adott cikkcsoport minden cikkét.
1. Válassza ki az **OK** lehetőséget.
1. A **Cikkek hozzáadása** párbeszédpanelen egy rács jeleníti meg a lekérdezésnek megfelelő összes elemet. Az eredmények áttekintése.

    Ha bármilyen módosítás szükséges, akkor a **Kijelölés** gombra kattintva visszatérhet a **Lekérdezés** párbeszédpanelre, és módosíthatja a lekérdezést.

1. Ha az eredmények tartalmazzák az összes hozzáadni kívánt tételt, akkor válassza az **OK** elemet.
1. Zárja be a lapot.

## <a name="manually-associate-an-item-with-a-quality-group"></a>Cikk manuális társítása minőségi csoporthoz

A következő lépések követésével társíthat cikket egy minőségi csoporthoz.

1. Ugorjon a **Készletkezelés \> Beállítás \> Minőség-ellenőrzés \> Cikkminőségi csoportok** elemre.
1. A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz. Ezután új sorhoz állítsa be a következő mezőket:

    - **Cikkszám** – Válassza ki a hozzáadni kívánt cikkszámot.
    - **Minőségi csoport** – A cikkhez hozzárendelni kívánt minőségi csoport kiválasztása.

1. Ismételje meg az előző lépést a cikk minden további, hozzáadni kívánt minőségi csoportjával.
1. Zárja be a lapokat.

## <a name="manually-add-a-quality-group-from-the-released-products-page"></a>Minőségi csoport manuális hozzáadása a Kiadott termékek lapon

Ahhoz, hogy minőségi csoportot adjon hozzá manuálisan a **Kiadott termékek** lapon, kövesse az alábbi lépéseket.

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Jelölje ki a terméket, amelyhez minőségi csoportot kíván rendelni.
1. A Műveleti panelen, a **Készletkezelés lapon** a **Minőség** csoportban válassza a **Cikkminőségi csoportok** lehetőséget.
1. A **Cikkek a minőségi csoportokban** oldalon a műveleti ablaktáblán válassza az **Új** elemet sor rácshoz adásához. Ezután az új sornál állítsa a **Minőségi csoport** mezőt a termékhez hozzárendelni kívánt minőségi csoportra.
1. Ismételje meg az előző lépést a termékhez hozzárendelni kívánt további minőségi csoportokkal.
1. Zárja be a lapokat.

## <a name="additional-resources"></a>További erőforrások

- [Minőségbiztosítási tesztműszerek](quality-test-instruments.md)
- [Minőségkezelési tesztek](quality-tests.md)
- [Minőségbiztosítási tesztcsoportok](quality-test-groups.md)
- [Minőségbiztosítási tesztváltozók](quality-test-variables.md)
- [Minőségi társítások](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
