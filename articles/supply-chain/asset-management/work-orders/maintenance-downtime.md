---
title: Karbantartás miatti üzemkimaradás
description: Ez a cikk a karbantartás miatti üzemkimaradás Eszközkezelésben való használatát írja le.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
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
ms.openlocfilehash: cc79dc1b5911679586fa560142ada5add1a881d2
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918244"
---
# <a name="maintenance-downtime"></a>Karbantartás miatti üzemkimaradás


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

A karbantartás miatti üzemkimaradás regisztrációkat a munkarendelésen kiválasztott eszközre vonatkozóan lehet létrehozni. Ez akkor lehet hasznos, ha a termelési területen egy vagy több gépen szeretné rögzíteni a karbantartás miatti üzemkimaradást. Először létre kell hoznia azokat a karbantartás miatti üzemkimaradásokat, amelyeket használni szeretne, például a meghibásodást és a tervezett leállítást. Ezt a **Karbantartás miatti üzemkimaradás okkódjai** helyen teheti meg. Ezután létrehozhatja a karbantartás miatti üzemkimaradás regisztrációkat a **Karbantartás miatti üzemkimaradás** helyen, és hozzáadhatja a megfelelő okkódokat.

## <a name="create-maintenance-downtime-reason-codes"></a>karbantartás miatti üzemkimaradás okkódjainak létrehozása

1. Kattintson az **Eszközkezelés** > **Beállítás** > **Munkarendelések** > **Karbantartás miatti üzemkimaradás okkódjai** lehetőségre.

2. Kattintson az **Új** elemre.

3. Írja be az azonosítót a **Karbantartás miatti üzemkimaradás okkódja** mezőbe.

4. Adjon meg egy nevet az okkódnak a **Név** mezőben.

5. Jelölje be a **KPI befoglalása** jelölőnégyzetet, ha azt szeretné, hogy az okkód szerepeljen az eszköz KPI-számításaiban. A tervezett termelési leállások általában nem szerepelnek a KPI-számításokban, mivel nem befolyásolják a várt teljesítményt.

6. Kattintson a **Mentés** gombra.

![1. ábra](media/15-work-orders.png)


Miután létrehozta a használni kívánt karbantartás miatti üzemkimaradás okkódokat, létrehozhatja a munkarendelésekhez és a eszközökhöz tartozó karbantartás miatti üzemkimaradás regisztrációkat.


## <a name="create-maintenance-downtime-registrations"></a>karbantartás miatti üzemkimaradás regisztrációinak létrehozása

1. Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.

2. Válassza ki a munkarendelést, majd kattintson a **Karbantartás miatti üzemkimaradás** elemre.

3. Kattintson az **Új** elemre.

4. Dátum-és időintervallum beszúrása a karbantartási leállás regisztrálásához a **Kezdés** és **Befejezés** mezőkbe.

5. A **Befejezés** mező kihagyásakor a program automatikusan beszúrja az időtartamot órában az **Időtartam** mezőbe.

6. Válasszon egy okkódot a **karbantartás miatti üzemkimaradás okkódja** mezőben.

7. Ha további regisztrációkat szeretne hozzáadni, ismételje meg a 3-6. lépést.

8. Kattintson a **Mentés** gombra.


![2. ábra](media/16-work-orders.png)


A karbantartás miatti üzemkimaradások kiszámításához használt naptár a tárgyi eszközök és paraméterek beállításában megadott beállítástól függ. Ha ki van választva egy erőforrás egy eszközön az **Összes eszköz** > **tárgyi eszköz** gyorslap > **erőforrás** mezőjében, akkor a program a társított erőforráscsoport naptárát használja, ahogy az a következő ábrán látható.

![3. ábra](media/17-work-orders.png)


Ha az eszközhöz nincs kiválasztva erőforrás, akkor a program az **Eszközkezelés paraméterei** alatt kiválasztott naptárat használja a következő ábrának megfelelően.

![4. ábra](media/18-work-orders.png)


Kattintson a **Vállalati eszközkezelés** > **Lekérdezések** > **Karbantartás miatti üzemkimaradás** lehetőségre az összes karbantartás miatti üzemkimaradás regisztráció megtekintéséhez.

>[!NOTE]
>Az **Eszközkezelés** modulban használt összes naptár a szervezeti felügyelet **Szervezeti adminisztráció** > **Beállítás** > **Naptárak** > **Naptárak** helyen van beállítva.

