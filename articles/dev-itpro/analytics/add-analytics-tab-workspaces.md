---
title: "Analitika hozzáadása munkaterületekhez Power BI Embedded használatával"
description: "Ez a témakör bemutatja, hogy miként ágyazható be egy Power BI jelentés egy munkaterület Elemzés lapjára."
author: tjvass
manager: AnnBe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application user, IT Pro
ms.reviewer: robinr
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 821d8927211d7ac3e479848c7e7bef9f650d4340
ms.openlocfilehash: 3f6b83166ba942e40e5e1f7c0ef9df40a44bfbc5
ms.contentlocale: hu-hu
ms.lasthandoff: 08/13/2018

---

# <a name="add-analytics-to-workspaces-by-using-power-bi-embedded"></a>Analitika hozzáadása munkaterületekhez Power BI Embedded használatával

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Ez a funkció a Dynamics 365 for Finance and Operationsben támogatott (7.2-es vagy újabb verzió).

## <a name="introduction"></a>Bevezetés
Ez a témakör bemutatja, hogy miként ágyazható be egy Microsoft Power BI jelentés egy munkaterület **Elemzés** lapjára. Például az itt megadott ajánlott kiterjed a **foglalási kezelési** a flottában-kezelés alkalmazást az analitikus munkaterület beágyazása a munkaterület egy **analitika** lapon.

## <a name="prerequisites"></a>Előfeltételek
+ A fejlesztői környezet 8-as vagy újabb Platform frissítés futó való hozzáférést.
+ Analitikai bizonylat (.pbix fájl), amely Microsoft kiemelt az üzleti Intelligencia asztal használata lett létrehozva, és, amelynek van az entitás üzletadatbázishoz származó adatok modellről.

## <a name="overview"></a>Áttekintés
Alkalmazás meglévő munkaterülethez kiterjesztése, vagy saját új munkaterület bevezetésének, beágyazott elemző nézetek segítségével az üzleti adatokban osztályon és interaktív nézetei szállítani. A folyamat hozzáadása egy analitikai munkaterület lap négy lépés tartozik.

1. Dynamics 365 erőforrásként .pbix fájlt hozzáadni.
2. Határozza meg az analitikus munkaterület lapon.
3. A munkaterület lap .pbix erőforrás beágyazása.
4. Választható: A nézet testreszabásához bővítmények.

