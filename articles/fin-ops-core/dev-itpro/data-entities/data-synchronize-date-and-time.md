---
title: Dátum és idő szinkronizálása az importálási feladatokban
description: Az importálási feladatokban használja az UTC időzónákat, hogy elkerülje az időzóna-átalakításokkal kapcsolatos problémákat.
author: peakerbl
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c76eadc5839785ba1624ee3894ef1d0872369aa9
ms.sourcegitcommit: 7aa7d756e1e98a53da62e03c608a9597ef9893ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/20/2021
ms.locfileid: "7403841"
---
# <a name="synchronize-date-and-time-in-import-jobs"></a>Dátum és idő szinkronizálása az importálási feladatokban

[!include [banner](../includes/banner.md)]

Fontos, hogy az importált feladat időzónáját UTC-formátumra (koordinált világidő) állítsa be. Az importált adatokban nem várt dátumok és időpontok is előfordulhatnak, ha más beállítást használ. A helyes beállítás nélkül az importálási folyamat az UTC-dátumot helyi formátumra alakítja, majd a rendszerbeállítások újra konvertálják.

A két konverzió hatására megváltoznak a dátumok az alkalmazások között. A kettős átalakítás például azzal jár, hogy egy alkalmazott kezdő dátuma eltérő lesz a helyi időzónákban lévő különbségek miatt a Dynamics 365 Human Resources és a Dynamics 365 Finance megoldásban. Az importálási feladat UTC-formátumra való beállításával ez a probléma megoldódik.

1. Válassza a Dynamics 365 Finance and Operations megoldásban az **Adatkezelés** lehetőséget.

2. Válassza a **Projektek importálása** lehetőséget, majd a projektet.

3. A **Forrásdátum formátumban** válassza a **CSV-Unicode** kódot.

   [![Forrásdátum formátumának módosítása UTC-re.](./media/data-source-date-format.png)](./media/data-source-date-format.png)

4. Az **Időzónaidőzóna** beállítását módosítsa az **Egyezményes világidő** lehetőségre, és a **Nyelv** legyen **En-US**.




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
