---
title: Tárgyi eszközök beállítása
description: Ez a témakör áttekintést nyújt a Tárgyi eszközök modul beállításához.
author: ShylaThompson
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 13771
ms.assetid: 8be64197-fea1-4a34-8af2-d939919c28b1
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ff025984307f979ce98947f2225971041ebbdbae
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818536"
---
# <a name="set-up-fixed-assets"></a>Tárgyi eszközök beállítása

[!include [banner](../includes/banner.md)]

Ez a témakör áttekintést nyújt a **Tárgyi eszközök** modul beállításához.

## <a name="overview"></a>Áttekintés

A Tárgyi eszközök lehetőségen belül a paraméterek az általános viselkedést szabályozzák.

A tárgyieszköz-csoportok lehetővé teszik az eszközök csoportosítását, valamint alapértelmezett attribútumok meghatározását egy csoporthoz rendelt minden eszköz esetén. A tárgyieszköz-csoportokhoz a rendszer könyveket társít. A könyvek nyomon követik egy tárgyi eszköz időben változó pénzügyi értékét az értékcsökkenési profil értékcsökkenési konfigurációjának használatával.

A tárgyi eszközök létrehozásukkor egy cikkcsoporthoz társulnak. Alapértelmezés szerint a tárgyieszköz-csoporthoz rendelt könyveket a tárgyi eszközhöz társítja a rendszer. A főkönyvbe történő feladásra konfigurált könyveket a rendszer egy feladási profillal társítja. A főkönyvi számlákat a feladási profilban határozza meg a rendszer könyvenként, és a tárgyieszköz-tranzakciók feladásakor használja őket.

![Tárgyieszköz-összetevők](./media/FAComponents_Updated.png)

## <a name="depreciation-profiles"></a>Értékcsökkenési profilok

Először az értékcsökkenési profilokat kell beállítani. Az értékcsökkenési profilban konfigurálhatja, hogyan történjen egy tárgyi eszköz időbeli értékcsökkenése. Meg kell adnia az értékcsökkenési módszert, az értékcsökkenési évet (naptári vagy pénzügyi év), valamint az értékcsökkenés gyakoriságát. További információk: [Értékcsökkenési profilok beállítása és létrehozása](tasks/set-up-depreciation-profiles.md)

## <a name="books"></a>Könyvek

Az értékcsökkenési profilok beállítása után létre kell hoznia az eszközökhöz szükséges könyveket. Minden könyv egy tárgyi eszköz független pénzügyi életciklusát követi nyomon. A könyveket konfigurálhatja, hogy feladják a kapcsolódó tranzakciókat a főkönyvbe. Ez a beállítás az alapértelmezett beállítás, mivel általában ez használatos a vállalati pénzügyi beszámolók készítésére. A nem a főkönyvbe, hanem csak a Tárgyi eszköz alkészletébe feladott könyveket általában adóbevallási célokra használják.

Az elsődleges értékcsökkenési profil minden könyvhöz hozzá van rendelve. A könyveknek alternatív vagy alternatív értékcsökkenési profiljuk is van, ha az ilyen típusú profilt kell alkalmazni. Ha automatikusan fel akarja venni a tárgyi eszköz könyvet az értékcsökkenési futtatásba, engedélyeznie kell az **Értékcsökkenés kiszámítása** lehetőséget. Ha ez a beállítás nincs engedélyezve egy eszközhöz, az értékcsökkenési javaslat kihagyja az eszközt.

Származtatott könyveket is beállíthat. A megadott származtatott tranzakciók az elsődleges tranzakció pontos másolataként lesznek feladva a származtatott könyvekkel szemben. Emiatt a származtatott tranzakciókat általában beszerzésekre és értékesítésekre állítják be, nem pedig értékcsökkenési tranzakciókra. További információkért lásd: [Értékmodellek beállítása](tasks/set-up-value-models.md).

## <a name="fixed-asset-posting-profiles"></a>Tárgyieszköz-feladási profilok

A könyvek beállítása után létrehozhatja a feladási profilt. A feladási profilt könyvenként kell meghatározni, de részletesebb szinten is meghatározható. Például meghatározhatja egy könyv és egy tárgyieszköz-csoport kombinációjának feladási profilját, vagy akár egyetlen tárgyieszköz-könyv profilját is. Alapértelmezés szerint a meghatározott főkönyvi számlákat a rendszer a tárgyieszköz-tranzakciókra használja.

Meg kell határoznia az értékesítési folyamatok során használt főkönyvi számlákat, mind a kivezetési eladásokat, mind a kivezetési selejteket. A kivezetés időpontjában az előzőleg feladott tárgyieszköz-tranzakciókat sztornózza a program az eredeti fiókból. A nettó összeget ezután áthelyezi a megfelelő számlára az eszköz értékesítésével kapcsolatos nyereséghez és veszteséghez. A tranzakciók helyes sztornírozása érdekében a vállalatnál használt különböző típusú tranzakciók mindegyikére be kell állítania számlákat. A fő számlának az eredeti számlának kell lennie, amit a feladási profilban adott meg a tranzakció típusaként, és a kivezetési számlán az ellenszámla tartalmazza a veszteséget és a nyereséget. Kivételt képez a nettó könyv szerinti érték. Ebben az esetben mind a fő-, mind az ellenszámlát be kell állítani a nyereségnek és a veszteségnek a kivezetési számlán. További információ: [Tárgyieszköz-feladási profilok beállítása](tasks/set-up-fixed-asset-posting-profiles.md)

