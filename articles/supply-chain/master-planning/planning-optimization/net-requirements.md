---
title: Nettó követelmények és a igénykövetési információk a Tervezési optimalizálással
description: Ez a cikk a tervezési optimalizálás során kiszámított nettó követelményekről és az igényekre vonatkozó információkról nyújt tájékoztatást.
author: t-benebo
ms.date: 7/28/2021
ms.topic: article
ms.search.form: ReqTransOverview
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 259e5793a8dfac67793034d98ccb627fe1947bab
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8888528"
---
# <a name="net-requirements-and-pegging-information-with-planning-optimization"></a>Nettó követelmények és a igénykövetési információk a Tervezési optimalizálással

[!include [banner](../../includes/banner.md)]

Az alaptervezés futtatásakor a Tervezési optimalizálásban fontos, hogy jobban megértsük a kimenetelét, hogy a meglévő készlet hogyan fedezi az igényt, és hogy miért jött létre konkrét készlet. A **Nettó követelmények** lapon jobban megértheti az alaptervezés által előállított számított követelményeket.

A **Nettó követelmények** lap megjeleníti a termékhez a Tervezési optimalizálás során kiszámított nettó követelményeket. Megjeleníti az alaptervezés futtatása során alkalmazott fedezeti beállításokat, a követelményösszegek tranzakciótípus szerinti lebontását és igénykövetési adatokat.

## <a name="open-the-net-requirements-page"></a>A Nettó követelmények lap megnyitása

A **Nettó követelmények** lapot a következőképpen nyithatja meg:

- Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre. Jelöljön ki vagy nyisson meg egy terméket. Ezután a műveleti ablaktáblán a **Terv** lapján a **Követelmény** csoportban válassza a **Nettó követelmények** lehetőséget.
- Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra. Nyisson meg egy értékesítési rendelést. Ezután az **Értékesítésirendelés-sorok** gyorslapon, az eszköztáron válassza a **Termék és a készlet \> Nettó követelmények** lehetőséget.
- Ugorjon az **Alaptervezés \> Alaptervezés \> Tervezett rendelések** pontra. Válasszon ki vagy nyisson meg egy tervezett rendelést. Ezután a műveleti ablaktáblán a **Nézet** lapon a **Követelmények** csoportban válassza a **Követelményprofil** lehetőséget.

## <a name="use-the-net-requirements-page"></a>A Nettó követelmények lap használata

A **Nettó követelmények** lap felső és alsó szakaszokból áll. Az ezen a lapon található műveletpanel egy **Frissítés** gombot tartalmaz. Ha ezt a gombot megnyomja, megjelenik egy parancsmenü.

### <a name="select-a-master-plan-to-view"></a>Válassza ki a megtekinteni kívánt alaptervet

A termék nettó követelményeinek áttekintése előtt győződjön meg róla, hogy a megfelelő alaptervet válassza ki a lap tetején lévő **Terv** mezőben.

### <a name="upper-section"></a>Felső szakasz

A lap felső része a következő lapokat tartalmazza:

- **Áttekintés** – A termékdimenziók cikk-követelményeinek megtekintése.
- **Cikkfedezet** – a követelmények számítása során használt fedezeti beállítások megtekintése.
- **Összegzés** – A követelményeket összegeinek tranzakciótípus szerinti lebontásának megjelenítése.
- **Időszak** – Az időszaksablonban meghatározott minden időszakhoz megtekinthetők a bevételezések, a problémák és az előre jelzett elérhető készlet. Grafikusan is megtekintheti az előre jelzett elérhető készletet.

### <a name="lower-section"></a>Alsó rész

A lap alsó része a következő lapokat tartalmazza:

- **Áttekintés** – Az alaptervezés futtatása során kiszámított termékkövetelmények listájának, valamint a követelményeknek megfelelő kiadási és bevételezési tranzakcióknak a megjelenítése. Alapértelmezés szerint a lista követelménydátum szerint van rendezve. Amikor kiválaszt egy követelményt, az alsó rész **Igénykövetés** gyorslapja megjeleníti a követelmény forrását vagy a követelményt teljesítő tranzakciókat.
- **Általános** – Részletes információk megjelenítése a kijelölt követelményről.
- **Művelet** – A követelményeknek megfelelő műveletküzenetek megtekintése.

### <a name="the-action-pane"></a>A Műveleti ablaktábla

Az alábbi parancsok érhetők el a Műveleti panelen:

- **Frisstés \> Alaptervezés** – Az alaptervezés futtatása közvetlenül a **Nettó követelmények** lapról.
- **Frisstés \> Előrejelzési tervezés** – Az előrejelzési tervezés futtatása közvetlenül a **Nettó követelmények** lapról. A Tervezési optimalizálás még nem támogatja ezt a műveletet.
- **Frissítés \> Folytonosság ütemezése** – A folytonosság ütemezésének futtatása közvetlenül a **Nettó követelmények** oldalról. A Tervezési optimalizálás még nem támogatja ezt a műveletet.

## <a name="example-scenario"></a>Példaforgatókönyv

Ez a példa azt mutatja be, hogyan jelennek meg az igénykövetési információk a **Nettó követelmények** lapon.

