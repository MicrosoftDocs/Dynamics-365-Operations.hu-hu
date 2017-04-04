---
title: "Időszaki naplók időszakok felosztása"
description: "Az időszaki naplókat olykor ismétlődő naplónak is nevezik, mivel az összeg, a szöveg és más adatok a napló feladásakor minden alkalommal megismétlődnek. Napló létrehozásakor adja meg az ismétlődéshez tartozó időszakot (pl. nap vagy hónap). Azoknak az időszakoknak a számát is adja meg, amelyek szerint a napló fel lesz adva."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261354
ms.assetid: 76c0d7bf-f795-4d42-9a86-a9f36989962c
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 58ab77aea9e66834c516806e5f0cfe3069c94ff3
ms.lasthandoff: 03/31/2017


---

# <a name="split-periods-in-periodic-journals"></a>Időszaki naplók időszakok felosztása

Az időszaki naplókat olykor ismétlődő naplónak is nevezik, mivel az összeg, a szöveg és más adatok a napló feladásakor minden alkalommal megismétlődnek. Napló létrehozásakor adja meg az ismétlődéshez tartozó időszakot (pl. nap vagy hónap). Azoknak az időszakoknak a számát is adja meg, amelyek szerint a napló fel lesz adva.

Többször beolvashat és tranzakciósorok feladása, használhatja a **Időszaki naplók** oldalon. A Cseh Köztársaság, Észtország, Magyarország, Lettország, Litvánia, Lengyelország és Oroszország, jogi személyek esetében a **Időszaki naplók** oldal bővített felosztása időszakokra működéséhez. <!---For more information, see [Create and process a periodic journal](http://ax.help.dynamics.com/en/wiki/create-and-process-a-periodic-journal/).-->

### <a name="example-split-for-periods-in-periodic-journals"></a>Példa: Felosztása az Időszaki naplók időszakokra

Egy biztosítótársaság kínál a szervezet prepaying a biztosítási kötvény teljes év engedményt. A kifizetést egy eszközszámlán adják fel például előre kifizetett biztosításként. A biztosítás havidíja ezután egész évben csökken egy olyan időszaki napló létrehozásával, amelyhez tartozik egy követelés az előre kifizetett biztosítási számlán, illetve egy tartozás a biztosítási költségszámlán. Ebben az esetben az osztott használható időszakok funkciót. Kattintson a **felosztása időszakokra** gombja a műveletpanel a **időszaknapló****vonalak** oldalon, és adja meg a következő mezőket.

|                       |                                                                                                                                                                                                             |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Field**             | **Description**                                                                                                                                                                                             |
| **Start date**        | Az első időszaknapló sorának dátumának kiválasztása.                                                                                                                                                        |
| **Number of periods** | Az időszakok között, amely a naplósor számát adja meg. Ez az érték határozza meg, hány új tranzakció jön létre. A tranzakció összege egyenlően oszlik meg az új tranzakciók között. |
| **Unit**              | Válassza ki a mértékegységet az időszak.                                                                                                                                                                  |
| **Időszak-intervallum**   | Határozza meg a könyvelési időszakok közötti intervallum.                                                                                                                                                              |

Negyedéves feladások készítése, például írja be a **4** a a **időszakok száma** mezőjében válassza az **hónap** a a **egység** mezőben, és írja be **3** a a **időszak** mező. A rendszer számára megadott, 3 hónapos időközönként napló sor összegének egynegyedével négy naplósorokat hoz létre. A főkönyvi napló is érhető el hasonló funkcionalitást. Főkönyvi napló sorai megtekintésekor jelölje ki a **időszaknapló**&gt;**mentés napló**.