## <a name="fixed-asset-groups"></a>Tárgyieszköz-csoportok

A tárgyi eszköz létrehozásakor a **Tárgyieszköz-csoport** az egyetlen kötelező mező. Az ebben a mezőben található érték határozza meg az eszköz számos tájékoztató mezőjének alapértelmezett értékét. A könyvek úgy vannak beállítva, hogy egy alapértelmezett könyv van egy csoport minden egyes eszközéhez hozzárendelve. Ezzel a módszerrel a könyvekhez beállított attribútumok lehetnek egy adott eszközcsoportra jellemzőek. Ezek az attribútumok tartalmazzák az élettartamot és az értékcsökkenési szabályt.

Különleges értékcsökkenési kereteket vagy rendkívüli értékcsökkenést is megadhat egy tárgyieszköz-csoport és egy könyv meghatározott kombinációjához. A különleges értékcsökkenési keretben meg kell adnia egy prioritást ahhoz, hogy meghatározza az engedmények számításának sorrendjét, ha több engedély van hozzárendelve egy könyvhöz. További információ: [Tárgyieszköz-csoportok beállítása](tasks/set-up-fixed-asset-groups.md).

## <a name="journal-names"></a>Naplónevek

A **Naplónevek** oldalon létre kell hoznia a naplóneveket, amelyeket Tárgyi eszközök naplójával használni kell. A **Naplótípus** mezőt **Tárgyi eszközök feladása** értékre kell állítani. Állítsa a **Bizonylatsorozatok** mezőt úgy, hogy a naplónevek a tárgyieszköz-naplóhoz legyenek használva. A tárgyieszköz-naplók ne használják a **Csak egy bizonylatszám** beállítást, mert egyedi bizonylatszám számos automatikus folyamathoz szükséges, például az átvitelekhez és a felosztásokhoz.

## <a name="fixed-asset-parameters"></a>Tárgyi eszköz paraméterei

Az utolsó lépés a tárgyi eszköz paramétereinek frissítése.

A **Tőkésítési küszöbérték** mező határozza meg az értékcsökkenés által érintett eszközöket. Ha egy beszerzési sor tárgyi eszközként van jelölve, de nem felel meg a megadott tőkésítési küszöbértéknek, a tárgyi eszközt a rendszer továbbra is létrehozza vagy frissíti, de az **Értékcsökkenés számítása** beállítása **Nem**. Ezért az értékcsökkenés nem vonatkozik automatikusa az eszközre az értékcsökkenési javaslatok részeként.

Egy fontos beállítás az **Értékcsökkenési kiigazítások automatikus létrehozása selejtezéskor**. Amikor ez a lehetőség **Igen**, ez a funkció automatikusan módosítja az eszköz értékcsökkenését az értékcsökkenési beállítások alapján az eszköz értékesítésének időpontjában. Készpénzfizetési engedmény levonására is van lehetőség a beszerzési összegből, amikor szállítói számla használatával tárgyi eszközt szerez be.

A **Beszerzési rendelések** gyorslapon beállíthatja, hogyan szeretné létrehozni az eszközöket a beszerzési folyamat részeként. Az első lehetőség neve a **Beszerzés modulból való tárgyieszköz-beszerzés engedélyezése**. Ha ez a beállítás **Igen**, az eszközbeszerzésre a számla feladásakor kerül sor. Ha ez a beállítás **Nem**, akkor is beletehet egy tárgyi eszközt egy beszerzési rendelésbe és számlába, de a beszerzés nem lesz feladva. A feladást külön lépésként kell elvégezni a Tárgyieszköz-naplóban. A **Tárgyi eszköz létrehozása termékbevételezés vagy számla feladása közben** beállítással a feladás során „menet közben” új tárgyi eszközt hozhat létre. Ezért az eszközt nem kell a tranzakció előtt tárgyi eszközként létrehozni. Az utolsó beállítási lehetőség, a **Tárgyi eszközök létrehozásának ellenőrzése a sorok bevitelekor** csak a beszerzési igényekre alkalmazható.

Beállíthatók okkódok a tárgyi eszköz módosításához vagy meghatározott tárgyieszköz-tranzakciókhoz.

Végül a **Számsorozatok** lapon megadhatja a tárgyi eszközök számsorozatait. A **Tárgyi eszköz** számsorozata felülbírálható a **Tárgyieszköz-csoport** számsorozata alapján, ha meg van adva.

További tudnivalókért lásd: [Tárgyi eszköz létrehozása](tasks/create-fixed-asset.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]