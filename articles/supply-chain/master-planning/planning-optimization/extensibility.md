---
title: Tervezési optimalizálás bővíthetősége
description: Ez a témakör a tervezési optimalizálásban támogatott, extensibility eseteket ismerteti.
author: t-benebo
ms.date: 08/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-07-07
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 7d649110959e6bcfdaeb32dd53c55dbc446ed1be
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857544"
---
# <a name="planning-optimization-extensibility"></a>Tervezési optimalizálás bővíthetősége

[!include [banner](../../includes/banner.md)]

Ez a témakör az alaptervezéssel kapcsolatos, a tervezési optimalizálásban támogatott, extenzitási eseteket írja le. Ezek a felhőalapú keresési funkciók a Microsoft Dynamics 365 Supply Chain Management 10.0.13 verziójától érhetők el.

## <a name="custom-processing-when-master-planning-is-completed"></a>Egyéni feldolgozás az alaptervezés befejezésekor

A tervezés optimalizálása során a leggyakoribb bővítési forgatókönyv, hogy az egyéni feldolgozás a terv frissítése után történik. Hozzáadhat például egy oszlopot a tervezett rendelések táblához (`ReqPO`), vagy statisztikai adatokat szeretne levezetni a generált tervből. Az ilyen eseteket lehetővé tevő fő bővítési pont az `MpsMasterPlanningEvents` osztály `jobCompletedSuccessfully` metódusa.

```X++
public static void jobCompletedSuccessfully(MpsMasterPlanningJobCompletedSuccessfullyEventArgs _args)
```

Példa arra a bővítésre, amely egyéni `CstmOrderPriority` mezőt állít be a tervezett rendeléshez.

```X++
[ExtensionOf(classStr(MpsMasterPlanningEvents))]
public static final class MpsMasterPlanningEvents_Cstm_Extension
{
    public static void jobCompletedSuccessfully(MpsMasterPlanningJobCompletedSuccessfullyEventArgs _args)
    {
        ttsbegin;

        var affectedPlannedOrdersQuery = _args.parmPostProcessingQueryBuilder().buildAffectedPlannedOrdersQuery();
        var affectedPlannedOrdersQueryRun = new QueryRun(affectedPlannedOrdersQuery);

        while (affectedPlannedOrdersQueryRun.next())
        {
            ReqPO reqPO = affectedPlannedOrdersQueryRun.get(tableNum(ReqPO));
            reqPO.selectForUpdate(true);
            reqPO.CstmOrderPriority = reqPO.ReqDate - systemDateGet() < 7 ? CstmPlannedOrderPriority::Urgent : CstmPlannedOrderPriority::Regular;
            reqPO.doUpdate();
        }

        ttscommit;

        next jobCompletedSuccessfully(_args);
    }

}
```

Egyéni logika hozzáadásakor vegye figyelembe a következő megszorításokat és gyakorlati tanácsokat:

- A `jobCompletedSuccessfully` metódus a tranzakció hatókörén kívül van meghívva. Ennek megfelelően a terv már látható lesz a felhasználó számára, amikor az egyéni logika elkezd futni. Ha a testreszabás további mezőket állít be a tervezett rendeléseken, fontos, hogy a felhasználók tudják, ezeknek a mezőknek az értékei végül konzisztensek lesznek (más szóval előfordulhat, hogy a tervezési feladat befejezése után azonnal elavultak).
- A `jobCompletedSuccessfully` metódus meghívása esetén egy másik alaptervezési feladat is elkezdődhet. Az új feladat befolyásolhatja a teljes tervet vagy a terv egy részét. Az új feladat lehet, hogy frissíti vagy törli azokat a tervezett rendeléseket vagy követelménytranzakciókat, amelyek a `jobCompletedSuccessfully` metódussal kezelt tervezési feladat részeként létrejöttek vagy módosultak. A frissítési ütközések kivételeit kezelni kell, amikor ez az esemény ki van bővítve.
- A módszer bővítése esetén ne használja az egyetlen tranzakció hatókörét. Egyetlen alaptervezési futtatás több millió követelménytranzakciót és többszázezer tervezett rendelést hoz létre. Ha ezeket a tranzakciókat és tervezett rendeléseket egyetlen tranzakció hatókörében dolgozza fel, sok SQL-zárolás történik, és blokkolja a többi tervezési folyamatot. Ezenkívül ha a tranzakciót hosszú ideig tárolja a rendszer, az SQL-adatbázisban létrejönnek "szellemrekordok". A szellemrekordok negatívan befolyásolják a rendszer minden folyamatát.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]