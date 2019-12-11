---
title: Helyalapú áruházészlelés engedélyezése
description: Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a hely alapú üzletészlelést a Dynamics 365 Commerce-webhely számára.
author: brianshook
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a542d6987280451910b4ff3bcfb3a109a0e028c6
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697612"
---
# <a name="enable-location-based-store-detection"></a>Helyalapú áruházészlelés engedélyezése

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a hely alapú üzletészlelést a Dynamics 365 Commerce-webhely számára.

## <a name="overview"></a>Áttekintés

A Commerce szolgáltatás helyalapú áruházészlelés funkciója segítségével az ügyfeleknek a helyük alapján biztosíthat releváns webhelytartalmat. Ha a helyalapú áruházészlelés be van kapcsolva, a Commerce megjelenítési szolgáltatása a vevő webböngészőjének IP-címéből származó ország-/régiókódot használja, hogy a vevőt a legjobb földrajzi webhely-konfigurációhoz irányítsa.

## <a name="privacy-notice"></a>Adatvédelmi nyilatkozat

Ha bekapcsolja a helyalapú áruházészlelés funkciót, akkor a program elküldi a vevő böngészőjének adatait a Microsoft helyszolgáltatásának. Ezt az információt arra használja a program, ha a vevőnek a saját helyéhez releváns tartalmat nyújtsa. Mind a vevő böngészőjéből küldött információ, mind a vevőnek visszaküldött helyalapú információ az adatvédelmi és cookie-kkal kapcsolatos megfelelési irányelvek hatálya alá tartozik.

## <a name="turn-on-location-based-store-detection"></a>Helyalapú áruházészlelés bekapcsolása

Ha be szeretné kapcsolni a helyalapú áruházészlelést a Commerce szolgáltatásban, hajtsa végre az alábbi lépéseket.

1. A szerkesztési eszközben nyissa meg a webhelyét.
1. A bal oldali navigációs ablakban válassza ki a **Webhelykezelés** lehetőséget.
1. Válassza az **Webhelybeállítások** lehetőséget.
1. Állítsa a **Helyalapú áruházészlelés engedélyezése** beállítást **Be** értékre.

## <a name="additional-resources"></a>További erőforrások

[Online áruház áttekintése](online-store-overview.md)

[E-commerce webhely létrehozása](create-ecommerce-site.md)

[Új e-commerce webhely telepítése](deploy-ecommerce-site.md)

[Online webhely társítása csatornával](associate-site-online-store.md)

[A tartománynév konfigurálása](configure-your-domain-name.md)

[Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása](add-cdn-support.md)

[Felhasználói bejelentkezéshez használt egyéni lapok beállítása](custom-pages-user-logins.md)