---
title: Munkavégzési helyszínek és eszközök
description: Ez a cikk az Eszközkezelés munkavégzési helyszíneit és eszközeit ismerteti. Az Eszközkezelés az eszközök és a karbantartási feladatok Dynamics 365 Supply Chain Management rendszerben történő kezelésére szolgáló speciális modul.
author: josaw1
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5271b673d758608cae8e43d72b7e75b259d5f142
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024614"
---
# <a name="functional-locations-and-assets"></a>Munkavégzési helyszínek és eszközök

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Ez a cikk az Eszközkezelés munkavégzési helyszíneit és eszközeit ismerteti. Az Eszközkezelés az eszközök és a karbantartási feladatok Dynamics 365 Supply Chain Management rendszerben történő kezelésére szolgáló speciális modul.

## <a name="overview"></a>Áttekintés

Az Eszközkezelés a Finance and Operations számos moduljával zökkenőmentesen együttműködik. A következő ábra a más modulokkal való kapcsolatot mutatja be.

![1. ábra](media/01-overview-image.png)

Az Eszközkezeléssel hatékonyan kezelhető és hajtható végre a cég különféle típusú felszerelésének kezelésére és szervizelésére szolgáló minden feladat. Felszerelés lehet minden gép, gyártóeszköz vagy jármű. Az Eszközkezelés több iparág megoldásait is támogatja.

A következő képen az Eszközkezelés fő funkcióinak az áttekintése látható.

![2. ábra](media/02-overview-image.png)

## <a name="functional-locations-and-assets"></a>Munkavégzési helyszínek és eszközök

A munkavégzési helyszínek a helyen lévő eszközök kezelésére szolgálnak. A kezelésbe az eszközök munkavégzési helyszíneken felmerülő költségek nyomon követése is beletartozik. A munkavégzési helyszínek hierarchikusan tagoltak, és a helyszíneknek mellékhelyszínei lehetnek. A munkavégzési helyszínek szerkezete statikus. Más szavakkal a helyszínek helye nem módosítható. Az eszközök telepíthetők munkavégzési helyszíneken, és szükség esetén további munkavégzési helyszíneken.

Az eszközök költsége az eszköz helyét követi. Más szóval, ha új munkavégzési helyszínen telepít egy eszközt, az eszköz automatikusan az új munkavégzési helyszínnel összekapcsolt pénzügyi dimenziókat használja. Így az eszköz költségei mindig össze vannak kapcsolva azzal a munkavégzési helyszínnel, amelyen az eszköz pillanatnyilag telepítve van. A pénzügyi dimenziók ilyen automatikus kezelésével garantálható a költségek teljes nyomon követése, amikor a cég projektellenőrzést végez a munkavégzési helyszíneken, illetve jelentést készít róluk.

A munkavégzési helyszínek hierarchiájának kialakítása attól függ, hogy a cég milyen követelményeket támaszt a belső vagy az ügyfeleknek szolgáltatott berendezésekkel kapcsolatban. A következő képen egy földrajzi helyeken alapuló munkavégzési helyszínre látható példa.

![3. ábra](media/03-overview-image.png)

A következő képen egy ügyfeleken alapuló munkavégzési helyszínre látható példa.

![4. ábra](media/04-overview-image.png)
