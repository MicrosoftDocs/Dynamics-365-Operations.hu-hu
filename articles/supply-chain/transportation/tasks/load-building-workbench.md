---
title: Rakomány-összeállítási munkaterület
description: Ez a témakör azt mutatja be, hogyan lehet használni a rakományépítő munkaterületet.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSLoadBuildWorkbench,TMSLoadBuildTemplateCreate,TMSLoadBuildStrategy,TMSLoadBuildTemplateApply
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 480006a6d091acdf5c88fdbf0d9e625088d660d4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247238"
---
# <a name="load-building-workbench"></a>Rakomány-összeállítási munkaterület

A rakomány-összeállítási munkaterületen a rakományok létrehozásakor használhatók a rakomány-összeállítási stratégiák.

## <a name="create-a-load-building-strategy"></a>Rakomány-összeállítási stratégia létrehozása

A rakomány-összeállítási stratégiák a rakományok automatikus összeállítására használható. Ez a lehetőség a következő helyzetekben előnyös lehet:

- Ha rendszeresen szállít egy meghatározott termékeket, akkor a rakománystratégiák segítségével időt takaríthat meg, mivel nem kell minden alkalommal ugyanazt a rakományt összeállítani.
- Ha a hatékonyság maximalizálása érdekében el szeretné kerülni a félig tele rakományokat, akkor a rakománystratégiák segítségével a lehető legjobban feltöltheti a rakományokat.

A `TMSLoadBuildingVolumeStrategy` nevű rakomány-összeállítási stratégiaosztály biztosítja a *Térfogaton alapuló rakomány-összeállítási stratégia* nevű rakomány-összeállítási stratégiát. Ez a stratégia lehetővé teszi a rakomány-sablonban megadott maximális magasság- és súlyértékek használatát, vagy a beállítások felülírását új értékek megadásával. Ez a stratégia az egyetlen olyan stratégia, amely beépítetten érkezik. (Előfordulhat azonban, hogy valamilyen egyéni stratégiát tartalmaz.)

A beépített *Térfogaton alapuló rakomány-összeállítási stratégia* stratégia használatához válassza a **Rakomány-összeállítási stratégia** mezőt a **Rakomány-összeállítási munkaterület** oldalon (**Szállításkezelés &gt; Tervezés &gt; Rakomány-összeállítási munkaterület**).

Rakomány-összeállítási stratégia létrehozásához kövesse az alábbi lépéseket.

1. Lépjen a **Szállításkezelés &gt; Beállítás &gt; Rakomány-összeállítás &gt; Rakomány-összeállítási stratégiák** pontra.
1. A műveleti ablaktáblán válassza az **Osztálylista létrehozása** lehetőséget, és győződjön meg arról, hogy az összes rendelkezésre álló osztály legfrissebb verzióival rendelkezik.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Adjon meg egy egyedi nevet a stratégiának, válassza ki a rakomány-összeállítási stratégiai osztályt, és adjon meg egy leírást.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A Műveleti panelen válassza a **Paraméterek** elemet.
1. A **Rakomány-összeállítási stratégia paraméterei** oldalon válassza a **Térfogat-kapacitás** lehetőséget a listából, majd az **Érték** mezőben adja meg a rakomány teljes térfogat-kapacitásának százalékát, amelyre az új rakomány-összeállítási stratégiát alkalmazni kell.
1. Válassza a **Súlykapacitás** lehetőséget a listából, majd az **Érték** mezőben adja meg a rakomány teljes súlykapacitásának százalékát, amelyre az új rakomány-összeállítási stratégiát alkalmazni kell.
1. Zárja be a **Rakomány-összeállítási stratégia paraméterei** oldalt.
1. Zárja be a **Rakomány-összeállítási stratégiák** oldalt.

Ezután hozzárendelheti a rakomány-összeállítási stratégiát egy rakomány-összeállítási sablonhoz. Azt is megteheti, hogy közvetlenül a rakomány-összeállítási munkaterületen is használhatja.

## <a name="use-a-load-building-strategy-in-the-load-building-workbench"></a>Rakomány-összeállítási stratégia használata a rakomány-összeállítási munkaterületen

1. Ugorjon a **Szállításkezelés &gt; Tervezés &gt; Rakomány-összeállítási munkaterület** elemre.
1. Tegye a következők egyikét:

    - Válassza ki a stratégiát a **Rakomány-összeállítási stratégia** mezőben.
    - Ha már meghatározta a rakomány-összeállítási sablont, és hozzárendelte a rakomány-összeállítási stratégiát, a műveleti panel **Sablonok kezelése** lapján válassza a **Sablon alkalmazása** lehetőséget. Majd a **Rakomány-összeállítási sablon alkalmazása** legördülő párbeszédpanelen válasszon egy sablont a **Rakomány-összeállítási sablon neve** mezőben.

1. A **Rakománysablonok sorrendje** gyorslapon válasszon egy vagy több [rakománysablont](load-template.md). A munkaterület az itt megadott sorrendben próbálja meg a rakományt az ilyen típusú tárolókba elhelyezni. Általában a lista tetején kell elhelyezni a legkisebb tárolókat, hogy a lehető legkisebb tartály legyen először kiválasztva.
1. A Művelet ablaktáblán válassza ki a **Rakományok javaslása** elemet.
1. Tekintse át a javasolt rakományokat és a javasolt rakománysorokat.
1. A művelet ablaktáblán válassza a **Rakományok létrehozása** lehetőséget, ha a **Javasolt rakománysorok** gyorslapjon szereplő forrásdokumentum-sorokon alapuló rakományokat kíván létrehozni.
1. Zárja be a **Rakomány-összeállítási munkaterület** oldalt.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]