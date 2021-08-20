---
title: Helyalapú áruházészlelés engedélyezése
description: Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a hely alapú üzletészlelést a Dynamics 365 Commerce-webhely számára.
author: brianshook
ms.date: 07/02/2020
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
ms.openlocfilehash: 98aa781a42b1c82cc00c8a680007b7200e9c7413fb8e3a67b0c723ff62c1d8e1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6749876"
---
# <a name="enable-location-based-store-detection"></a>Helyalapú áruházészlelés engedélyezése

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a hely alapú üzletészlelést a Dynamics 365 Commerce-webhely számára.

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

[Tartománynév konfigurálása](configure-your-domain-name.md)

[Új e-kereskedelmi bérlő telepítése](deploy-ecommerce-site.md)

[E-kereskedelmi webhely létrehozása](create-ecommerce-site.md)

[Dynamics 365 Commerce webhely társítása online csatornával](associate-site-online-store.md)

[robots.txt fájlok kezelése](manage-robots-txt-files.md)

[URL-átirányítások tömeges feltöltése](upload-bulk-redirects.md)

[B2C-bérlő beállítása a Commerce-ben](set-up-B2C-tenant.md)

[Felhasználói bejelentkezéshez használt egyéni lapok beállítása](custom-pages-user-logins.md)

[Több B2C-bérlő konfigurálása egy Commerce környezetben](configure-multi-B2C-tenants.md)

[Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása](add-cdn-support.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
