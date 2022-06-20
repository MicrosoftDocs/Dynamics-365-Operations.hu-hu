---
title: Kísérlet beállítása
description: Ez a témakör azt ismerteti, hogyan lehet kísérleteket beállítani egy külső szolgáltatásban.
author: sushma-rao
ms.date: 06/08/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: 1073cdc509622279ce7388b8b406079a4e6e9e09
ms.sourcegitcommit: 427fe14824a9d937661ae21b9e9574be2bc9360b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/09/2022
ms.locfileid: "8946166"
---
# <a name="set-up-an-experiment"></a>Kísérlet beállítása

Miután [meghatározott egy hipotézist, valamint a használni kívánt sikerességi mérőszámokat](experimentation-identify.md), be kell állítani a kísérletet a harmadik fél szolgáltatásban. A következő ábra azokat a lépéseket mutatja be, amelyekkel egy e-kereskedelmi webhelyhez tartozó kísérletet lehet létrehozni és futtatni a Dynamics 365 Commerce rendszerben. A további lépések külön cikkekbe tartoznak.

[ ![Kísérletezés felhasználói interakciósorozata – Beállítás.](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)


## <a name="set-up-your-experiment-in-the-third-party-service"></a>A kísérlet beállítása a harmadik szolgáltatásban
Eddigre már eldöntötte, hogy harmadik fél szolgáltatással futtatja és követi nyomon a kísérletet, és beállította a kísérlet-összekötőt. Ezeket az előfeltételeket a [Kísérletezés a Dynamics 365 Commerce rendszerben](experimentation-overview.md) rész sorolja fel.

Kövesse a kísérlet harmadik fél szolgáltatásban való létrehozásához szükséges lépéseket. Ha az összekötőt jól konfigurálta, a harmadik fél szolgáltatásban beállított kísérletek teljes listája mintegy 5 percen belül megjelenik a Commerce webhelykészítőben.

## <a name="set-up-your-success-metrics"></a>A sikerességi mérőszámok beállítása
Minden kísérlethez mérőszámok szükségesek a változatok hatásainak mérésére és a hipotézis ellenőrzésére. Hajtsa végre az alábbi lépéseket, ha engedélyezni szeretné a mérőszámok számítását a harmadik fél szolgáltatásban a Dynamics 365 Commerce rendszerben élő telemetria eseményei segítségével.

Az alábbi lépések szerint állítsa be a sikeresség mérőszámát a "box out-of-box" modulokhoz.

1. A Commerce webhelykészítőben a bal oldali navigációs ablakban válassza ki az **Oldalak** fület, majd válassza ki azt az oldalt, amelyhez a mérőszámokat gyűjteni szeretné. 
1. Lépjen a követni kívánt oldal vagy modul jobb oldali tulajdonságok panelján lévő **Követendő eseményazonosítók** szakaszra.
1. Válassza ki a **Nézet** lehetőséget. Megjelenik az összes kattintási eseményazonosító listája. A nyomon követni kívánt esemény másolása, majd az eseménykulcs beillesztése a külső szolgáltatás kijelölt helyére. Ha egynél több eseményre van szüksége, akkor egyenként másolja át a kulcsokat. 
1. Lapnézetek SHA-256 oldalnév kivonatértékének használata a webhelyszerkesztőben `.PageView`. Például a következő eseményazonosító `Homepage.PageView` lenne: `e217eb66c7808ecc43b0f5c517c6a83b39d72b91412fbd54a485da9d8e186a9`.
1. Hajtsa végre a szükséges lépéseket a mérőszámoknak a harmadik fél szolgáltatásban való nyomon követéséhez.

Egyéni modulra való kattintások esetén kövesse az alábbi lépéseket a kattintási események eszközlése érdekében:

1. Az alábbi funkcióval készítse elő a **modulHoz a Szükséges Szövegkontent** objektumot. Ez a művelet bemenetként veszi az oldalnevet, a modulnevet és az SDK által biztosított alapértelmezett y objektumot.

    ```TypeScript
    getTelemetryObject(pageName: string, moduleName: string, telemetry: ITelemetry): ITelemetryContent
    ```
    
    A következő példa: 
    
    ```TypeScript
    private readonly telemetryContent: ITelemetryContent = getTelemetryObject(this.props.context.request.telemetryPageName!, this.props.friendlyName, this.props.telemetry);
    ```
    
1. Hozza létre a rakományadatokat, amelyek információt tartalmaznak arról, hogy mi a létrehozására van szükség. Gombok és más statikus vezérlők esetén a szöveget is használhatja, **például** "Vásárlás" vagy "Keresés". És olyan összetevők esetén, amelyeken rákattint egy termékkártyára, elküldheti a recid **azonosítót,** amely a termék vagy a termékazonosító rekordazonosítója.

    ```TypeScript
    getPayloadObject(eventType: string, telemetryContent: ITelemetryContent, etext: string, recid?: string): IPayLoad
    ```
    Statikus vezérlők esetén példaként adja át a gomb szöveg-karakterláncát az alábbi módon:

    ```TypeScript
    const payLoad = getPayloadObject('click', this.props.telemetryContent, 'Shop Now', '');
    ```
    Példaként termékkatonákra, adja át a termék recordId-ját az alábbi módon:

    ```TypeScript
    const payLoad = getPayloadObject('click', telemetryContent!, '', product.RecordId.toString());
    ```
    
1. Az esemény **regisztrálása az OnClstb** . funkcióval hívható.

    ```TypeScript
    onTelemetryClick = (telemetryContent: ITelemetryContent, payLoad: IPayLoad, linkText: string) => () =>
    ```

    A következő példa:

    ```TypeScript
    onClick: onTelemetryClick(this.props.telemetryContent, payLoad, linkText)
    ```

## <a name="previous-step"></a>Előző lépés
[Hipotézis meghatározása és mérőszámok megadása egy kísérlethez](experimentation-identify.md) 


## <a name="next-step"></a>Következő lépés
[Kísérlet csatlakoztatása és szerkesztése](experimentation-connect-edit.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
