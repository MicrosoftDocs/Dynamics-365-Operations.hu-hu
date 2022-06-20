---
title: A fájlokba exportált leányvállalati adatok importálása
description: Ez a cikk bemutatja, hogy hogyan lehet előkészíteni Microsoft Dynamics a külső rendszerből az adatokat a 365 Pénzügybe történő importáláshoz.
author: jinniew
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 6886e2ee79ee9e4ccc067dc4f661c1eea646cfa6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846770"
---
# <a name="import-subsidiary-data-from-files"></a>A fájlokba exportált leányvállalati adatok importálása

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogy hogyan lehet előkészíteni Microsoft Dynamics a külső rendszerből az adatokat a 365 Pénzügybe történő importáláshoz. A **Konszolidálás importálással** oldal (**Konszolidációk \> Konszolidálás importálással**) használható a külső rendszerekből származó leányvállalati adatok átvitelének előkészítésére.

1. Hozzon létre egy leányvállalati jogi személyt a konszolidációhoz. A jogi személyek létrehozásáról a [Jogi személy létrehozása](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md) című témakörben talál információt. A további tudnivalókat lásd: [Jogi személy előkészítése a konszolidációs folyamathoz](prepare-company-for-consolidation.md), valamint [Alárendelt jogi személy beállítása a konszolidációra](set-up-subsidiary-company-for-consolidation.md).

2. Készítse elő importált adatokat tartalmazó fájlt. Az importálási folyamattal kapcsolatos további tudnivalókat lásd: [Adatimportálási és -exportálási feladatok áttekintése](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).
3. Exportálja az adatokat egy fájlba az Adatimportálási és -exportálási feladatok áttekintése folyamat lépéseit követve: [Adatimportálási és -exportálási folyamatok áttekintése](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md). Ezzel az eljárással adatokat konszolidálhat a Dynamics 365 Pénzügy egy másik példányán, vagy a következőből:Dynamics 365 Business Central Ha külső rendszerekből importál adatokat, az adatoknak [A leányvállalatok adatainak exportálása fájlokba](export-subsidiary-data-to-file.md) részben leírtaknak megfelelő formátumúnak kell lenniük.
4. Lépjen ide: **Konszolidációk \> Konszolidálás importálással**. Adja meg a jelentés és/vagy az importálás részleteit a **Konszolidálás importálással** oldal **Kritériumok** lapján a következő mezők beállításával.

    | Mező                                 | A jelentés értéke | Az importálás értéke |
    |---------------------------------------|----------------------|----------------------|
    | Leírás                           | Nem alkalmazható | Adja meg az importálást azonosító leírást. |
    | Fő számla                          | Határozza meg a jelentésbe foglalható számlák tartományát. Ha nem ad meg tartományt, a rendszer minden számlát beemel. | Határozza meg az importálásba foglalható számlák tartományát. Ha nem ad meg tartományt, a rendszer minden számlát beemel. |
    | Konszolidációs időszak                  | Adja meg a konszolidálandó dátumtartományt. | Adja meg a konszolidálandó dátumtartományt. |
    | Tényleges összegek belefoglalása                | Tényleges összegek felvételéhez állítsa ezt a lehetőséget **Igen** értékre. | Tényleges összegek felvételéhez állítsa ezt a lehetőséget **Igen** értékre. |
    | Költségvetési összegek belefoglalása                | Ha költségvetési összegeket akar felvenni a konszolidációkba, állítsa ezt a lehetőséget **Igen** értékre. | Ha költségvetési összegeket akar felvenni a konszolidációkba, állítsa ezt a lehetőséget **Igen** értékre. |
    | Egyenlegek újraépítése a konszolidálási folyamat során | Állítsa **Igen** értékre, ha az újraépítési folyamatnak teljes mértékben törölnie kell az egyenleget és az új rekordokat, és újra létre kell hoznia az egyenleget az időmérés kezdetétől számítva. | Állítsa **Igen** értékre, ha az újraépítési folyamatnak teljes mértékben törölnie kell az egyenleget és az új rekordokat, és újra létre kell hoznia az egyenleget az időmérés kezdetétől számítva. |
    | Költségvetési modellek                         | Nem alkalmazható | Ha költségvetési összegek importálását választotta, adja meg a konszolidálandó költségvetési modelleket. |
    | Költségvetési árfolyamtípus                      | Nem alkalmazható | Írja be a költségvetés árfolyamtípusát. |

6. Ha eltérő könyvelési pénznemek vannak, a **Pénznemátváltás** lap mezőivel konfigurálhatja a konszolidáció során végzett fordítást.

    | Mező                      | Leírás |
    |----------------------------|-------------|
    | Forrás jogi személy        | Válassza ki azt a jogi személyt, amelyből importál. |
    | Forrás könyvelési pénznem | Ez az alapértelmezett pénznem az a pénznem, amely a **Forrásként megadott jogi személy** mezőben kiválasztott forrásként megadott jogi személyhez van társítva. |
    | Forrásszámlák és Célszámlák       | Definiálja a forrásként megadott jogi személytől importálandó számlatartományt. |
    | Árfolyamtípus         | Válassza ki az árfolyamtípust. Az árfolyamtípusok hozzárendelése a fő számla létrehozásakor történik. További tudnivalókkal kapcsolatban lásd: [Fő számla létrehozása](tasks/create-main-account.md). |
    | Következő dátumú árfolyam alkalmazása:   | Adja meg azt a dátumot, amikor alkalmazni kell az adott napon érvényes árfolyamot. Másik lehetőségként megadhatja az árfolyamként használandó értéket. |
    | Árfolyam              | Az alapértelmezett érték az **Árfolyamtípus** mezőben kiválasztott árfolyamtípustól függ. Ha felhasználói árfolyamot adott meg, megadhatja az árfolyamot. |

7. A **Futtatás a háttérben** **Igen** értékre való állításával engedélyezheti az importálási folyamatnak a háttérben való futtatását.
8. Állítsa **Igen** értékre a **Kötegelt feldolgozás** lehetőséget, ha a konszolidációt meghatározott időpontban szeretné futtatni kötegelt feladatként. A konszolidáció azonnali futtatásához kattintson az **OK** gombra. 

Ezt követően a rendszer hozzáadja a leányvállalatok konszolidációra kijelölt tranzakcióit és egyenlegeit a konszolidált jogi személy megfelelő számláihoz.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
