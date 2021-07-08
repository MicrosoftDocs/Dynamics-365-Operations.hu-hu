---
title: Szabadság vásárlása és eladása
description: A Dynamics 365 Human Resources alkalmazásban lehetséges benyújtani szabadáság vásárlására és eladására irányuló kérelmet a vállalatnál beállított szabadság vásárlására és eladására vonatkozó irányelvek alapján.
author: andreabichsel
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ESSLeaveBuyRequestEntry, EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6d32abacc1539cb930ad6f1ebcfe6fa9af4befcf
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271485"
---
# <a name="buy-and-sell-leave"></a>Szabadság vásárlása és eladása

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

Ha egy vásárlás vagy eladás szabadságra vonatkozó kérés munkafolyamata sikertelen, az **EssLeaveBuySellRequestApprover** jogosultsággal rendelkező felhasználók minden szabadság vásárlási és eladási kérés üzenetnaplóját áttekinthatják. Ehhez lépjen a **Szabadság és távollét > Link > Szabadság vásárlási és eladási kérések > Üzenetnaplóban** (a bal felső oldalon). Az **Üzenetnapló** bemutatja a felhasználókat a tranzakciók feldolgozásának és a kapcsolódó munkafolyamat-előzményeknek a megjelenítése.


## <a name="see-also"></a>Lásd még

[Szabadság és távollét áttekintése](hr-leave-and-absence-overview.md)</br>
[Szabadság vásárlásával és eladásával kapcsolatos irányelv kezelése](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
