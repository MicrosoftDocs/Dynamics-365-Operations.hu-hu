---
title: Commerce- és csevegési modul proaktív csevegési paraméterei
description: Ez a témakör a Commerce moduljainak proaktív paramétereit írja le Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-07-20
ms.openlocfilehash: f3cff89a25ff84414e7fdd32cbb26404c2080187
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690951"
---
# <a name="commerce-chat-module-proactive-chat-parameters"></a>Commerce- és csevegési modul proaktív csevegési paraméterei

[!include [banner](includes/banner.md)]

Ez a témakör a Commerce Csevegés és Az Ügyfélszolgálat moduljaival, illetve a commerce Commerce-beszélgetés Power Virtual Agents moduljainak proaktív paramétereit írja le Microsoft Dynamics 365 Commerce.

## <a name="proactive-chat-properties"></a>Proaktív csevegés tulajdonságai

A proaktív csevegési tulajdonságok a Commerce-webhelyszerkesztő moduljaival együtt a Commerce Commerce- és Ügyfélszolgáltatás commercechannel- és Commerce-beszélgetés Power Virtual Agents szolgáltatásának tulajdonságai ablakában találhatók.

> [!NOTE]
> Alapértelmezés szerint az itt felsorolt összes proaktív csevegési tulajdonság üres. Javasoljuk, hogy ismerje meg ezeket a tulajdonságokat, és csak a szükségesek szerint állítsa be őket. Ez a megközelítés segít csökkenteni a hibás proaktív csevegések kezdeményezését.

### <a name="proactive-chat"></a>Proaktív beszélgetés

| Rövid név | Leírás | Alapértelmezett érték |
|---------------|-------------|---------------|
| Engedélyezett | A vevőknek a különböző eseményindítók alapján való proaktív aktiválása. | Letiltva |
| Üdvözlőcsomó | A proaktív beszélgetés kezdeményezésekor használt üdvözlőüzenet | Üres |

### <a name="wait-time-proactive-chat"></a>Várakozási idő (proaktív beszélgetés)

| Rövid név | Leírás |
|---------------|-------------|
| Várakozási idő (mp) | Ennyi időt (másodpercben) töltöttek a webhely felhasználói a webhely lapján a proaktív beszélgetés kezdeményezése előtt. |
| Üdvözlőcsomó | A proaktív beszélgetés kezdeményezésekor használt üdvözlőüzenet |

### <a name="number-of-page-visits-proactive-chat"></a>Laplátogatások száma (proaktív csevegés)

| Rövid név | Leírás |
|---------------|-------------|
| Laplátogatások száma | A proaktív csevegés aktiválása előtti oldallátogatások száma. A webhely felhasználóinak előbb el kell fogadniuk a rá vonatkozó kérést a cookie-hozzájárulási üzenetben. |
| Üdvözlőcsomó | A proaktív beszélgetés kezdeményezésekor használt üdvözlőüzenet |

### <a name="specific-pages-proactive-chat"></a>Adott lapok (proaktív beszélgetés)

| Rövid név | Leírás |
|---------------|-------------|
| Oldalak | Azon lapok listája, amelyek a meglátogatott oldalakat elindító proaktív beszélgetéseket váltják ki. |
| Üdvözlőcsomó | A proaktív beszélgetés kezdeményezésekor használt üdvözlőüzenet |

### <a name="from-specific-pages-proactive-chat"></a>Adott oldalakról (proaktív beszélgetés)

| Rövid név | Leírás |
|---------------|-------------|
| Oldalak | Azon lapok listája, amelyek aktiválják a proaktív csevegést, amikor a felhasználók eltnakelnek onnan. |
| Üdvözlőcsomó | A proaktív beszélgetés kezdeményezésekor használt üdvözlőüzenet |

### <a name="specific-countryregion-proactive-chat"></a>Adott ország/régió (proaktív beszélgetés)

| Rövid név | Leírás |
|---------------|-------------|
| Ország kódja | Azok a felhasználók, akik megadott országokból vagy régiókból látogatott el, el fognak indítanának egy proaktív beszélgetéseket. Az ország-/régiókódnak két nagybetűnek kell lennie (például **US**). |
| Üdvözlőcsomó | A proaktív beszélgetés kezdeményezésekor használt üdvözlőüzenet |

### <a name="date-range-proactive-chat"></a>Dátumtartomány (proaktív beszélgetés)

| Rövid név | Leírás |
|---------------|-------------|
| Kezdő dátum (ht/hh/éva) | Az a dátum, amelyen vagy amely után el fognak indítva a proaktív beszélgetés. |
| Záró dátum (ht/hh/éva) | Az a dátum, amelyen vagy amely előtt el fognak indítva a proaktív beszélgetés. |
| Üdvözlőcsomó | A proaktív beszélgetés kezdeményezésekor használt üdvözlőüzenet |

### <a name="total-amount-in-cart-proactive-chat"></a>Teljes összeg a kosárban (proaktív beszélgetés)

| Rövid név | Leírás |
|---------------|-------------|
| Minimum | A bevásárlókocsiban található minimális pénzbeli összeg, amely proaktív csevegést vált ki, amikor a felhasználók ellátogatott a bevásárlókocsi oldalára. |
| Maximum | A bevásárlókocsiban található maximális pénzbeli összeg, amely proaktív csevegést vált ki, amikor a felhasználók ellátogatott a bevásárlókocsi oldalára. |
|Üdvözlőcsomó | A proaktív beszélgetés kezdeményezésekor használt üdvözlőüzenet |

### <a name="total-number-of-items-in-cart-proactive-chat"></a>A kosárban lévő cikkek száma összesen (proaktív beszélgetés)

| Rövid név | Leírás |
|---------------|-------------|
| Minimum | A bevásárlókocsiban található cikkek minimális száma, amely proaktív csevegést vált ki, amikor a felhasználók ellátogatott a bevásárlókocsi oldalára. |
| Maximum | A bevásárlókocsiban található cikkek maximális száma ( a bevásárlókocsit is beleértve), amely proaktív csevegést vált ki, amikor a felhasználók ellátogatott a bevásárlókocsi oldalára. |
| Üdvözlőcsomó | A proaktív beszélgetés kezdeményezésekor használt üdvözlőüzenet |

### <a name="specific-products-in-cart-proactive-chat"></a>A kosárban megadott termékek (proaktív csevegés)

| Rövid név | Leírás |
|---------------|-------------|
| Termékazonosító/ku. | A termék azonosítói/tartás egysége (SKU) számai, amelyek proaktív csevegést vált ki, amikor a felhasználók a bevásárlókocsiba lépnek. |
| Üdvözlőcsomó | A proaktív beszélgetés kezdeményezésekor használt üdvözlőüzenet |

## <a name="additional-resources"></a>További erőforrások

[Commerce commerce csevegési funkciók – áttekintés](commerce-chat-overview.md)

[Commerce Commerce Commerce Commerce commercechannel for Customer Service modul](commerce-chat-module.md)

[Commerce Commerce-beszélgetés modullal Power Virtual Agents](chat-module-pva.md)
