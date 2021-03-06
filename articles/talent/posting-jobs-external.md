---
title: Állások feladása a Broadbean felületére az Attract szolgáltatásból
description: Ez a témakör bemutatja, hogyan lehet a Dynamics 365 Talent - Attract alkalmazást használni állások közzétételére a Broadbean felületén.
author: pganapmsft
manager: AnnBe
ms.date: 05/16/2019
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
ms.openlocfilehash: 41fa057606887069a9ea0f1f2178eeaff59f33ca
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461444"
---
# <a name="post-jobs-to-broadbean-from-attract"></a>Állások feladása a Broadbean felületére az Attract szolgáltatásból

[!include [banner](includes/banner.md)]

A Microsoft Dynamics 365 Talent: Attract segít a tehetségek bevonzásában azáltal, hogy lehetővé teszi, hogy állásait közvetlenül a Boadbean felületén tegye közzé. Miután [létrehozta az állást](./creating-jobs-attract.md) az Attract megoldásban, csupán egy gombot kell kiválasztania ahhoz, hogy az állást az összes potenciális pályázóhoz eljuttassa a Broadbean oldalán.

Az állásoknak a Broadbeanen történő feladásához megfelelő Broadbean-licenc szükséges. A Broadbean különböző termékeket és csomagokat kínál. Ha további tájékoztatást szeretne a Broadbean licenceléséről és árképzéséről, [vegye fel a kapcsolatot a Broadbeannel](https://www.broadbean.com/contact-us/).

Ha Ön adminisztrátor, akinek a Broadbean és az Attract integrációjának konfigurálásáról további információra van szüksége, tekintse meg [A Broadbean integrációjának engedélyezése a Microsoft Dynamics 365 Talent – Attract megoldásbaj](./attract-admin-job-board-settings.md) című cikket.

## <a name="post-jobs-to-broadbean"></a>Állások közzététele a Broadbean felületén

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
2. A **Feladások** szakaszban válassza a három pont (**...**) gombot, amely megfelel a Broadbean-nek, és válassza **Megtekintés** lehetőséget.

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

### <a name="troubleshoot-job-posting-to-broadbean"></a>A Broadbean álláshirdetéseinek hibaelhárítása

Ha probléma merül fel a feladással a Broadbean-be, próbálja meg ezeket a lépéseket.

1. Győződjön meg róla, hogy az Attract megoldásban megadott Broadbean hitelesítő adatok érvényesek és helyesek.
2. Ha a hitelesítő adatok érvényesek és helyesek forduljon a [Broadbean támogatáshoz](https://www.broadbean.com/resources/support/).
3. Ha a probléma továbbra is fennáll, forduljon [Microsoft támogatáshoz](./talent-support.md).

## <a name="see-also"></a>Lásd még

[Állás létrehozása, jóváhagyása és feladása az Attract alkalmazásban](./creating-jobs-attract.md)

[Broadbean integráció engedélyezése a Microsoft Dynamics 365 Talent - Attract megoldásban](./attract-admin-job-board-settings.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]