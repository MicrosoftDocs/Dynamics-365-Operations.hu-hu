---
title: Nem várt különbség a kérés- és munkamenetadatok között a tesztelés során
description: Váratlan különbség áll elő a raktári alkalmazás feladat-ellenőrzési eredményei között a kérés- és munkamenetadatok között.
author: mamuszal
ms.date: 03/11/2022
ms.topic: troubleshooting
ms.search.form: WHSValidatorRunInstance_executeRun
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mamuszal
ms.search.validFrom: 2022-03-11
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: da8f0506a76b0d0cc02bfc2e1bff01b4ddccb578
ms.sourcegitcommit: 941119133be1765f653d5d5270dfdf58466e1d07
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/17/2022
ms.locfileid: "8456953"
---
# <a name="unexpected-difference-between-request-and-session-data-during-testing"></a>Nem várt különbség a kérés- és munkamenetadatok között a tesztelés során

Hibakód: WarehouseKereséseDeviceRequestInputValidationError

## <a name="symptoms"></a>Tünetek

A raktári alkalmazás feladat-ellenőrzési [keretrendszerének használata esetén](/dynamics365-release-plan/2019wave2/dynamics365-supply-chain-management/warehouse-app-task-validation-rsat) a validator a következő hibaüzenetet adja vissza:

> Váratlan különbség a kérés- és munkamenetadatok között. A raktári mobileszköz XML-protokollja megsértve. REQUEST_XML_TAMPERING

## <a name="cause"></a>Ok

A hiba akkor fordul elő, amikor a tesztfuttatásban sikeresen futó utolsó lépés kimenete nem egyezik meg a következő lépés rögzített bemenettel. Ez a helyzet akkor merülhet fel, ha a feladat-érvényesítő nem használja egy előző lépés kimenetét egy következő lépés bemeneteként. Ehelyett a rögzített XML-adatokat használja minden egyes lépéshez.

A legtöbb esetben a hiba a feladat újrafuttatása során fordul elő, de a teszthez szükség van néhány olyan rekordra, amelyet ugyanannak a feladatnak a korábbi futtatása módosított vagy eltávolított.

## <a name="resolution"></a>Megoldás

A raktári alkalmazás feladat-ellenőrzési tesztje nem idempotent művelet, hanem a mögöttes adatokat módosítja. Emiatt előfordulhat, hogy a feladat újrafuttatása előtt alaphelyzetbe kell állítania a megfelelő adatokat.

1. Tekintse át az utolsó sikeres tesztlépés kimeneti XML-fájlját annak megállapításához, hogy hol maradt le a teszt.
1. Vizsgálja meg a tesztet, és győződjön meg arról, hogy az összes szükséges értékesítési rendelés, átátviteli rendelés, munkafejléc és egyéb rekord még mindig jelen van és a várt állapotban van.
1. A hiányzó vagy módosított rekordok újra létrehozása vagy szerkesztése. Másik lehetőségként hozzon létre új tesztbeállítást, és úgy tervezse meg a tesztet, hogy érvényes, meglévő rekordokat használjon.
