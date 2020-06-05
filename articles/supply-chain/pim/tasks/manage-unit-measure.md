---
title: Mértékegység kezelése
description: Ez az eljárás bemutatja, hogyan lehet meghatározni egy mértékegységet, meghatározni fordításokat a mértékegységhez és a leírását, és átváltási szabályokat megadni a kapcsolódó egységekhez.
author: sorenva
manager: tfehr
ms.date: 07/08/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: abc02c73ae36975fa4872d638fe53cbf0379d15d
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383665"
---
# <a name="manage-unit-of-measure"></a>Mértékegység kezelése

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan lehet meghatározni egy mértékegységet, meghatározni fordításokat a mértékegységhez és a leírását, és átváltási szabályokat megadni a kapcsolódó egységekhez. Ezt a folyamatot bemutatóadatokkal vagy saját adatokkal is elvégezheti.

1. Kattintson ide: **Navigációs ablaktábla > Modulok > Termékinformációk kezelése > Termékek > Kiadott termékek karbantartása**.
2. Kattintson a **Mértékegységek** elemre.

## <a name="create-a-unit-of-measure"></a>Mértékegység létrehozása
1. Kattintson az **Új** elemre.
2. Írjon be egy értéket a **Mértékegység** mezőbe. Adja meg a mértékegységre történő hivatkozás során használt azonosítót vagy szimbólumot.  
3. Írjon egy értéket a **Leírás** mezőbe. Írjon be egy jellemző nevet a mértékegységnek a rendszer nyelvén.  
4. Válasszon ki egy lehetőséget a **Mértékegységosztály** mezőben. Az egységosztály határozza meg, hogy milyen logikai csoport, például terület, tömeg vagy mennyiség része a mértékegység.  
5. A **Tizedes pontosság** mezőben meg kell adnia egy számot. Adja meg a tizedesek számát, amelyre az átalakított mértékegységet kerekíteni kell a mértékegység számítás befejeztével.  
6. Kattintson a **Mentés** gombra.

## <a name="define-unit-translations"></a>Egység fordításainak meghatározása
1. A **Művelet panelen** kattintson az **Egységleírások** elemre.
2. Kattintson az **Új** elemre. Használjon egységes szöveget az azonosító fordítására vagy egy mértékegységet képviselő szimbólumot külső dokumentumokhoz vevő vagy szállító-specifikus nyelveken.  
3. A **Nyelv** mezőben adjon meg vagy válasszon ki egy értéket.
4. Írjon be egy értéket a **Szöveg** mezőbe.
5. Kattintson a **Mentés** gombra.
6. Zárja be a lapot.
7. A **Művelet panelen** kattintson az **Lefordított egységleírások** elemre.
8. Kattintson az **Új** elemre. Határozzon meg nyelvspecifikus leírásokat a mértékegységhez.  
9. A **Nyelv** mezőben adjon meg vagy válasszon ki egy értéket.
10. Írjon egy értéket a **Leírás** mezőbe.
11. Kattintson a **Mentés** gombra.
12. Zárja be a lapot.

## <a name="define-unit-conversion-rules"></a>Egység átváltási szabályok definiálása
1. A **Művelet panelen** kattintson az **Egységek átváltása** elemre. Adjon meg szabályokat a mértékegységek átalakításához más mértékegységekről és -re a kijelölt egységosztályban.  
2. Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.
3. A **Tényező** mezőben adjon meg egy számot. Átszámítási arány a forrás és a cél mértékegység között. Például a centiméterről méterre való átváltási arány 100, mert egy méter 100 centiméterből áll.  
4. A **Cél egység** mezőben adjon meg vagy válasszon ki egy értéket.
5. A **Kerekítés** mezőben válasszon egy lehetőséget. Határozza meg, hogyan kell kerekíteni a konvertált értéket.  
6. Kattintson az **OK** gombra.
7. Zárja be a lapot.

