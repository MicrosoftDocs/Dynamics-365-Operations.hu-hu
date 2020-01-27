---
title: A tartománynév konfigurálása
description: Ez a témakör azt mutatja be, hogyan lehet konfigurálni a tartománynevet egy Microsoft Dynamics 365 e-kereskedelmi webhelyhez.
author: psimolin
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8f73c034563fb1cc6b05091b4c47e2a788d1a8b6
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945536"
---
# <a name="configure-your-domain-name"></a>A tartománynév konfigurálása

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet konfigurálni a tartománynevet egy Microsoft Dynamics 365 e-kereskedelmi webhelyhez. 

## <a name="add-domains-during-e-commerce-initialization"></a>Tartományok hozzáadása az e-kereskedelem inicializálásakor

Ha e-kereskedelmi környezethez szeretné társítani a tartományokat, akkor az [Új e-commerce webhely telepítése](deploy-ecommerce-site.md) részben leírtaknak megfelelően végezze el az e-kereskedelem inicializálását. Inicializáláskor a program megkéri, hogy az e-kereskedelmi környezet létrehozásához szükséges adatokat adja meg. A **Támogatott állomásnevek** mezőbe vegye fel az összes olyan tartományt, amelyet ezzel a környezettel használni szándékozik. Több tartományt kell elkülöníteni pontosvesszővel. Ily módon a tartományok konfigurálása az összes szükséges e-kereskedelem összetevőben megtörténik, és a program készen áll arra, hogy a tartalomkézbesítési hálózatból (CDN) vagy webkiszolgálóról érkező forgalmat váltson át, és azt az e-kereskedelmi frontendre irányítja.

## <a name="add-domains-after-e-commerce-initialization"></a>Tartományok hozzáadása az e-kereskedelem inicializálása után

Ha az e-kereskedelem inicializálását követően az e-kereskedelmi környezethez szeretné társítani az új tartományokat, akkor szolgáltatási kérelmet kell elküldenie.

## <a name="additional-resources"></a>További erőforrások

[Új e-commerce webhely telepítése](deploy-ecommerce-site.md)

[E-kereskedelmi webhely létrehozása](create-ecommerce-site.md)

[Online webhely társítása csatornával](associate-site-online-store.md)

[Robots.txt fájlok kezelése](manage-robots-txt-files.md)

[Felhasználói bejelentkezéshez használt egyéni lapok beállítása](custom-pages-user-logins.md)

[Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása](add-cdn-support.md)

[Helyalapú áruházészlelés engedélyezése](enable-store-detection.md)
