---
title: Teljesítmény optimalizálása a kötegelt feladatok munkaidő utáni ütemezésével
description: Ez a témakör azt mutatja be, hogyan lehet megoldani a Microsoft Dynamics 365 Human Resources bizonyos teljesítményproblémáit a hosszan futó kötegelt feladatok munkaidő utánra ütemezésével.
author: andreabichsel
ms.date: 06/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: d2369b3209901eb2d60232a47d89284779199e1c98a56142758353d65a1faaf7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6766871"
---
# <a name="optimize-performance-by-scheduling-batch-jobs-after-hours"></a>Teljesítmény optimalizálása a kötegelt feladatok munkaidő utáni ütemezésével

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="issue"></a>Kiadás

A Microsoft Dynamics 365 Human Resources esetében teljesítménnyel kapcsolatos problémák jelentkezhetnek, ha a szokásos munkaidő alatt hosszú futási idejű feladatok futnak.

## <a name="resolution"></a>Felbontás

A következő kötegelt feladatokat munkaidőn kívülre ütemezze. Ajánljuk a gyakran futó kötegelt feladatok gyakoriságának áttekintését is. Ha lehetséges, csökkentse a kötegelt feladat ismétlődését. Sok esetben az alapértelmezett gyakoriság elegendő.

A következő kötegelt feladatoknak éjszaka vagy munkaidő után kell futniuk. Ellenőrizze az ismétlődő kötegelt feladatok időzónáját. Előfordulhat, hogy egyes kötegelt feladatok a Pacific standard Time (PST) időzónát használják.

| Kötegelt feladat | Alapértelmezett előfordulás |
| --- | --- |
| Kötegelt feladatelőzmények tisztítása | 1 alkalommal havonta |
| Az exportálás előkészítési adatainak kiürítése | 1 alkalommal naponta |
| Common Data Service kihagyott kérelem szinkronizálásának integrációja | 1 alkalommal naponta |
| Adatbázis-tömörítési rendszerfeladat, amelynek a munkaidőn kívüli rendszeres futtatására van szükség. | 1 alkalommal naponta |
| Adatbázisindex-újraépítési rendszerfeladat, amelynek a munkaidőn kívüli rendszeres futtatására van szükség. | 1 alkalommal naponta |

1. A Human Resources alkalmazásban válassza a **Rendszerfelügyelet** elemet.

2. A **Keresés** sávon keressen rá a fenti kötegelt feladatok egyikére.

3. Válassza a **Futtatás a háttérben** lehetőséget, majd az **Ismétlődés** elemet.

   ![Ismétlődés beállítása.](media/talent-batch-history-cleanup-recurrence.png)

4. Az **Ismétlődés meghatározása** részben állítsa a **Kezdő dátum** és **Kezdő időpont** értékét úgy, hogy munkaidőn kívül vagy hétvégén legyen. Válassza a **Nincs záró dátum** lehetőséget. 

   ![Az ismétlődés kezdő dátumának és időpontjának meghatározása.](media/talent-batch-history-cleanup-define-recurrence.png)

5. Válassza ki az **OK** lehetőséget.

6. Szükség szerint módosítsa a **Futtatás a háttérben** rész többi paraméterét, majd válassza az **OK** lehetőséget.

## <a name="additional-resources"></a>További erőforrások

[Teljesítmény optimalizálása automatikus tisztítási feladatokkal](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]