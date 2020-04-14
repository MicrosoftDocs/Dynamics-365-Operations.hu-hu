---
title: Kosármodul
description: Ez a témakör a kosármodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 03/19/2020
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
ms.openlocfilehash: 598b35b1bd365e761d8d4c5ef214935e60b971f4
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154017"
---
# <a name="cart-module"></a>Kosármodul

[!include [banner](includes/banner.md)]

Ez a témakör a kosármodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A kosármodullal megjeleníthetők a kosárba tett cikkek, mielőtt az ügyfél a pénztárra lép. A modul a rendelés összegzését is megjeleníti, és lehetővé teszi, hogy a vevő hozzáadja vagy eltávolítsa a promóciós kódokat.

A kosár modul támogatja a bejelentkezett fizetést és a vendégfizetést. Támogatja a **Vissza a vásárláshoz** hivatkozást. A hivatkozáshoz vezető útvonalat a **Webhely-beállítások \> Bővítmények \> Útvonala** oldalon.

A kosár modul a kosár azonosítója alapján jeleníti meg az adatokat, ami a webhely teljes területén elérhető böngésző cookie.

## <a name="cart-module-properties-and-slots"></a>A kosármodul tulajdonságai és helyei

A kosár modulnak van egy **Címsor** tulajdonsága, amelyet olyan értékekre állíthat, mint **Bevásárlótáska** vagy **Kosárban levő cikkek**. 

## <a name="modules-that-can-be-used-in-a-cart-module"></a>A kosármodulban használható modulok

- **Szövegblokk** – Ez a modul a kosár modulban használható egyéni üzenetküldést támogatja. Az üzeneteket a tartalomkezelő rendszer (CMS) vezérli. Bármilyen üzenet megadható, például: „A rendeléssel kapcsolatos problémák esetén hívja az 1-800-Fabrikam számot”.
- **Áruházválasztó** – Ez a modul felsorolja azokat a közeli áruházakat, ahol a cikkek elérhetők és felvehetők. Ez lehetővé teszi a felhasználók számára, hogy a közelben levő üzleteket megtalálják. A modullal kapcsolatos további tudnivalókat lásd: [Üzletkiválasztó modul](store-selector.md).

## <a name="cart-module-settings"></a>Kosármodul beállításai

A kosár-modulok beállításai a **Webhelybeállítások \> Bővítmények** pontban konfigurálhatók:

- **Maximális mennyiség** – Ez a tulajdonság megadja az egyes cikkek kosárhoz adható maximális számát. Előfordulhat például, hogy egy kiskereskedő úgy dönt, hogy egyetlen tranzakcióban csak 10 terméket lehet értékesíteni.
- **Készletellenőrzés** – Ha **Igaz** értékre van beállítva, akkor a program a kosárba csak azután veszi fel a cikket, hogy a vásárlásmező modul meggyőződött róla, hogy az adott termék készleten van. Ez a készletellenőrzés végrehajtásra kerül azokban az esetekben, amikor a cikk kiszállításra kerül, mind azokban az esetekben, amikor a vevő az áruházban veszi fel. Ha **Hamis** értékre van állítva, akkor a program nem végez készletellenőrzést, mielőtt a cikkeket felveszi a kosárba, és a rendelés leadásra kerül.
- **Készletpuffer** – ez a tulajdonság a készlethez tartozó pufferméret meghatározására szolgál. A készlet leltározása valós időben történik, és sok vevői rendelés esetén nehéz a készlet pontos leltározása. A készletellenőrzés során, ha a készlet kisebb, mint a puffermennyiség, akkor a rendszer a terméket kifogyottként kezeli. Ezért ha az értékesítések gyorsabban történnek több csatornán keresztül, és a leltározás nem teljes mértékben szinkronizált, akkor kisebb a kockázata annak, hogy a kifogyott cikkek eladásra kerülnek.
- **Vissza a vásárláshoz** – a tulajdonság a **Vissza a vásárláshoz** linkhez megadott útvonal meghatározására szolgál. Az útvonal a webhely szintjén konfigurálható, amely lehetővé teszi, hogy a kiskereskedők visszavigyék a vevőt a kezdőlapra vagy más lapjára.

## <a name="commerce-scale-unit-interaction"></a>Commerce Scale Unit-interakció

A kosármodul a termék adatait a Commerce Scale Unit API-k használatával olvassa be. A böngésző cookie-jából származó kosárazonosító szolgál az összes termékadat beolvasására a Commerce Scale Unitról.

## <a name="add-a-cart-module-to-a-page"></a>Kosármodul felvétele egy oldalra

A kosármodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Hozzon létre egy **Kosártöredék** nevű töredéket, majd adjon hozzá egy új töredéket.
1. Adjon hozzá egy fejlécet a kosármodulhoz.
1. Adjon hozzá egy üzletválasztó modult a kosár modulhoz.
1. Mentse a töredéket, fejezze be a szerkesztését, majd tegye közzé a töredéket.
1. Hozzon létre egy **Kosársablon** nevű sablont, és adja hozzá a most létrehozott kosártöredéket.
1. Mentse a sablont, fejezze be a szerkesztését, majd tegye közzé a sablont.
1. Hozzon létre egy olyan oldalt, amely az új sablont használja.
1. Mentse a lapot, és tekintse meg az előnézetét.
1. Fejezze be az oldal szerkesztését, majd tegye közzé.

## <a name="additional-resources"></a>További erőforrások

[Kezdő csomag áttekintése](starter-kit-overview.md)

[Tárolómodul](add-container-module.md)

[Üzletkiválasztó modul](store-selector.md)

[Vásárlásmező-modul](add-buy-box.md)

[Fizetésmodul](add-checkout-module.md)

[Rendelésmegerősítési modul](order-confirmation-module.md)

[Fejlécmodul](author-header-module.md)

[Láblécmodul](author-footer-module.md)
