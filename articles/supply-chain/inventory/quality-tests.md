---
title: Minőségbiztosítási tesztek
description: Ez a témakör azt mutatja be, hogyan lehet teszteket létrehozni, amelyek minőségi rendelésekhez használhatók a Microsoft Dynamics 365 Supply Chain Management alkalmazásban.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c10b67f86fc29b5e8c08081a9b789d4f42c24cf4
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573849"
---
# <a name="quality-management-tests"></a>Minőségbiztosítási tesztek

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet teszteket létrehozni, amelyek minőségi rendelésekhez használhatók a Microsoft Dynamics 365 Supply Chain Management alkalmazásban.

A **Tesztek** oldalon lehet meghatározni és megtekinteni azokat a teszteket, amelyekkel megállapítható, hogy a termékek megfelelnek-e a minőségi specifikációknak. Hozzárendelhet egy vagy több különálló tesztet egy tesztcsoporthoz. Ebben az esetben tesztspecifikus adatokat is megadhat, például az elfogadható mérési értékeket. A mértékegységeket a mennyiségi teszteknél lehet használni. A kvalitatív tesztekhez tesztváltozókat kell használni.

- Mennyiségi teszt esetén a **Típus** mező beállítása *Tört* vagy *Egész szám*. Mértékegység is meg van határozva. A minőségi specifikációk és a teszteredmények számokként fejeződnek ki.
- (Minőségi tesztek esetén a **Típus** mező értéke legyen *Lehetőség*.) A minőségi tesztekhez további, a mérendő tesztváltozóra és annak sorszámozott lehetőségeire vonatkozó adatok szükségesek. A minőségi specifikációk és a teszteredmények egy eredménynek megfelelően fejeződnek ki.

Opcionálisan tesztműszert is hozzá lehet rendelni egy teszthez. A minőségi rendelésekhez azonban nem szükséges tesztműszereket létrehozni és használni. További információért lásd: [Minőségbiztosítási tesztműszerek](quality-test-instruments.md).

A tesztekhez tetszés szerint megadhat egy egységet is, ezzel jelezheti, a mértékegységet, amelyben a teszteredményeket rögzítik. Például a hőmérséklet-teszthez tartozhat egy Fahrenheit vagy Celsius.

## <a name="example-of-a-test"></a>Példa egy tesztre

Egy gyártóvállalat a beszerzett anyagon két tesztet végez el: ezek egyike az anyagminőséggel kapcsolatos mennyiségi teszt, a másik pedig a csomagolási sérüléseket felmérő minőségi teszt. A vállalat további adatokat ad meg a kvalitatív tesztre vonatkozóan, hogy azonosítsa a tesztváltozót (például sérült csomagolás) és annak kimeneteleit. A vállalat a **Tesztcsoportok** oldalon hozzárendeli a két tesztet egy tesztcsoporthoz és megadja a tesztspecifikus adatokat. A tesztcsoportot hozzárendeli egy minőségi rendeléshez, hogy a két teszt eredményét jelenteni tudja.

## <a name="create-a-test"></a>Teszt létrehozása

Teszt létrehozásához kövesse az alábbi lépéseket.

1. Ugorjon a **Készletkezelés \> Beállítás \> Minőség-ellenőrzés \> Tesztek** elemre.
1. A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz. Ezután új sorhoz állítsa be a következő mezőket:

    - **Teszt** – Adja meg a teszt egyedi azonosítóját vagy nevét.
    - **Leírás** – Adja meg a teszt részletes leírását.
    - **Típus** – válassza ki a teszt által biztosított eredmények típusát. Mennyiségi tesztek esetén válassza a *Tört* vagy az *Egész érték* lehetőséget. Kvalitatív tesztek esetén válassza a *Lehetőség* értéket.
    - **Tesztműszer** – Válassza ki a teszthez használt [tesztműszert](quality-test-instruments.md).
    - **Egység** – ha a *Típus* mezőben a *Tört* vagy **Egész szám** lehetőséget választotta (azaz mennyiségi tesztről van szó), válassza ki azt a mértékegységet, amelyben a teszteredményeket rögzíteni kell.

1. Zárja be a lapot.

> [!NOTE]
> A teszt mentése után a rácsban már nem szerkeszthető a **Típus** mező. Ha módosítania kell egy teszthez rögzíteni kívánt teszteredmények típusát, válassza a Műveleti panelen a **Minőségteszt típusának módosítása** lehetőséget. A **Minőségteszt típusának módosítása** párbeszédpanelen állítsa a kívánt típusra az **Új típus** mezőt, majd a párbeszédpanel bezárásához kattintson az **OK** gombra.

## <a name="additional-resources"></a>További erőforrások

- [Minőségbiztosítási tesztműszerek](quality-test-instruments.md)
- [Minőségbiztosítási tesztcsoportok](quality-test-groups.md)
- [Minőségbiztosítási tesztváltozók](quality-test-variables.md)
- [Minőségi társítások](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
