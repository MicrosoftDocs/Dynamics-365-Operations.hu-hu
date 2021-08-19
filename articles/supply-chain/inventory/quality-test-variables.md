---
title: Minőségbiztosítási tesztváltozók
description: Ez a témakör azt mutatja be, hogyan lehet tesztváltozókat létrehozni, amelyek a minőségi rendelések kvalitatív tesztjeihez használhatók a Microsoft Dynamics 365 Supply Chain Management alkalmazásban.
author: rachel-profitt
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
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8233864d6b668c8462a59a425e66b1aec38576633922062573d8605c9c73d2a8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6734211"
---
# <a name="quality-management-test-variables"></a>Minőségbiztosítási tesztváltozók

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet tesztváltozókat létrehozni, amelyek a minőségi rendelések kvalitatív tesztjeihez használhatók a Microsoft Dynamics 365 Supply Chain Management alkalmazásban.

Minden egyes, a **Tesztek** oldalon megadott minőségi teszthez definiálnia kell egy változót és annak eredményeit. (Minőségi tesztek esetén a **Tesztek** a **Típus** mező értéke legyen *Lehetőség*.)

A **Tesztváltozók** oldalon lehet beállítani, módosítani vagy megtekinteni a minőségi teszthez kapcsolódó tesztváltozó lehetséges eredményeit. Mindegyik eredményhez *Sikeres* vagy *Sikertelen* eredményállapot hozzárendelésével kell jelezni, hogy a teszt sikeres vagy sikertelen volt, amennyiben az eredményt teszteredményként választják ki. A **Tesztcsoportok** oldal használatával lehet tesztváltozót és az alapértelmezett eredményt adott minőségi teszthez hozzárendelni.

Minden tesztváltozónál ajánlott legalább két eredményt meghatározni: egyet *Sikeres* eredménystátuszhoz, egyet pedig *Sikertelen* eredménystátuszhoz. Nincs korlátozva a definiálható változók és eredmények teljes száma. Ezenkívül az eredmények rögzítésére több teszt is használhatja ugyanazt a tesztváltozót.

## <a name="examples-of-test-variables"></a>Példák tesztváltozókra

### <a name="example-1"></a>1. példa

Egy gyártóvállalat két tesztet végez el a gyártott anyagokon. Az egyik tesztben a pH-szint egy színcsíkhoz van társítva. Az elfogadható pH-szintek a világosabb színek, a nem elfogadható pH-szintek a sötétebb színek. Egy másik teszten több vizuális vizsgálatot végeznek, és a minőségbiztosítási dolgozók saját belátásuk szerint döntik el, hogy a cikk megfelelő-e, vagy sem.

### <a name="example-2"></a>2. példa

Egy süteménygyártó a készterméken vizsgálatot végez. A vizsgálat tesztnek többféle változója van. Az egyik változó az íz, ennek lehetséges eredményei: jó és rossz. Egy másik változó a szín, ennek lehetséges eredményei: túl sötét, túl világos és megfelelő.

## <a name="create-a-test-variable"></a>Új tesztváltozó létrehozása

Tesztváltozó létrehozásához kövesse az alábbi lépéseket.

1. Ugorjon a **Készletkezelés \> Beállítás \> Minőség-ellenőrzés \> Tesztváltozók** elemre.
1. A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz. Ezután új sorhoz állítsa be a következő mezőket:

    - **Változó** – Adja meg a változó egyedi azonosítóját vagy nevét.
    - **Leírás** – Adja meg a változó részletes leírását.

1. Amíg az új sor még ki van választva, válassza ki az **Eredményeket** a műveleti panelen.
1. A **Tesztváltozó eredményei** oldalon a Műveleti ablaktáblán válassza az **Új** elemet sor rácshoz adásához. Ezután új sorhoz állítsa be a következő mezőket:

    - **Eredmény** – Adja meg az eredmény egyedi azonosítóját vagy nevét.
    - **Leírás** – Adja meg az eredmény részletes leírását.
    - **Eredmény állapota** Mindegyik eredménynél a *Sikeres* vagy *Sikertelen* eredményállapot hozzárendelésével kell jelezni, hogy a teszt sikeres vagy sikertelen volt, amennyiben az eredményt teszteredményként választják ki.

1. Ismételje meg az előző lépést minden további eredményhez. Győződjön meg róla, hogy legalább egy eredményállapot *Sikeres*, és legalább egy eredményállapot *Sikertelen*.
1. Zárja be a lapokat.

## <a name="additional-resources"></a>További erőforrások

- [Minőségbiztosítási tesztműszerek](quality-test-instruments.md)
- [Minőségkezelési tesztek](quality-tests.md)
- [Minőségbiztosítási tesztcsoportok](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
