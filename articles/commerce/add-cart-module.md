---
title: Kosármodul
description: Ez a témakör a kosármodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: 1c910f08e5999ec586b5cb656d5769e9d4abd069
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2019
ms.locfileid: "2696761"
---
# <a name="cart-module"></a>Kosármodul

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör a kosármodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A kosármodul olyan tároló, amely az összes olyan modult tárolja, amely szükséges a kosárban található elemek megjelenítéséhez. Tartalmazza például az összes kosárhoz adott elemet, a rendelés összesítését és a promóciós kódokat.

A kosármodul a kosár azonosítója alapján jeleníti meg az adatokat. A kosár azonosítója a webhely egészén elérhető böngésző-cookie.

## <a name="cart-module-properties-and-slots"></a>A kosármodul tulajdonságai és helyei

Tárolóként a kosármodul néhány alapvető tulajdonságot vezérel, például a fejlécet és a szélességet. A fejléc általában olyan szöveg, mint a **Bevásárlókocsi**, **Az Ön kosara** vagy a **Kosárban található termékek**. A szélesség beállítás határozza meg, hogy a tárolóban lévő moduloknak igazodniuk kell a tároló szélességéhez, vagy kitölthetik a képernyőt.

A kosár lap több területre van felosztva: kosár sortételei, rendelés összesítése és fizetés, valamint a „keresés az áruházban” funkció. Minden terület a kosármodul egy helyére van leképezve, és minden hely egy előre meghatározott modulkészletet fogad el.

## <a name="modules-that-can-be-used-in-a-cart-module"></a>A kosármodulban használható modulok

- **Kosár sortételei** – Ez a modul a kosárba felvett összes cikk összesítését jeleníti meg. Az adatok tartalmazzák a termék címét, a kiválasztott méreteket, az árat, a mennyiséget és az engedményeket. Ez a modul olyan műveleteket is támogat, mint az „eltávolítás a kosárból” és a „felvétel a kívánságlistára”. Minden sortétel esetében lehetőség van a cikkek szállítására vagy az üzletben történő felvételére. Ezt a beállítást külön kell konfigurálni a felvétel az áruházban modulban.
- **Rendelésösszesítés** – Ez a modul egy rendelés összesítését jeleníti meg. Az adatok között szerepelnek a részösszegek, a szállítás, az adók és a megtakarítások. Ehhez a modulhoz be lehet állítani egy fejlécet.
- **Promóciós** – Ez a modul lehetővé teszi, hogy a vevő promóciós kódokat váltson be. Lehetőség van egy promóciós kód beváltására vagy eltávolítására.
- **Fizetés** – Ez a modul kezdeményezi a fizetési műveletet, és átirányítja a felhasználót a fizetési lapra. Ehhez a modulhoz három hivatkozást kell konfigurálni:

    - **Fizetés** – Ez a hivatkozás arra kényszeríti a vevőket, hogy bejelentkezzenek, ha még nincsenek bejelentkezve.
    - **Fizetés vendégként** – Ez a hivatkozás lehetővé teszi az anonim vevők számára rendelések leadását. Csak akkor jelenik meg, ha a vevők nincsenek bejelentkezve.
    - **Vissza a vásárláshoz** – Ez a hivatkozás lehetővé teszi, hogy a vevők a kezdőlapra vagy bármely más oldalra lépjenek, és tovább folytathassák a vásárlást.

- **Tartalomgazdag blokk** – Ez a modul a kosár modulban használható egyéni üzenetküldést támogatja. Az üzeneteket a tartalomkezelő rendszer (CMS) vezérli. Bármilyen üzenet megadható, például: „A rendeléssel kapcsolatos problémák esetén hívja az 1-800-Fabrikam számot”.
- **Felvétel az áruházban** – Ez a modul felsorolja azokat a közeli áruházakat, ahol a cikkek elérhetők és felvehetők. Alapértelmezés szerint ez a modul azokat az áruházakat jeleníti meg, amelyek a vevő tartózkodási helyének 50 km sugarú körében találhatók. A keresési sugár azonban testreszabható a modulban. Minden áruház esetében készletellenőrzés történik, ha a készlet-ellenőrzési funkció be van kapcsolva, és a megfelelő készleten vagy elfogyott üzenet jelenik meg.
- **Áruházkeresés a Bing Maps használatával** – Ez a modul a felvétel az áruházban modulon belül használható. Lehetővé teszi, hogy a vevők egy hely megadásával keressenek üzleteket. A Bing Maps földrajzi kódolási alkalmazásprogramozási felülete (API) használatával alakítható át a vevő által megadott helyszín egy földrajzi szélességgé és hosszúsággá. Ha ez a modul nincs használatban, akkor csak a vevő aktuális tartózkodási helyéhez közeli áruházak jelennek meg, és a vevő nem kereshet másik helyet.

