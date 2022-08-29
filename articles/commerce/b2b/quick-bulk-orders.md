---
title: B2B webhelyrendelések gyors elküldése
description: Ez a témakör olyan Microsoft Dynamics 365 Commerce lehetőségeket ismertet, amelyek lehetővé tírják az üzleti (B2B) webhely felhasználóinak gyors tömeges elküldéset és a rendelések ismételt megismétlhetőségét.
author: ShalabhjainMSFT
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.23
ms.search.industry: retail
ms.search.form: RetailOperations
ms.openlocfilehash: a153be1da43b63e8d29d6ece3dcbf47d5bbec487
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275120"
---
# <a name="place-b2b-website-orders-quickly"></a>B2B webhelyrendelések gyors elküldése

[!include [banner](../../includes/banner.md)]

Ez a témakör olyan Microsoft Dynamics 365 Commerce lehetőségeket ismertet, amelyek lehetővé tírják az üzleti (B2B) webhely felhasználóinak gyors tömeges elküldéset és a rendelések ismételt megismétlhetőségét.

Dynamics 365 Commerce A B2B e-commerce webhelyek segítségével a felhasználók szokásos műveleteket végezhetnek el, például keresést és böngészést végezhetnek el az új termékek között, megtekinthetik a termék részletes adatait, cikkeket adhatnak a kosárhoz, illetve kijelentkezhetik őket. Ugyanakkor míg a vevők általában kis mennyiségben rendelik a cikkeket, és csak egyszer rendelik meg őket, a B2B vevők jellemzően nagy mennyiségben rendelnek cikkeket, és többször rendelik újra őket. Mivel ezek a vevők általában pontosan tudják, hogy milyen cikkeket vásárolnak, gyakran kihagyják a termékfelfedezési fázist, és közvetlenül a rendeléshez ugrik. Ezeknek a vevőknek az igényeinek kielégítése érdekében a Commerce B2B e-commerce webhelyek különféle lehetőségeket nyújtanak, amelyek segítik őket a rendelések gyors megrendelésében.

## <a name="bulk-order-by-item-number"></a>Tömeges rendelés cikkszám szerint

A Commerce B2B e-commerce webhelyek lehetővé teszi a webhely felhasználóinak, hogy cikkeket vegyenek fel a kosárba úgy, hogy a kívánt mennyiséggel együtt termékcikkszámokat adnak meg.

Az alábbi ábra a gyors rendelési tételek termékszámok szerint történő bevitelét mutatja be.

![Gyors rendelésbevitel termékcikkszám szerint.](../media/QuickAddByItem.png)

## <a name="bulk-order-by-variant"></a>Tömeges rendelés változatok szerint

A Commerce B2B e-commerce webhelyek segítségével a webhely felhasználói gyorsan hozzáadják ugyanannak a terméknek a különböző változatait egyetlen nézetben, és méret, szín és stílus szerint jelenítik meg a készlet rendelkezésre állását. Ezen kívül a telephely felhasználói egyszerűen **megadhatja ugyanazt a mennyiséget minden készleten álló termékhez az Összes mennyiség beírva beállításával**.

Az alábbi ábra a gyorsrendelési bevitelt mutatja be, ahol a "Adja meg a mennyiségek bevitele" funkciót használja a rendszer.

![A "Mennyiségek bevitele" funkciót használó gyorsrendelési bejegyzés.](../media/MatrixView.png)

## <a name="use-order-templates-for-quick-order-entry"></a>Rendeléssablonok használata gyors rendelésbevitelhez

A B2B webhelyek bevásárlói gyakran rendelnek együtt meghatározott cikkeket. Ha például egy kivitelezési telephelyre ad fel rendeléseket, akkor érdemes ingeket, ingeket, stb. ingeket, stb. Ha olyan kórházaknak ad ki rendeléseket, ahol más az egyenruha, 444 éves vagy a tisztítási személyzet tagjainak, akkor érdemes az egyes egyenruhatípusokat összecsoportosodni a könnyebb rendelés érdekében. Ilyen típusú helyzetekben a Commerce B2B webhelyek lehetővé teszik a rendeléssablonok létrejöttét. A webhely felhasználói bármilyen számú egyéni sablont létrehozhatnak, majd a sablonokból megrendelhetik az összes, illetve egy része elemet.

A következő ábra egy rendeléssablon példáját mutatja be.

![Példa rendeléssablonra](../media/OrderTemplateHeader.png)

A következő ábra a rendeléssablonok részletes nézetét mutatja be.

![Példa egy rendeléssablon részletes nézetre.](../media/OrderTemplateLines.png)

## <a name="reorder-from-order-history"></a>Újrarendelés a rendelési előzményekből

A Commerce B2B e-commerce webhelyek segítségével a webhely felhasználói gyorsan átrendelhetik a cikkeket a rendelési előzményeikből. A webhely felhasználói vagy a rendelési előzményeikből vásárolnak kiválasztott cikkeket, vagy minden korábban beszerzett cikket hozzáadhatnak a kosárhoz.

A következő ábra a felhasználó rendelési előzményeit mutatja be, és a cikkek átrendelésének beállításait.

![Újrarendelés a rendelési előzményekből](../media/Reorder.png)

Ez a cikk néhány olyan módszert ismertet, amelyek segítségével a Commerce B2B webhelyek segítik a felhasználókat a kívánt termékek gyors megkeresésében, megrendelésében és újrarendelésében. A fejlesztésben további lehetőségek állnak készen a tömeges rendelések rögzítésének további egyszerűsítése érdekében.
