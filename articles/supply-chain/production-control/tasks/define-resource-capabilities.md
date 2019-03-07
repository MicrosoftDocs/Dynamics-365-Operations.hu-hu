---
title: Erőforrás-képességek meghatározása
description: Az erőforrás-képességek azt mutatják, hogy az erőforrások milyen műveleteket képesek elvégezni.
author: sorenva
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrCapability
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0940883d0e9edf56e61b5ecd817062aac5e0f8a6
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "340154"
---
# <a name="define-resource-capabilities"></a>Erőforrás-képességek meghatározása

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

