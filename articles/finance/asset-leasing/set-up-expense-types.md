---
title: Költségtípusok beállítása
description: Ez a cikk bemutatja, hogyan lehet beállítani a költségtípusokat a tárgyi eszközök eszköztípusában.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseExpenseTypeTable
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2019-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9978041059437d5d3556236c7ac02c00db93f933
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908038"
---
# <a name="set-up-expense-types"></a>Költségtípusok beállítása

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogyan lehet beállítani a költségtípusokat a tárgyi eszközök eszköztípusában. A fizetési ütemezés által nem képviselt költségeket *Költségnek* nevezzük. Ilyen költségek például a ingatlanadók, a közterület karbantartási költségei és a biztosítási költségek.

## <a name="add-an-administrative-expense-type"></a>Adminisztratív költségtípus hozzáadása

1. Nyissa meg az **Eszközlízing \> Beállítás \> Költségtípusok** lehetőséget.
2. Válassza az **Új** lehetőséget.
3. A megfelelő mezőkben adja meg az új költségtípust és a megnevezést.

## <a name="assign-accounts-to-administrative-costs"></a>Számlák hozzárendelése az adminisztrációs költségekhez

Ezután a számlákat a költségtípusokhoz kell társítani. Ezek a számlák a költségütemezési bejegyzésekkor lesznek terhelve és feladva. Az ellenszámla minden lízing **Működési költségfizetési ütemezés** sorában meg van adva.

1. Nyissa meg az **Eszközlízing \> Beállítás \> Eszközlízing paraméterei** lehetőséget.
2. A **Számlák** fül **Működési költségek** gyorslapján, a **Költségtípus** mezőjében válassza ki a költség típusát.
3. Válassza a **Hozzáadás** lehetőséget.
4. A **Könyv típusa** mezőben válassza ki azt a könyvtípust, amelyet az adminisztratív költségekhez szeretne kapcsolni.

    > [!NOTE]
    > Ugyanahhoz a költségszámlához több könyvtípus is csatolható.

5. A **Számlakód** mezőben adja meg, hogy a könyv mely lízingekre legyen alkalmazva:

    - **Mind** – Könyv alkalmazása az összes lízinghez.
    - **Csoport** – A könyv alkalmazása a lízingek egy adott csoportjára.
    - **Tábla** – Könyv alkalmazása egy adott lízinghez.

6. Ha kiválasztotta a **Csoport** vagy **Tábla** lehetőséget a **Számlakód** mezőben, válassza ki a számlaszámot vagy csoportszámot a **Számla-/Csoportszám** mezőben.
7. A megfelelő mezőkben válassza ki a pénzügyi lízing fő számláját és az operatív lízing fő számláját.

Miután elvégezte ezeket a lépéseket, hozzáadhatja a költségeket a kijelölt **Lízing részletei** lapján található **Működési költségek fizetési ütemezése** sorokon keresztül. Új lízing létrehozásakor költségeket is hozzáadhat.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
