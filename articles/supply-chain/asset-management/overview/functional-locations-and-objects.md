---
title: Munkavégzési helyszínek és eszközök
description: Ez a témakör az Eszközkezelés működési helyeit és tárgyi eszközeit írja le. Az Eszközkezelés az eszközök és a karbantartási feladatok Dynamics 365 Supply Chain Management rendszerben történő kezelésére szolgáló speciális modul.
author: johanhoffmann
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0d8d155b8bbf981408f6f15e914fc3bb1da25c9c
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111076"
---
# <a name="functional-locations-and-assets"></a>Munkavégzési helyszínek és eszközök

[!include [banner](../../includes/banner.md)]

 

Ez a témakör az Eszközkezelés működési helyeit és tárgyi eszközeit írja le. Az Eszközkezelés az eszközök és a karbantartási feladatok Dynamics 365 Supply Chain Management rendszerben történő kezelésére szolgáló speciális modul.

## <a name="overview"></a>Áttekintés

Az Eszközkezelés problémamentesen integrálható több modullal más pénzügyi és műveleti alkalmazásokkal. A következő ábra a más modulokkal való kapcsolatot mutatja be.

![Az Eszközkezelés egyéb modulokkal való kapcsolódását mutató ábra.](media/01-overview-image.png)

Az Eszközkezeléssel hatékonyan kezelhető és hajtható végre a cég különféle típusú felszerelésének kezelésére és szervizelésére szolgáló minden feladat. Felszerelés lehet minden gép, gyártóeszköz vagy jármű. Az Eszközkezelés több iparág megoldásait is támogatja.

A következő képen az Eszközkezelés fő funkcióinak az áttekintése látható.

![Az Eszközkezelés fő funkcióit mutató ábra.](media/02-overview-image.png)

## <a name="functional-locations-and-assets"></a>Munkavégzési helyszínek és eszközök

A munkavégzési helyszínek a helyen lévő eszközök kezelésére szolgálnak. A kezelésbe az eszközök munkavégzési helyszíneken felmerülő költségek nyomon követése is beletartozik. A munkavégzési helyszínek hierarchikusan tagoltak, és a helyszíneknek mellékhelyszínei lehetnek. A munkavégzési helyszínek szerkezete statikus. Más szavakkal a helyszínek helye nem módosítható. Az eszközök telepíthetők munkavégzési helyszíneken, és szükség esetén további munkavégzési helyszíneken.

Az eszközök költsége az eszköz helyét követi. Más szóval, ha új munkavégzési helyszínen telepít egy eszközt, az eszköz automatikusan az új munkavégzési helyszínnel összekapcsolt pénzügyi dimenziókat használja. Így az eszköz költségei mindig össze vannak kapcsolva azzal a munkavégzési helyszínnel, amelyen az eszköz pillanatnyilag telepítve van. A pénzügyi dimenziók ilyen automatikus kezelésével garantálható a költségek teljes nyomon követése, amikor a cég projektellenőrzést végez a munkavégzési helyszíneken, illetve jelentést készít róluk.

A munkavégzési helyszínek hierarchiájának kialakítása attól függ, hogy a cég milyen követelményeket támaszt a belső vagy az ügyfeleknek szolgáltatott berendezésekkel kapcsolatban. A következő képen egy földrajzi helyeken alapuló munkavégzési helyszínre látható példa.

![A földrajzi helyek alapján munkavégzési helyszíneket mutató ábra.](media/03-overview-image.png)

A következő képen egy ügyfeleken alapuló munkavégzési helyszínre látható példa.

![Az ügyfelek alapján munkavégzési helyszíneket mutató ábra.](media/04-overview-image.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
