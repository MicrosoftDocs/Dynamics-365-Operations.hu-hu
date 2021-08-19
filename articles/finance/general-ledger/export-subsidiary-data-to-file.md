---
title: A leányvállalatok adatainak exportálása fájlokba
description: Ez a témakör bemutatja, hogy hogyan lehet előkészíteni az adatok Microsoft Dynamics 365 Finance rendszerből történő exportálását, majd egy konszolidált jogi személybe történő importálását.
author: jinniew
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 02ae9945f7b67fb64be78a024910d7e1151c7446fd54b71034c5ba448c00b081
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768771"
---
# <a name="export-subsidiary-data-to-files"></a>A leányvállalatok adatainak exportálása fájlokba

[!include [banner](../includes/banner.md)]

Az **Exportálás** oldal (**Rendszerfelügyelet \> Munkaterületek \> Importálás/exportálás**) használatával előkészítheti a leányvállalatok adatainak egy olyan fájlba történő exportálását, amely később importálható egy konszolidált jogi személybe. Az importálási és exportálási folyamatokkal kapcsolatos további tudnivalókat lásd: [Adatimportálási és -exportálási feladatok áttekintése](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).

1. Hozzon létre egy jogi személyt a konszolidációs folyamathoz. A jogi személyek létrehozásáról a [Jogi személy létrehozása](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md) című témakörben talál információt. A további tudnivalókat lásd: [Jogi személy előkészítése a konszolidációs folyamathoz](prepare-company-for-consolidation.md), valamint [Alárendelt jogi személy beállítása a konszolidációra](set-up-subsidiary-company-for-consolidation.md). 

2. Lépjen a **Konszolidációk \> Vállalati egyenlegek exportálása** lehetőségre. Adja meg a konszolidáció részleteit a **Vállalati egyenlegek exportálása** oldal **Kritériumok** lapján a következő mezők beállításával.

    | Mező                             | Leírás |
    |-----------------------------------|-------|
    | Fő számla                      | Adja meg a konszolidálni kívánt számlákat. Ha minden számlát fel akar venni, hagyja üresen ezt a mezőt. |
    | Konszolidációs számla használata         | Ha meghatározta a konszolidációs számlákat, állítsa ezt a beállítást **Igen** értékre. |
    | Konszolidációs számla kiválasztásának forrása | Válassza a **Fő számla** vagy a **Konszolidációs számlacsoport** lehetőséget. |
    | Konszolidációsszámla-csoport       | Válasszon ki egy konszolidációs számlacsoportot a kiválasztott konszolidációs számlához. |
    | Konszolidációs időszak              | Adja meg a konszolidáció dátumtartományát. |
    | Tényleges összegek belefoglalása            | Tényleges összegek felvételéhez állítsa ezt a lehetőséget **Igen** értékre. |
    | Költségvetési összegek belefoglalása            | Ha költségvetési összegeket akar felvenni a konszolidációkba, állítsa ezt a lehetőséget **Igen** értékre. |
    | Költségvetési modellek                     | Adja meg a felvenni kívánt költségvetési modellt. |

3. Adja meg a konszolidáció részleteit a **Pénzügyi dimenziók** lapon:

    - Adja meg, hogy milyen pénzügyi dimenziók adatai kerüljenek át a leányvállalati számlákról a konszolidált jogi személy tranzakcióiba.
    - Válassza ki a pénzügyi dimenziókat a listából.
    - Azonosítsa a konszolidált pénzügyi dimenziók helyes meghatározását. A következő lehetőségek érhetők el: **Dimenzió**, **Csoportdimenzió**, **Vállalati számlák** és **Számla**.

        > [!NOTE]
        > A **Csoportdimenzió** beállítással definiálhatja a konszolidált vállalatcsoport által használt dimenzióértéket.

    - Adja meg a konszolidálni kívánt szegmensrendelést.

4. A **Jogi személyek** lapon a következő lépéseket követve adja meg az exportálni kívánt jogi személyt:

    1. Válassza az **Új** lehetőséget.
    2. A **Forrás jogi személy** mezőbe írja be a jogi személyt.

        Ha azonos adatbázisban tárolt több leányvállalatra is érvényesek ugyanazok a feltételek, akkor az ilyen leányvállalatok adatai egyetlen exportálási műveletben átvihetők külön exportfájlokba.

        1. Hozzon létre egy sort minden olyan leányvállalati jogi személynek, amelynek a számláit fájlokba fogja exportálni. Ezeket a fájlokat kell majd importálni a konszolidált jogi személybe.
        2. Adja meg minden leányvállalat esetében a leányvállalat nevét és az exportálás során létrejövő exportfájl nevét.

    3. Az **Átváltási különbözetek számlatípusa** mezőben válassza a **Nyereség és veszteség** vagy a **Mérleg** lehetőséget.
    4. Írja be a létrehozandó exportfájl nevét.

5. Az exportálás futtatásához válassza az **OK** lehetőséget.

Az exportálás befejeződése után a program egy üzenetben jeleníti meg, hogy hány rekordot mentett az egyes fájlokba. Ezt követően importálhatja a fájlokat a konszolidált jogi személybe.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]