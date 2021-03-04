---
title: Online csatorna létrehozása és a csatorna attribútumainak meghatározása
description: Ezzel az eljárással bemutatja, hogyan hozhat létre új online csatornát, és ezt hogyan adhatja hozzá a szervezeti hierarchiához.
author: jashanno
manager: AnnBe
ms.date: 06/04/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailSPOnlineStoreDetailPage, SysLookupMultiSelectGrid, DimensionLookup, OMHierarchyManager, HierarchyDesigner, OMNodeSelection, HierarchyPublishAndCloseForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f15b035c01801041d637a2d315d8a3ddcc9d6540
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412915"
---
# <a name="create-online-channel-and-define-channel-attributes"></a>Online csatorna létrehozása és a csatorna attribútumainak meghatározása

[!include [banner](../includes/banner.md)]

Ezzel az eljárással bemutatja, hogyan hozhat létre új online csatornát, és ezt hogyan adhatja hozzá a szervezeti hierarchiához. Új online csatorna létrehozása előtt létre kell hoznia a szervezeti hierarchiát. Ez az eljárás az USRT bemutatócéget használja.


## <a name="create-a-new-online-channel"></a>Hozzon létre egy új online csatornát.
1. Nyissa meg a következőt: Kiskereskedelem és kereskedelem > Csatornák > Online áruházak.
2. Kattintson az Új elemre.
3. Írjon be egy értéket a Név mezőbe.
4. A Raktár mezőben adjon meg vagy válasszon ki egy értéket.
5. Válasszon ki egy lehetőséget az Üzlet időzónája mezőben.
6. Adjon meg vagy válasszon ki egy értéket az Alapértelmezett vevő mezőben.
7. Adjon meg vagy válasszon ki egy értéket a Vevői címjegyzék mezőben.
8. Adjon meg vagy válasszon ki egy értéket a Fizetési feltételek mezőben.
9. A Fizetési mód mezőben adjon meg vagy válasszon ki egy értéket.
10. Adjon meg vagy válasszon ki egy értéket az E-mail értesítési profil mezőben.
11. Bontsa ki a Pénzügyi dimenziók szakaszt.
12. Adjon meg vagy válasszon ki egy értéket az Üzleti egység mezőben.
    * Hasonlóképpen állítsa be az értéket minden más alapértelmezett dimenzióra vonatkozóan.  
13. Kattintson a Mentés gombra.

## <a name="add-the-online-channel-to-organization-hierarchy"></a>Az online csatorna hozzáadása szervezeti hierarchiához
1. Zárja be a lapot.
2. Ugrás a Szervezet felügyelete > Szervezetek > Szervezeti hierarchiák menüpontokra.
3. Keresse meg és jelölje ki a kívánt rekordot a listán.
4. Kattintson a Megtekintés menüpontra.
5. Kattintson a Szerkesztés lehetőségre.
    * Az új csatornát bármely hierarchia-csomópont alá beillesztheti.  
6. Kattintson a Beszúrás lehetőségre.
7. Kattintson a Commerce csatorna elemre.
8. Kattintson az OK gombra.
9. A Közzététel gombra kattintva megnyithatja a legördülő párbeszédablakot.
10. Az Érvényesség dátuma mezőben adjon meg egy dátumot és időpontot.
11. Kattintson a Közzététel parancsra.

## <a name="configure-orders-for-near-real-time-notification"></a>Megrendelések konfigurálása a szinte valós idejű értesítésekhez
1. Menjen a Kiskereskedelem és kereskedelem > Központ beállítása > Paraméterek > Kiskereskedelmi paraméterek lehetőségre.
2. A Valós idejű szolgáltatás használata az elektronikus kereskedelmi megrendelés létrehozásához beállítást állítsa „Igen” értékre.
3. Futtassa a 1070 elosztási ütemezést a módosítások szinkronizálására a csatornaadatbázisba. 




[!INCLUDE[footer-include](../../includes/footer-banner.md)]