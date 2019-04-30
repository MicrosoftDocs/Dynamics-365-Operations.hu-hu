---
title: Álláshirdetések feladása külső karrieroldalak felületére az Attractból
description: Ez a témakör bemutatja, hogyan lehet a Dynamics 365 for Talent - Attract alkalmazást használni állások közzétételére külső toborzóoldalakon
author: pganapmsft
manager: AnnBe
ms.date: 03/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-03-19
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: eca599ad189edae29ef2de496196b08799a5e745
ms.sourcegitcommit: 1653d1e28d02f8a9a4bea8df562ac98d7a350ed1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/15/2019
ms.locfileid: "993668"
---
# <a name="post-jobs-to-external-career-sites-from-attract"></a>Álláshirdetések feladása külső karrieroldalak felületére az Attractból

[!include [banner](../includes/banner.md)]

A nyitott pozíciókat elehető legjobb alkalmas jelölt számára szeretné eljuttatni. A toborzási oldalak, például a Broadbean segítenek elérni ezt a célt. A Microsoft Dynamics 365 Talent: Attract lehetővé teszi, hogy állásokat egyen közzé a Broadbean oldalon, és a Microsoft folyamatosan új ajánlatokat biztosít majd ezen a területen.

## <a name="post-jobs-to-broadbean"></a>Állások közzététele a Broadbean-en

Mielőtt állást tehetne közzé a Broadbean-en konfigurálnia kell az Broadbean integrációt.

> [!NOTE]
> - Állások közzétételéhez külső webhelyeken rendelkeznie kell az [Átfogó felvételi bővítménnyel](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).
> - Ez a funkció jelenleg előnézetben van. Ha ki szeretné próbálni, akkor [be kell kapcsolnia az Attract rendszergazdai beállításai között](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).

### <a name="configure-broadbean-integration"></a>Broadbean integráció konfigurálása

1. Jelentkezzen be Attract alkalmazásba rendszergazdaként
2. Válassza ki a **Beállítások** gombot (fogaskerék-szimbólum) a lap jobb felső sarkában, majd válassza a **Felügyeleti központ** lehetőséget.
3. A **Feladattábla beállításai** lapon a **Broadbean integráció engedélyezése** szakaszban, kapcsolja be az integrációt.
4. Forduljon a Broadbean-hoz, és adja meg az adatokat a **Felhasználónév, Ügyfél-azonosító, Titkosítási Token** elemekhez.

> [!WARNING]
> A Broadbean hitelesítő adatai kényes és bizalmas természetűek. Ezért átgondoltan ossza meg azokat. Mindenki akinek rendszergazdai szerepköre van az Attract megoldásban megtekintheti ezeket a hitelesítő adatokat.

> [!NOTE]
> A Microsoft és Attract vesz nem részt ezen értékek létrehozásában és kezelésében. Az Ön felelőssége naprakészen tartani azokat az Attract megoldásban, illetve az, hogy együttműködjön a Broadbeannel, hogy megoldja a hitelesítési adatokkal kapcsolatos esetleges problémákat.

### <a name="post-a-job-to-broadbean"></a>Állás közzététele a Broadbean-en

Miután a Broadbean be van kapcsolva,a toborzók és a rendszergazdák állásokat tehetnek közzé rajta. Egy jelentkezési URL-cím szükséges az álláshoz.

1. Az Attract megoldásban nyissa meg az állást, amelyet fel szeretné adni, a Broadbean-be.
2. A **Feladások** részben válassza a **Feladás most** gombot, amely megfele a Broadbean-nek.
3. Kövesse a Broadbean ablakának utasításait.

Az Attract a következő adatokat továbbítja a Broadbean számára:

- Kérésazonosító
- Beosztás
- Feladat leírása
- Munkavégzés helyszíne
- Jelentkezési URL
- Toborzó adatai

A feladás sikeres befejezése után a Broadbean-ben a **Feladások** részében Attract állásnak a Broadbean státusza **Feladva**.

> [!NOTE]
> - A Broadbean megköveteli az **Iparág** mezőt. Alapértelmezés szerint ez a mező **IT** értékre van beállítva. Az érték módosítható a megfelelő iparágra a Broadbean álláshirdetés ablakában.
> - Eltart egy ideig, amíg a Boradbean befejezi az állás közzétételét az összes kiválasztott hirdetőfelületre Emiatt előfordulhat, hogy csak egy kis késedelemmel végzi el az Attract az állapotfrissítés t az álláshoz.

### <a name="view-a-broadbean-job-posting"></a>Egy Broadbean álláshirdetés megtekintése

Miután Broadbean-ben közzétesz egy állást az, Attractból is megtekintheti.

1. Az Attract megoldásban nyissa meg az állást, amelyet meg szeretne tekinteni a Broadbean-ben.
2. A **feladások** szakaszban,válassz a három pont (**...**) gombot, amely megfelel a Broadbean-nek, és válassza **Megtekintés** lehetőséget.

A Broadbean álláshirdetés egy új ablakban jelenik meg.

### <a name="update-a-broadbean-job-posting"></a>Egy Broadbean álláshirdetés frissítése

Kétféle módon frissíthet egy Broadbean álláshirdetést.

1. Az Attract megoldásban nyissa meg az állást, amelyet frissíteni szeretne.
2. A **Feladások** részben válassza a **Feladás frissítése** gombot, amely megfele a Broadbean-nek.
3. Szerkessze a feladást a Broadbean ablakában.

– vagy –

1. Az Attract megoldásban nyissa meg az állást, amelyet meg szeretne tekinteni a Broadbean-ben.
2. A **feladások** szakaszban,válassz a három pont (**...**) gombot, amely megfelel a Broadbean-nek, és válassza **Megtekintés** lehetőséget.
3. Broadbean ablakában szerkesztheti az állás adatait, és ezután újraküldheti az állást. Az állás részletei az Attract megoldásban nem változnak.

### <a name="remove-a-broadbean-job-posting"></a>Egy Broadbean álláshirdetés eltávolítása

A Broadbean-ből igény esetén eltávolíthatja az álláshirdetést.

1. Az Attract megoldásban nyissa meg az állást, amelyet el szeretne távolítani.
2. A **Feladások** szakaszban,válassza a három pont (**...**) gombot, amely megfelel a Broadbean-nek, és válassza **Közzététel eltávolítása** lehetőséget.

Miután a Broadbean eltávolítja az állást Broadbean elemhez az Attract megoldásban megjelenik egy **Feladás most** gomb. Ez a gomb jelzi, hogy az állás törölve lett, és újra fel lehet adni.

### <a name="troubleshoot-the-broadbean-integration"></a>Broadbean-integráció – hibaelhárítás

Ha probléma merül fel a feladással a Broadbean-be, próbálja meg ezeket a lépéseket.

1. Győződjön meg róla, hogy az Attract megoldásban megadott Broadbean hitelesítő adatok érvényesek és helyesek.
2. Ha a hitelesítő adatok érvényesek és helyesek forduljon a [Broadbean támogatáshoz](https://www.broadbean.com/resources/support/).
3. Ha a probléma továbbra is fennáll, forduljon [Microsoft támogatáshoz](./talent-support.md).
