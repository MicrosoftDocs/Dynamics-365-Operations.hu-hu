---
title: A tartománynév konfigurálása
description: Ez a témakör azt mutatja be, hogyan lehet konfigurálni a tartománynevet egy Microsoft Dynamics 365 e-kereskedelmi webhelyhez.
author: psimolin
manager: AnnBe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d3df563b62b40970509340802a09bb36dda14777
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001000"
---
# <a name="configure-your-domain-name"></a>A tartománynév konfigurálása


[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet konfigurálni a tartománynevet egy Microsoft Dynamics 365 e-kereskedelmi webhelyhez. 

## <a name="add-domains-during-e-commerce-initialization"></a>Tartományok hozzáadása az e-kereskedelem inicializálásakor

Ha a Dynamics 365 Commerce e-kereskedelmi környezethez szeretné társítani a tartományokat, akkor az [Új e-kereskedelmi bérlő üzembe helyezése](deploy-ecommerce-site.md) részben leírtaknak megfelelően végezze el az e-kereskedelem inicializálását. Inicializáláskor a program megkéri, hogy az e-kereskedelmi környezet létrehozásához szükséges adatokat adja meg. A **Támogatott állomásnevek** mezőbe vegye fel az összes olyan tartományt, amelyet ezzel a környezettel használni szándékozik. Több tartományt kell elkülöníteni pontosvesszővel. Ily módon a tartományok konfigurálása az összes szükséges Kereskedelmi összetevőben megtörténik, és a program készen áll arra, hogy a tartalomkézbesítési hálózatból (CDN) vagy webkiszolgálóról érkező forgalmat váltson át, és azt az e-kereskedelmi frontendre irányítja.

## <a name="add-domains-after-e-commerce-initialization"></a>Tartományok hozzáadása az e-kereskedelem inicializálása után

Ha az e-kereskedelem inicializálását követően az e-kereskedelmi környezethez szeretné társítani az új tartományokat, akkor szolgáltatási kérelmet kell elküldenie.

## <a name="additional-resources"></a>További erőforrások

[Új e-kereskedelmi bérlő telepítése](deploy-ecommerce-site.md)

[E-kereskedelmi webhely létrehozása](create-ecommerce-site.md)

[Dynamics 365 Commerce webhely társítása online csatornával](associate-site-online-store.md)

[robots.txt fájlok kezelése](manage-robots-txt-files.md)

[URL-átirányítások tömeges feltöltése](upload-bulk-redirects.md)

[B2C-bérlő beállítása a Commerce-ben](set-up-B2C-tenant.md)

[Felhasználói bejelentkezéshez használt egyéni lapok beállítása](custom-pages-user-logins.md)

[Több B2C-bérlő konfigurálása egy Commerce környezetben](configure-multi-B2C-tenants.md)

[Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása](add-cdn-support.md)

[Helyalapú áruházészlelés engedélyezése](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]