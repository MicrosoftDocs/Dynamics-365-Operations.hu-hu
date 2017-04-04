---
title: "Befektetett eszközök beállítása"
description: "Ez a témakör áttekintést nyújt a tárgyi eszközök modul beállításához."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13771
ms.assetid: 8be64197-fea1-4a34-8af2-d939919c28b1
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b41901d573e977a89fcd1a7c1ebf7185e162c654
ms.openlocfilehash: dde8053df96d03c8c8e52fa6d2fdf7f74e95ec92
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-fixed-assets"></a>Befektetett eszközök beállítása

Ez a témakör áttekintést nyújt a tárgyi eszközök modul beállításához.

<a name="overview"></a>Áttekintés
--------
A Tárgyi eszközök lehetőségen belül a paraméterek az általános viselkedést szabályozzák.

A tárgyieszköz-csoportok lehetővé teszik az eszközök csoportosítását, valamint alapértelmezett attribútumok meghatározását egy csoporthoz rendelt minden eszköz esetén. A tárgyieszköz-csoportokhoz a rendszer könyveket társít. A könyvek nyomon követik egy tárgyi eszköz időben változó pénzügyi értékét az értékcsökkenési profil értékcsökkenési konfigurációjának használatával.

A tárgyi eszközök létrehozásukkor egy cikkcsoporthoz társulnak. Alapértelmezés szerint a tárgyieszköz-csoporthoz rendelt könyveket a tárgyi eszközhöz társítja a rendszer. A főkönyvbe történő feladásra konfigurált könyveket a rendszer egy feladási profillal társítja. A főkönyvi számlákat a feladási profilban határozza meg a rendszer könyvenként, és a tárgyieszköz-tranzakciók feladásakor használja őket. 

![TárgyiEszközÖsszetevőkKép](./media/FAComponents_Updated.png)

## <a name="depreciation-profiles"></a>Értékcsökkenési profilok
Először az értékcsökkenési profilokat kell beállítani. Az értékcsökkenési profilban konfigurálhatja, hogyan történjen egy tárgyi eszköz időbeli értékcsökkenése. Meg kell adnia az értékcsökkenési módszert, az értékcsökkenési évet (naptári vagy pénzügyi év), valamint az értékcsökkenés gyakoriságát.

## <a name="books"></a>Könyvek
Az értékcsökkenési profilok beállítása után létre kell hoznia az eszközökhöz szükséges könyveket. Minden könyv egy tárgyi eszköz független pénzügyi életciklusát követi nyomon. A könyveket konfigurálhatja, hogy feladják a kapcsolódó tranzakciókat a főkönyvbe. Ez a beállítás az alapértelmezett beállítás oka a vállalati pénzügyi jelentések szokás használni. Könyveket, amelyek a főkönyvi könyvelést nem csak a tárgyi eszközök analitikus könyvel, és általában adóbevallási célokra használják.

Az elsődleges értékcsökkenési profil minden könyvhöz hozzá van rendelve. A könyveknek alternatív vagy alternatív értékcsökkenési profiljuk is van, ha az ilyen típusú profilt kell alkalmazni. Ha automatikusan fel akarja venni a tárgyi eszköz könyvet az értékcsökkenési futtatásba, engedélyeznie kell az Értékcsökkenés kiszámítása lehetőséget. Ha a beállítás nincs bejelölve, az eszköz, értékcsökkenési javaslat átugorja az eszköz.

Származtatott könyveket is beállíthat. A megadott származtatott tranzakciók az elsődleges tranzakció pontos másolataként lesznek feladva a származtatott könyvekkel szemben. Emiatt a származtatott tranzakciókat általában beszerzésekre és értékesítésekre állítják be, nem pedig értékcsökkenési tranzakciókra.

## <a name="fixed-asset-posting-profiles"></a>Tárgyieszköz-feladási profilok
A könyvek beállítása után létrehozhatja a feladási profilt. A feladási profilt könyvenként kell meghatározni, de részletesebb szinten is meghatározható. Például meghatározhatja egy könyv és egy tárgyieszköz-csoport kombinációjának feladási profilját, vagy akár egyetlen tárgyieszköz-könyv profilját is. Alapértelmezés szerint a meghatározott főkönyvi számlákat a rendszer a tárgyieszköz-tranzakciókra használja.

