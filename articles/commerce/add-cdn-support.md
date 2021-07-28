---
title: Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása
description: Ez a témakör azt mutatja be, hogyan lehet hozzáadni tartalomkézbesítési hálózatot (CDN) a Microsoft Dynamics 365 Commerce-környezetéhez.
author: brianshook
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 85ca468fe6c440fb333b4c32f59f1d41eb89f4e6
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6346828"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a>Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet hozzáadni tartalomkézbesítési hálózatot (CDN) a Microsoft Dynamics 365 Commerce-környezetéhez.

Ha egy e-kereskedelmi környezetet hoz létre a Dynamics 365 Commerce alkalmazásban, akkor konfigurálhatja úgy, hogy együttműködjön az Ön CDN-szolgáltatásával. 

Az Ön egyéni tartománya az e-kereskedelmi környezet létesítési folyamata során engedélyezhető. Azt is megteheti, hogy egy szolgáltatáskérelmet használ a beállításához a létesítési folyamat befejeződését követően. Az e-kereskedelmi környezet létesítési folyamata egy olyan állomásnevet generál, amely a környezethez van társítva. Ez az állomásnév a következő formátummal rendelkezik, ahol az \<*e-commerce-tenant-name*\> az Ön környezetének neve:

&lt;e-kereskedelmi-bérlő-neve&gt;.commerce.dynamics.com

A létesítési folyamat során létrejövő állomásnév vagy végpont csak a következőhöz támogat Secure Sockets Layer (SSL) tanúsítvány: \*.commerce.dynamics.com. Nem támogatja az SSL-t egyéni tartományok esetében. Ezért a CDN egyéni tartományainak esetében meg kell szüntetnie az SSL-t, majd továbbítania kell a CDN-ből a forgalmat a Commerce által generált állomásnévre vagy végpontra. 

Ezenkívül a Commerce programból származó *statikák* (JavaScript vagy egymásba ágyazott stíluslap \[CSS\] fájlok) a Commerce által generált végpontból kerülnek kiszolgálásra (\*. commerce.dynamics.com). A statikák csak akkor gyorsítótárazhatók, ha az a Commerce által generált állomásnév vagy végpont a CDN mögé kerül.

## <a name="set-up-ssl"></a>SSL beállítása

Miután létrehozta a Commerce-környezetet a megadott egyéni tartománnyal, vagy miután egy szolgáltatáskéréssel megadta az egyéni tartományt a környezete számára, a Commerce előkészítési csapatával együttműködve meg kell terveznie a DNS változásait.

A korábban említettek szerint a létrehozott állomásnév vagy végpont csak a \*.commerce.dynamics.com esetében támogat SSL-tanúsítványt. Nem támogatja az SSL-t egyéni tartományok esetében.

## <a name="cdn-services"></a>CDN-szolgáltatások

A Commerce-környezettel együtt bármely CDN-szolgáltatás használható. Íme két példa:

- **Microsoft Azure Front Door Service** – Az Azure CDN-megoldása. További tájékoztatás az Azure Front Door Service szolgáltatásról: [Azure Front Door Service dokumentációja](/azure/frontdoor/).
- **Akamai Dynamic Site Accelerator** – További tudnivalók: [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).

## <a name="cdn-setup"></a>CDN beállítása

A CDN beállítási folyamata az alábbi általános lépésekből áll:

1. Adjon hozzá egy előtéri állomást.
1. Konfiguráljon egy háttérkészletet.
1. Állítsa be az útvonaltervezés szabályait.

### <a name="add-a-front-end-host"></a>Adjon hozzá egy előtéri állomást

Bármely CDN-szolgáltatás használható, de a jelen témakör példájában az Azure Front Door Service kerül felhasználásra. 

Az Azure Front Door Service beállításával kapcsolatos információkat itt talál: [Rövid útmutató: Front Door létrehozása egy magas szintű rendelkezésre állású, globális webes alkalmazáshoz](/azure/frontdoor/quickstart-create-front-door).

### <a name="configure-a-backend-pool-in-azure-front-door-service"></a>Háttérkészlet konfigurálása az Azure Front Door Service szolgáltatásban

Kövesse az alábbi lépéseket háttérkészlet konfigurálásához az Azure Front Door Service szolgáltatásban.

