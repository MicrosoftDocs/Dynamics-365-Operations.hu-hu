---
title: Szabadság vásárlása és eladása
description: Ez a témakör azt ismerteti, hogyan lehet a vásárlásra és eladásra vonatkozó kéréseket a Dynamics 365 Human Resources szolgáltatásban benyújtani.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ESSLeaveBuyRequestEntry, EssWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 695840516849dcfeb69895f6808d828d5878c59b
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8688176"
---
# <a name="buy-and-sell-leave"></a>Szabadság vásárlása és eladása


>[!Important]
>Az ebben a témakörben említett funkciók jelenleg csak a különálló Dynamics 365 Human Resources rendszerében lévő vevőknek érhetők el. A funkciók egy része vagy egésze a Finance infrastruktúra jövőbeni kiadásának részeként lesz elérhető a Finance 10.0.26-ös kiadása után.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A Dynamics 365 Human Resources alkalmazásban lehetséges benyújtani szabadáság vásárlására és eladására irányuló kérelmet a vállalatnál beállított szabadság vásárlására és eladására vonatkozó irányelvek alapján.  

## <a name="request-to-buy-leave"></a>Szabadságvásárlási kérelem

1. Az **Alkalmazotti önkiszolgáló rendszer** munkaterületen válassza a **Szabadságvásárlási kérelem** lehetőséget a **Szabadságegyenlegek** csempén. 

2. Adjon meg egy **Szabadságtípust**, és adja meg az **Összeg** elemet a megvásárolni kívánt szabadság összegéhez. 

3. Ha elkészült, válassza a **Küldés** elemet a kérés elküldéséhez. 

Az egyenlegei vagy automatikusan frissülnek, vagy egy jóváhagyási folyamaton mennek keresztül a frissítés előtt. Ez attól függ, hogy hogyan lett konfigurálva a vásárlási irányelv.

## <a name="request-to-sell-leave"></a>Szabadságeladási kérelem

1. Az **Alkalmazotti önkiszolgáló rendszer** munkaterületen válassza a **Szabadságeladási kérelem** lehetőséget a **Szabadságegyenlegek** csempén. 

2. Adjon meg egy **Szabadságtípust**, és adja meg az **Összeg** elemet az eladni kívánt szabadság összegéhez. 

3. Ha elkészült, válassza a **Küldés** elemet a kérés elküldéséhez.

Az egyenlegei vagy automatikusan frissülnek, vagy egy jóváhagyási folyamaton mennek keresztül a frissítés előtt. Ez attól függ, hogy hogyan lett konfigurálva a vásárlási irányelv.


## <a name="troubleshooting"></a>Hibaelhárítás 

Ha egy vásárlás vagy eladás szabadságra vonatkozó kérés munkafolyamata sikertelen, az **EssLeaveBuySellRequestApprover** jogosultsággal rendelkező felhasználók minden szabadság vásárlási és eladási kérés üzenetnaplóját áttekinthatják. Ehhez lépjen a **Szabadság és távollét > Linkek > Szabadság vásárlási és eladási kérések > Üzenetnaplóban** menüpontra (a bal felső oldalon). Az **Üzenetnapló** bemutatja a felhasználókat a tranzakciók feldolgozásának és a kapcsolódó munkafolyamat-előzményeknek a megjelenítése.


## <a name="see-also"></a>Lásd még

[Szabadság és távollét áttekintése](hr-leave-and-absence-overview.md)</br>
[Szabadság vásárlásával és eladásával kapcsolatos irányelv kezelése](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
