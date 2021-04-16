---
title: Lízingek kezelése a lízingimportálási keretrendszeren keresztül
description: Ez a témakör bemutatja, hogyan használhatja a Lízingimportálási keretrendszert több lízinghez egyszerre.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 26fb195ff18dc0c86d3546b782265043c2c78bf4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819794"
---
# <a name="manage-leases-through-the-lease-import-framework"></a>Lízingek kezelése a lízingimportálási keretrendszeren keresztül

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan használhatja a Lízingimportálási keretrendszert több lízinghez egy lépésben. Ezzel a funkcióval időt takaríthat meg, és az emberi hibák esélyének csökkentésével pontosabb beállításokat is biztosíthat. Emellett ez a funkció a Microsoft Dynamics 365 Finance-et külső adatentitásokkal is összekapcsolhatja az adatok hatékony feltöltése érdekében.

Az eszközlízing külső rendszerekkel való integrálására a következő adatentitások használhatók:

- Lízing-előkészítés
- Fizetési szerződés-előkészítés
- Működéshez kapcsolódó szerződés előkészítése

Az importálási folyamat segítségével módosíthatja a lízinget, frissítheti a nem pénzügyi adatokat, vagy új lízingeket adhat hozzá. Importálás előtt megtekintheti és szerkesztheti a lízingadatokat.

A rendszer a következő három folyamatot futtathatja a lízingimportálás csomagon keresztül.

| Folyamat típusa  | Leírás |
|---------------|-------------|
| Rekord hozzáadása    | Az ilyen folyamattípussal rendelkező áttelepített lízingek lízinget hoznak létre a rendszerben. A fizetési ütemezést manuálisan kell megerősíteni, és a kezdeti kibúvó naplóbejegyzést az áttelepítés után manuálisan kell feladni. |
| Rekord frissítése | Az ilyen folyamattípussal rendelkező áttelepített lízingek a rendszerben már szereplő lízing mezőértékeit frissítik. Csak a **Mezők gyűjteményének frissítése** lapon kijelölt mezők frissülnek. Azt javasoljuk, hogy a **Mezők gyűjteményének frissítése** lapon válasszon ki nem pénzügyi mezőket, mert ez a folyamattípus nem módosítja a lízinget. |
| Rekord korrekciója | Az ilyen folyamattípussal rendelkező áttelepített lízingek kiigazítják a lízinget. Ez a kiigazítás a lízing pénzügyi lízingmódosítását okozza. A lízing feldolgozása után a rendszer új fizetési ütemezést hoz létre a lízing importálási csomagjából származó új adatok használatával. A rendszer nem erősíti meg a kifizetési ütemezést, és nem adja fel a helyesbítő naplóbejegyzést. |

Miután az adatokat feltöltötte az **Adatkezelés** munkaterületen keresztül, nyissa meg a **Fejléc importálása** lapot (**Eszközlízing \> Lízingimportálási keretrendszer \> Fejléc importálása**). Ez a lap a korábban felsorolt három adatentitás összes importálását tartalmazza.

Ha a feldolgozás futtatása előtt meg szeretné tekinteni a lízing átmeneti adatait, válassza az **Előkészítési adatok** lehetőséget.

Az összehasonlításfunkció lehetővé teszi az importáló rekordok és a rendszerben már meglévő megfelelő rekord összehasonlítását. Egy adott lízingrekord összehasonlításához jelöljön ki egy lízinget, majd válassza az **Összehasonlítás** lehetőséget. Ezt a lépést a **Különbözeti** jelentés létrehozásához kell végrehajtania a lízingrekordok áttelepítése előtt. Az Összehasonlítás funkció összehasonlítja az átmeneti adatok értékeit a rendszerben jelenleg lévő lízingek értékeivel.

> [!NOTE]
> Az Összehasonlítás funkció nem működik a **Rekord hozzáadása** folyamattípussal rendelkező lízingek esetében, mivel nincs mit összehasonlítani az adott lízinggel.
>
> Ha egyszerre több lízinget szeretne összehasonlítani, nyissa meg az **Eszközlízing \> Lízingimportálási keretrendszer \> Időszakos \> Összehasonlítás** című lehetőséget, és válassza az **Összehasonlítás** lehetőséget.

Az egyes entitásoknál megtekintheti a különbséget aközött, hogy mi van jelenleg a rendszerben, és mi van az előkészítési táblákban. Az előkészítési táblákban lévő minden entitásnál válassza a **Különbségek megtekintése** lehetőséget. A megjelenő párbeszédpanelen látható az aktuális érték és a javasolt előkészítési érték.

Az előkészítési értéket úgy is frissítheti, hogy módosítja az **Új érték** oszlopban, majd kiválasztja az **Előkészítés frissítése** lehetőséget.

A lízingek érvényesítésével biztosíthatja, hogy a rekordok hibák bevezetése nélkül is bekerülhessenek a rendszerbe. A lízingrekord áttelepítése előtt a rendszer számos ellenőrzést futtat annak érdekében, hogy a rekord importálása sikeres legyen. Az egyes lízingek érvényesítéséhez válassza az **Érvényesítés** lehetőséget.

> [!NOTE]
> Ha egyszerre több lízinget szeretne érvényesíteni, nyissa meg az **Eszközlízing \> Lízingimportálási keretrendszer \> Időszakos \> Érvényesítés** című lehetőséget, és válassza az **Összehasonlítás** lehetőséget.

Egyéni bérlet feldolgozásához válassza a **Lízingrekordok áttelepítése** lehetőséget a **Fejléc importálása** lapon. A lízingáttelepítésekénél a rendszer végrehajtja a **Folyamat típusa** mezőben megadott műveletet.

> [!NOTE]
> Ha egyszerre több lízinget szeretne érvényesíteni, nyissa meg az **Eszközlízing \> Lízingimportálási keretrendszer \> Időszakos \> Érvényesítés** című lehetőséget, és válassza az **Összehasonlítás** lehetőséget.

A lízingek összehasonlítása után futtathat egy jelentést az importálási azonosítóban szereplő minden egyes lízing különbségeinek megtekintéséhez. Ha egy lízinghez szeretné futtatni a jelentést, jelölje ki a lízinget az átmeneti adatok között, majd válassza a **Összehasonlítás és jelentés megtekintése \> Különbségek jelentése** lehetőséget.

> [!NOTE]
> Ha egyszerre több lízinget szeretne érvényesíteni, nyissa meg az **Eszközlízing \> Lekérdezések és jelentések \> Különbségek jelentése** lehetőséget, és válassza az **Összehasonlítás** lehetőséget.

## <a name="set-up-update-fields"></a>Frissítési mezők beállítása

Ha a lízingimportálási keretrendszert használja a lízingek frissítéséhez, és a folyamat típusa **Rekord frissítése**, kiválaszthatja a frissítendő mezőket.

1. Nyissa meg az **Eszközlízing \> Lízingimportálási keretrendszer \> Beállítás \> Mezőgyűjtemény frissítése** lehetőséget.
2. A megjelenő lapon jelölje ki a frissíteni kívánt mezőket, majd a zöld nyíllal helyezze át őket a **Kijelölt mezők** listára. A lízingimportálási csomag használatával csak a **Kijelölt mezők** listájában szereplő mezők frissíthetők.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]