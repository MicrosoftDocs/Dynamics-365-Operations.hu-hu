---
title: Vegyes azonosítótábla bevételezése
description: Ez a témakör azt írja le, hogyan kell használni a vegyes adatokat fogadó adatokat több cikkhez mobileszközzel történő regisztrálásra és létrehozására.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFAutoConfirm, WHSLicensePlate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 76ba316a5ed55902aed35acb4ef21623c7676b38
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907058"
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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]