---
title: Teljesítmény optimalizálása automatikus tisztítási feladatokkal
description: Ez a cikk azt mutatja be, hogyan lehet megoldani a Microsoft Dynamics 365 Human Resources bizonyos teljesítménnyel kapcsolatos problémáit a kötegeltfeladat-előzmények adattisztításával.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: a983fde8ba393ab25f2b330014e04a1379f0e4d0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418796"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a>Teljesítmény optimalizálása automatikus tisztítási feladatokkal

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

