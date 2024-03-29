---
title: Feltétel értékelése
description: Ez a témakör bemutatja, hogyan lehet állapotértékelési sablont létrehozni és regisztrálni egy eszközre az Eszközkezelésben.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectCondition, EntAssetConditionTemplate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c43424a0955d7a046186e8a4120c050990df6060
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015056"
---
# <a name="condition-assessment"></a>Feltétel értékelése

[!include [banner](../../includes/banner.md)]

 

Ez a témakör bemutatja, hogyan lehet állapotértékelési sablont létrehozni és regisztrálni egy eszközre az Eszközkezelésben. Az állapot felmérését szabályos időközönként végzik, és az elsődleges cél az eszközökre vonatkozó állapotadatok létrehozása és karbantartása. A megelőző karbantartás szempontjából, fontos, hogy figyelemmel kísérjék legfontosabb információkat, mint a jelenlegi állapot, és a fennmaradó élettartam. Továbbá, ha rendszeres időközönként elvégzi az állapotfelmérést, megfigyelheti és összehasonlíthatja a gépek állapotát a gyárban.

Az állapotfelmérés segítségével számos feltételt mérhetnek és figyelhetnek a berendezésekben. Példa: Mérheti a rezgéseket egy gépen. Miután vibrációs méréseket regisztrált az Eszközkezelésben több különböző géphez, kereshet a legújabb regisztrált felmérésre, és megtekintheti a legújabb vibrációs méréseket.

Az állapotfelmérés eszközökre vonatkozóan készül. Állapotfelmérési eljárás végrehajtása előtt be kell állítania egy állapotfelmérési sablont egy eszköztípusra. A sablonok használatának oka az állapotfelméréshez az, hogy elkerülhető legyen a hasonló eszközökre vonatkozó állapotadatok eltérése. Az Eszközkezelésben az állapotfelmérés létrehozásának és használatának sorrendje: Először beállítja a szükséges állapotfelmérési sablonokat. Ezt követően társítja a sablonokat az **Eszköztípusok** képernyőn található eszköztípusokkal. Végül az **Eszköz** űrlapon szereplő eszközökhöz létrehozhat állapotfelmérési regisztrációkat.

## <a name="create-a-condition-assessment-template"></a>Állapotfelmérési sablon létrehozása

1. Válassza az **Eszközkezelés** > **Beállítások** > **Eszköztípusok** > **Állapotfelmérés** lehetőséget.
2. Válassza az **Új** lehetőséget egy új sablon létrehozásához.
3. A **Sablonazonosító** mezőbe írja be a sablon azonosítóját.
4. Adjon meg egy nevet a sablonnak a **Név** mezőben.
5. Az **Állapotfelmérési sorok** gyorslapon adja hozzá az állapotfelméréshez szükséges sorokat, beleértve a megfelelő feltételtípus és mértékegység kiválasztását.
6. Az **Eszköztípusok** gyorslapon adja meg azokat az eszköztípusokat, amelyeket az állapotfelmérési-sablon használhat.
7. A **Sorok** és **Eszköztípusok** mezőkben a **Részletek** csoportban sorokban a kiválasztott állapotfelmérő sablonhoz kapcsolódó felmérési sorok és eszköztípusok száma látható.


## <a name="create-condition-assessment-registration-on-an-asset"></a>Állapotfelmérés regisztrációjának létrehozása egy eszközhöz

1. Válassza ki **az Eszközkezelés** > **– Összes** > **eszköz lehetőséget**.
2. A listáról válassza ki azt az eszközt, amelyhez állapotfelmérés-regisztrációt szeretne létrehozni.
3. Az **Általános** lapon kattintson az **Állapotfelmérés** gombra.
4. Új regisztráció létrehozásához kattintson az **Új** elemre.
5. Válassza ki a **Dátum** mezőben az állapotfelmérés dátumát.
6. Válassza ki annak a munkavállalónak a nevét, a **Dolgozó** mezőben a állapotfelmérést végezte.
7. A **Sorok** mezőben az állapotfelméréshez beállított felmérési sorok száma látható.
8. Válassza ki a **Sablon** mezőben az állapotfelmérés sablonját. A program automatikusan beszúrja a sablon nevét a **Név** mezőbe, és a kapcsolódó regisztrációs sorokat beilleszti az **Állapotfelmérés-sorok** gyorslapra.
9. A kiválasztott állapotfelmérésre vonatkozó megjegyzéseket a **Megjegyzések** gyorslapon illeszthet be.
10. Az egyes állapootfelérési sorok esetében írja be a mérési adatokat az **Érték** mezőbe.
11. A kiválasztott regisztrációs sorhoz kapcsolódó megjegyzést az **Állapotfelmérési sorok** gyorslap > **Megjegyzések** mezőjében lehet beszúrni. Ha megjegyzést fűz egy sorhoz, a **Megjegyzés** jelölőnégyzet automatikusan be lesz jelölve.

Ha egy eszközhöz állapotfelmérés-regisztrációt végzett, kinyomtathat egy állapotértékelő jelentést.

>[!NOTE]
>A munkarendelések állapotértékelését is regisztrálhatja (**Eszközkezelési** > **·** > **munkarendelések – Minden munkarendelés** > **feltételének értékelési** gombja.)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]