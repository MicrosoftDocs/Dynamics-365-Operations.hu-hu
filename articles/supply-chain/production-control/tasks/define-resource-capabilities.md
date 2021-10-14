---
title: Erőforrás-képességek meghatározása
description: Az erőforrás-képességek azt mutatják, hogy az erőforrások milyen műveleteket képesek elvégezni.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WrkCtrCapability
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 42451da0bd465ce3a18ecf18570f3331847474c1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579112"
---
# <a name="define-resource-capabilities"></a>Erőforrás-képességek meghatározása

[!include [banner](../../includes/banner.md)]

Az erőforrás-képességek azt mutatják, hogy az erőforrások milyen műveleteket képesek elvégezni. Az ütemezés során a feladat és a művelet követelményeihez hozzárendelődnek a rendelkezésre álló erőforrások képességei. Ez az útmutató segít létrehozni egy erőforrás-képességet, és azt hozzárendelni egy erőforráshoz. A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.


## <a name="create-a-resource-capability"></a>Új erőforrás-képesség létrehozása
1. Menjen rá az erőforrás-képességekre.
2. Kattintson az Új elemre.
3. A Képesség mezőbe írja be az erőforrás képességének azonosítóját.
    * Egy adott művelethez a képesség azonosítóját adja meg, hogy meghatározza, hogy az erőforrásoknak ezzel a képességgel kell rendelkezniük a művelet végrehajtásához.  
4. Adja meg a képesség leírását a Leírás mezőben.

## <a name="assign-capability-to-a-resource"></a>Képesség hozzárendelése egy erőforráshoz.
1. Kattintson a Hozzáadás gombra.
2. Az Erőforrás mezőbe írja be az erőforrás azonosítóját.
    * Egy erőforrás-képesség hozzárendelhető egy vagy több erőforráshoz.  
3. A Lejárat ideje mezőben adjon meg egy dátumot.
    * A mező segítségével adhatja meg, hogy az erőforrás képessége csak korlátozott időtartamra adott.  
4. Adjon meg egy számot a Prioritás mezőben.
    * Feladatok és műveletek ütemezésekor meg lehet adni, hogy prioritás szerint kívánja-e kijelölni az erőforrásokat. Ha ezt választja, és egynél több erőforrás tudja elvégezni feladatot vagy műveletet a kért dátumig, a szükséges képesség tekintetében legalacsonyabb prioritású erőforrás lesz jelölve.  
5. Adjon meg egy számot a Szint mezőben.
    * Amikor Ön határozza meg, hogy a feladat vagy a művelet egy adott képességet igényel, meghatározhatja a szükséges minimális szintet is. A képesség szint segítségével különbséget tehet azon erőforrások között, amelyek ugyanazt a feladatot hajthatják végre, de eltérő sebességgel, méretben, és stb.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]