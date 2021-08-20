---
title: Karbantartási ütemezés költsége
description: Ez a cikk az Eszközkezelés karbantartási ütemezésének költségét ismerteti.
author: johanhoffmann
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 267452bf5ec8cafebb5927045e8708a41603ec16f48626b7fd351d13fdb2fab7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746256"
---
# <a name="maintenance-schedule-cost"></a>Karbantartási ütemezés költsége

[!include [banner](../../includes/banner.md)]

 

Az Eszközkezelésben kiszámolható karbantartási ütemezés soraiban lévő költségvetési költség. Ez akkor lehet hasznos, ha áttekintést szeretne kapni a várható költségekről, például a következő évre tervezett megelőző karbantartási feladatokkal kapcsolatos költségekről. A számítások a karbantartási ütemezés „Karbantartási tervek”, „Karbantartási körök” és „Karbantartási kérések” típusú sorain.

1. Kattintson az **Eszközkezelés** > **Lekérdezések** > **Eszközök** > **Karbantartási ütemezés költsége** elemre.

2. Ha pénzügyi dimenziókba csoportosítva szeretné a költségeket látni, a **Karbantartási ütemezés költsége** párbeszédpanelen válasszon ki egy **pénzügyi dimenziókészletet**.

>[!NOTE]
>A pénzügyi dimenziókészletek a **Főkönyv** > **Számlatükör** > **Dimenziók** > **Pénzügyi dimenziókészletek** részen állíthatók be.

3. A **Szint** mezőben adhatja meg, hogy a karbantartási ütemezés sorai milyen részletesen jelenítsék meg a munkavégzési helyszíneket. Ha például az „1” értéket adja meg a mezőben, és többszintű struktúrát használ a munkavégzési helyszínekhez, akkor a karbantartási ütemezés minden munkavégzési helyszínhez tartozó sora a legfelső szinten jelenik meg, így a sorban szereplő óraszámok hozzáadhatók az alacsonyabb szinten található munkavégzési helyszínekből. Ha a „0” értéket adja meg a **Szint** mezőben, akkor részletes eredmény jelenik meg, amely a karbantartási ütemezési minden sorát megjeleníti az összes olyan munkavégzési helyszínnél, amelyhez a sor kapcsolódik.

4. Ha adott eszközre vonatkozóan szeretne számítást végezni, kattintson a **Belefoglalandó rekordok** gyorslap **Szűrő** elemére, és válassza ki a megfelelő eszközöket. Ha szükséges, megadhatja a költségszámítás **várható kezdési dátumát**, vagy kiválaszthat egy másik **állapotot** a költségszámításhoz.

5. Kattintson az **OK** gombra az költségszámítás indításához.

6. A **Karbantartási ütemezés költsége** lap > **Csoportosítás alapja...** Művelet panel csoportjaiban kattintson a megfelelő gombokra a költségszámításhoz kívánt részletességi szintjének a megjelenítéséhez. A kiválasztott Művelet panel csoport gombjai ki vannak emelve. A gombra kattintva aktiválhatja vagy inaktiválhatja a funkciót.

7. Ha új költségszámítási számítást szeretne végezni, kattintson a **Költségszámítás** gombra.

A lenti ábra a karbantartás ütemezés költség-számításának eredményeit mutatja.

![1. ábra](media/17-preventive-maintenance.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]