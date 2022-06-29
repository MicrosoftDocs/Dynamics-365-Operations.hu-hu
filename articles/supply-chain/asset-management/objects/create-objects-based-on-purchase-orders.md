---
title: Eszközök létrehozása beszerzési rendelések alapján
description: Ez a cikk bemutatja, hogy hogyan lehet létrehozni az eszközelemek listáját, amely a tárgyi eszközök eszközkezelési feladatokhoz való létrehozásához ad alapot.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectItem, EntAssetPendingAssets
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ccd14493aac6484dc54ccf51ae159a071c8697a5
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015609"
---
# <a name="create-assets-based-on-purchase-orders"></a>Eszközök létrehozása beszerzési rendelések alapján

[!include [banner](../../includes/banner.md)]

 

Ez a cikk bemutatja, hogy hogyan lehet létrehozni az eszközelemek listáját, amely a tárgyi eszközök eszközkezelési feladatokhoz való létrehozásához ad alapot. Az eszköztételek alapján megtekintheti az ezekre a cikkekre létrehozott beszerzésirendelés-sorok listáját. Ennek a funkciónak a célja, hogy a beszerzési rendelés alapján könnyen létre lehessen hozni egy eszközt az Eszközkezelésben.

Először be kell állítania az eszközök beszerzési rendelésből történő létrehozására szolgáló cikkeket az **Eszköztételek** helyen. A beszerzésirendelés-sor létrehozása után az eszközök a **Függőben lévő eszközök** között hozhatók létre. Meg lehet határozni azt, hogy a beszerzési rendelés melyik szakaszában kell létrehozni az eszközt.


## <a name="select-asset-items"></a>Eszközelemek kiválasztása

1. Kattintson az **Eszközkezelés** > **Beállítások** > **Eszközök** > **Elemek** lehetőségre.
2. Új eszközelem létrehozásához kattintson az **Új** gombra.
3. Válassza ki a cikket a **Cikkszám** mezőben. Ha elhagyja ezt a mezőt, a program automatikusan beszúrja a cikk nevét a **Terméknév** mezőbe.
4. Az **Általános** gyorslapon válasszon ki egy eszköztípust a cikkhez.
5. Válassza ki a cikkhez tartozó eszközgyártót és modellt.
6. Mentse a cikket.


## <a name="create-assets-from-pending-assets"></a>Eszközök létrehozása függőben lévő eszközökből

1. Kattintson **a Függőben** > **lévő eszközök eszközkezelési** > **elemre**.
2. A beszerzési rendelések frissített listája az **Eszközcikkek** helyen kiválasztott cikkek alapján jelenik meg.
3. A beszerzési rendelések állapotát szűrheti, így kiválaszthatja, hogy melyik életciklus-állapotban kell létrehozni az eszközt. Előfordulhat például, hogy csak akkor szeretne eszközöket létrehozni, ha egy termékbevételezés fel lett adva egy beszerzési rendelésre.
4. A cikkre vonatkozó részletes információk megtekintéséhez válassza ki a beszerzési rendelési sor **Hivatkozási szám** linkjét.
5. Ha módosítani szeretné, hogy mely dimenziók jelenjenek meg a **Készletdimenziók** gyorslapon, kattintson a **Dimenziók megjelenítése** gombra, és adja meg a kívánt beállításokat.
6. Ha beszerzésirendelés-soron alapuló eszközt szeretne létrehozni, jelölje be a jelölőnégyzetét a **Jelölés** oszlopnál ahhoz a sorhoz a listaoldalon, majd kattintson az **Eszközök létrehozása** parancsra. Ekkor megjelenik egy üzenet, amely tájékoztatja az eszközazonosítóról.
7. Válassza ki az eszközt az **Összes eszköz** listából, majd kattintson a **Szerkesztés** gombra, hogy további információkat adjon hozzá az eszközhöz.
8. Ha a **Függőbenlévő eszközök** mezőben törölni szeretne egy sort, mert nem szeretne létrehozni egy eszközt, akkor jelölje be a sorhoz tartozó **Jelölés** oszlopban lévő jelölőnégyzetet, majd kattintson a **Függőben lévő eszközökelvetése** parancsra. Ekkor megjelenik egy üzenet, amely tájékoztatja az eszközazonosítóról. Nem törli a beszerzési rendelést vagy értékesítéi rendelést, csak azt a rekordot, amelyből az eszközt az **Eszközkezelésben** létrehozhatta volna.

>[!NOTE]
>Minden termékdimenzió (méret, szín, konfiguráció stb) automatikusan van átvíve az eszközattribútumokhoz. A nyomon követési dimenziók (sorozatszám) az eszköz létrehozásakor közvetlenül az eszközben lesznek tárolva.


## <a name="find-pending-assets"></a>Függőben lévő eszközök megkeresése

A függőben lévő eszközök ellenőrzéséhez futtathat egy **Függőben lévő eszközszám** parancsot. Ez a funkció például arra használható, hogy értesítést kapjon valahányszor egy függőben lévő eszköz készen áll eszközként történő létrehozásra.

1. Kattintson az **Eszközkezelés** > **Időszakos** > **Eszközök** > **Függőben lévő eszközök száma** lehetőségre.
2. Kattintson az **Ok** gombra a feladat futtatásához, és a lista frissítéséhez a **Függőben lévő eszközök** helyen.
3. Beállíthatja, hogy a feladat kötegelt feladatként fusson, például naponta egyszer.

**Figyelmeztetés:** Ha az adatok módosulnak egy beszerzési rendelésen *miután* létrehozott egy eszközt kapcsolódó cikk alapján, ezek a módosítások nem jelennek meg az eszköznél.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]