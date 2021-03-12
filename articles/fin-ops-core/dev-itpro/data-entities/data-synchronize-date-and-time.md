---
title: Dátum és idő szinkronizálása az importálási feladatokban
description: Az importálási feladatokban használja az UTC időzónákat, hogy elkerülje az időzóna-átalakításokkal kapcsolatos problémákat.
author: Sunil-Garg
manager: tfehr
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ae04b09a68e64d6d70c0329e689ab08c3903fca0
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798719"
---
# <a name="synchronize-date-and-time-in-import-jobs"></a>Dátum és idő szinkronizálása az importálási feladatokban

[!include [banner](../includes/banner.md)]

Fontos, hogy az importált feladat időzónáját UTC-formátumra (koordinált világidő) állítsa be. Az importált adatokban nem várt dátumok és időpontok is előfordulhatnak, ha más beállítást használ. A helyes beállítás nélkül az importálási folyamat az UTC-dátumot helyi formátumra alakítja, majd a rendszerbeállítások újra konvertálják.

A két konverzió hatására megváltoznak a dátumok az alkalmazások között. A kettős átalakítás például azzal jár, hogy egy alkalmazott kezdő dátuma eltérő lesz a helyi időzónákban lévő különbségek miatt a Dynamics 365 Human Resources és a Dynamics 365 Finance megoldásban. Az importálási feladat UTC-formátumra való beállításával ez a probléma megoldódik.

1. Válassza a Dynamics 365 Finance and Operations megoldásban az **Adatkezelés** lehetőséget.

2. Válassza a **Projektek importálása** lehetőséget, majd a projektet.

3. A **Forrásdátum formátumban** válassza a **CSV-Unicode** kódot.

   [![Forrásdátum formátumának módosítása UTC-formátumra](./media/data-source-date-format.png)](./media/data-source-date-format.png)

4. Az **Időzónaidőzóna** beállítását módosítsa az **Egyezményes világidő** lehetőségre, és a **Nyelv** legyen **En-US**.


