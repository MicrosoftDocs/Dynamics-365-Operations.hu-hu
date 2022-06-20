---
title: Fürt beállítása
description: Ez a témakör ismerteti, hogyan lehet beállítani a fürt kitárolását, és hogyan lehet cikk-visszaigazolást alkalmazni a fürt kitárolása esetén.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSClusterProfile, WHSRFAutoConfirm, WHSWorkCluster
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3094649da2ce9a700a4d1cde236609013f4b9744
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862308"
---
# <a name="set-up-cluster-picking"></a>Fürt beállítása

[!include[banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan engedélyezheti a dolgozóknak, hogy mobileszközeiket használva fürtökbe csoportosítják a kitárolási munkát, így egyszerre több munkarendelés cikkeit is ki tudják válogatni egy helyről. Ezt nevezik *fürtkitárolás*.

## <a name="about-cluster-picking"></a>Fürt kitárolása

Miután munkarendelések ki vannak adva a raktárba, a dolgozó használható mobileszköz rendelje hozzá a rendelések a fürthöz. A fürt szervezi a dolgozó a kitárolási munka. A Munkarendelés hozzá van rendelve egy fürtből, amikor a dolgozó kell használni a fürt kitárolási a kitárolási munka a rendeléshez. A dolgozó egyéb kitárolási módokkal nem használható. A Munkarendelés van rendelve egy fürt tévedésből, ha a dolgozó kell a fürt felbontása és ezután hozza létre újból.

Szükség esetén dolgozó lehet átadni a fürt egy másik dolgozó. Ekkor a fürt állapotát megfelelt. Ha a dolgozó használja a mobileszköz annak jelzésére, hogy a kitárolási és betárolási munka befejeződött, akkor a kliensben meg kell erősíteni a szállítmányt vagy rakományt.

## <a name="enable-cluster-picking"></a>Fürtkitárolás engedélyezése

Ahhoz, hogy a fürtkitárolás, be kell állítania a következőket:

- **Fürtprofilok** – Adja meg, hogy automatikus legyen-e a fürtazonosítók előállítása, adja meg a használandó beosztások számát, azt, hogy mikor kell eltörni a fürtöket, és hogyan kell sorrendbe állítani és ellenőrizni a kitárolási munkát.

- **Munkasablonok** – A kitárolási munka fürthöz kitároláshoz létrehozásával meghatározása.

- **Helyirányelvek** – Adja meg, honnan kell kitárolni a cikkeket, és hová kell rakni őket.

- **Mobileszköz menüelemei** – A folyamatban lévő munkát, hogy fürtkitárolás által használandó mobileszköz menü elemeinek beállítása. Hozzá kell adnia majd menüelem mobileszköz menü, hogy a mobileszközök jelenik meg.

- **Raktárkezelési paraméterek** – Adja meg a fürtök azonosítóinak létrehozásához használandó számsorozat.

## <a name="set-up-a-cluster-profile"></a>Nyugtaprofil beállítása

Az okkód beállításához kövesse az alábbi lépéseket:

1. Kattintson a **Raktárkezelés** \> **Beállítás** \> **Mobileszköz** \> **Fürtprofilok** elemre.

1. Új mérő létrehozásához kattintson az **Új** elemre.

1. Kattintson a **Fürt létrehozása** elemre, és a **Fürtrendezés** alatt kattintson az **Új** elemre a fürt rendezési kritériumának beállításához. A rendezési kritérium sorrendjét, amelyben a dolgozó a kitárolási munka hajt végre. Tetszőleges számú intervallumot lehet létrehozni.

1. A **Sorszám** mezőben adjon meg egy számot, amely meghatározza a rendezési feltételek feldolgozási sorrendjét.

1. Az a **mezőnév** mezőben, válassza ki a mezőt, amely meghatározza a rendezést. Ha például bejelöli a **WMSLocationId** mezőben, a munka hely szerint lesznek rendezve.

1. A **Rendezés** mezőben az alábbi beállítások közül választhat:

| **Lehetőség**     | **Leírás**                                                                                                                                                                                                                    |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Növekvő**  | A kitárolási munka van a rendezési feltételek alapján növekvő sorrendben sorrendbe állítva. Ha például a **WMSLocationId** feltételeit, és a hely azonosítók rendezési mező 1, 2, 3, 4, akkor program kivesz 4 helyről először. |
| **Csökkenő** | A kitárolási munka van a rendezési feltételek alapján növekvő sorrendben sorrendbe állítva. Ha például a **WMSLocationId** feltételeit, és a hely azonosítók rendezési mező 1, 2, 3, 4, akkor program kivesz 1 helyről először. |

## <a name="item-confirmation"></a>Cikkmegerősítés

Ha a fürtkiválasztást alkalmazzák, a cikkek megerősítése döntő fontosságú a fürtökhöz hozzáadott cikkek ellenőrzéséhez. A fürtkiválasztás folyamán ellenőrizheti a fürtkiválasztás cikkeit. A beállítás a termékvonalkód-beállításon alapul.

### <a name="set-up-item-verification-with-cluster-picking"></a>Cikkellenőrzés beállítása a fürtkiválasztásnál

1. A mobileszköz menüpontjában nyissa meg a munkamegerősítés beállítási képernyőjét: **Raktárkezelés** \> **Raktárkezelés** \> **Beállítás** \> **Mobileszköz** \> **Mobileszköz menüpontjai**.

1. A mobileszköz menüpontjából nyissa meg a **Munkamegerősítés beállítását**. A **Termékmegerősítés** beállítás lehetővé teszi, hogy a mobileszközről ellenőrizze a készlet minden elemét a beolvasáskor.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]