---
title: Kísérletezés a Dynamics 365 Commerce rendszerben
description: A kísérletezés lehetővé teszi az oldal-elrendezések és tartalmak létrehozását, szerkesztését és kezelését a webhelykészítőben. A kísérletezés teljes körű támogatása biztosított az e-commerce oldalakhoz és az oldalon belül található entitásokhoz.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: c1bb03fb82123e78ba21a9af2b948a386b6b4338
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009974"
---
# <a name="experimentation-in-dynamics-365-commerce"></a>Kísérletezés a Dynamics 365 Commerce szolgáltatásban
A Dynamics 365 Commerce szolgáltatáson belüli kísérletezést az e-kereskedelmi oldalak hatékonyságával kapcsolatos hipotézisek igazolására, valamint adatokra alapozott döntések meghozatalára alkalmazhatja. A Commerce támogatja az oldalakon, modulokon és töredékeken végzendő A/B tesztelést, valamint lehetővé teszi a webhellyel összefüggésben javasolt változtatások hatásának felmérését.

A Commerce webhelykészítőben oldal- és tartalomkezeléseket hozhat létre, szerkeszthet és kezelhet, melyeket **változatokként** is ismerhet. A Commerce harmadik fél szolgáltatásokba épül, és lehetővé teszi ezek használatát kísérletek és kezelési megbízások létrehozására. A Commerce modulban rögzített valós idejű adatfolyamok olyan elemzéseket tesznek lehetővé, amelyek meghatározzák a harmadik fél szolgáltatáson belül a kísérlet eredményeit. Ezt követően ezen elemzések felhasználásával alátámaszthatja vagy megcáfolhatja a hipotézisét.

## <a name="set-up-prerequisites"></a> A telepítés előfeltételei
1. **A Commerce megfelelő verziójának beszerzése** – Frissítse a modulkönyvtárát, az online csatornabővíthetőségi szoftverfejlesztői készletét (SDK-t) és a Commerce Scale Unitot 10.0.13-as vagy újabb verziójú Commerce modulra.
1. **Állítson be egy kísérlet-összekötőt** – A kísérlet-összekötővel a Commerce harmadik felek szolgáltatásaival összekapcsolódhat, és ezáltal lehívhatja a kísérletek listáját, és meghatározhatja, hogy mikor jelenjen meg egy kísérlet a felhasználó számára. Harmadik fél összekötőt itt vásárolhat: [AppSource](https://appsource.microsoft.com). Kövesse a kiadó által adott beállítási utasításokat. Ha külső szolgáltatás konfigurálása nélkül szeretné ezt elérni, akkor a Commerce-ben rendelkezésre álló tesztösszekötőt is használhatja a kísérletezési munkafolyamat tesztelésére. További tudnivalókért lásd: [Összekötők konfigurálása és engedélyezése](e-commerce-extensibility/connectors.md). 
1. **A kísérletezési funkció zászlóinak bekapcsolása a Commerce modulban** – A bérlő szintjén engedélyezheti a kísérletezést a **Bérlő beállításai > Funkciók** felületre lépve, illetve megteheti ugyanezt a webhely szintjén is a **Webhelybeállítások > Funkciók** felületen.
    - A **Kísérletezés** zászló engedélyezésével az oldalon belüli modulokból kísérletváltozatokat hozhat létre anélkül, hogy a kísérlet alá nem tartozó tartalmat kellene megváltoztatni vagy lemásolni. Ezzel biztosíthatja, hogy a folyamatban lévő, a kísérleten kívül eső tartalomfrissítések szinkronban maradjanak a kísérlet életciklusa alatt. A zászló letiltásával leállíthatja, hogy a felhasználók számára megjelenjen az összes kísérlet, valamint eltávolíthatja az összes szerkesztési funkciót a webhelykészítőből.
    - A **Kísérlet oldalakon vagy töredékeken** zászló engedélyezésével adott oldalon vagy töredéken futtathat kísérleteket. Ezzel a teljes oldalról vagy töredékről egy teljes másolati példány jön létre az adott oldalon vagy töredéken belüli összes modulhoz. Ezt a módot akkor használhatja, amikor átfogó tartalommódosításokat szeretne tesztelni vagy amikor a folyamatban lévő, több példányt érintő tartalomfrissítések szinkronizálása nem szempont. A zászló letiltásával megakadályozhatja azt, hogy az oldalakon és töredékeken új kísérleteket lehessen létrehozni és szerkeszteni.
    > [!NOTE]
    > A **Kísérletezés** zászlót ugyancsak engedélyezni kell ahhoz, hogy a **Kísérlet oldalakon vagy töredékeken** funkció működni tudjon.
    
## <a name="experimentation-lifecycle"></a>A kísérletezés életciklusa
A kísérletek beállítása, változatok létrehozása és a kísérletek lefolytatása egy ismétlődő folyamatot alkot. A következő ábra a kísérletezés életciklusát mutatja be a Commerce modulban és a harmadik fél szolgáltatásokban. 

[ ![A kísérletezés életciklusa](./media/experimentation_lifecycle.svg) ](./media/experimentation_lifecycle.svg#lightbox)

A kísérletezési folyamat egyes lépéseivel kapcsolatos további tudnivalókat lásd a következő témakörökben.
- [Hipotézis meghatározása és mérőszámok megadása egy kísérlethez](experimentation-identify.md)
- [Kísérlet beállítása](experimentation-setup.md)
- [Kísérlet csatlakoztatása és szerkesztése](experimentation-connect-edit.md)
- [Kísérlet előnézetének megtekintése és közzététele](experimentation-preview-publish.md)
- [Kísérlet futtatása és nyomon követése](experimentation-run-monitor.md)
- [Változat előléptetése és egy kísérlet végrehajtása](experimentation-review-complete.md)

> [!NOTE]
> Ha meg szeretné tudni, hol tart egy kísérlet az életciklusban, a webhelykészítőben lépjen a **Kísérletek** fülre a bal oldali navigációs panelen. A kísérletek listája mind a Commerce modulban, mind pedig a harmadik fél szolgáltatásban az egyes kísérletek állapotával együtt jelenik meg. További tudnivalókért lásd: [Egy kísérlet állapotának áttekintése](experimentation-status.md).

## <a name="next-step"></a>Következő lépés
[Hipotézis meghatározása és sikerességi mérőszámok megadása egy kísérlethez](experimentation-identify.md) 