## <a name="cart-module-settings"></a>Kosármodul beállításai

A kosármodulok három megadható beállítással rendelkeznek:

- **Maximális mennyiség** – Az egyes cikkek kosárhoz adható maximális száma. Előfordulhat például, hogy egy kiskereskedő úgy dönt, hogy egyetlen tranzakcióban csak 10 terméket lehet értékesíteni.
- **Készletellenőrzés** – Ha **Igaz** értékre van beállítva, akkor a program a kosárba csak azután veszi fel a cikket, hogy a vásárlásmező modul meggyőződött róla, hogy az adott termék készleten van. Ez a készletellenőrzés végrehajtásra kerül mind azokban az esetekben, amikor a cikk kiszállításra kerül, mind azokban az esetekben, amikor a vevő az áruházban veszi fel. Ha **Hamis** értékre van állítva, akkor a program nem végez készletellenőrzést, mielőtt a cikkeket felveszi a kosárba, és a rendelés leadásra kerül.
- **Készletpuffer** – A készlet leltározása valós időben történik, és sok vevői rendelés esetén nehéz a készlet pontos leltározása. Ezért megadható egy puffer a készlethez. A készletellenőrzés során, ha a készlet kisebb, mint a puffermennyiség, akkor a rendszer a terméket kifogyottként kezeli. Ezért ha az értékesítések gyorsabban történnek több csatornán keresztül, és ezáltal a leltározás nem teljes mértékben szinkronizált, akkor kisebb a kockázata annak, hogy a kifogyott cikkek eladásra kerülnek.

## <a name="retail-server-interaction"></a>Kiskereskedelmi kiszolgálói interakció

A kosármodul a termék adatait a Retail Server API-k használatával olvassa be. A böngésző cookie-jából származó kosárazonosító szolgál az összes termékadat beolvasására a Retail Serverről.

## <a name="add-a-cart-module-to-a-page"></a>Kosármodul felvétele egy oldalra

A kosármodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Hozzon létre egy **kosártöredék** nevű töredéket, majd adjon hozzá egy kosármodult.
1. A kosármodul **Kosár sortételei** helyén adjon hozzá egy kosár sortételei modult.
1. A **Rendelésösszesítés** helyen adjon hozzá egy rendelésösszesítés modult.
1. A **Promóciós kód** helyen adjon hozzá egy promóciós kód modult.
1. A **Fizetés** helyen adjon hozzá egy fizetési modult.
1. A **Keresés az áruházban** helyen adjon hozzá egy felvételt az áruházban modult.
1. A felvétel az áruházban modulban válassza ki az **Áruház keresése** helyet, és adjon hozzá egy áruházkeresés a Bing Maps használatával modult.
1. Adja be a töredéket, és tegye közzé.
1. Hozzon létre egy **kosársablon** nevű sablont, és adja hozzá a most létrehozott kosártöredéket.
1. Mentse a sablont, adja be és tegye közzé.
1. Hozzon létre egy olyan oldalt, amely az új sablont használja.
1. Mentse a lapot, és tekintse meg az előnézetét.
1. Adja be a lapot, és tegye közzé.

## <a name="additional-resources"></a>További erőforrások

[Kezdő csomag áttekintése](starter-kit-overview.md)

[Tárolómodul](add-container-module.md)

[Vásárlásmező modul](add-buy-box.md)

[Fizetésmodul](add-checkout-module.md)

[Rendelésmegerősítés modul](order-confirmation-module.md)

[Fejlécmodul](author-header-module.md)

[Láblécmodul](author-footer-module.md)
