---
title: Teljesítmény optimalizálása automatikus tisztítási feladatokkal
description: Ez a cikk azt mutatja be, hogyan lehet megoldani a Microsoft Dynamics 365 Human Resources bizonyos teljesítménnyel kapcsolatos problémáit a kötegeltfeladat-előzmények adattisztításával.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 6a9e94e282aa8f101b42c1378ef21c6c1fe0477e
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053491"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a>Teljesítmény optimalizálása automatikus tisztítási feladatokkal

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Kibocsátás**

A Microsoft Dynamics 365 Human Resources teljesítményproblémái akkor tapasztalhatók, ha a kötelegelt feladatok előzményei túl nagy méretűre növekednek.

**Ok**

A gyakran futó kötegelt feladatok nem fenntartható növekedést eredményezhetnek a kötegelt feladatok előzményeiben. Ennek hatására a teljesítménnyel kapcsolatos problémák merülhetnek fel. 

**Feloldás**

Ütemezzen automatikus feladatot a kötegelt feladat előzményeinek tisztítására. Javasoljuk, hogy a feladatot hetente futtassák, de előfordulhat, hogy a környezettől függően gyakrabban vagy ritkábban kell futtatnia a tisztítást. A következő eljárás a javasolt beállításokat tartalmazza, de ezeket az igényeknek megfelelően módosíthatja.

1. A Human Resources alkalmazásban válassza a **Rendszerfelügyelet** elemet.

2. A **Keresés** sávon adja meg: **Kötegelt feladat előzményeinek tisztítása**.

   ![Kötegelt feladat előzményeinek tisztítása – keresés](media/talent-batch-history-cleanup-search-bar.png)

3. Az **Előzmények időkorlátja (nap)** mezőben adja meg: **30**.

   ![Előzmények időkorlátjának 30 napra állítása](media/talent-batch-history-cleanup-history-limit.png)

4. Válassza a **Futtatás a háttérben** lehetőséget, majd az **Ismétlődés** elemet.

   ![Ismétlődés beállítása](media/talent-batch-history-cleanup-recurrence.png)

5. Az **Ismétlődés meghatározása** részben állítsa a **Kezdő dátum** és **Kezdő időpont** értékét úgy, hogy munkaidőn kívül vagy hétvégén legyen, majd válassza a **NINCS ZÁRÓ DÁTUM** lehetőséget. 

   ![Az ismétlődés kezdő dátumának és időpontjának meghatározása](media/talent-batch-history-cleanup-define-recurrence.png)

6. Az **ISMÉTLŐDÉSI MINTA** részben válassza a **Napok** elemet és állítsa az **ISMÉTLÉS MEGHATÁROZOTT IDŐKÖZÖNKÉNT** lehetőséget **7** értékre.

   ![Állítsa a tisztítást heti ismétlődésre](media/talent-batch-history-cleanup-recurrence-pattern.png)

7. Válassza ki az **OK** lehetőséget.

8. Szükség szerint módosítsa a **Futtatás a háttérben** rész többi paraméterét, majd válassza az **OK** lehetőséget.



[!INCLUDE[footer-include](../includes/footer-banner.md)]