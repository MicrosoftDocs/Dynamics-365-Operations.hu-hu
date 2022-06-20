---
title: Pénzügyi dimenziókészletek
description: Ez a cikk a pénzügyi dimenziókészleteket írja le, és a használatuk optimalizálásához nyújt tippeket.
author: yukonpeegs
ms.date: 03/07/2022
ms.topic: article
ems.prod: ''
ms.technology: ''
ms.search.form: DimensionFocus, LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom: 25871
ms.search.region: Global
ms.author: epegors
ms.search.validFrom: 2021-03-23
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 3d4c15504b2ad128493e1bafa36aed271c2ab6dc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864281"
---
# <a name="financial-dimension-sets"></a>Pénzügyi dimenziókészletek

[!include [banner](../includes/banner.md)]

Ez a cikk a pénzügyi dimenziókészleteket írja le, és a használatuk optimalizálásához nyújt tippeket.

A dimenziókészlet a pénzügyi dimenziók rendezett listája, amely a főkönyvi adatok felhasználó által definiált módon való összesítéséhez használható. A dimenziókészletek elsődleges használata a főkönyvi kivonat meghatározása.

Az egyetlen normál dimenziókészlet az a dimenziókészlet, amely csak a fő számlát tartalmazza.

A **Pénzügyi dimenziókészletek** lap a pénzügyi dimenziókészletek létrehozására és kezelésére használható.

## <a name="dimension-set-balances"></a>Dimenziókészlet-egyenlegek

A dimenziókészleteknek egyenlege lehet a pénzügyi dimenziók alapján. Az egyenlegek a főkönyvben léteznek, és a dimenziókészlet-definíción alapulnak. Az egyenlegek a főkönyvi adatokból vannak összegezve, ami javítja a beolvasási teljesítményüket (például főkönyvi kivonat létrehozása során).

## <a name="create-balances"></a>Egyenlegek létrehozása

Az **Egyenlegek létrehozása** gombbal inicializálhatja egy olyan dimenziókészlet egyenlegét, amely jelenleg nem rendelkezik egyenlegekkel.

> [!NOTE]
> Javasoljuk, hogy korlátozza az egyenleggel rendelkezik dimenziókészletek számát, mivel az egyenlegek frissítése minden főkönyvi feladási tevékenységet befolyásol.

## <a name="update-balances"></a>Egyenlegek módosítása

Az **Egyenlegek frissítése** gombra kattintva a legutóbbi főkönyvi feladási tevékenységet is beleveheti az egyenlegekbe. Az egyenlegfrissítések világos műveletek. Csak a legutóbbi frissítés óta történt főkönyvi feladási tevékenységet kell feldolgozniuk.

> [!NOTE]
> A főkönyvi kivonatok megjelenítése frissítést kényszerít ki annak a biztosítására, hogy a megjelenített egyenlegek aktuálisak legyenek. Fontolja meg egy ismétlődő kötegelt feladat használatát, hogy gyorsan frissüljenek a leggyakrabban használt dimenziókészletek. Ezzel a módszerrel minimálisra csökkentheti a főkönyvi kivonat felhasználók várakozási idejét.

## <a name="rebuild-balances"></a>Egyenlegek újbóli létrehozása

Az **Egyenlegek újbóli létrehozása** gomb használatával az egyenlegeket a nulláról hozza újra létre. Ily módon gondoskodhatja arról, hogy azok megegyeznek a főkönyvi adatokkal. Az egyenlegek újraépítése rengeteg számítás igényel, és általában nem szükséges.

> [!NOTE]
> Ha olyan forgatókönyve van, amely rendszeresen megköveteli az egyenlegek újraépítését, akkor forduljon az ügyfélszolgálathoz. Az ügyféltámogatás segítségével meghatározható, hogy az egyenlegek miért nem egyeznek meg a főkönyvi adatokkal.

## <a name="clear-balances"></a>Egyenlegek rendezése

Az **Egyenlegek törlése** gombbal eltávolíthatja az egyenlegeket, és leállíthatja a további frissítéseket. A dimenziókészlet már nem lesz hatással a főkönyvi feladási tevékenységekre.

## <a name="delete-a-dimension-set"></a>Dimenziókészlet törlése

Ne törölje és hozza létre **újra** a dimenziókészleteket bármilyen lehetséges megoldás formájában, hogy egy adott dimenziókészlet egyenlegének adataival megoldja a lehetséges problémákat. A dimenziókészletek újralétrehozása költséges. Ha további segítségre van szüksége a kérdésekhez, forduljon az ügyfélszolgálathoz. 


További információért lásd: [Pénzügyi dimenziók](financial-dimensions.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
