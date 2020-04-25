---
title: Kanbanállapot frissítése
description: Amikor a rendszer tévedésből kiüríti a kanbant vagy a kapott kanbant ki kell üríteni, frissítenie kell a kanban állapotát.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Kanban, KanbanResetEmpty
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bb8559c0843d7e6e538b5b29dc394a50d05462ee
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210341"
---
# <a name="update-kanban-status"></a>Kanbanállapot frissítése

[!include [banner](../../includes/banner.md)]

Amikor a rendszer tévedésből kiüríti a kanbant vagy a kapott kanbant ki kell üríteni, frissítenie kell a kanban állapotát. Ez az eljárás az USMF bemutatócéget használja. Ezt az eljárást a Művezető használja.


## <a name="find-the-kanban"></a>A kanban keresése.
1. Ugorjon a Gyártásvezérlés > Kanban > Kanbanok pontra.
2. Nyissa meg az Anyagkezelési egység állapota oszlopszűrőt.
3. Kattintás a Törlés gombra.
    * Ez visszaállítja a szűrőket.  
4. Rekordok kereséséhez használja a gyorsszűrőt. Például végezzen szűrést a „000149” értékkel a Kártyaszám mezőben.

## <a name="change-emptied-status-to-received-status"></a>Módosítsa a kiürített állapotot beérkezett állapotra
1. Kattintson az Üres anyagkezelési egység sztornírozása lehetőségre.
2. Kattintson az OK gombra.
    * Vegye figyelembe, hogy az Anyagkezelési egység állapota Bevételezett.  

## <a name="change-received-status-to-emptied-status"></a>Módosítsa a beérkezett állapotot kiürített állapotra
1. Kattintson az Üres kanban lehetőségre.
2. A listában jelölje meg a kiválasztott sort.
    * Vegye figyelembe, hogy az Anyagkezelési egység állapota Kiürítve.  

