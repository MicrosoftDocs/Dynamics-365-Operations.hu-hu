---
title: Eszközkezelés integrálása tárgyi eszközökkel
description: Ez a témakör azt mutatja be, hogyan lehet integrálni az eszközkezelés és a tárgyi eszközök modulokat, hogy a tárgyi eszközöket a karbantartás alatt álló eszközökkel lehessen kapcsolni.
author: kamaybac
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: cdda44d361011706fe0ba170309908533aa0c2f7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429409"
---
# <a name="integrate-asset-management-with-fixed-assets"></a>Eszközkezelés integrálása tárgyi eszközökkel

[!include [banner](../../includes/banner.md)]

Az **Eszközkezelés** és a **tárgyi eszközök** modulok integrálásával a tárgyi eszközöket a karbantartás alatt álló eszközökkel lehet kapcsolni. A tárgyi eszközök felhasználói ezt követően létrehozhatnak egy új vagy meglévő tárgyi eszközből karbantartás alatt álló eszközt, és az eszközkezelési felhasználók egy meglévő tárgyi eszközhöz rendelhetik a karbantartás alatt álló eszközt. Ez a funkció megkönnyíti a tárgyi eszközök felhasználói számára, hogy megtekintsék a kapcsolódó karbantartás alatt álló eszköz munkarendeléseiből feladott költségeket.

> [!NOTE]
> Ebben a témakörben a *karbantartás alatt álló eszköz* az **Eszközkezelés** modul eszközeire utal, a *tárgyi eszközök* pedig a **Tárgyi eszközök** modul eszközeire.

## <a name="set-a-default-location-for-new-maintenance-assets-that-are-created-from-fixed-assets-optional"></a>A tárgyi eszközökből létrehozott új karbantartás alatt álló eszközök alapértelmezett helyének beállítása (nem kötelező)

Ezzel a nem kötelező konfigurációval beállíthat alapértelmezett munkavégzési helyszínt a tárgyi eszközökből létrehozott új karbantartás alatt álló eszközökhöz. Ezt a konfigurációt általában csak egy alkalommal hajthatja végre, ha egyáltalán végrehajtja.

A konfiguráció befejezéséhez kövesse az alábbi lépéseket.

1. Lépjen az **Eszközkezelés \> Beállítás \> Eszközkezelési paraméterek** részre.
1. A **Tárgyi eszközök** mezőben lévő **munkavégzési helyszín** lapon válassza ki az alapértelmezett helyét.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

## <a name="work-with-integrated-maintenance-assets-and-fixed-assets"></a>Integrált karbantartás alatt álló eszközök és tárgyi eszközök használata

Ez a szakasz olyan eljárások gyűjteményét mutatja be, amelyek az integrált eszközkezelés és a tárgyi eszközök funkcióinak használatára különböző módszereket mutatnak be.

### <a name="associate-an-existing-maintenance-asset-with-a-fixed-asset"></a>Meglévő karbantartás alatt álló eszköz társítása tárgyi eszközhöz

Meglévő karbantartás alatt álló eszköz társításához tárgyi eszközhöz kövesse ezeket a lépéseket.

1. Lépjen az **Eszközkezelés \> Eszközök \> Összes eszköz** (vagy **Aktív eszközök**) lehetőséget.
1. Válasszon egy eszközt.
1. A **Tárgyi eszköz** gyorslapon a **Tárgyi eszköz száma** mezőben válasszon egy meglévő tárgyi eszközt.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

### <a name="view-the-fixed-asset-that-is-associated-with-a-selected-maintenance-asset"></a>Tekintse meg a kiválasztott karbantartás alatt álló eszközhöz társított tárgyi eszközt

A kiválasztott karbantartás alatt álló eszközhöz társított tárgyi eszköz megtekintéséhez kövesse ezeket a lépéseket.

1. Lépjen az **Eszközkezelés \> Eszközök \> Összes eszköz** (vagy **Aktív eszközök**) lehetőséget.
1. Válasszon egy eszközt.
1. A **Tárgyi eszköz** gyorslapon a **Tárgyi eszköz száma** mezőben válassza a hivatkozást.

    A **Tárgyi eszköz** oldal megnyílik a kiválasztott eszközhöz. (Ez a lap általában a **Tárgyi eszközök \> tárgyi eszközök \> tárgyi eszközök** helyen található.)

### <a name="view-the-maintenance-asset-that-is-associated-with-a-selected-fixed-asset"></a>Tekintse meg a kiválasztott tárgyi eszközhöz társított karbantartás alatt álló eszközt

A kiválasztott tárgyi eszközhöz társított karbantartás alatt álló eszköz megtekintéséhez kövesse ezeket a lépéseket.

