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
ms.openlocfilehash: b8faa7b73349c48d3a02b685546b47c4969c6027
ms.sourcegitcommit: 3289478a05040910f356baf1995ce0523d347368
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2022
ms.locfileid: "9109432"
---
# <a name="synchronize-date-and-time-in-import-jobs"></a>Dátum és idő szinkronizálása az importálási feladatokban

[!include [banner](../includes/banner.md)]

Fontos, hogy az importált feladat időzónáját UTC-formátumra (koordinált világidő) állítsa be. Az importált adatokban nem várt dátumok és időpontok is előfordulhatnak, ha más beállítást használ. A helyes beállítás nélkül az importálási folyamat az UTC-dátumot helyi formátumra alakítja, majd a rendszerbeállítások újra konvertálják.

A két konverzió hatására megváltoznak a dátumok az alkalmazások között. A kettős átalakítás Dynamics 365 Human Resources például a helyi időzónák eltérése miatt az alkalmazottak kezdő dátuma eltérő lehet a dynamics 365 Pénzügy és a Dynamics 365 Pénzügy között. Az importálási feladat UTC-formátumra való beállításával ez a probléma megoldódik.

1. A Dynamics 365 Pénzügy és műveletek eszközben válassza az Adatkezelés **lehetőséget**.

2. Válassza a **Projektek importálása** lehetőséget, majd a projektet.

3. A **Forrásdátum formátumban** válassza a **CSV-Unicode** kódot.

   [![Forrásdátum formátumának módosítása UTC-re.](./media/data-source-date-format.png)](./media/data-source-date-format.png)

4. Az **Időzónaidőzóna** beállítását módosítsa az **Egyezményes világidő** lehetőségre, és a **Nyelv** legyen **En-US**.




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

