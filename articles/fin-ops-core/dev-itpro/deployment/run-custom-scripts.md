---
title: Egyéni X++ parancsfájlok futtatása nullás leállással
description: Ez a témakör azt ismerteti, hogyan lehet olyan telepíthető csomagokat feltölteni és futtatni, amelyek egyéni X++ parancsprogramokat tartalmaznak a rendszer felfüggesztése nélkül.
author: AndersGirke
ms.date: 12/16/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-12-16
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: ff01e2ff8ec105603bb91e0b555301f36e8985b4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8867329"
---
# <a name="run-custom-x-scripts-with-zero-downtime"></a>Egyéni X++ parancsfájlok futtatása nullás leállással

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Ezzel a funkcióval egyéni X++ Microsoft Dynamics parancsfájlokat tartalmazó telepíthető csomagokat tölthet fel és futtathat anélkül, hogy végig kellene mennie a Lifecycle Services (LCS) rendszeren, vagy fel kellene függesztenie a rendszert. Ebből következően korrigálni lehet az kisebb adatkonzisztenciákat anélkül, hogy megszakítanák a leállást.

Az kisebb inkonzisztenciák kijavítása érdekében X++ parancsfájl használata azért előnyös, mert a rendszer a parancsprogram futtatásakor automatikusan beállítja az összes kapcsolódó táblát. Ez a megközelítés elősegíti a javítás integritását, és minimálisra csökkenti az új inkonzisztenciák bevezető kockázatát.

> [!IMPORTANT]
> Ez a funkció csak az adatok kisebb inkonzisztenciáit korrigálja. Nem használható a következő célokra és egyéb célokra:
>
> - Adatgyűjtés
> - Sémák változásai
> - Adatáttelepítés vagy más, hosszú ideig futó folyamatok
> - Olyan adatok javítása, amelyek más módon javíthatók, például rendszeres üzleti folyamatok, adatkonzisztencia-eszközök vagy más önkiszolgáló eszközök
>
> Ez a funkció lehetővé teszi, hogy az engedélyezett felhasználók közvetlenül módosítják az entitásokat és a rekordokat, anélkül, hogy futtatni kell az entitásokhoz társított üzleti logikát. Ezek a változtatások adatintegritási problémákat okozhatnak. A szervezet emiatt megkövetelheti, hogy a parancsfájl futtatása előtt és/vagy után belső és külső könyvvizsgálók (vagy más ezzel egyenértékű felek) jóváhagyását és jóváhagyását írja elő. Megfelelési okokból előfordulhat, hogy egyes jellemzőket érintő módosításokat a külső jelentésekben (például a pénzügyi jelentésekben) vagy jelenteni kell az állami hatóságoknak. A vállalat kizárólagos felelős minden olyan módosításért, amely az adatokon keresztül ezen a funkción keresztül módosul, valamint ezek jóváhagyásáért, jóváhagyásáért és közzétételéért, valamint az alkalmazandó törvényeknek való megfelelésért. A funkció használatának minden kockázatát magában kell viseli.

A rendszerbe feltöltött minden telepíthető csomag egy kötelező munkafolyamaton megy keresztül. Biztonsági okokból, és a feladatkörök szétválasztásának biztosítása érdekében a telepíthető csomagot feltöltő felhasználó nem jóváhagyhatja a munkafolyamat következő lépéseit. Egy másik felhasználónak jóvá kell hagynia. A csomag jóváhagyása után azonban az a felhasználó, aki feltöltötte, a további lépéseket is el tudja látni.

A rendszer megköveteli, hogy minden telepíthető csomag végig menjen egy tesztfutáson. Ahhoz, hogy a parancsfájl a termelési adatokon fusson, a felhasználónak a **tesztnapló elfogadása beállítással ellenőriznie kell a kimenet helyességét**. Ha a kimenet nem megfelelő, akkor a felhasználónak a Kiválasztás kiválasztásával meg kell jelölnie a csomagot **sikertelenként**. Ebben az esetben a parancsprogram nem fog tudni termelési adatokon futni.

A rendszer minden feltöltött csomagot ment, és egy meghatározott esemény-munkafolyamaton megy keresztül. A rendszer minden eseményhez egy naplót tart, amely tartalmazza az időbélyeget és annak a személynek az azonosítóját, aki az eseményt végrehajtotta. Így a rendszer gondoskodik a könyvvizsgálati ellenőrzésről.

A következő ábra bemutatja, hogy hogyan futtatták az egyes telepíthető csomagokat az X++ rendszerben, és milyen entitásokat volt ez a helyzet.

![Parancsfájl részletei oldal.](media/script-details.png "Parancsfájl részletei oldal")

## <a name="assign-duties-to-users-to-control-access"></a>Feladatok hozzárendelése a felhasználókhoz a hozzáférés szabályozásához

Ez a funkció a következő feladatokat biztosítja. A rendszergazdák ezekkel a feladatokkal lehet szabályozni a szolgáltatáshoz való hozzáférést.

