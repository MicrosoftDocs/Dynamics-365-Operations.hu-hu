---
title: Álláshirdetések feladása külső karrieroldalak felületére az Attractból
description: Ez a témakör bemutatja, hogyan lehet a Dynamics 365 for Talent - Attract alkalmazást használni állások közzétételére külső toborzóoldalakon
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
ms.openlocfilehash: 936ff85a4dabb715cb83b875a5c58c9fb7a0ac26
ms.sourcegitcommit: 7c49475402632069685df714546770d30804af7f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/11/2019
ms.locfileid: "1739817"
---
# <a name="post-jobs-to-broadbean"></a>Állások közzététele a Broadbean felületén

[!include [banner](../includes/banner.md)]

A Microsoft Dynamics 365 for Talent: Attract segít a tehetségek bevonzásában azáltal, hogy lehetővé teszi, hogy állásait közvetlenül a Boadbean felületén tegye közzé. Miután [létrehozta az állást](./creating-jobs-attract.md) az Attract megoldásban, csupán egy gombot kell kiválasztania ahhoz, hogy az állást az összes potenciális pályázóhoz eljuttassa a Broadbean oldalán.

Az állásoknak a Broadbeanen történő feladásához megfelelő Broadbean-licenc szükséges. A Broadbean különböző termékeket és csomagokat kínál. Ha további tájékoztatást szeretne a Broadbean licenceléséről és árképzéséről, [vegye fel a kapcsolatot a Broadbeannel](https://www.broadbean.com/contact-us/).

Ha Ön egy olyan adminisztrátor, akinek több információra van szüksége a Broadbean-integrációnak az Attract szolgáltatással történő konfigurálásával kapcsolatban, lásd: [Külső álláshirdetések beállításainak megadása](./attract-admin-job-board-settings.md).

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

[Állások létrehozása](./creating-jobs-attract.md)

[Külső álláshirdetések beállításainak megadása](./attract-admin-job-board-settings.md)