1. Adja hozzá az **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** elemet egy háttérkészlethez egyéni állomásként, amelynek a háttérállomás fejléce ugyanaz, az **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** esetében.
1. A **Terheléselosztás** alatt hagyja meg az alapértelmezett értékeket.
1. Tiltsa le a háttérkészlet állapotellenőrzését.

A következő ábra a **Háttéralkalmazás hozzáadása** párbeszédpanelt mutatja az Azure Front Door Service szolgáltatásban a megadott háttéralkalmazás állomásnevét.

![Háttérkészlet hozzáadása párbeszédpanel.](./media/CDN_BackendPool.png)

A következő ábra a **Háttérkészlet hozzáadása** párbeszédpanelt mutatja az Azure Front Door Service szolgáltatásban az alapértelmezett terheléselosztási értékeket.

![Háttérkészlet párbeszédpanel hozzáadása folytatva.](./media/CDN_BackendPool_2.png)

> [!NOTE]
> Győződjön meg róla, hogy letiltja az **Állapotellenőrzések** funkciót a saját Azure Front Door Service beállításakor a Commerce számára.


### <a name="set-up-rules-in-azure-front-door-service"></a>Szabályok beállítása az Azure Front Door Service szolgáltatásban

Ha be szeretne állítani egy útvonaltervezési szabályt az Azure Front Door Service szolgáltatásban, hajtsa végre az alábbi lépéseket.

1. Útvonaltervezési szabály hozzáadása.
1. A **Név** mezőbe írja be az **alapértelmezett** szót.
1. Az **Elfogadott protokoll** mezőben válassza a **HTTP és HTTPS** lehetőséget.
1. Az **Előtéri állomások** mezőbe írja be a **dynamics-ecom-bérlő-neve.azurefd.net** kifejezést.
1. Az **Egyeztetendő minták** alatt a felső mezőbe írja be a következőt: **/\***.
1. Az **Útvonal részletei** adja meg az **Útvonal típusa** beállítás számára a **Továbbítás** értéket.
1. Válassza ki a **Háttérkészlet** mezőben az **ecom-backend** elemet.
1. A **Továbbítási protokollok** mezőcsoportban válassza ki az **Egyeztetési kérelem** beállítást. 
1. Állítsa az **URL újraírása** beállítást **Letiltva** értékre.
1. Állítsa a **Gyorsítótárazás** beállítást **Letiltva** értékre.


> [!WARNING]
> Ha a használni kívánt tartomány már aktív és élő, hozzon létre egy támogatási jegyet az [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) **Támogatás** mozaikján, és kérjen segítséget a következő lépésekhez. További információért tekintse át a [Támogatás igénylése a Finance and Operations alkalmazásokhoz vagy a Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md) szolgáltatáshoz.

Ha a tartománya új, és nem egy korábban létező élő tartomány, akkor a saját egyéni tartományát hozzáadhatja az Azure Front Door Service konfigurációhoz. Ez lehetővé teszi a webforgalom számára, hogy az Azure Front Door példányon keresztül irányítsa a webhelyét. Az egyéni tartomány (például `www.fabrikam.com`) hozzáadásához be kell állítania egy kanonikus nevet (CNAME) a tartomány számára.

A következő ábra a **CNAME konfigurálása** párbeszédpanelt mutatja az Azure Front Door Service szolgáltatásban.

![CNAME-konfiguráció párbeszédpanel.](./media/CNAME_Configuration.png)

A tanúsítványt kezelheti az Azure Front Door Service szolgáltatásával, vagy használhatja az egyéni tartományhoz tartozó saját tanúsítványát.

A következő ábra az **Egyéni tartomány HTTPS** párbeszédpanelt mutatja az Azure Front Door Service szolgáltatásban.

![Egyéni tartomány HTTPS párbeszédpanel.](./media/Custom_Domain_HTTPS.png)

Az Azure Front Doorhoz való egyéni tartományok hozzáadásával kapcsolatos további információkat lásd az [Egyéni tartomány hozzáadása a Front Doorhoz](/azure/frontdoor/front-door-custom-domain) menüpontot.

A CDN-nek most már helyesen konfiguráltnak kell lennie, hogy használható legyen a Commerce webhelyével.

## <a name="additional-resources"></a>További erőforrások

[Tartalomkézbesítési hálózat végrehajtási beállításai](cdn-options.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]