---
title: Kosármodul
description: Ez a témakör a kosármodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f6dd8fb56f7342eb9c877eda503a92f4a31e5863
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025436"
---
# <a name="cart-module"></a>Kosármodul


[!include [banner](includes/banner.md)]

Ez a témakör a kosármodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A kosármodullal megjeleníthetők a kosárba tett cikkek, mielőtt az ügyfél a pénztárra lép. Tartalmazza például az összes kosárhoz adott elemet és a rendelés összesítését. Lehetővé teszi, hogy az ügyfél promóciós kódokat alkalmazzon vagy távolítson el.

A kosár modul támogatja a bejelentkezett fizetést és a vendégfizetést. Támogatja a **Vissza a vásárláshoz** hivatkozást. A hivatkozáshoz vezető útvonalat a **Webhely-beállítások \> Bővítmények \> Útvonala** oldalon.

A kosármodul a kosár azonosítója alapján jeleníti meg az adatokat. A kosár azonosítója a webhely egészén elérhető böngésző-cookie.

## <a name="cart-module-properties-and-slots"></a>A kosármodul tulajdonságai és helyei

A kosár modulnak van egy **Címsor** tulajdonsága, amelyet olyan értékekre állíthat, mint **Bevásárlótáska** vagy **Kosárban levő cikkek**. 

## <a name="modules-that-can-be-used-in-a-cart-module"></a>A kosármodulban használható modulok

- **Szövegblokk** – Ez a modul a kosár modulban használható egyéni üzenetküldést támogatja. Az üzeneteket a tartalomkezelő rendszer (CMS) vezérli. Bármilyen üzenet megadható, például: „A rendeléssel kapcsolatos problémák esetén hívja az 1-800-Fabrikam számot”.
- **Áruházválasztó** – Ez a modul felsorolja azokat a közeli áruházakat, ahol a cikkek elérhetők és felvehetők. Ez lehetővé teszi a felhasználók számára, hogy a közelben levő üzleteket megtalálják. Az áruházválasztó modul integrálva van a Bing Maps földrajzi kódolási alkalmazásprogramozási felületével (API), hogy a vevő által megadott helyszínt egy földrajzi szélességgé és hosszúsággá alakíthassa. A Bing Maps API-kulcsot kötelező megadni, és hozzá kell adni a Retail megosztott paraméterei oldalhoz a Dynamics 365 Retail szolgáltatásban. Ez a modul két tulajdonságot támogat, **Keresési sugár** és **Szolgáltatási feltételek hivatkozását**. A **Keresési sugár** tulajdonság az üzletek keresési sugarát határozza meg (mérföldben). Ha nincs megadva érték, akkor a program az alapértelmezett keresési sugarat (50 mérföld) használja. Ha Bing-térképeket vagy külső szolgáltatásokat használnak, a **szolgáltatási feltételek hivatkozása** tulajdonsággal lehet hivatkozást biztosítani a szolgáltatási feltételekhez. A Bing Maps szolgáltatáshoz a szolgáltatási feltételek hivatkozása szükséges. 

## <a name="cart-module-settings"></a>Kosármodul beállításai

A kosár-modulok beállításai a **Webhelybeállítások \> Bővítmények** pontban konfigurálhatók:

- **Maximális mennyiség** – Ez a tulajdonság megadja az egyes cikkek kosárhoz adható maximális számát. Előfordulhat például, hogy egy kiskereskedő úgy dönt, hogy egyetlen tranzakcióban csak 10 terméket lehet értékesíteni.
- **Készletellenőrzés** – Ha **Igaz** értékre van beállítva, akkor a program a kosárba csak azután veszi fel a cikket, hogy a vásárlásmező modul meggyőződött róla, hogy az adott termék készleten van. Ez a készletellenőrzés végrehajtásra kerül mind azokban az esetekben, amikor a cikk kiszállításra kerül, mind azokban az esetekben, amikor a vevő az áruházban veszi fel. Ha **Hamis** értékre van állítva, akkor a program nem végez készletellenőrzést, mielőtt a cikkeket felveszi a kosárba, és a rendelés leadásra kerül.
- **Készletpuffer** – ez a tulajdonság a készlethez tartozó pufferméret meghatározására szolgál. A készlet leltározása valós időben történik, és sok vevői rendelés esetén nehéz a készlet pontos leltározása. A készletellenőrzés során, ha a készlet kisebb, mint a puffermennyiség, akkor a rendszer a terméket kifogyottként kezeli. Ezért ha az értékesítések gyorsabban történnek több csatornán keresztül, és a leltározás nem teljes mértékben szinkronizált, akkor kisebb a kockázata annak, hogy a kifogyott cikkek eladásra kerülnek.
- **Vissza a vásárláshoz** – a tulajdonság a **Vissza a vásárláshoz** linkhez megadott útvonal meghatározására szolgál. Ez az útvonal a webhely szintjén konfigurálható. Ennek a konfigurációnak köszönhetően a kiskereskedők visszavihetik a vevőt a webhely kezdőlapjára vagy más lapjára.

## <a name="commerce-scale-unit-interaction"></a>Commerce Scale Unit-interakció

A kosármodul a termék adatait a Commerce Scale Unit API-k használatával olvassa be. A böngésző cookie-jából származó kosárazonosító szolgál az összes termékadat beolvasására a Commerce Scale Unitról.

## <a name="add-a-cart-module-to-a-page"></a>Kosármodul felvétele egy oldalra

A kosármodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Hozzon létre egy **Kosártöredék** nevű töredéket, majd adjon hozzá egy kosármodult.
1. Adjon hozzá egy fejlécet a kosármodulhoz.
1. Adjon hozzá egy üzletválasztó modult a kosár modulhoz.
1. Mentse a töredéket, fejezze be a szerkesztését, majd tegye közzé.
1. Hozzon létre egy **Kosársablon** nevű sablont, és adja hozzá a most létrehozott kosártöredéket.
1. Mentse a sablont, fejezze be a szerkesztését, majd tegye közzé.
1. Hozzon létre egy olyan oldalt, amely az új sablont használja.
1. Mentse a lapot, és tekintse meg az előnézetét.
1. Fejezze be a lap szerkesztését, és tegye közzé.

## <a name="additional-resources"></a>További erőforrások

[Kezdő csomag áttekintése](starter-kit-overview.md)

[Tárolómodul](add-container-module.md)

[Vásárlásmező modul](add-buy-box.md)

[Fizetésmodul](add-checkout-module.md)

[Rendelésmegerősítés modul](order-confirmation-module.md)

[Fejlécmodul](author-header-module.md)

[Láblécmodul](author-footer-module.md)
