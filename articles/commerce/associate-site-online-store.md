---
title: Dynamics 365 Commerce webhely társítása online csatornával
description: Ez a témakör bemutatja, hogyan lehet egy vagy Microsoft Dynamics 365 Commerce több online áruházhoz kötni a webhelyet.
author: bicyclingfool
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 006c8b60791e0176c808762025f3bfdeaff9c48d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878673"
---
# <a name="associate-a-dynamics-365-commerce-site-with-an-online-channel"></a>Dynamics 365 Commerce webhely társítása online csatornával

[!include [banner](includes/banner.md)]

Ez a témakör bemutatja, hogyan lehet egy vagy Microsoft Dynamics 365 Commerce több online áruházhoz kötni a webhelyet. 

Miután a Dynamics 365 Commerce e-kereskedelmi környezetet a Microsoft Dynamics Lifecycle Services (LCS) portál segítségével létesítette, készen áll az első e-kereskedelmi webhely létrehozására. A webhely kezdeti létrehozásának részeként a webhelyet a korábban létrehozott online áruházhoz kell társítania. Ezzel a lépéssel a webhelyet egy online csatornához köti, és ezáltal a webhely képes a navigációs hierarchia, a termékek, kategóriák, árak, szállítási lehetőségek és az online áruházban megadott minden más elem megjelenítésére.

Egy új webhely létrehozásához és online áruházhoz társításához az LCS-ben válassza ki a webhely-létrehozási környezet hivatkozását. Ezután a webhely-létrehozási környezet oldalán válassza az **Új webhely** elemet. Az **Új webhely** párbeszédpanelen meg kell adnia néhány alapvető információt a webhelyéről. A kötelezően megadandő információk teljes magyarázatával kapcsolatban tekintse meg: [Új e-kereskedelmi webhely létrehozása](create-ecommerce-site.md).

Miután létrehozta a webhelyet, a **Termékek** lap kiválasztásával ellenőrizheti, hogy az online áruházhoz van-e társítva. Az online áruházhoz rendelt termékek választékát kell látnia. A lap bal felső részén található legördülő mező segítségével is megnyithatja a termékeket kategóriánként.

## <a name="additional-resources"></a>További erőforrások

[Tartománynév konfigurálása](configure-your-domain-name.md)

[Új e-kereskedelmi bérlő telepítése](deploy-ecommerce-site.md)

[E-kereskedelmi webhely létrehozása](create-ecommerce-site.md)

[Robots.txt fájlok kezelése](manage-robots-txt-files.md)

[URL-átirányítások tömeges feltöltése](upload-bulk-redirects.md)

[B2C-bérlő beállítása a Commerce-ben](set-up-B2C-tenant.md)

[Felhasználói bejelentkezéshez használt egyéni lapok beállítása](custom-pages-user-logins.md)

[Több B2C-bérlő konfigurálása egy Commerce környezetben](configure-multi-B2C-tenants.md)

[Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása](add-cdn-support.md)

[Helyalapú áruházészlelés engedélyezése](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]