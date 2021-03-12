---
title: Készlet mozgatásának engedélyezése társított munkával a Raktárkezelésben
description: Ez a témakör leírja, hogyan állíthatja be és alkalmazhatja a darabkitárolás megerősítését mobileszközről.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorker
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3e7d0cdace306e6f266dd690db2c9855ea75009e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970331"
---
# <a name="movement-of-inventory-with-associated-work-in-warehouse-management"></a>Készlet mozgatásának engedélyezése társított munkával a Raktárkezelésben

[!include [banner](../includes/banner.md)]

A készletmozgás használatával megadhatja, hogy melyik raktárosok számára engedélyezett a lefoglalt készlet mozgatása. Ez rugalmasságot biztosít a szabályozott raktárakban, mert lehetőséget nyújt úgy dönteni, hogy nem engedélyezi új kitárolási hely választását a dolgozó számára a már létrehozott kitárolási munkákhoz. Emellett lehetővé teszi a raktárvezető számára annak a kontrollját, hogy egyes kevésbé tapasztalt dolgozók milyen lehetőségekkel rendelkezzenek.

A raktári dolgozók napi tevékenységének kezelését érintő rugalmasság például az alábbi esetekben lehet hasznos:

## <a name="scenario-1"></a>1. eset
A vállalatnak van egy viszonylag kis fogadóterülete, amely zsúfolva van betárolásra váró raklapokkal és dobozokkal. Az aktuális napon nagy szállítmány várható, ezért a bevételezési adminisztrátor úgy dönt, hogy kiüríti a beérkezési területet úgy, hogy a raklapok egy részét egy másodlagos bejövő előkészítő területre helyezi át.

## <a name="scenario-2"></a>2. eset
Egy tapasztalt raktári dolgozó észreveszi, hogy bizonyos cikkeket egy helyre lehetne konszolidálni ahelyett, hogy három közeli helyen tárolnák őket, mindhárom helyen kis mennyiségben. A dolgozó konszolidálni szeretné a mennyiséget azzal, hogy mindhárom helyről egy helyre viszi a cikkeket, azonos azonosítótábla alá.

## <a name="scenario-3"></a>3. eset
Egy raklap szállításra vár egy előkészítő helyen, például a STAGE01 helyen, amely a BAYDOOR01 közelében van. Azonban a tervek módosítása miatt a teherautó érkezése a BAYDOOR04 területre van ütemezve. A szállítási adminisztrátor tud erről, és biztosítania kell, hogy a teherautónak ne kelljen várnia a berakodásra a STAGE01 területről. A szállítási adminisztrátor úgy dönt, hogy a szállítmányhoz tartozó cikkeket át kell helyezni a STAGE01 területről az új célhoz közelebbi STAGE04 területre.

### <a name="current-limitations"></a>Jelenlegi korlátozások

Az áthelyezhető munkafoglalások a következőkre korlátoznak: értékesítési rendelés, átmozgatási rendelés kiadása, átmozgatási rendelés – bevételezés, beszerzési rendelés és feltöltési munka.

A cikkek áthelyezése korlátozott a munkasorok felosztásának megakadályozása érdekében. Ez azt jelenti, hogy ha van egy munkasorunk 100 darabra az A cikkből a Loc1 helyről, nem lehet csak 30 darabot áthelyezni az A cikkből innen egy másik helyre. Ez a meglévő munkasor felosztását eredményezné 30 és 70 cikkre, mivel most már más a hely.

Az előkészítési esetekben, amikor az azonosítótábla, amelyről vagy amelyre áthelyezzük a cikkeket, a munkarendelés cél azonosítótáblájaként van beállítva, csak a teljes azonosítótábla mozgása engedélyezett, hogy ne legyen felbontva a cél azonosítótábla.
Jelenleg csak az ad hoc mozgás támogatott. Ez azt jelenti, hogy nem lehet mozgatni a foglalt készletet a mozgás sablon szerint mobileszközmenü-elemekkel.

### <a name="set-up-permission-to-move-reserved-inventory-for-individual-workers"></a>Engedély beállítása az egyes dolgozók számára a lefoglalt készlet mozgatásához

Annak a dolgozónak az esetében, akinek a számára engedélyezni kell a foglalt készlet mozgatását, jelölje be a **Készlet mozgatásának engedélyezése társított munkával** jelölőnégyzetet a következő helyen: **Raktárkezelés** > **Beállítás** > **Dolgozó**.  

### <a name="backported"></a>Visszaportolás

Ezt a funkciót visszaportoltuk a Microsoft Dynamics AX 2012 R3 verzióba, és elérhető lesz az CU12 részeként.
Önállóan is letölthető a 3192548 KB-számon. 