- **Egyéni parancsfájlok karbantartása** – ez a feladat lehetővé teszi egyéni X++ parancsfájlok feltöltését, tesztelését, ellenőrzését és futtatását környezetben (\[a felhasználó elfogadási tesztje, az UAT\] és a termelés).
- **Egyéni parancsfájlok jóváhagyása** – ez a feladat lehetőséget biztosít egy feltöltött egyéni X++ parancsfájl jóváhagyására. A jóváhagyás kötelező lépés a parancsfájlok tesztelése, ellenőrzése és futtatása előtt.

A rosszindulatú tevékenységek kockázatának csökkentése érdekében minden parancsfájlt kifejezetten jóvá kell hagynia a feltöltött felhasználótól különböző felhasználónak. A funkció szervezetnél való használata előtt egy rendszergazdának legalább két fontos és jól megbízható felhasználóhoz hozzá kell rendelnie a megelőző feladatokat. Bár egyetlen felhasználónak mindkét feladata lehet, ennek ellenére nem hagyhatja jóvá a saját parancsfájlját.

## <a name="create-a-deployable-package"></a>Telepíthető csomag létrehozása

A funkcióhoz szükség van egy rendszeres, telepíthető csomagra, amely a következőben is létrejön:Visual Studio Az útmutatás a [modellek telepíthető csomagjainak létrehozása útmutatóban olvasható](../deployment/create-apply-deployable-package.md).

A telepíthető csomagnak pontosan egy futtatható X++ osztályt kell tartalmaznia. Más szóval kell lennie egy osztálynak, amely a következő aláírással rendelkezik.

```xpp
public static void main(Args _args)
```

> [!NOTE]
> A fő metódus nevének kisbetűsnek kell lennie.

## <a name="code-example"></a>Példa kódra

A következő példakód mutatja be, hogyan lehet egy telepíthető csomagot rendszerezettként.

```xpp
class MyScriptClassForIssueXYZ
{
    public static void main(Args _args)
    {
        if (curExt() != 'DAT')
        {
            throw error("This script must run in the DAT company!");
        }

        ttsbegin;

        MyTable myTable;

        update_recordset myTable
            setting myField = 17
            where myTable.myReference == 'xyz';

        if (myTable.RowCount() != 1)
        {
            throw error("Not updating the expected row!");
        }

        info("Success");
  
        ttscommit;
    }

}
```

## <a name="best-practices"></a>Bevált gyakorlatok

Az alábbi lista a parancsfájlok sikeres megírására, megvalósítására és futtatására vonatkozó gyakorlati lépéseket ismerteti. A lista nem teljes, és csak útmutatásként kell figyelembe venni.

- **Írjon** egy sikeres üzenetet a forgatókönyv végén. Ily módon láthatja, hogy a parancsfájl kivételek nélkül futott-e.
- **Adja** meg a tranzakció hatókörének explicit kezelését.
- **Használja** a meglévő üzleti logikát (`update()` például metódusokat) a **·**`doUpdate()``doInsert()` használat és a metódusok `doDelete()` használatával, de ne kerüljék el az üzleti logikát. Ezzel a módszersel biztosítható a függő adatok megfelelő kezelése. Jelentős mértékben csökkenti az adatok további inkonzisztenciáinak a kockázatát is.
- **Helyessíteni** kell a vállalati környezetet. Ez a megközelítés gyakori hibákat fog kitéve a parancsfájl futtatásakor. Például azt tárja fel, hogy nem a megfelelő vállalatban futtatják-e a parancsfájlt.
- **Állítja** be, hogy az érintett rekordok száma megfelel az elvárásoknak. Ez a megközelítés azt tárja fel, hogy az adatok váratlanul eltoltak-e a rendszerben a parancsfájl előkészítette közben.
- **Használjon** egyedi osztályneveket mindegyik forgatókönyvhöz (például a név egy munkaelemre való hivatkozással). Ez a megközelítés megakadályozza a névvel kapcsolatos problémákat a parancsfájl feltöltésekor. Ha új iteráció szükséges egy forgatókönyvhöz, mindenképpen adjon új nevet a forgatókönyvnek.
- **Előbb** tesztelje az egyes parancsfájlokat nem termelési környezetben. A kapcsolódó adatokra gyakorolt tervezett és véletlenül gyakorolt hatás tesztelése. Annak biztosítása, hogy minden olyan üzleti folyamat, amely hatással lehet rá, sikeresek és később teljesen befejeződni tudjanak.

## <a name="upload-and-run-a-deployable-package"></a>Telepíthető csomag feltöltése és futtatása

A következő eljárás szerint tölthet fel és futtathat parancsfájlt.

