---
title: A Commerce Katalógusok B2B testreszabásokkal kapcsolatos extensibility hatása
description: Ez a témakör a Commerce Catalogs for B2B funkció extensibility hatását ismerteti a következőben:Microsoft Dynamics 365 Commerce
author: ashishmsft
ms.date: 04/28/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: aff333bfe8003233dd5d8181aa8c5dd7eaeffcd0
ms.sourcegitcommit: 0abc777986112ea2332f5bf0e815b303b952356c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/29/2022
ms.locfileid: "8657195"
---
# <a name="extensibility-impact-of-commerce-catalogs-for-b2b-customizations"></a>A Commerce Katalógusok B2B testreszabásokkal kapcsolatos extensibility hatása

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ez a témakör a Commerce Catalogs for B2B **funkció extensibility** hatását ismerteti a következőben:Microsoft Dynamics 365 Commerce

Ha a katalógus kontextusát kiterjeszti az egyedi helyzetekre, lehet, hogy frissíteni kell a testreszabott beállításokat. Ez a frissítés azt a szokásos folyamatot követi, amit a vevőknek végre kell követniük, mert előfordulhat, hogy testreszabott szolgáltatásaik nem támogatják automatikusan a legújabb funkciókat a frissítés után. Ha a testreszabások új funkciókat vagy hibajavításokat tartalmaznak a tapasztalataikban, akkor javasoljuk, hogy ennek megfelelően frissítse a testreszabási kódot. Ez a frissítés hasonlít a Microsoft által a core kódra esetleg végrehajtott módosításokra.

Tekintse át a testreszabási eseteket, amelyek alapján eldönthető, hogy frissíteni kell-e a testreszabásokat.

> [!NOTE]
> - Minden árusítási alkalmazásprogramozási felületnek katalógusban kell lennie. Emiatt fontos, hogy át kell adni a **CatalogID paramétert**.
> - Az alapértelmezett katalógus (**CatalogID0**=**·**) nem érvényes katalógus a bejelentkezett vállalathoz (B2B) felhasználók számára. Emiatt minden "0" értékű vagy alapértelmezett értéket használó API-hívás sikertelen lesz, mert a webhely felhasználóinak nincs hozzáférésük a 0 katalógushoz. A megfelelő tapasztalat érdekében frissíteni kell a vevő API-hívásait, hogy azok át tudják adni a katalógusválasztóban kiválasztott katalógusazonosítót. Ha alapértelmezett értéket használ, és a felhasználó átváltja a katalógusokat, akkor a webhelynek meg kell adnia a kijelölt katalógus adatait. Ennek megfelelően az alapvető Commerce-kódból futtatott API-knak megfelelően az testreszabott API-knak át kell haladni a kiválasztott katalóguson.

A következő testreszabási esetek fejlesztői frissítéseket igényelnek:

- **1. eset:** A [vevő](e-commerce-extensibility/data-actions.md) bemutatja saját adat műveletét, amely egy termékhez kapcsolódó API-t vagy adat műveletet hívja meg. A következő frissítési lépések szükségesek:

    1. Ha az adat művelete közvetlen API-hívást használ, frissítse úgy az adat műveletet, hogy az a katalógusazonosítót átadja, ahogy az a következő példaként látható.

        ![A katalógusazonosítót azonosító frissített adat művelete](./media/customization1_a.png)

    1. Ha az adat művelet más, a testreszabott termékekkel kapcsolatos adat műveletet hív meg, akkor a kódot frissíteni kell, hogy néhány új paramétert, **például a requestContext paramétert is át tudja haladni**. Az **requestContext** paraméterrel lehet beolvasni az aktuális katalógusazonosítót, amint azt a következő példa is mutatja.

        ![Az új paramétert adva adatokat adva frissített adatok művelete.](./media/customization1_b.png)

- **2. eset:** Egy vevő [felülbírált adat művelete van](e-commerce-extensibility/data-action-overrides.md). A következő frissítési lépés szükséges:

    - Az adat művelet frissítése az 1. esetnek megfelelően

- **3. eset:** A vevőnek van egy nézetkiterjesztése, egy forgatókönyv-hosszabbító modulja vagy egy másik modulja, [amely](e-commerce-extensibility/modules-overview.md#clone-a-module-library-module) API-k vagy adatműveletek hívásait tartalmazza. A következő frissítési lépés szükséges:

    - A kód frissítése az 1. esetnek megfelelő módon, az alábbi példaként látható módon.

       ![Módosított kód, amely az új paramétert tartalmazza.](./media/customization3.png)

- **4. eset:** Egy vevő **getById API-hívást** használ. A következő frissítési lépés szükséges:

    - Váltson ehelyett **a getByIds** API-hívásra, mivel a getById **APT hívásnak vannak korlátai,** ezért nem támogatja a katalógus ismertségét.

- **5. eset:** Egy vevő egy adat művelete, amely több, különböző katalógusból származó termék adatait olvassa be. A következő frissítési lépés szükséges:

    - Az API-hívások felosztása katalógusazonosító szerint. Például a bevásárlókocsi API-k esetében a kosár különböző katalógusok termékeit tartalmazhatja. A terméksorokat katalógusazonosító szerint kell csoportosíteni, és az egyes katalógusok API-ját külön kell hívni, mint azt az alábbi példa mutatja.

        ![Frissített adat művelet, amely katalógusazonosító szerint csoportba tartozó terméksorokat tartalmaz.](./media/customization5.png)

## <a name="additional-resources"></a>További erőforrások

[Commerce katalógusok létrehozása B2B webhelyekhez](catalogs-b2b-sites.md)

[Commerce catalogs for B2B – gyakori kérdések](catalogs-b2b-sites-FAQ.md)