1. Lépjen a **Tárgyi eszközök \> Tárgyi eszközök \> Tárgyi eszközök** menüpontba.
1. Válasszon egy eszközt.
1. A Művelet ablaktábla **Eszközkezelés** lapjának **Nézet** csoportjában válassza a **karbantartás alatt álló eszköz** elemet.

    A kiválasztott tárgyi eszközhöz társított eszközhöz tartozó **karbantartás alatt álló eszköz** oldal megnyílik. (Ez a lap általában a **Eszközkezelés \> Ezsközök \> Összes eszköz** helyen található.)

### <a name="view-maintenance-costs-that-are-associated-with-a-fixed-asset"></a>Tárgyi eszközhöz társított karbantartási költségek megtekintése

Az eszközkezelési munkarendeléseket a karbantartás alatt álló eszközökhöz lehet feladni, és az egyes munkarendelések esetében általában költség szerepel. Ha egy tárgyi eszközhöz egy karbantartás alatt álló eszköz van társítva, akkor közvetlenül a tárgyi eszközről is megtekintheti a kapcsolódó költségeket.

A tárgyi eszközhöz társított karbantartási költségek megtekintéséhez kövesse ezeket a lépéseket.

1. Lépjen a **Tárgyi eszközök \> Tárgyi eszközök \> Tárgyi eszközök** menüpontba.
1. Válasszon egy eszközt.
1. A Művelet ablaktábla **Eszközkezelés** lapjának **Nézet** csoportjában válassza a **karbantartási költség** elemet.

    Megnyitja a **karbantartási költség** lapot, és megjeleníti a kapcsolódó költségeket.

### <a name="create-a-new-maintenance-asset-for-an-existing-fixed-asset"></a><a name="new-maintenance-from-fixed"></a>Új karbantartás alatt álló eszköz létrehozása meglévő tárgyi eszközhöz

Új karbantartás alatt álló eszköz meglévő tárgyi eszközhöz való létrehozásához kövesse ezeket a lépéseket.

1. Lépjen a **Tárgyi eszközök \> Tárgyi eszközök \> Tárgyi eszközök** menüpontba.
1. Válasszon egy eszközt.
1. A Művelet ablaktábla **Eszközkezelés** lapjának **Új** csoportjában válassza a **karbantartás alatt álló eszköz létrehozása** elemet. (Ha ez a beállítás nem érhető el, előfordulhat, hogy egy karbantartás alatt álló eszköz már hozzá van rendelve a kiválasztott tárgyi eszközhöz.)
1. FEjezze be az eszköz létrehozását az [Eszköz létrehozása](../objects/create-an-object.md) részben leírtaknak megfelelően.

### <a name="create-a-new-fixed-asset-and-add-a-new-maintenance-asset-for-it"></a>Új tárgyi eszköz létrehozása és hozzáadása új karbantartás alatt álló eszközhöz

Új tárgyi eszköz létrehozásához és új karbantartás alatt álló eszköz hozzáadásához kövesse ezeket a lépéseket.

1. Lépjen a **Tárgyi eszközök \> Tárgyi eszközök \> Tárgyi eszközök** menüpontba.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Fejezze be a tárgyi eszköz létrehozását az [Tárgyi eszköz létrehozása](../../../finance/fixed-assets/tasks/create-fixed-asset.md) részben leírtaknak megfelelően.
1. A Művelet ablaktábla **Eszközkezelés** lapjának **Új** csoportjában válassza a **karbantartás alatt álló eszköz létrehozása** elemet.
1. FEjezze be az eszköz létrehozását az [Eszköz létrehozása](../objects/create-an-object.md) részben leírtaknak megfelelően.

### <a name="remove-the-association-between-two-assets"></a>Két eszköz közötti társítás eltávolítása

Bizonyos esetekben előfordulhat, hogy egy karbantartás alatt álló eszköz társítását fel kell oldani egy tárgyi eszközről. Ha például egy tárgyi eszközből [új karbantartás alatt álló eszközt](#new-maintenance-from-fixed) szeretne létrehozni, előbb el kell távolítania a meglévő társításokat.

Karbantartás alatt álló eszköz és tárgyi eszköz közti meglévő társítás eltávolításához kövesse ezeket a lépéseket.

1. Lépjen az **Eszközkezelés \> Eszközök \> Összes eszköz** (vagy **Aktív eszközök**) lehetőséget.
1. Keresse meg és nyissa meg a tárgyi eszközt.
1. A **tárgyi eszköz** gyorslapon törölje a jelet az érték a **munkavégzési helyszín** mezőből.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]