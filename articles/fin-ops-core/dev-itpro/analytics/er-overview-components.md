---
title: Elektronikus jelentéskészítés összetevői
description: Ez a témakör az elektronikus jelentéskészítés (ER) összetevőit ismerteti.
author: nselin
ms.date: 09/28/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 58941
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.region: global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6356fdaee4c6298dd87ef965fcd91937144cd529
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2022
ms.locfileid: "7985734"
---
# <a name="electronic-reporting-components"></a>Elektronikus jelentéskészítés összetevői

[!include [banner](../includes/banner.md)]

Az Elektronikus jelentéskészítés (ER) a következő típusú összetevőket támogatja:

- Adatmodell
- Modell leképezése
- Formátum
- Metaadatok

## <a name="data-model-component"></a>Adatmodell összetevője

Az adatmodell-összetevő az adatszerkezet absztrakt ábrázolása. Egy adott üzleti területet ír le elegendő részletességgel ahhoz, hogy megfeleljen a terület jelentési követelményeinek. Egy adatmodell-összetevő a következő részekből áll:

- **Adatmodell** – Területspecifikus üzleti entitások egy csoportja, és egy hierarchikusan felépített kapcsolatrendszer ezen entitások között.
- **Modell-leképezés** – Összekapcsolja az alkalmazás-adatforrásokat az adatmodell adott, egyes elemeivel a futásidőben, valamint az adatfolyam, és az üzleti adatok megadásának szabályai az adatmodell-összetevőbe.

Az adatmodell üzleti entitását egy tároló vagy rekord képviseli. Az üzleti entitások tulajdonságai adatelemként vagy mezőként jelennek meg. Minden adatelem egyedi névvel, címkével, leírással és értékkel rendelkezik. Az egyes adatelemek értékeit megszerkesztheti, hogy karakterláncként, egész számként, valós számként, dátumként, enumerációként (enum) vagy logikai értékként legyenek felismerve. Továbbá az adatelem lehet másik rekord vagy rekordlista is.

Egyetlen adatmodell-összetevő több tartományspecifikus üzletientitás-hierarchiát tartalmazhat. Modell-hozzárendeléseket is tartalmazhat, amelyek támogatják a jelentésspecifikus adatáramlást futásidőben. A hierarchiákat egyetlen rekord különbözteti meg, amit a modell-hozzárendelés gyökerének választott ki. Például, a fizetési tartomány adatmodellje támogathatja a következő leképezéseket:


- Vállalat \> Szállító \> Az AP tartomány kifizetési tranzakciói
- Vevő \> Vállalat \> Az AR tartomány kifizetési tranzakciói

Az üzleti entitásokat (úgy mint a vállalat és a fizetési tranzakciók) csak egyszer hozza létre. A különféle hozzárendelések szükség esetén újra felhasználhatók.

## <a name="model-mapping-component"></a>Modell-leképezési összetevő

A modell-leképezés összekapcsolja az alkalmazás-adatforrásokat az adatmodell adott, egyes elemeivel a futásidőben, valamint az adatfolyam, és az üzleti adatok megadásának szabályai az adatmodell-összetevőbe.

A modell-hozzárendelés, amely támogatja a kimenő elektronikus dokumentumokat, a következő lehetőségeket kínálja:

- Használhat különböző adattípusokat az adatmodell adatforrásaként. Ezek az adattípusok lefedik a táblákat, az entitásokat, a metódusokat és az enumerációkat is.
- Olyan felhasználói bemeneti paramétereket támogat, amelyeket meghatározhat az adatmodell adatforrásaiként, amikor bizonyos adatokat a futási időben kell megadni.
- Támogatja az adatok átalakítását a szükséges csoportokba. Az adatok szűrését, rendezését és összegzését is lehetővé teszi, illetve logikai számított mezők hozzáfűzését a Microsoft Excel képleteihez hasonló képletekkel. További tudnivalókért lásd: [Képletszerkesztő az elektronikus jelentéskészítésben (ER)](general-electronic-reporting-formula-designer.md).

A modell-hozzárendelés, amely támogatja a bejövő elektronikus dokumentumokat, a következő lehetőségeket kínálja:

- Különböző frissíthető adatelemeket használhat célként. Ezek az adatelemek lefedik a táblákat, az entitásokat és a nézeteket is. Az elektronikus dokumentumok bejövő adatai alapján lehet frissíteni az adatokat. Egy modell hozzárendelésben több cél is használható.
- Olyan felhasználói bemeneti paramétereket támogat, amelyeket meghatározhat az adatmodell adatforrásaiként, amikor bizonyos adatokat a futási időben kell megadni.

A jelentéskészítéshez egyesített adatforrásként használt minden üzleti tartományhoz egy adatmodell-összetevő van tervezve. Az egységes adatforrás leválasztja a jelentést az adatforrások fizikai megvalósításától. Az összetevő olyan módon képezi le a tartományspecifikus üzleti fogalmakat és funkciókat, amely hatékonyabbá teszi a jelentésformátum kezdeti tervét és további karbantartását.

## <a name="format-component"></a>Formátum összetevője

### <a name="format-components-for-outgoing-electronic-documents"></a>Kimenő elektronikus dokumentumok komponensformázása

