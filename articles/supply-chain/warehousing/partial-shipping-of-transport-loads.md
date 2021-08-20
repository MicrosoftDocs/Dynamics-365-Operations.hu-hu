---
title: Szállítási rakomány részleges szállítása
description: Ez a témakör bemutatja, hogyan lehet szállítási rakományt részben szállítani és elhalasztani a szállítmányhoz tartozó kapacitás tervezését.
author: Mirzaab
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSTransportLoad
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 5ea844531314b4dd2ff3fa46d8f0b57d9c47059e684d677f06f8259b264d4a90
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6782299"
---
# <a name="partial-shipment-of-a-transport-load"></a>Szállítási rakomány részleges szállítása

[!include[banner](../includes/banner.md)]

Szállítási rakományok részleges szállításának beállításával lehet kezelni szállítmányokat akkor, ha a kapacitást nem lehet meghatározni mindaddig, amíg az összes értékesítési sor be nem került a szállítmányba. A folyamat így majd akkor zárható le, ha ismert a raklapok pontos száma. Így nem kell eldönteni, melyik raklapok kerüljenek mely szállítmányba, addig a pillanatig, amíg a szállítmányt fizikailag kirakodják az előkészített készletből.

Ez a funkció alternatívát kínál a merevebb szerkezet követéséhez, amelynél meg kell határozni, hogy melyik raklapot kell hozzárendelni melyik szállítmányhoz, mielőtt a kitárolási munkát vagy a betöltési munkát létre lehetne hozni. Ehelyett a felhasználók beállíthatják az egyes rakományok részleges szállítmány megerősítéséhez. Ezután e rakományoknál sor kerülhet a szállítási berakodásra. Így a szállítástervezési részleg anélkül tervezhet rakományokat, hogy figyelembe kellene venni az egyes szállítások kapacitását.

A berakodás időpontjában a dolgozók új szállítási terhelést határozhatnak meg, amelybe a raklap betölthető. Azt is megtehetik, hogy meglévő szállítási rakományt azonosítanak. Ez az adat mobileszközön keresztül rögzíthető. Ezért számos raktáros betölthet készletet ugyanabból a rakományból vagy különböző rakományokból azonos targoncára. A rakományok ezután részben vagy egészben szállíthatók.

> [!NOTE] 
> Készlet rakományból adott szállítási rakományba való betöltésére munkát kell létrehozni munkasablonban található betöltési osztály használatával. A szokásos **kitárolási** típusú kitárolási munka nem tölthető be szállítási rakományba, például teherautóba.

## <a name="set-up-transport-loads-for-partial-shipment"></a>Szállítási rakományok beállítása részleges szállításra

A rakományok részleges szállítására szolgáló beállítás a következő két eljárásból áll.

### <a name="set-the-loading-strategy"></a>A berakodási stratégia beállítása

A berakodási stratégia beállításával engedélyeznie kell a részleges berakodást. A berakodási stratégiát rakomány létrehozása után lehet beállítani.

1. Válassza a **Raktárkezelés** \> **Rakományok** \> **Minden rakomány** elemet.
2. Válasszon ki egy rakományt, majd kattintson a **Fejléc** lehetőségre.
3. A **Berakodási stratégia** mezőben válassza a **Részleges rakomány indítása engedélyezett** lehetőséget.

### <a name="create-a-menu-item-for-loading-of-transport-loads"></a>Hozzon létre menüpontot szállítási rakományok berakodásához

Létre kell hoznia egy új menüelemet, amely engedélyezi a szállítási rakományok berakodását. A szállítási rakomány lehetővé teszi a munkasorok csoportosítását egy vagy több rakományból. Minden, a szállítási rakományhoz hozzáadott elem ezután elszállítható mobil leolvasó használatával.

1. Válassza a **Raktárkezelés** \> **Beállítás** \> **Mobileszköz** \> **Mobileszköz menüpontjai** pontot.
2. Válassza az **Új** elemet, majd a **Mód** mezőben válassza a **Munka** elemet.
3. A **Meglévő munka használata** lehetőséget állítsa **Igen** értékre.
4. Az **Általános** lapon az **Irányítja** mezőben válassza a **Szállítási berakodás** elemet.
5. A szállítmány mobil képolvasón való megerősítéséhez az **Engedélyezett szállítási visszaigazolás típusa** mezőben válassza a **Szállítási rakomány** elemet.

## <a name="confirm-shipment-of-a-transport-load-from-the-client"></a>Az ügyféltől érkező szállítási rakományok szállításának visszaigazolása

A beállítás segítségével megerősítheti a teljes rakományt vagy részleges rakományt tartalmazó szállítmányok szállításának megerősítését.

1. Válassza a **Raktárkezelés** \> **Rakományok** \> **Szállítási rakományok** elemet.
2. A műveleti ablaktábla **Indítás és fogadás** lapján lévő **Megerősítés** csoportban válassza a **Szállítás** elemet.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]