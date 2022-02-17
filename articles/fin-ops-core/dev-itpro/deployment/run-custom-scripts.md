---
title: Futtasson egyéni X++ szkripteket nulla állásidővel
description: Ez a témakör bemutatja, hogyan tölthet fel és futtathat telepíthető csomagokat, amelyek egyéni X++ szkripteket tartalmaznak a rendszer felfüggesztése nélkül.
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
ms.openlocfilehash: fcd0a472fa5116ca0b3a59561b6eeb72181a9113
ms.sourcegitcommit: 44e6875e974a3a1b3e1d7a24c1a3cff3d3697cdc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2022
ms.locfileid: "8088344"
---
# <a name="run-custom-x-scripts-with-zero-downtime"></a>Futtasson egyéni X++ szkripteket nulla állásidővel

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Ez a funkció lehetővé teszi olyan telepíthető csomagok feltöltését és futtatását, amelyek egyéni X++ szkripteket tartalmaznak anélkül, hogy át kellene menniük Microsoft Dynamics Életciklus-szolgáltatások (LCS), vagy függessze fel a rendszert. Emiatt kijavíthatja a kisebb adatellentmondásokat anélkül, hogy zavaró leállást okozna.

Az X++ szkript használatának előnye a kisebb adatellentmondások kijavítására, hogy a rendszer automatikusan módosítja az összes kapcsolódó táblát a szkript futtatásakor. Ez a megközelítés segít biztosítani a korrekció integritását, és segít minimalizálni az új következetlenségek bevezetésének kockázatát.

> [!IMPORTANT]
> Ez a funkció csak a kisebb adatellentmondások kijavítására szolgál. Nem használható a következő célokra vagy bármilyen más célra:
>
> - Adatgyűjtés
> - Sémaváltások
> - Adatmigráció vagy egyéb hosszan tartó folyamatok
> - Más módon javítható adatok javítása, például szokásos üzleti folyamatok, adatkonzisztencia-eszközök vagy egyéb önkiszolgáló eszközök
>
> A szolgáltatás lehetővé teszi a jogosult felhasználók számára, hogy közvetlenül módosítsák az entitásokat és rekordjaikat, anélkül, hogy futtatniuk kellene az entitásokhoz társított üzleti logikát. Ezek a változtatások adatintegritási problémákat okozhatnak. Ezért előfordulhat, hogy szervezete megkövetelheti, hogy a szkript futtatása előtt és/vagy után beszerezze a belső és külső auditorok (vagy más egyenértékű érdekelt felek) jóváhagyását és jóváhagyását. Megfelelőségi okokból előfordulhat, hogy bizonyos jellemzőket érintő változásokat külső jelentésekben (például pénzügyi kimutatásokban) is közzé kell tenni, vagy jelenteni kell a kormányzati hatóságoknak. Az Ön szervezete kizárólagos felelősséggel tartozik az adatain ezen funkción keresztül végrehajtott bármilyen módosításért, a változtatások jóváhagyásáért, aláírásáért vagy nyilvánosságra hozataláért, valamint a vonatkozó jogszabályok betartásáért. A funkció használatának minden kockázatát Ön viseli.

A rendszerbe feltöltött összes telepíthető csomag kötelező munkafolyamaton megy keresztül. Biztonsági óvintézkedésként és a feladatok elkülönítésének elősegítése érdekében a telepíthető csomagot feltöltő felhasználó nem hagyhatja jóvá a munkafolyamat következő lépéseihez. Egy másik felhasználónak jóvá kell hagynia. A csomag jóváhagyása után azonban az azt feltöltő felhasználó elvégezheti a fennmaradó lépéseket.

A rendszer megköveteli, hogy minden telepíthető csomag tesztfutáson menjen keresztül. Mielőtt a parancsfájl futhatna éles adatokon, a felhasználónak a kiválasztással ellenőriznie kell, hogy a kimenet helyes-e **Tesztnapló elfogadása**. Ha a kimenet nem megfelelő, a felhasználónak meg kell jelölnie a csomagot sikertelenként a kiválasztással **Elhagyott**. Ebben az esetben a szkript nem futhat termelési adatokon.

Minden feltöltött csomag mentésre kerül a rendszerben, és az események meghatározott munkafolyamatán megy keresztül. A rendszer minden eseményről naplót vezet, amely tartalmazza az időbélyeget és az eseményt végrehajtó személy azonosítóját. Ily módon a rendszer biztosítja az ellenőrzési nyomvonal meglétét.

Ahogy a következő ábra mutatja, a rendszer részleteket ad arról, hogy az egyes telepíthető csomagok hogyan futottak az X++-ban, és mely entitásokat érintette meg.

![Szkript részleteinek oldala.](media/script-details.png "Szkript részleteinek oldala")

## <a name="assign-duties-to-users-to-control-access"></a>Rendeljen ki feladatokat a felhasználóknak a hozzáférés szabályozására