Meg kell határoznia az értékesítési folyamatok során használt főkönyvi számlákat, mind a kivezetési eladásokat, mind a kivezetési selejteket. A kivezetés időpontjában az előzőleg feladott tárgyieszköz-tranzakciókat sztornózza a program az eredeti fiókból, és áthelyezi a nettó összeget a megfelelő számlára az eszköz értékesítésével kapcsolatos nyereséghez és veszteséghez. A tranzakciók helyes sztornírozása érdekében a vállalatnál használt különböző típusú tranzakciók mindegyikére be kell állítania számlákat. A fő számlának az eredeti számlának kell lennie, amit a feladási profilban adott meg a tranzakció típusaként, és a kivezetési számlán az ellenszámla tartalmazza a veszteséget és a nyereséget. Kivételt képez a nettó könyv szerinti érték. Ebben az esetben mind a fő-, mind az ellenszámlát be kell állítani a nyereségnek és a veszteségnek a kivezetési számlán.

## <a name="fixed-asset-groups"></a>Tárgyieszköz-csoportok
Tárgyi eszköz létrehozásakor a Tárgyieszköz-csoport az egyetlen kötelező mező. Az ebben a mezőben található érték határozza meg az eszköz számos tájékoztató mezőjének alapértelmezett értékét. A könyvek úgy vannak beállítva, hogy egy alapértelmezett könyv van egy csoport minden egyes eszközéhez hozzárendelve. Ezután beállíthatja azon könyvek attribútumait, amelyek egy eszközcsoportra vonatkoznak, például az Élettartam és az Értékcsökkenési szabály.

Különleges értékcsökkenési kereteket vagy rendkívüli értékcsökkenést is megadhat egy tárgyieszköz-csoport és egy könyv meghatározott kombinációjához. A különleges értékcsökkenési keretben meg kell adnia egy prioritást ahhoz, hogy meghatározza az engedmények számításának sorrendjét, ha több engedély van hozzárendelve egy könyvhöz.

## <a name="fixed-asset-parameters"></a>Tárgyi eszköz paraméterei
Az utolsó lépés a tárgyi eszköz paramétereinek frissítése.

A Tőkésítési küszöbérték mező határozza meg az értékcsökkenés által érintett eszközöket. Ha a beszerzési sor egy befektetett eszközt választotta, de nem felel meg a megadott tőkésítési küszöbérték, tárgyi eszköz továbbra is létrehozva vagy frissítve, de az értékcsökkenési számítás beállítás értéke nem. Ezért az eszköz nem lehet automatikusan értékcsökkenésének részeként az értékcsökkenési javaslatot.

Fontos beállítás az Értékcsökkenési kiigazítások automatikus létrehozása selejtezéskor. Amikor ez a lehetőség Igen, ez a funkció automatikusan módosítja az eszköz értékcsökkenését az értékcsökkenési beállítások alapján az eszköz értékesítésének időpontjában. Készpénzfizetési engedmény levonására is van lehetőség a beszerzési összegből, amikor szállítói számla használatával tárgyi eszközt szerez be.

A Beszerzési rendelések gyorslapon beállíthatja, hogyan szeretné létrehozni az eszközöket a beszerzési folyamat részeként. Az első lehetőség a Beszerzés modulból való tárgyieszköz-beszerzés engedélyezése. Ha ez a beállítás Igen, az eszközbeszerzésre a számla feladásakor kerül sor. Nem állítja ezt a beállítást, ha a befektetett eszköz beszerzési megrendelés és számla továbbra is elhelyezhetjük, de megszerzése nem lehet feladni. A feladást külön lépésként kell elvégezni a tárgyieszköz-naplóban. Szállítólevél vagy számla lehetőséget a létrehozása eszköz lehetővé teszi, hogy hozzon létre egy új eszköz "menet közben" feladás során, hogy nem kell beállítani a tranzakció előtt tárgyi eszközként. Az utolsó beállítási lehetőség, a Tárgyi eszközök létrehozásának ellenőrzése a sorok bevitelekor csak a beszerzési igényekre alkalmazható.

Beállíthatók okkódok a tárgyi eszköz módosításához vagy meghatározott tárgyieszköz-tranzakciókhoz.

Végül a Számsorozatok lapon megadhatja a tárgyi eszközök számsorozatait. A Tárgyi eszköz számsorozata felülbírálható a Tárgyieszköz-csoport számsorozata alapján, ha meg van adva.


