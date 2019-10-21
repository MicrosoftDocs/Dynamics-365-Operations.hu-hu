---
title: Karbantartási ütemezés költsége
description: Ez a cikk az Eszközkezelés karbantartási ütemezésének költségét ismerteti.
author: josaw1
manager: AnnBe
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b2f53a4a64b06efc9269c607bfe1fc3a41c90cdd
ms.sourcegitcommit: 6476f27c8d3dced7c2e9a7344a4e378b51a1983e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/27/2019
ms.locfileid: "1922068"
---
# <a name="maintenance-schedule-cost"></a>Karbantartási ütemezés költsége

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Az Eszközkezelésben kiszámolható karbantartási ütemezés soraiban lévő költségvetési költség. Ez akkor lehet hasznos, ha áttekintést szeretne kapni a várható költségekről, például a következő évre tervezett megelőző karbantartási feladatokkal kapcsolatos költségekről. A számítások a karbantartási ütemezés „Karbantartási tervek”, „Karbantartási körök” és „Karbantartási kérések” típusú sorain.

1. Kattintson az **Eszközkezelés** > **Lekérdezések** > **Eszközök** > **Karbantartási ütemezés költsége** elemre.

2. Ha pénzügyi dimenziókba csoportosítva szeretné a költségeket látni, a **Karbantartási ütemezés költsége** párbeszédpanelen válasszon ki egy **pénzügyi dimenziókészletet**.

>[!NOTE]
>A pénzügyi dimenziókészletek a **Főkönyv** > **Számlatükör** > **Dimenziók** > **Pénzügyi dimenziókészletek** részen állíthatók be.

3. A **Szint** mezőben adhatja meg, hogy a karbantartási ütemezés sorai milyen részletesen jelenítsék meg a munkavégzési helyszíneket. Ha például az „1” értéket adja meg a mezőben, és többszintű struktúrát használ a munkavégzési helyszínekhez, akkor a karbantartási ütemezés minden munkavégzési helyszínhez tartozó sora a legfelső szinten jelenik meg, így a sorban szereplő óraszámok hozzáadhatók az alacsonyabb szinten található munkavégzési helyszínekből. Ha a „0” értéket adja meg a **Szint** mezőben, akkor részletes eredmény jelenik meg, amely a karbantartási ütemezési minden sorát megjeleníti az összes olyan munkavégzési helyszínnél, amelyhez a sor kapcsolódik.

4. Ha adott eszközre vonatkozóan szeretne számítást végezni, kattintson a **Belefoglalandó rekordok** gyorslap **Szűrő** elemére, és válassza ki a megfelelő eszközöket. Ha szükséges, megadhatja a költségszámítás **várható kezdési dátumát**, vagy kiválaszthat egy másik **állapotot** a költségszámításhoz.

5. Kattintson az **OK** gombra az költségszámítás indításához.

6. A **Karbantartási ütemezés költsége** lap > **Csoportosítás alapja...** műveleti ablaktáblacsoportjaiban kattintson a megfelelő gombokra a költségszámításhoz kívánt részletességi szintjének a megjelenítéséhez. A kiválasztott műveleti ablaktáblacsoport gombjai ki vannak emelve. A gombra kattintva aktiválhatja vagy inaktiválhatja a funkciót.

7. Ha új költségszámítási számítást szeretne végezni, kattintson a **Költségszámítás** gombra.

A lenti ábra a karbantartás ütemezés költség-számításának eredményeit mutatja.

![1. ábra](media/17-preventive-maintenance.png)

