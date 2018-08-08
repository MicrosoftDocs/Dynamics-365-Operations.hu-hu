---
title: "Vegyes azonosítótábla bevételezése"
description: "Ez a témakör leírja, hogyan használható a vegyes azonosítótáblák bevételezése munka regisztrálásához és létrehozásához több cikkhez, mobileszközzel."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ec3fdff6e1118f4a4ef4146d315fe8c58664f453
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="mixed-license-plate-receiving"></a>Vegyes azonosítótábla bevételezése

[!include [banner](../includes/banner.md)]

A vegyes azonosítótábla bevételezése teszi lehetővé több cikkből álló azonosítótábla létrehozását a betárolási munka regisztrálása és létrehozása előtt. 

A több cikkből álló azonosítótáblát nem kell felosztani a bevételezési tárolónál minden egyes cikk regisztrálásához. 

Ha egy cikkel kapcsolatos folyamatot használunk a forrásbizonylat sorainak azonosítására, lehetőség van vonalkódok beolvasására a cikkellenőrzéskor. Ha a vonalkódhoz konfigurálva van mennyiség és mértékegység, a rendszer automatikusan hozzáadja a cikket és a mennyiséget a vegyes azonosítótáblához, majd ismét megjeleníti a képernyőt egy másik cikk beolvasásához. Ez lehetővé teszi, hogy gyorsan beolvassa az elemeket anélkül, hogy mindegyik lépésénél el kellene végezni a megerősítést. 

A vegyes azonosítótábla bevételezésének folyamatában megjelenítheti az azonosítótáblára már beolvasott elemek listáját, és módosíthatja vagy javíthatja a cikkek mennyiségét.

## <a name="where-it-applies"></a>Alkalmazási kör

A vegyes azonosítótáblák bevételezése mobileszközös fogadási folyamat munka regisztrálásához és létrehozásához több sorhoz/cikkhez, egy időben. Akkor hasznos, ha több cikkből álló bejövő azonosítótáblákat bevételez. 

## <a name="how-to-set-up-mixed-license-plate-receiving"></a>Vegyes azonosítótáblák bevételezésének beállítása
A vegyes azonosítótábla bevételezése mobileszköz-menüelemként van beállítva.

Létre kell hoznia egy új menüelemet olyan munka móddal, amely nem használ meglévő munkát, és a következő módszerek valamelyikét használja:

- Vegyes azonosítótábla bevételezése
- Vegyes azonosítótábla bevételezése és eltárolása

A forrásbizonylat sorainak azonosítására szolgáló beállítások a következők: beszerzési rendelés – cikk, beszerzésirendelés-sor, visszárurendelés, átmozgatási rendelés – cikk és átmozgatási rendelés sora. Ezek a beállítások módosíthatják a bevételezési rendelést vagy egyetlen azonosítótáblát. Az utolsó beállítás a rakománycikk szerint. Több cikket lehet hozzáadni egy azonosítótáblához, de több rakomány között nem lehet váltani.

