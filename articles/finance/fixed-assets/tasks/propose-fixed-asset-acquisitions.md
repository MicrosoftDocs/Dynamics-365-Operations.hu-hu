---
title: Javaslat tárgyieszköz-beszerzésekre
description: Ez a témakör azt ismerteti, hogyan lehet tárgyi eszközt szerezni a tárgyieszköz-napló beszerzési javaslatának használatával.
author: moaamer
ms.date: 03/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 35d2171dc828cb0227f310e81be1d3e3359f41c5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909069"
---
# <a name="propose-fixed-asset-acquisitions"></a>Javaslat tárgyieszköz-beszerzésekre

[!include [banner](../../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet tárgyi eszközt szerezni a tárgyieszköz-napló beszerzési javaslatának használatával. Ez a könyvelői szerepkört és a bemutató adatokat használja a USMF jogi személyhez. Ha tárgyi eszköz javaslati naplón keresztül kíván beszerezni egy tárgyi eszközt, először létre kell hoznia a tárgyi eszköz rekordját, majd meg kell határoznia a beszerzési árat a tárgyi eszköz könyvében.

## <a name="create-an-asset-acquisition-proposal"></a>Eszközbeszerzési javaslat létrehozása

Eszközbeszerzési javaslat létrehozásához végezze el a következő lépéseket. 

1. A navigációs ablaktáblán nyissa meg a **Modulok > Tárgyi eszközök > Naplóbejegyzések > Tárgyi eszközök naplója** elemet.
2. Válassza az **Új** lehetőséget.
3. A **Név** mezőben adjon meg vagy válasszon ki egy értéket.
4. A Műveleti ablaktáblán válassza a **Sorok** elemet.
5. Válassza a **Javaslatok** lehetőséget.
6. Válassza a **Beszerzési javaslat** lehetőséget.
7. Válassza ki a **Szűrő** elemet. A korábbi értékek törléséhez kattintson az **Alaphelyzetbe állítás** pontra.
8. Válassza ki a **Tárgyieszköz-szám** elnevezésű sort.
9. A **Feltétel** mezőben adjon meg vagy válasszon ki egy értéket. Állítsa be a javaslat kapcsán beszerezni kívánt tárgyi eszközökre vonatkozó további feltételeket.  
10. A panelből való kilépéshez nyomja meg kétszer az **OK** gombot.
- Erősítse meg a tranzakciós sorok létrehozását.  
- A beszerzési javaslat kizárólag az értékmodellben beállított beszerzési dátummal és beszerzési árral rendelkező tárgyi eszközöket veszi figyelembe.  
11. Az oldalon válassza a **Könyvek** lapot.
12. Válassza a **Feladás** parancsot.

## <a name="include-default-financial-dimensions-in-an-acquisition-proposal"></a>Alapértelmezett pénzügyi dimenziók beépítése egy beszerzési javaslatba

A beszerzési tranzakció Excel-bővítményekkel is létrehozható a **Tárgyi eszközök > Naplórekordok > Tárgyieszköz napló** menüben. Hozzon létre egy új naplót, és lépjen a lap **Sorok** szakaszára, és válassza az Excel ikont, majd válasszon egy Tárgyieszköznapló-sort. A rendszer létrehoz és megnyit egy naplósorokat ábrázoló Excel-sablont. Hozzáadhatja a sablonhoz hozzáadott naplósorok adatait, majd ezeket az adatokat újra közzéteheti a rendszerben. 

Ha alapértelmezett dimenziókat állítottak be a kijelölt tárgyieszköz-könyvhöz és az Excel-sablonban megadott megfelelő tárgyi eszközökhöz, akkor a program az alapértelmezett pénzügyi dimenziókat az eszközkönyv törzsadatainak alapján nevezi meg, amikor a naplót közzéteszik az Excelből a rendszerbe. Ha a tárgyieszköz-napló Excel-bővítményből való közzétételekor automatikusan szerepeltetni szeretné a pénzügyi dimenziókat, az alapértelmezett dimenziókat előzetesen be kell állítani.  


[!INCLUDE [footer-include](../../../includes/footer-banner.md)]