1. A Pénzügy és műveletek alkalmazásban használja **a Rendszerfelügyelet \>\>\> – Időszakos feladatok adatbázis-egyéni parancsfájlokat.**
1. Válassza a **Feltöltés** elemet.
1. Válassza ki a korábban ismertetett módon létrehozott telepíthető csomagot. A program megkérdezi, hogy mi a forgatókönyv célja.
1. A parancsfájlt most jóvá kell hagynia egy másik felhasználónak, aki feltöltötte. A jóváhagyónak a következő lépéseket kell követnie:

    1. Ugrás a Rendszerfelügyelet **időszakos alapadatbázis \>\> egyéni parancsfájljaihoz \>**.
    1. Válassza ki a jóváhagyni kívánt parancsfájlt, majd a Részletek **lehetőséget**.
    1. Válassza a Jóváhagyás vagy elutasítás lehetőséget **a műveletpanel Munkafolyamat feldolgozása lapján**, **az** Indítás **csoportban** **.** Ha a Jóváhagyás lehetőséget **választja**, a parancsfájl jóváhagyottként lesz megjelölve, és feloldja tesztelésre való zárolását. Ha az Elutasítás lehetőséget **választja**, a parancsprogram zárolva van. Mindkét esetben az esemény naplózva van, és a parancsfájl másolata a rendszerben marad.

1. A forgatókönyvet tesztelni kell, hogy biztosan azt tegye, amit tenni kíván. A tesztelő ugyanaz lehet, mint a feltöltő vagy a jóváhagyó, vagy lehet egy harmadik felhasználó is, aki a szükséges engedélyekkel rendelkezik. A tesztelőnek a következő lépéseket kell követnie:

    1. Ugrás a Rendszerfelügyelet **időszakos alapadatbázis \>\> egyéni parancsfájljaihoz \>**.
    1. Válassza ki a tesztelni kívánt parancsfájlt, majd válassza a Részletek **lehetőséget**.
    1. A Munkaablak Munkafolyamat feldolgozása **lap** **·** **Tesztcsoport csoportjában válassza a Teszt futtatása lehetőséget.** A parancsfájlt egy ideiglenes tranzakción belül futtatja a rendszer, amely automatikusan megszakad, miközben összegyűjti a különböző naplókat és SQL utasításokat.
    1. Amikor a parancsfájl futása befejeződött, ellenőrizze a naplókat, és ellenőrizze, hogy az eredmények megfelelnek-e az elvárásoknak. Tegye a következők egyikét:

        - Ha meg van elégedve a teszteredménysel, **·** **·** **a** műveletpanel Folyamat munkafolyamat lapjának Tesztcsoportjában válassza a Tesztnapló elfogadása lehetőséget a parancsfájl futtatásának lehetővé tennie. Az eseménynapló azt a tényet tükrözi, hogy a parancsfájl tesztelése történt, és jelzi, hogy ki és mikor tesztelték.
        - Ha nem elégedett a teszteredménysel, a műveletpanel Folyamat munkafolyamat lapjának Beállításával megakadályozhatja a parancsfájl futtatását, **·** **·** **válassza** a Beszúrás lehetőséget a Záró csoportban. A rendszer a parancsfájl másolatát az előzménynaplóval együtt megtartja.

1. Ha biztos benne, hogy a forgatókönyv megfelel az elvárásoknak, **·** **·** **futtassa** a munkaablak Munkafolyamat futtatása lapján található Futtatás csoportban. Ez a parancs nem ugyanaz, mint az előző tesztfuttatás, de a tranzakció a végén lesz vállalt.
1. Miután a parancsfájl futása befejeződött, ellenőrizze az eredményt, és ellenőrizze, hogy a forgatókönyv a kívánt megfelelően működik-e. Tegye a következők egyikét:

    - Ha meg van elégedve az eredménysel, **·** **·** **válassza** a Munkaablak Munkafolyamat feldolgozása lap Záró csoportjában a Feloldott cél lehetőséget. Az eseménynapló azt a tényet tükrözi, hogy a parancsfájl sikeresen futott, és jelzi, hogy ki és mikor ellenőrizte a parancsfájlt. A parancsfájlt mentette a rendszer, de most zárolva van, és nem futtatható újra.
    - Ha nem elégedett az eredménysel, **·** **·** **válassza** a Munkaablak Munkafolyamat feldolgozása lap Záró csoportjában a Cél feloldatlan lehetőséget. Az eseménynapló azt jelzi, hogy a forgatókönyv nem tudta teljesíteni a célokat, és jelzi, hogy ki és mikor futtatta a forgatókönyvet. A parancsfájlt mentette a rendszer, de most zárolva van, és nem futtatható újra. A rendszer azonban nem vonja vissza automatikusan a parancsfájl-műveletet. Lehet, hogy meg kell írni, importálni és futtatnia kell egy új parancsfájlt, hogy visszavonja a sikertelen parancsfájlnak a rendszeren gyakorolt hatását.

Az utolsó lépésben kiválasztott beállítás meghatározza a parancsfájl végső állapotát. A folyamat a szükséges megismétlhető.

## <a name="upload-and-run-a-deployable-package-through-lcs"></a>Telepíthető csomag feltöltése és futtatása az LCS-n keresztül

A telepíthető csomag a Pénzügy és műveletek alkalmazás felhasználói felületén való telepítése helyett feltölthető az LCS-be, és a szokásos eljárás szerint telepítheti azt. A további tudnivalókat lásd [A telepíthető csomagok telepítése a parancssorból](../deployment/install-deployable-package.md).

Bár ebben a megközelítésben kevesebb korlátozás van, kisebb hiba védelmét biztosítja. Ezenkívül, mivel az összes kiszolgáló újraindítását igényli, leállást okoz.
