---
title: Mobileszköz felhasználói beállításai
description: Ez a témakör bemutatja a raktári dolgozók mobileszköze felhasználói beállításainak kezelését.
author: MarkusFogelberg
ms.date: 02/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppDeviceBrand,WHSMobileAppUserDisplaySettings
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: mafoge
ms.search.validFrom: 2021-02-09
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 080b84d712a9c634611090f71b9ecca75e13cdcb
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837465"
---
# <a name="mobile-device-user-settings"></a>Mobileszköz felhasználói beállításai

[!include [banner](../../includes/banner.md)]

Az új Raktárkezelés mobilalkalmazás alkalmazásspecifikus beállításokat tesz lehetővé, amelyek segítséget nyújtanak a felhasználói felület személyre szabása során. Mivel az alkalmazás különböző képernyőméretek és -konfigurációk (például táblagép, telefon és karon viselt) eszközökön használható, hasznos lehet ezen beállítások központi kezelése a Microsoft Dynamics 365 Supply Chain Management rendszerben.

A *Mobileszköz felhasználói beállításai* funkció segítségével meghatározhatja azokat a globális felhasználói beállításokat, amelyek minden eszközön használatosak. Az egyes eszközmárkák, eszközmodellek és/vagy dolgozók esetében részletesebb felhasználói beállításokat is meg lehet határozni. Amikor egy dolgozó bejelentkezik a Raktárkezelés mobilalkalmazásba, az alkalmazás beolvassa és alkalmazza a Supply Chain Management alkalmazásban az egyező márkához, eszközhöz és/vagy felhasználóazonosítóhoz tárolt legspecifikusabb beállítási profilt.

Ez a funkció gyors kezdést biztosít a dolgozóknak új eszköz használata esetén. Íme néhány példa:

- A rendszergazdák olyan általános preferenciákat állíthatnak be, amelyek a legmegfelelőbbek egy adott gyártótól származó eszközök és/vagy konkrét eszközmodellek esetén. A dolgozók tehát úgy is elkezdhetnek használni egy új eszközt, hogy nem kell feltétlenül módosítaniuk a beállításokat.
- Ha vállalata a dolgozók által felváltva használt, egyforma eszközöket használ, a dolgozók minden bejelentkezéskor látni fogják a preferált beállításukat, még akkor is, ha még soha nem használták az adott napon azt a konkrét fizikai eszközt.
- A Supply Chain Management rendszerben a rendszergazdák megtekinthetik és szerkeszthetik az összes tárolt beállítást, még az egyes dolgozók esetében is. Ez a funkció segít a hibaelhárításban, illetve az új funkciók finomhangolásában.

> [!IMPORTANT]
> A *Mobileszköz-felhasználói beállítások* funkció csak az új Raktárkezelés mobilalkalmazásra vonatkozik. Nem működik a régi raktári alkalmazással.

## <a name="turn-on-the-mobile-device-user-settings-feature"></a>A Mobileszköz-felhasználói beállítások funkció bekapcsolása

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Raktárkezelés*
- **Funkciónév:** *Felhasználói beállítások, ikonok és lépéscímek az új raktári alkalmazáshoz*

## <a name="create-and-manage-user-settings"></a>Felhasználói beállítások létrehozása és kezelése

A **Mobileszköz-felhasználói beállítások** oldalon létrehozhatja, részletesen megtekintheti és kezelheti a beállítási profilokat. Amikor a dolgozó először módosítja a felhasználói beállításait egy új eszközön, a rendszer automatikusan hozzáad egy új profilt ehhez az oldalhoz, ha még nem létezik. Ez a profil minden alkalommal frissül, amikor a dolgozó módosítja a beállítást.

Olyan beállítási profilt is meghatározhat, amely minden eszközmárkára, eszközmodellre és/vagy dolgozóra alkalmazható. Ezután az egyes márkákra, modellekre és/vagy dolgozókra vonatkozó konkrétabb beállítások alkalmazásával részletesebb beállításokat végezhet.

A következő lépéseket követve létrehozhatja és kezelheti a mobileszközök felhasználói beállításait.

1. Lépjen a **Raktárkezelés \> Mobileszköz \> Mobileszköz-felhasználói beállítások** elemre.
1. Válasszon ki egy létező felhasználóibeállítás-profilt a lista ablaktáblán a rekord megnyitásához. Másik lehetőségként válassza az **Új** lehetőséget a műveleti ablaktáblán egy új profil létrehozásához.

    A lista ablaktáblán minden profil címkével van ellátva, jelezve a márkát, a modellt és/vagy a felhasználói azonosítót, amelyre a profil vonatkozik. Általánosabb profilok esetében a jellemzők egy része vagy minden profil értéke *Összes* lesz.

