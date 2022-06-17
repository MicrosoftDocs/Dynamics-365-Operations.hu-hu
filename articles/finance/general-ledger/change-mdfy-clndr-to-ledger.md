---
title: Főkönyvi naptár módosítása vagy újbóli hozzárendelése
description: Ez a cikk ismerteti, hogyan módosíthatja a főkönyvhöz aktuálisan hozzárendelt naptárat, és hogyan rendelhet új naptárat a főkönyvhöz.
author: kweekley
ms.date: 05/07/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-07
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 751954e0dc5f682b99ab7fe349cd505dc9da7858
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848606"
---
# <a name="change-or-reassign-a-ledger-calendar"></a>Főkönyvi naptár módosítása vagy újbóli hozzárendelése

[!include [banner](../includes/banner.md)]

Ez a cikk ismerteti, hogyan módosíthatja a főkönyvhöz aktuálisan hozzárendelt naptárat, és hogyan rendelhet új naptárat a főkönyvhöz.

## <a name="issue"></a>Probléma

Bizonyos esetekben a vállalatoknak vagy módosítaniuk kell a főkönyvhöz rendelt meglévő naptárat, vagy új naptárat kell hozzárendelniük.

## <a name="resolution"></a>Megoldás

A főkönyvi naptár módosítására vagy új naptár hozzárendelésére két forgatókönyv létezik. Az első forgatókönyv egy meglévő naptár módosítását fedi le, amely már hozzá van rendelve van a főkönyvhöz. A második forgatókönyvben egy új naptár létrehozása szerepel, amelyet a főkönyvhöz rendelnek. Mindkét módosítás bármikor elvégezhető, még akkor is, ha a tranzakciókat már feladták a főkönyvbe.

### <a name="change-an-existing-fiscal-calendar"></a>Meglévő pénzügyi naptár módosítása

Ha módosítani szeretné a főkönyvhöz már hozzárendelt naptárat, lépjen a **Főkönyv \> Főkönyv beállítása \> Főkönyv** menüpontba, és válassza ki a pénzügyi naptár hivatkozását a **Főkönyvi naptárak** oldal megnyitáshoz.

Azonban a naptár lehetséges módosításainak vannak korlátai. Például módosíthatja az *időszakok* kezdő és záró dátumait egy éven belül, de nem módosíthatja egy *év* kezdő és záró dátumait a naptárban.

Az adott év időszakainak módosításához válassza ki a megfelelő naptárat és évet. Első lépésként az **Időszak törlése** gombbal törölje ki a meglévő üzemeltetési időszakok némelyikét vagy mindegyikét. Az első kivételével az összes üzemeltetési időszak törölhető. Ezután az **Időszak felosztása** gombbal feloszthatja a fennmaradó időszakot vagy időszakokat új időszakokra a következő időszak megfelelő kezdő dátumának megadásával.

Miután módosította a naptárban lévő időszakokat, le kell futtatnia a **Főkönyvi időszakok újraszámítása** folyamatot minden jogi személyben (vállalatban), amelyhez a naptár hozzá van rendelve. Bár nem jelenik meg figyelmeztető üzenet, hogy erre a lépésre emlékeztesse, az újraszámítási folyamat elvégzése szükséges az időszak frissítéséhez, amely az egyes feladott tranzakciókhoz van hozzárendelve a Főkönyvben. Az újraszámítási folyamat futtatásához válassza a **Főkönyvi időszakok újraszámítása** lehetőséget az egyes vállalatok **Főkönyv beállítása** oldalán.

Ha az újraszámítási folyamatot nem futtatják le, előfordulhat, hogy a főkönyvi kivonaton vagy a pénzügyi kimutatásokon szereplő tranzakcióegyenlegek helytelenül szerepelnek az időszakokban. Ebben az esetben az újraszámítási folyamat futtatásával bármikor helyesbítheti az egyenlegeket.

### <a name="assign-a-new-fiscal-calendar"></a>Új pénzügyi naptár hozzárendelése

Új pénzügyi naptár hozzárendeléséhez lépjen a **Főkönyv \> Főkönyv beállítása \> Főkönyv** menüpontra, és válassza a **Szerkesztés** lehetőséget, amellyel a **Főkönyv** oldal szerkesztési módba lép. Ezután a **Pénzügyi naptár** mezőben válasszon új pénzügyi naptárat.

Miután módosította a főkönyv pénzügyi naptárát, futtatnia kell a **Főkönyvi időszakok újraszámítása** folyamatot. Ha új pénzügyi naptárat rendel a főkönyvhöz, egy üzenet emlékezteti a lépés végrehajtására. Bár az üzenetből úgy tűnhet, hogy az újraszámítási folyamat nem kötelező, valójában az. Kötelező frissítenie azt az időszakot, amelyet hozzárendelt az egyes feladott tranzakciókhoz a Főkönyvben. Az újraszámítási folyamat futtatásához válassza a **Főkönyvi időszakok újraszámítása** lehetőséget a **Főkönyv beállítása** oldalon.

Ha az újraszámítási folyamatot nem futtatják le, előfordulhat, hogy a főkönyvi kivonaton vagy a pénzügyi kimutatásokon szereplő tranzakcióegyenlegek helytelenül szerepelnek az időszakokban. Ebben az esetben az újraszámítási folyamat futtatásával bármikor helyesbítheti az egyenlegeket.
