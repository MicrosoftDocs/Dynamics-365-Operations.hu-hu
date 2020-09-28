---
title: Projekterőforrás-ütemezés teljesítménye
description: Ez a témakör azt mutatja be, hogyan javítható az erőforrás-ütemezés teljesítménye nagy számú projekt esetében.
author: Yowelle
manager: AnnBe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 10.0.14
ms.search.validFrom: 2020-09-01
ms.openlocfilehash: 988fc83230f08a6534caa7c37784757d73c1cc12
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760569"
---
# <a name="project-resource-scheduling-performance"></a>Projekterőforrás-ütemezés teljesítménye

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]


Az erőforrás-ütemezéssel kapcsolatos teljesítmény-problémák akkor merülhetnek fel, ha a projektek száma több ezer. Az erőforrás-ütemezés hatékonyságának javítása érdekében elérhető egy szolgáltatás, amely lehetővé teszi a felhasználók számára, hogy csökkentsék az erőforrás-elérhetőségi képernyő indításához szükséges időt. Ez a művelet eltávolítja az erőforrás-kapacitások összesítő szinkronizálási folyamatát, és a **ResProjectResource** táblát használja az erőforrás-keresés felgyorsítására. Ne felejtse el, hogy a **ResRollup** tábla már nem lesz használva.

> [!IMPORTANT]
> Ha függőség van az erőforrás-kapacitás összesítő szinkronizálási folyamatán vagy a **ResProjectResource** táblán, ne használja ezt a funkciót.

## <a name="enable-resource-scheduling-performance-enhancement"></a>Az erőforrás-ütemezés teljesítményjavításának engedélyezése
Az erőforrás-ütemezés hatékonysága növelésének engedélyezéséhez hajtsa végre a következő lépéseket.

1. Nyissa meg a **Funkciókezelés** > **Összes** elemet, majd a szolgáltatások listájában keresse meg a **Az erőforrás-ütemezés teljesítményjavítása funkció engedélyezése** lehetőséget.
2. Válassza az **Engedélyezés most** lehetőséget.

> [!NOTE]
> Ha nem találja a funkciót a listán, válassza a **Frissítések keresése** lehetőséget a lista frissítéséhez.

3. Frissítse a böngészőprogramot, majd nyissa meg a **Projektmenedzsment és a könyvelés** > **Időszakos** > **Projekterőforrások** > **Erőforrásnaptárak kapacitásának szinkronizálása az összes vállalat között** lehetőséget.
4. Az előző adatok eltávolításához állítsa a **Meglévő kapacitásrekordok eltávolítása** elemet **Igen** értékre. Ha növekményes adatokat szeretne generálni, állítsa **Nem** értékre.
5. Az **időszak kódja** mezőben válassza ki azt az időszakot, amelyben az adatokat létrehozni kell. Ha kiválaszt egy időszakot, akkor nem kell megadni a kezdő és a záró dátumot.
6. Ha üresen hagyja az **Időszak kódja** mezőt, válassza ki a kezdési és befejezési dátumokat az adatok generálásához.
7. Válassza ki az **OK** lehetőséget.

 > [!NOTE]
 > Ennek hatására a program a környezete összes vállalata között megosztja az általános adatokat a **ResCalendarCapacity** táblába, így a kötegelt feladatot csak egy jogi személyben kell futtatni. Az ebben a kötegelt feladatban szereplő adatok szükségesek az erőforráskapacitás a társított naptáron keresztül történő számításához.

8. Nyissa meg a **Projektvezetés és könyvelés** > **Időszakos** > **Projekterőforrások** > **Projekterőforrások kitöltése az összes vállalat között** menüt, és válassza az **OK** lehetőséget. Ez a **ResProjectResource**, **ResCalendarDateTimeRange** és **ResEffectiveDateTimeRange** táblák általános adatainak adatfrissítési parancsfájlja. A **PSAPRojSchedRole.RootActivity** mező értékeit is frissíti a program. Ha ez nem fut, akkor figyelmeztetés jelenik meg, amikor megpróbálja végrehajtani az erőforrás-ütemezési műveleteket.
 
## <a name="turn-off-resource-scheduling-performance-enhancement"></a>Az erőforrás-ütemezés teljesítményjavításának kikapcsolása

1. Nyissa meg a **Funkciókezelés** > **Összes** elemet, majd keresse meg a **Az erőforrás-ütemezés teljesítményjavítása funkció engedélyezése** lehetőséget.
2. Válassza ki a funkciót, majd válassza a **Letiltás** gombot.
3. Frissítse a böngészőt.
4. Válassza a **Projektvezetés és könyvelés** > **Időszakos** > **Kapacitásszinkronizálás** > **Erőforrás kapacitás-összesítéseinek szinkronizálása** lehetőségeket.
5. A **Kapacitás összesítő szinkronizálása** lapon állítsa be a **Meglévő kapacitás-rekordok eltávolítása** elemet **Igen** értékre a korábbi adatok eltávolításához. Ha növekményes adatokat szeretne generálni, állítsa **Nem** értékre.
6. Az **időszak kódja** mezőben válassza ki azt az időszakot, amelyben az adatokat létrehozni kell. Ha kiválaszt egy időszakot, akkor nem kell megadni a kezdő és a záró dátumot.
7. Ha üresen hagyja az **Időszak kódja** mezőt, válassza ki a kezdési és befejezési dátumokat az adatok generálásához.
8. Válassza ki az **OK** lehetőséget.

> [!NOTE]
> Ennek hatására a program a környezete összes vállalata között megosztja az általános adatokat a **ResRollup** táblába, így a kötegelt feladatot csak egy jogi személyben kell futtatni. Ez a kötegelt feladat minden **Erőforrás elérhetősége** nézet esetében szükséges. Ha ezt a kötegelt feladatot nem futtatja, akkor a program a **ResRollup** adatait a menet közben hozza létre, amely időt vehet igénybe.