### <a name="prerequisites"></a>Előfeltételek

A forgatókönyv elvégzése előtt a következő előfeltételeket kell előkészíteni:

1. Olyan rendszeren kell dolgoznia, ahol elérhetők a szabványos mintaadatok, és a jogi személyt *USMF*-re kell állítani.
2. Ez a példa az *1000*-es terméket használja, amely része az USMF-mintaadatoknak. Győződjön meg róla, hogy a termék elérhető és a következő módon van beállítva:

    - **Alapértelmezett rendelési típus:** *Beszerzési rendelés*
    - **Aktuális készlet:** *10,00*

3. Hozzon létre egy értékesítési rendelést *25,00* mennyiséggel az *1000*-es termékből. Az aktuális készletet tároló tárolási dimenziókat használja.
4. A *DynPlan* alapterv alaptervezését futtassa.

### <a name="review-the-calculated-requirements"></a>Tekintse át a számított követelményeket

Ezután megnyitja az **1000**-es termék *Nettó követelmények lapját*, és áttekinti, hogy a számított követelmények hogyan felelnek meg egymásnak.

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Válassza ki azt a terméket, amelynél a **Cikkszám** értéke *1000*.
1. A műveleti ablaktáblán a **Terv** lapján a **Követelmény** csoportban válassza a **Nettó követelmények** lehetőséget.
1. A **Nettó követelmények** lapon állítsa a **Terv** mezőt *DynPlan* értékre.
1. A lap alsó részén található **Áttekintés** lapon ellenőrizze, hogy a következő követelmények a rács soraiként vannak-e felsorolva.

    | Hivatkozás | Követelménymennyiség | Halmozott |
    |---|---|---|
    | Aktuális készlet | 10,00 | 10,00 |
    | Terv. besz. rendelések | 15.00 | 25.00 |
    | Értékesítési rendelés | -25,00 | (Üres) |

    > [!NOTE]
    > A **Követelmény mennyisége** mező a szükséglet által megkövetelt összmennyiséget (ha az érték negatív), vagy a biztosított mennyiséget (pozitív érték esetén) jelenti. A **Halmozott** mező a kiválasztott időszakban felhalmozott összes bevételezési és kiadási mennyiséget jelöli.

1. Válassza ki az *Aktuális készlet* követelménysort, majd az **Igénykövetés** gyorslapon ellenőrizze az ehhez a készlethez tartozó követelményeket. A következő sornak itt kell megjelennie.

    | Hivatkozás | Követelménymennyiség | Fedezett mennyiség |
    |---|---|---|
    | Értékesítési rendelés | -25,00 | -10,00 |

    A meglévő aktuális készlet részben lefedi az értékesítési rendelésből származó igényt.

    ![Az aktuális készletre vonatkozó igénykövetési adatok](media/pegging-on-hand.png "Az aktuális készletre vonatkozó igénykövetési adatok")

1. Válassza ki a *Tervezett beszerzési rendelések* követelménysort, majd az **Igénykövetés** gyorslapon ellenőrizze az ehhez a készlethez tartozó követelményeket. A következő sornak itt kell megjelennie.

    | Hivatkozás | Követelménymennyiség | Fedezett mennyiség |
    |---|---|---|
    | Értékesítési rendelés | -25,00 | -15,00 |

    Mivel az értékesítési rendelést már részben fedezték, a rendszer tervezett beszerzési rendelést hoz létre a fennmaradó fedezetlen mennyiségre.

    ![A tervezett beszerzési rendelésre vonatkozó igénykövetési adatok](media/pegging-planned-purchase-order.png "A tervezett beszerzési rendelésre vonatkozó igénykövetési adatok")

1. Válassza ki az *Értékesítési rendelés* követelménysort, majd az **Igénykövetés** gyorslapon ellenőrizze az igényt fedező követelményeket. A következő soroknak itt kell megjelennie.

    | Hivatkozás | Követelménymennyiség | Fedezett mennyiség |
    |---|---|---|
    | Aktuális készlet | 10,00 | 10,00 |
    | Terv. besz. rendelések | 15.00 | 15.00 |

    ![Az értékesítési rendelésre vonatkozó igénykövetési adatok](media/pegging-planned-purchase-order.png "Az értékesítési rendelésre vonatkozó igénykövetési adatok")

> [!NOTE]
> Mivel a Tervezési optimalizálás még nem támogat bizonyos funkciókat, a *Biztonsági készlet* és a *Lejárt köteg* követelménytípusok nem szerepelnek a **Nettó követelmények** lapon. További tájékoztatás: [Tervezésoptimalizálás illeszkedési elemzése](planning-optimization-fit-analysis.md).
>
> A beépített alaptervezési motor használata esetén a kötegvezérelt termékek támogatottak. Kötegvezérelt termékek esetén a lejárt aktuális készlet megjelenik a **Nettó követelmények** lapon, de nincs hozzájuk igénykövetés. Az ilyen típusú lejárt készletet tartalmazó sorok *Lejárt köteg* követelménysorokként jelennek meg a **Nettó követelmények** lapon.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