1. Az új vagy kiválasztott beállítási profil rekordja fejlécében állítsa be a következő mezőket:

    - **Eszköz márkaneve** – válassza ki annak az eszköznek a nevét, amelyre a profilnak vonatkoznia kell. Ha a profil minden márkára érvényes, akkor ezt a mezőt hagyja üresen. Az értékek listája tartalmazza a rendszerben definiált összes márkát. A márkák listájának meghatározásával kapcsolatos tudnivalókat lásd a következő szakaszban.
    - **Eszköz modellazonosítója** – válassza ki annak a modellnek a nevét, amelyre a profilnak vonatkoznia kell. Ha a profil a kiválasztott márka minden modelljére érvényes, akkor ezt a mezőt hagyja üresen. Az értékek listája tartalmaz minden olyan modellt, amely az **Eszköz márkaneve** mezőben kiválasztott márka esetében meghatározott. Az egyes márkákhoz tartozó modellek listájának meghatározásával kapcsolatos tudnivalókat lásd a következő szakaszban.
    - **Felhasználói azonosító** – annak a raktári dolgozónak a felhasználói azonosítója, akire a beállítási profil alkalmazandó. Ha a profil minden dolgozóra érvényes, akkor ezt a mezőt hagyja üresen.

1. Az **Általános** gyorslapon állítsa be a következő mezőket:

    - **Gomb pozíciója** – válassza ki, hogyan helyezkedjenek el a gombok az eszközön. A szoftver úgy helyezi át az alkalmazás elemeit, hogy jobban elférjenek a dolgozó preferenciáinak vagy domináns kezének megfelelően. A következő lehetőségek érhetők el: *Jobb oldalt alul (alapértelmezett)*, *Bal oldalt alul*, *Jobb oldalt felül* és *Bal oldalt felül*.
    - **Megjelenítési tájolás** – válassza ki az alkalmazásban alapértelmezés szerint alkalmazni kívánt megjelenítési tájolást.
    - **Beolvasás kamerával** – állítsa ezt a lehetőséget *Igen* értékre, hogy az eszköz a kamerájával beolvassa az olyan beviteli mezőket, amelyeknél a preferált beviteli mód *Beolvasás*. Ha az eszköz beépített szkennerrel rendelkezik, állítsa ezt a lehetőséget *Nem* értékre, hogy helyette a szkennert használja.
    - **Termék fényképének megjelenítése** – itt kiválaszthatja, hogy a termék fényképeit meg kell-e jeleníteni, ha elérhetők a kiadott termékhez. A termékképek hozzáadásáról lásd: [Kép hozzáadása termékhez](../pim/tasks/add-image-product.md).
    - **Szín téma megjelenítése** – az eszköz színtémájának kiválasztása.
    - **Hangszint** – válassza ki az eszköz hangszintjét. 0 (nulla) és 10 közötti értéket válasszon. A *0* érték azt jelenti, hogy nincs hang, a *10* pedig a maximális hangerőt. Az alapértelmezett érték *4*.
    - **Rezgési szint** – válassza ki az eszköz rezgési szintjét. 0 (nulla) és 5 közötti értéket válasszon. A *0* érték azt jelenti, hogy nincs rezgés, a *5* pedig a maximális rezgést. Az alapértelmezett érték *1*.
    - **Szöveg méretezési százaléka** – határozza meg a szövegméretet a szokásos méret százalékaként. Adjon meg egy 70 és 400 közötti értéket. A *70* egyenlő a legkisebb szöveg léptékével, és a *400* egyenlő a legnagyobb szöveg léptékével. Az alapértelmezett érték *100*.
    - **Gomb méretezési százaléka** – határozza meg a gombméretet a szokásos méret százalékaként. Adjon meg egy 50 és 200 közötti értéket. A *50* egyenlő a legkisebb gomb léptékével, és a *200* egyenlő a legnagyobb gomb léptékével. Az alapértelmezett érték *100*.

## <a name="create-and-manage-mobile-device-brands"></a>Mobilmárkák létrehozása és kezelése

A **Mobilmárkák** oldalon megtekintheti, létrehozhatja és kezelheti a beállítási profilokkal használható eszközmárkákat és modelleket. A mobilalkalmazás automatikusan lekéri és elküldi a helyi márkanevet és modellazonosítót, amikor egy dolgozó először módosítja a beállításait egy adott eszközön. Ezért a program általában automatikusan generálja ezeket a rekordokat. Ugyanakkor kezelheti az oldal összes rekordját is. Hasznosabb leírásokat adhat például az egyes márkák és modellek esetében, hogy megkülönböztesse a hasonló vagy nehezen kibogozható modellazonosítókat.

A következő lépéseket követve létrehozhatja és kezelheti a mobileszközök márkáit és modelljeit.

1. Lépjen a **Raktárkezelés \> Mobileszköz \> Mobilmárkák** menüre.
1. A rekord megnyitásához válassza ki a mobilmárka nevét a lista ablaktáblán. Másik lehetőségként válassza az **Új** lehetőséget a műveleti ablaktáblán egy új márka létrehozásához.
1. Az új vagy kiválasztott eszközmárka rekordja fejlécében állítsa be a következő mezőket:

    - **Eszköz márkaneve** – az eszköz márkaneve, például a *Microsoft Corporation*.
    - **Leírás** – a márkanevek megkülönböztetésére egy leírást is meg lehet adni.

1. A **Mobileszközmodellek** gyorslap a kiválasztott eszközmárka összes modelljét megjeleníti. Az eszköztár gombjaival hozzáadhat sorokat a rácshoz, illetve eltávolíthat sorokat. Minden egyes sorhoz beállíthatja a következő mezőket:

    - **Eszköz modellazonosítója** – az eszköz modellazonosítója, például a *Surface Book 2*.
    - **Leírás** – a modellazonosítók megkülönböztetésére egy leírást is meg lehet adni.