A formátum összetevője a futásidőben létrejövő jelentési kimenet sémája. A rendszer az alábbi elemekből áll:

- Egy formátum, amely a kimenő elektronikus dokumentum futásidőben generált struktúráját és tartalmát határozza meg.
- Adatforrásokból, amelyek felhasználói bemeneti paraméterek és tartományspecifikus adatmodellek formájában jelennek meg kiválasztott modell-hozzárendeléssel.
- Egy formátum hozzárendelésből, amely formátum-adatforrások formájában jelenik meg olyan egyedi formátumelemekkel, amelyek megadják a futásidőben az adatfolyamot és a formátumkimenet generálásának szabályait.
- Formátumérvényesítésből, amely olyan konfigurálható szabályok formájában jelenik meg, melyek a jelentéslétrehozást kontrollálják a futásidőben a futó környezetben. Létezhet például egy olyan szabály, amely leállítja a szállítói kifizetések kimenetének létrehozását, és kivételt okoz, ha a kiválasztott szállító meghatározott attribútumai hiányoznak, például a bankszámlaszám.

Egy formátum összetevő, amely támogatja az alábbi funkciókat:

- Különálló fájlokként különböző formátumú kimeneti jelentést hoz létre, például szöveg, XML, Microsoft Word-dokumentum vagy munkalap
- Több külön fájl létrehozása, és ezen fájlok zip fájlba történő tömörítése

A formátum-összetevő lehetővé teszi bizonyos fájlok csatolását, amelyek a jelentési kimenetben a következőképpen használhatók:

- Excel-munkafüzetek, melyek olyan munkalapot tartalmaznak amik sablonként használhatóak a kimenethez az OPENXML munkalap formátumban
- Word-fájlok, melyek olyan dokumentumot tartalmaznak, amely sablonként használható a kimenethez a Microsoft Word-dokumentum formátumban
- Más fájlok, amelyeket előre definiált fájlként konvertálni lehet a formátum kimenetébe.

A következő ábra azt mutatja, hogy hogyan áramlanak az adatok ezeknek a formátumoknak az esetében.

[![Bejövő formátum-összetevők adatáramlása.](./media/ER-overview-03.png)](./media/ER-overview-03.png)

Egyetlen ER-formátumkonfiguráció futtatásához, adatok importálásához egy bejövő elektronikus dokumentumból, meg kell adni egy formátumkonfiguráció kívánt hozzárendelését, valamint a modell-hozzárendelés integrációs pontját. A különböző típusú bejövő dokumentumokhoz ugyanaz a modell-leképezés és célok használhatók különböző formátumokkal.

## <a name="component-versioning"></a>Összetevő verziókövetése

Az ER-összetevő esetében támogatott a verziókövetés. A következő munkafolyamat az ER-összetevők változásainak kezelésére szolgál:

1. Az eredetileg létrehozott verzió **Tervezet** verzióként van megjelölve. Ez a verzió szerkeszthető és elérhető próbakísérletekhez.
2. A **Tervezet** verzió átkonvertálható egy **Befejeződött** verzióvá. Ez a verzió használható a helyi jelentési folyamatokban.
3. A **Befejeződött** verzió átkonvertálható egy **Megosztott** verzióvá. Ezen verzió közzétételre kerül az Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban, és a globális jelentési folyamatokban is használható.
4. A **Megosztott** verzió átkonvertálható **Nem folytatott** verzióvá. Ez a verzió törölhető.

A **Befejeződött** vagy **Megosztott** állapotú verziók elérhetőek más adatcsere céljából. Egy ezekkel az állapotokkal rendelkező összetevőn a következő műveletek végezhetőek el:

- Az összetevő szerializálható XML-formátumba és a rendszerből exportálható XML formátumú fájlba.
- Az összetevők újraszerializálhatóak XML fájlból, és importálhatóak az alkalmazásba egy ER-összetevő új verziójaként.

## <a name="component-date-effectivity"></a>Összetevő érvényességi dátuma

Az ER-összetevő verziói érvényességi dátumhoz kötöttek. Az ER-összetevőhöz beállítható az „érvényesség kezdete” dátum, hogy meghatározzuk, mikortól lesz érvényes az összetevő a jelentési folyamatban. Az alkalmazás munkamenetdátuma arra használható, hogy meghatározzuk, érvényes-e az összetevő a végrehajtásra. Amennyiben egy adott dátumhoz egynél több verzió is érvényes, a jelentési folyamathoz a legutóbbi verzió kerül felhasználásra.

## <a name="component-access"></a>Összetevő hozzáférése

Az ER formátumösszetevőkhöz való hozzáférés a Nemzetközi Szabványügyi Szervezet (ISO) ország-/régiókód beállításától függ. Ha ez a beállítás üres a formátum beállítások kiválasztott verziójánál, akkor a formátum összetevők elérhetőek bármely vállalatnál a futásidő során. Ha a beállítás tartalmazza az ország/régió ISO kódját, akkor a formátum összetevője csak abból a vállalatból érhető el, amely elsődleges címének egy formátum-összetevő ország/terület ISO kódja van megadva.

Előfordulhat, hogy az adatformátum-összetevők különböző verziói más ország/régió ISO kód beállításaival rendelkeznek.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