> [!NOTE]
> Elemzési jelentések létrehozásával kapcsolatos további tudnivalókat lásd: [Power az üzleti Intelligencia asztali – első lépések](https://powerbi.microsoft.com/en-us/documentation/powerbi-desktop-getting-started/). Ez a lap elévült vonatkozó információkat, melyek segítséget nyújtanak arra az elemzési jelentés megoldások létrehozása esetén.

## <a name="add-a-pbix-file-as-a-resource"></a>Erőforrásként .pbix fájlt kell hozzáadni
Mielőtt elkezdené, létre kell hoznia vagy a kiemelt Üzletiintelligencia-jelentés beágyazza a munkaterület beszerzése. Elemzési jelentések létrehozásával kapcsolatos további tudnivalókat lásd: [Power az üzleti Intelligencia asztali – első lépések](https://powerbi.microsoft.com/en-us/documentation/powerbi-desktop-getting-started/).

Adja meg a Visual Studio projekt műtermék .pbix fájl lépésekkel.

1. Hozzon létre egy új projektet a megfelelő modellben.
2. A Solution Explorer alkalmazásban válassza ki a projektet, kattintson rá jobb gombbal, majd válassza ki a **Hozzáadás** \> **Új elem** pontot.
3. Az a **új elem hozzáadása** párbeszédpanel **műveletek műtermékek**, jelölje be a **erőforrás** sablon.
4. Írjon be egy nevet, amely veszi figyelembe a jelentés X ++ metaadatokban hivatkozik, és kattintson a **hozzáadása**.

    ![Új elem párbeszédpanelen hozzáadása](media/analytical-workspace-add.png)

5. Keresse meg a .pbix fájlt, amely tartalmazza az elemzési jelentés, és kattintson a **nyitott**.

    ![Válassza ki az erőforrás párbeszédpanel jelenik meg](media/analytical-workspace-select-resource.png)

Dynamics 365 erőforrásként felvett .pbix fájl, hogy a jelentések beágyazása munkaterületek, és közvetlen kapcsolatokat menüelemek vehet fel.

## <a name="add-a-tab-control-to-an-application-workspace"></a>Az alkalmazás munkaterületének lap vezérlő hozzáadása
Ebben a példában ajánlott kiterjed a **foglalási kezelése** munkaterület hozzáadásával flottában felügyeleti modellben a **analitika** meghatározásának lap a **FMClerkWorkspace** képernyőn.

A következő ábra azt mutatja, hogy mi a **FMClerkWorkspace** képernyőn dolgozunk a Microsoft Visual Studio-tervezőben.

![A képernyőn FMClerkWorkspace változtatások előtt](media/analytical-workspace-definition-before.png)

Kövesse az alábbi lépéseket képernyő definíció kiterjeszteni az **foglalási kezelési** munkaterület.

1. Nyissa meg a képernyőtervezőben tervezési definíciójának bővítésére.
2. A tervezési meghatározásában, válassza ki a felső elem címkéje **tervezési | Minta: Munkaterület üzemi**.
3. Kattintson a jobb gombbal, majd a **Új** \> **Lap** nevű új vezérlő hozzáadása **FormTabControl1**.
4. A képernyőtervezőben válassza: **FormTabControl1**.
5. Kattintson a jobb gombbal, majd a **új lap** hozzáadása egy új lap.
6. Nevezze át a lap következhet, mint például **munkaterület**.
7. A képernyőtervezőben válassza: **FormTabControl1**.
8. Válasszon egy feladatot, kattintson rá a jobb gombbal, majd válassza az **Új lap oldal** menüpontot.
9. Nevezze át a lap következhet, mint például **Elemzés**.
10. Az űrlap-tervezőben, jelölje be a **analitika (lapon)**.
11. A **Felirat**  tulajdonságot **Elemzés** értékre kell állítani.
12. Kattintson a jobb gombbal a vezérlőelem, és adja meg **Új** \> **Csoport** új űrlapvezérlő csoport hozzáadása.
13. Nevezze át a lap következhet, mint például **powerBIReportGroup**.
14. Az űrlap-tervezőben, jelölje be a **PanoramaBody (lap)**, és húzza a vezérlő a **munkaterület** lapon.
15. A tervezési meghatározásában, válassza ki a felső elem címkéje **tervezési |} Minta: Munkaterület üzemi**.
16. Válasszon egy feladatot, kattintson rá a jobb gombbal, majd válassza a **Minta eltávolítása** menüpontot.
17. Kattintson ismét jobb gombbal, és adja meg **Hozzáadás minta** \> **Munkaterület többlapos**.
18. A build ellenőrizheti a módosítások végrehajtása.

A következő ábra mutatja, hogy a terv néz módosítások alkalmazása után.

![Módosítások után FMClerkWorkspace](media/analytical-workspace-definition-after.png)

Most, hogy a munkaterület jelentés beágyazása használt űrlap-vezérlőelemek felvett tulajdonságaként méretét, hogy így alkalmazkodik az elrendezés kell megadni. Alapértelmezés szerint mind **szűrők ablak** lap és a **lap** oldal a jelentésen látható lesz. Ezeket a vezérlőelemeket a jelentés a cél fogyasztó megfelelő láthatóságát azonban módosítható.

> [!NOTE]
> Beágyazott munkaterületek esetén javasoljuk, hogy a bővítmények használatával egyaránt rejtse el a **Szűrő ablaktábla** és a **Lap** oldalakat a konzisztencia érdekében.

Ekkor befejezte a jelentkezési lap definíciójának kiterjesztését. Testreszabott bővítmények segítségével a további tudnivalókat lásd: [Testreszabás: Overlayering és bővítéseinek](../extensibility/customization-overlayering-extensions.md).

## <a name="add-x-business-logic-to-embed-a-viewer-control"></a>X ++ üzleti logikát a jelentésmegjelenítő vezérlőben beágyazása hozzáadása
Kövesse az alábbi lépéseket, amely inicializálja a jelentésmegjelenítő vezérlőben beágyazott üzleti logikát szeretne adni a **foglalási kezelési** munkaterület.

1. Nyissa meg a **FMClerkWorkspace** képernyőtervezőt tervezési definíciójának bővítésére.
2. Nyomja le az F7 eléréséhez a kód megadása alapjául szolgáló kódot.
3. Adja hozzá a következő X++ kódot.

    ```
    [Form] 
    public class FMClerkWorkspace extends FormRun
    {
        private boolean initReportControl = true;
        protected void initAnalyticalReport()
        {
            if (!initReportControl)
            {
                return;
            }
            // Note: secure entry point into the Workspace's Analytics report
            if (Global::hasMenuItemAccess(menuItemDisplayStr(FMClerkWorkspace), MenuItemType::Display))
            {
                // initialize the PBI report control using shared helper
                PBIReportHelper::initializeReportControl('FMPBIWorkspaces', powerBIReportGroup);
            }
            initReportControl = false;
        }
        /// <summary>
        /// Initializes the form.
        /// </summary>
        public void init()
        {
            super();
            this.initAnalyticalReport();
        }
    }
    ```

4. A build ellenőrizheti a módosítások végrehajtása.

Üzleti logika inicializálja a jelentésmegjelenítő vezérlőben beágyazott felvételét a feladat már befejeződött. A következő ábra mutatja, hogy a munkaterület néz módosítások alkalmazása után.

![A munkaterület ágyazott jelentés](media/analytical-workspace-final.png)

> [!NOTE]
> A meglévő működési nézet alatt az oldalcím a munkaterület lapok használatával hozzáfér.

## <a name="reference"></a>Hivatkozás

### <a name="pbireporthelperinitializereportcontrol-method"></a>PBIReportHelper.initializeReportControl mód
Ez a szakasz a segítő osztály, amelynek használatával az üzleti Intelligencia teljesítmény jelentés (.pbix erőforrás) beágyazása csoport űrlapvezérlő kapcsolatban tartalmaz tájékoztatást.

#### <a name="syntax"></a>Szintaxis
```
public static void initializeReportControl(
    str                 _resourceName,
    FormGroupControl    _formGroupControl,
    str                 _defaultPageName = '',
    boolean             _showFilterPane = false,
    boolean             _showNavPane = false,
    List                _defaultFilters = new List(Types::Class))
```

#### <a name="parameters"></a>Paraméterek

| Név             | Leírás                                                                                                  |
|------------------|--------------------------------------------------------------------------------------------------------------|
| resourceName     | A .pbix erőforrás neve                                                                              |
| formGroupControl | A képernyőn az üzleti Intelligencia teljesítmény jelentés vezérlőelem alkalmazandó csoportvezérlőnek.                                              |
| defaultPageName  | Alapértelmezett oldalnév.                                                                                       |
| showFilterPane   | Logikai érték, amely azt jelzi, hogy megjelenjen (**true**) vagy rejtve maradjon (**false**) a szűrés ablaktáblája.     |
| showNavPane      | Logikai érték, amely azt jelzi, hogy megjelenjen (**true**) vagy rejtve maradjon (**false**) a navigációs ablaktábla. |
| defaultFilters   | A Power BI jelentés alapértelmezett szűrői.                                                                 |

