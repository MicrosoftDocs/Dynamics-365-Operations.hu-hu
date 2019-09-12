---
title: Eszközök számlálóinak manuális frissítése
description: Ez a témakör az Eszközkezelésben használt eszközszámlálók manuális frissítését ismerteti.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
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
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1e7c5ec288404c18b00f9dcd0e66f50744d0aa2f
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875695"
---
# <a name="manual-update-of-asset-counters"></a>Eszközök számlálóinak manuális frissítése

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


A számlálókkal regisztrációk hozhatók létre egy eszközön, például a művelet óraszámával vagy a gyártott mennyiséggel kapcsolatban.

Ha a számlálóhoz kiválasztott típust a számláló értékeinek öröklésére állítja (az **Eszközkezelés** > **Beállítás** > **Eszköztípusok** > **Számlálók** > **Általános** gyorslap > **Elem számlálóértékeinek öröklése** váltógomb „Igen” értékű), és új adott típusú számlálósort hoz létre, akkor az adott számlálótípust használó alárendelt eszközök automatikusan frissülnek.

A **Minden eszköz** részen, az eszköz leolvasott értékei alapján hozhatja létre az eszköz óraszám- vagy mennyiségszámláló regisztrációit.

1. Kattintson az **Eszközkezelés** > **Általános** > **Eszközök** > **Összes eszköz** elemre.

2. Válassza ki az eszközt a listából, majd kattintson a **Számlálók** elemre. Az **Eszközszámlálók** képernyőn látható a kiválasztott eszköz korábbi számlálóregisztrációinak a listája.

3. Új regisztráció létrehozásához kattintson az **Új** gombra. A program automatikusan beszúrja az eszközazonosítót.

4. A **Számláló** mezőben válassza ki a megfelelő számlálót. Csak az eszközön kiválasztott eszköztípushoz kapcsolódó számlálók érhetők el. A program automatikusan beilleszti a kapcsolódó egységet az **Egység** mezőbe.

5. Válassza ki a számláló regisztrációjának dátumát és időpontját.

6. Az **Érték** mezőbe írja be a legutóbbi számlálóregisztráció óta létrehozott számot, vagy az **Összesített érték** mezőbe írja be a teljes számot.

- Ha egy eszközhöz fizikailag telepít új számlálót, akkor a módosítást regisztrálni kell az eszközön az **Eszközszámlálók** részen. Ezután két, azonos időbélyegzővel rendelkező regisztrációs sort kell létrehoznia, és az új számláló sorában be kell jelölni a **Számláló alaphelyzetbe állítása** jelölőnégyzetet. A két regisztrációs sor létrehozásakor az első sor tartozzon a helyettesíteni kívánt számlálóhoz. Az **Összesen** mezőben lévő teljes szám az adott típusú számláló összes regisztrált értékének az összege.  
- Ha a **Számláló alaphelyzetbe állítása** jelölőnégyzet be van jelölve egy olyan eszközön, amelyiknek az időköztípusa „Egyszer ettől...” vagy „Egyszer elérés után...”, akkor a számláló továbbra is aktív az új számlálósorban, mert külön számlálósor jön létre, és a rendszer az új számlálóval kezd újra.

![1. ábra](media/11-work-orders.png)


Ha több eszközön kell számlálót regisztrálnia, akkor ezt az **Eszközkezelés** > **Lekérdezések** > **Eszközök** > **Eszközszámlálók** részen teheti meg.

>[!NOTE]
>A manuális számlálóregisztrációk eltéréseinek meghatározásához beállíthat tartományt, illetve megadhatja azt az üzenettípust, amelyet meg kell jeleníteni, ha a regisztrációk a megadott tartományon kívül esnek. A számlálók beállításáról a [Számlálók](../setup-for-objects/counters.md) című cikkben talál további információt.