Ez a funkció a következő feladatokat látja el. A rendszergazdák ezeket a feladatokat a funkcióhoz való hozzáférés szabályozására használhatják.

- **Egyéni szkriptek karbantartása** – Ez a kötelezettség lehetővé teszi egyéni X++ szkriptek feltöltését, tesztelését, ellenőrzését és futtatását környezetekben (felhasználói elfogadási tesztelés\[ UAT\] és termelés).
- **Egyéni szkriptek jóváhagyása** – Ez a kötelezettség lehetővé teszi egy feltöltött egyéni X++ szkript jóváhagyását. A jóváhagyás egy kötelező lépés a szkript tesztelése, ellenőrzése és futtatása előtt.

A rosszindulatú műveletek kockázatának minimalizálása érdekében minden szkriptet kifejezetten jóvá kell hagynia a feltöltő felhasználótól eltérő felhasználónak. Mielőtt használhatná ezt a funkciót a szervezetében, az adminisztrátornak legalább két releváns és nagyon megbízható felhasználót ki kell jelölnie az előző feladatokkal. Bár egyetlen felhasználónak mindkét kötelezettsége lehet, az a felhasználó továbbra sem tudja jóváhagyni saját szkriptjeit.

## <a name="create-a-deployable-package"></a>Telepíthető csomag létrehozása

A funkció használatához egy normál telepíthető csomagra van szükség, amelyen létrehozható Visual Studio. Az utasításokat lásd [Hozzon létre telepíthető modellcsomagokat](../deployment/create-apply-deployable-package.md).

A telepíthető csomagnak pontosan egy futtatható X++ osztályt kell tartalmaznia. Más szóval, egy osztálynak kell lennie, amely tartalmaz egy metódust, amely a következő aláírással rendelkezik.

```xpp
public static void main(Args _args)
```

> [!NOTE]
> A fő metódus nevének kisbetűnek kell lennie.

## <a name="code-example"></a>Kódpélda

A következő kódpélda bemutatja, hogyan lehet egy telepíthető csomagot felépíteni.

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

Az alábbi lista néhány bevált módszert ír le a szkriptek sikeres írásához, megvalósításához és futtatásához. A lista nem kimerítő, és csak iránymutatásnak tekinthető.

- **Tedd** írj egy sikerüzenetet a forgatókönyv végére. Így láthatja, hogy a szkript kivétel nélkül futott.
- **Tedd** adja hozzá a tranzakció hatókörének kifejezett kezelését.
- **Tedd** használja a meglévő üzleti logikát, mint pl`update()` módszerek, de **nem** használatával megkerülheti az üzleti logikát`doUpdate()`,`doInsert()`, és`doDelete()` mód. Ez a megközelítés segít biztosítani a függő adatok helyes kezelését. Jelentősen csökkenti a további adatellentmondások kockázatát is.
- **Tedd** érvényesíteni a vállalati kontextust. Ez a megközelítés felfedi a szkript futtatása során előforduló gyakori hibákat. Például felfedi, hogy a szkript nem a megfelelő cégen fut-e.
- **Tedd** állítsa, hogy az érintett rekordok száma megfelel az elvárásoknak. Ez a megközelítés megmutatja, hogy az adatok váratlanul elmozdultak-e a rendszerben a szkript előkészítése során.
- **Tedd** használjon egyedi osztályneveket minden szkripthez (például úgy, hogy a névben szerepel egy hivatkozás egy munkaelemre). Ez a megközelítés megakadályozza a névütközési problémákat a szkript feltöltésekor. Ha egy szkript új iterációjára van szükség, feltétlenül új nevet adjon neki.
- **Tedd** minden szkriptet először teszteljen nem éles környezetben. Tesztelje a tervezett hatást és a nem szándékos mellékhatásokat a kapcsolódó adatokon. Gondoskodjon arról, hogy az esetlegesen érintett üzleti folyamatokat sikeresen és maradéktalanul lehessen befejezni.

## <a name="upload-and-run-a-deployable-package"></a>Tölts fel és futtass egy telepíthető csomagot

A szkript feltöltéséhez és futtatásához kövesse az alábbi eljárást.

1. A Finance and Operations alkalmazásban nyissa meg a következőt: **Rendszer adminisztráció \> Időszakos feladatok \> Adatbázis \> Egyedi szkriptek**.
1. Válassza a **Feltöltés** elemet.
1. Válassza ki a telepíthető csomagot, amelyet a témakörben korábban leírtak szerint hozott létre. A rendszer kéri, hogy adja meg a szkript célját.
1. A szkriptet most nem a feltöltő felhasználónak kell jóváhagynia. A jóváhagyónak követnie kell az alábbi lépéseket:

    1. Menj **Rendszer adminisztráció \> Időszakos \> Adatbázis \> Egyedi szkriptek**.
    1. Válassza ki a jóváhagyni kívánt szkriptet, majd válassza ki **Részletek**.
    1. A Műveletpanelen a **Folyamat munkafolyamat** lapon, a **Rajt** csoport, válassza ki **Jóváhagy** vagy **Elutasít**. Ha kiválasztod **Jóváhagy**, a szkript jóváhagyottként van megjelölve, és tesztelésre fel van oldva. Ha kiválasztod **Elutasít**, a szkript zárolva van. Az esemény mindkét esetben naplózásra kerül, és a szkript másolata a rendszerben marad.

