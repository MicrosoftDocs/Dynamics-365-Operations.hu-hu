---
title: Kísérletezés a Dynamics 365 Commerce rendszerben
description: A kísérletezés lehetővé teszi az oldal-elrendezések és tartalmak létrehozását, szerkesztését és kezelését a webhelykészítőben. A kísérletezés teljes körű támogatása biztosított az e-commerce oldalakhoz és az oldalon belül található entitásokhoz.
author: sushma-rao
ms.date: 06/07/2022
ms.topic: overview
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: 1ef877072ba7ffe1b0326cf8d526b512b5ab30b8
ms.sourcegitcommit: 427fe14824a9d937661ae21b9e9574be2bc9360b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/09/2022
ms.locfileid: "8946214"
---
# <a name="experimentation-in-dynamics-365-commerce"></a>Kísérletezés a Dynamics 365 Commerce szolgáltatásban
A Dynamics 365 Commerce szolgáltatáson belüli kísérletezést az e-kereskedelmi oldalak hatékonyságával kapcsolatos hipotézisek igazolására, valamint adatokra alapozott döntések meghozatalára alkalmazhatja. A Commerce támogatja az oldalakon, modulokon és töredékeken végzendő A/B tesztelést, valamint lehetővé teszi a webhellyel összefüggésben javasolt változtatások hatásának felmérését.

A Commerce webhelykészítőben oldal- és tartalomkezeléseket hozhat létre, szerkeszthet és kezelhet, melyeket **változatokként** is ismerhet. A Commerce harmadik fél szolgáltatásokba épül, és lehetővé teszi ezek használatát kísérletek és kezelési megbízások létrehozására. A Commerce modulban rögzített valós idejű adatfolyamok olyan elemzéseket tesznek lehetővé, amelyek meghatározzák a harmadik fél szolgáltatáson belül a kísérlet eredményeit. Ezt követően ezen elemzések felhasználásával alátámaszthatja vagy megcáfolhatja a hipotézisét.

## <a name="set-up-prerequisites"></a> A telepítés előfeltételei

1. **A Commerce megfelelő verziójának beszerzése** – Frissítse a modulkönyvtárát, az online csatornabővíthetőségi szoftverfejlesztői készletét (SDK-t) és a Commerce Scale Unitot 10.0.13-as vagy újabb verziójú Commerce modulra.
1. **Állítson be egy kísérlet-összekötőt** – A kísérlet-összekötővel a Commerce harmadik felek szolgáltatásaival összekapcsolódhat, és ezáltal lehívhatja a kísérletek listáját, és meghatározhatja, hogy mikor jelenjen meg egy kísérlet a felhasználó számára. Harmadik fél összekötőt itt vásárolhat: [AppSource](https://appsource.microsoft.com). Kövesse a kiadó által adott beállítási utasításokat. Ha külső szolgáltatás konfigurálása nélkül szeretné ezt elérni, akkor a Commerce-ben rendelkezésre álló tesztösszekötőt is használhatja a kísérletezési munkafolyamat tesztelésére. További tudnivalókért lásd: [Összekötők konfigurálása és engedélyezése](e-commerce-extensibility/connectors.md). 
1. **Kapcsolja be a commerce rendszer a kísérletek** funkció jelzőját – **\>** a bérlői szinten engedélyezheti a kísérleteket a Bérlőbeállítási funkciók funkcióval vagy **a hely szintjén a Webhely beállításai funkcióval.\>** A Modulok variációinak **létrehozásához kapcsolja** be a Kísérletjelzőt. A zászló letiltásával leállíthatja, hogy a felhasználók számára megjelenjen az összes kísérlet, valamint eltávolíthatja az összes szerkesztési funkciót a webhelykészítőből.
    
## <a name="experimentation-lifecycle"></a>A kísérletezés életciklusa

A kísérletek beállítása, változatok létrehozása és a kísérletek lefolytatása egy ismétlődő folyamatot alkot. A következő ábra a kísérletezés életciklusát mutatja be a Commerce modulban és a harmadik fél szolgáltatásokban. 

[ ![A kísérletezés életciklusa.](./media/experimentation_lifecycle.svg) ](./media/experimentation_lifecycle.svg#lightbox)

Ha többet szeretne tudni a kísérletek folyamatának egyes lépéseit, olvassa el a következő cikkeket.
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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