1. A szkriptet tesztelni kell, hogy megbizonyosodjon arról, hogy azt csinálja, amire szánták. A tesztelő lehet ugyanaz, mint a feltöltő vagy a jóváhagyó, vagy lehet egy harmadik felhasználó, aki rendelkezik a szükséges jogosultságokkal. A tesztelőnek az alábbi lépéseket kell követnie:

    1. Menj **Rendszer adminisztráció \> Időszakos \> Adatbázis \> Egyedi szkriptek**.
    1. Válassza ki a tesztelni kívánt szkriptet, majd válassza ki **Részletek**.
    1. A Műveletpanelen a **Folyamat munkafolyamat** lapon, a **Teszt** csoport, válassza ki **Futtassa a tesztet**. A szkript egy ideiglenes tranzakción belül fut, amelyet a rendszer automatikusan megszakít, miközben különféle naplókat és SQL utasításokat gyűjt.
    1. Amikor a szkript futott, tekintse át a naplókat, és ellenőrizze, hogy az eredmények megfelelnek-e az elvárásoknak. Tegye a következők egyikét:

        - Ha elégedett a teszt eredménnyel, válassza a lehetőséget **Tesztnapló elfogadása** ban,-ben **Teszt** csoport a **Folyamat munkafolyamat** a Műveleti ablaktáblán a szkript futtatásának engedélyezéséhez. Az eseménynapló tükrözi a szkript tesztelésének tényét, és jelzi, hogy ki és mikor tesztelte.
        - Ha nem elégedett a teszt eredménnyel, válassza a lehetőséget **Elhagyott** ban,-ben **Vége** csoport a **Folyamat munkafolyamat** a Műveleti ablaktáblán, hogy megakadályozza a szkript futtatását. A rendszer megőrzi a szkript másolatát az előzmények naplójával együtt.

1. Ha biztos abban, hogy a szkript megfelel az elvárásoknak, válassza a lehetőséget **Fuss** ban,-ben **Fuss** csoport a **Folyamat munkafolyamat** a Műveletpanel lapfülén a futtatásához. Ez a parancs ugyanazt teszi, mint az előző tesztfutás, de a tranzakció véglegesítésre kerül a végén.
1. Miután a szkript futott, ellenőrizze az eredményt, és győződjön meg arról, hogy a szkript a kívánt módon működött. Tegye a következők egyikét:

    - Ha elégedett az eredménnyel, válassza a lehetőséget **A cél megoldva** ban,-ben **Vége** csoport a **Folyamat munkafolyamat** a Műveletpanel lapján. Az eseménynapló tükrözi a szkript sikeres lefutását, és jelzi, hogy ki és mikor ellenőrizte a szkriptet. A szkript mentve van, de most zárolva van, és nem futtatható újra.
    - Ha nem elégedett az eredménnyel, válassza a lehetőséget **A cél megoldatlan** ban,-ben **Vége** csoport a **Folyamat munkafolyamat** a Műveletpanel lapján. Az eseménynapló tükrözi azt a tényt, hogy a szkript nem teljesítette a kitűzött célt, és jelzi, hogy ki és mikor futtatta a szkriptet. A szkript mentve van, de most zárolva van, és nem futtatható újra. A rendszer azonban nem vonja vissza automatikusan a szkriptműveletet. Előfordulhat, hogy új szkriptet kell írnia, importálnia és futtatnia, hogy visszavonja a hibás szkript által a rendszerre gyakorolt hatást.

Az utolsó lépésben végzett választása határozza meg a szkript végső állapotát. Igény szerint megismételheti a folyamatot.

## <a name="upload-and-run-a-deployable-package-through-lcs"></a>Töltsön fel és futtasson egy telepíthető csomagot az LCS-n keresztül

Ahelyett, hogy a Finance and Operations alkalmazás felhasználói felületén keresztül telepítené a telepíthető csomagot, az előző szakaszban leírtak szerint, feltöltheti az LCS-be, és a szokásos eljárással telepítheti. További információkért lásd [Telepítse a telepíthető csomagokat a parancssorból](../deployment/install-deployable-package.md).

Bár ez a megközelítés kevesebb korlátozást tartalmaz, kevesebb hibavédelmet biztosít. Ezenkívül, mivel az összes kiszolgáló újraindítását igényli, némi leállást okoz.
