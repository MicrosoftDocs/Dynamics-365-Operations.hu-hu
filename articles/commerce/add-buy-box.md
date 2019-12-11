---
title: Vásárlásmező modul
description: Ez a témakör a vásárlásmező moduljaival foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e86b1881e6829ccc33f36ada453af20c1815a2fa
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811141"
---
# <a name="buy-box-module"></a>Vásárlásmező modul

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör a vásárlásmező moduljaival foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A *vásárlásmező* kifejezés általában a termék részletes lapjának azon területére utal, amely „görgetés nélkül látható”, és a termék megvásárlásához szükséges legfontosabb adat mindegyikét tartalmazza. (A „görgetés nélkül látható” terület a lap első betöltésekor jelenik meg, így a felhasználóknak nem kell legörgetni, hogy lássák azt.)

A vásárlásmező egy speciális tároló, amely a termék részletes lapjának vásárlásmező részén látható összes modult tárolja.

A termék részletes lapjának URL-címe tartalmazza a termékazonosítót. A vásárlásmező modul megjelenítéséhez szükséges összes adat ebből a termékazonosítóból származik. Ha nincs megadva termékazonosító, akkor a program nem jeleníti meg megfelelően a vásárlásmező modult a lapon. Ezért a vásárlásmező modul nem használható olyan lapon, amely nem rendelkezik termékkontextussal (például egy kezdőlap vagy egy marketinglap).

## <a name="buy-box-module-properties-and-slots"></a>A vásárlásmező modul tulajdonságai és helyei 

Tárolóként a vásárlásmező modul néhány alapvető tulajdonságot, például a szélességet vezérli. A szélesség beállítás határozza meg, hogy a tárolóban lévő moduloknak igazodniuk kell a tároló szélességéhez, vagy kitölthetik a képernyőt.

A termék részletes lapján a vásárlásmező két részre van osztva: a bal oldalon levő médiaterületre és a jobb oldali tartalomterületre. Ezt a két területet a vásárlásmező modulban helyek jelölik. Minden hely úgy van beállítva, hogy csak a hely által támogatott speciális modulokat fogadja el. A **Média** hely például csak a médiatár modult támogatja.

Alapértelmezés szerint a médiaterület és a tartalomterület oszlopszélességeinek aránya 2:1. Az oszlopok szélességét azonban felülbírálhatja a téma. Ezenkívül a mobileszközök esetében a két terület egymásra van halmozva, így az egyik terület a másik terület alatt jelenik meg.

## <a name="modules-that-can-be-used-in-a-buy-box-module"></a>A vásárlásmező modulban használható modulok

- **Médiatár** – Ez a modul a termék képeinek bemutatására szolgál a termék részletes lapján. Egy vagy több képet is támogathat. Támogatja a miniatűr képeket is. A miniatűr képek vízszintes (a kép alatti sorként) vagy függőleges (a kép melletti oszlopként) elrendezésben is megadhatók. A médiatár modul a vásárlásmező modul **Média** helyén adható hozzá. Jelenleg csak képeket és videókat támogat.
- **Termék címe** – Ez a modul a termék címét jeleníti meg a termék részletes lapján. Alapértelmezés szerint a **H1** fejléccímke van használatban, de a fejléccímke a szükséges módon módosítható.
- **Termékértékelés** – Ez a modul az adott termék felhasználói értékelései alapján a csillagértékeléseket jeleníti meg. A vásárlásmező modul minden termék esetében beolvassa az értékelési szolgáltatásból származó termékértékeléseket.
- **Termék ára** – Ez a modul a termék árát jeleníti meg. Az ár tartalmazza az áthúzott árakat és engedményeket.
- **Termékleírás** – Ez a modul a termék leírását jeleníti meg.
- **Termék konfigurálása** – Ez a modul a termék nagyságát, stílusát és méreteit jeleníti meg. A méretválasztók egymás felett függőlegesen vagy egymás mellett is megjeleníthetők. Egy termékváltozat kiválasztásakor a program frissíti a vásárlásmezőbe tartozó egyéb tulajdonságokat (például a termék leírását és a képeket) a változat adatainak megjelenítéséhez.
- **Termék mennyisége** – Ez a modul a termék mennyiségének konfigurálására szolgál. Egy beállítással korlátozható egy termék vagy változat mennyisége, amelyet fel lehet venni a kosárba.
- **Hozzáadás a kosárhoz** – Ez a modul a „hozzáadás a kosárhoz” művelet végrehajtásához használatos. Csak termék vagy változat adható hozzá a kosárhoz. Más szóval egy alaptermék nem adható hozzá a kosárhoz. A modul rendelkezik egy **Ugrás a kosárhoz** tulajdonsággal, amelyet a webhely szerzője beállíthat. Ha ez a tulajdonság **Igaz** értékre van állítva, akkor a felhasználó a kosár oldalra kerül, valahányszor egy „hozzáadás a kosárhoz” művelet aktiválódik. Ha **Hamis** értékre van állítva, akkor a vásárló továbbra is böngészhet a termék részletes lapját, miután a cikkeket hozzáadta a kosárhoz.
- **Hozzáadás a kívánságlistához** – Ez a modul egy elem vásárlói kívánságlistára való felvételéhez használható. Csak termék vagy változat adható hozzá a kívánságlistához. Ezenkívül a vásárlónak be kell jelentkeznie a webhelyre. A modulban található hibakezelő logika gondoskodik arról, hogy mindkét feltétel teljesüljön.
- **Keresés az áruházban** – Ez a modul elindítja az „online vásárlás, átvétel az áruházban” folyamatot.
- **Felvétel az áruházban** – Ez a modul felsorolja azokat a közeli áruházakat, ahol a cikkek elérhetők és felvehetők. Alapértelmezés szerint ez a modul azokat az áruházakat jeleníti meg, amelyek a vevő tartózkodási helyének 50 km sugarú körében találhatók. A keresési sugár azonban testreszabható a modulban. Minden áruház esetében készletellenőrzés történik, ha a készlet-ellenőrzési funkció be van kapcsolva, és a megfelelő készleten vagy elfogyott üzenet jelenik meg.
- **Áruházkeresés a Bing Maps használatával** – Ez a modul a felvétel az áruházban modulon belül használható. Lehetővé teszi, hogy a vevők egy hely megadásával keressenek üzleteket. A Bing Maps földrajzi kódolási alkalmazásprogramozási felülete (API) használatával alakítható át a megadott helyszín egy földrajzi szélességgé és hosszúsággá. Ha ez a modul van használatban, akkor csak a vevő aktuális tartózkodási helyéhez közeli áruházak jelennek meg, és a vevő nem kereshet másik helyet.
- **Tartalomgazdag blokk** – Ez a modul egy üzenetet jelenít meg, amelyet a webhely szerzője vagy a kiskereskedő népszerűsíteni kíván a vásárlásmezőben, például: „A rendeléssel kapcsolatos problémák esetén hívja az 1-800-FABRIKAM számot” vagy az „Ingyenes szállítás 100 USD-t meghaladó összegű rendelés esetén”. Az üzeneteket a tartalomkezelő rendszer (CMS) vezérli.

## <a name="buy-box-module-settings"></a>Vásárlásmező modul beállításai

A vásárlásmező moduljai három megadható beállítással rendelkeznek:

- **Maximális mennyiség** – Az egyes cikkek kosárhoz adható maximális száma. Előfordulhat például, hogy egy kiskereskedő úgy dönt, hogy egyetlen tranzakcióban csak 10 terméket lehet értékesíteni.
- **Készletellenőrzés** – Ha **Igaz** értékre van beállítva, akkor a program a kosárba csak azután veszi fel a cikket, hogy a vásárlásmező modul meggyőződött róla, hogy az adott termék készleten van. Ez a készletellenőrzés végrehajtásra kerül mind azokban az esetekben, amikor a cikk kiszállításra kerül, mind azokban az esetekben, amikor a vevő az áruházban veszi fel. Ha **Hamis** értékre van állítva, akkor a program nem végez készletellenőrzést, mielőtt a cikkeket felveszi a kosárba, és a rendelés leadásra kerül.
- **Készletpuffer** – A készlet leltározása valós időben történik, és sok vevői rendelés esetén nehéz a készlet pontos leltározása. Ezért megadható egy puffer a készlethez. A készletellenőrzés során, ha a készlet kisebb, mint a puffermennyiség, akkor a rendszer a terméket kifogyottként kezeli. Ezért ha az értékesítések gyorsabban történnek több csatornán keresztül, és ezáltal a leltározás nem teljes mértékben szinkronizált, akkor kisebb a kockázata annak, hogy a kifogyott cikkek eladásra kerülnek.

## <a name="retail-server-interaction"></a>Kiskereskedelmi kiszolgálói interakció

A vásárlásmező modul a termék adatait a Retail Server API-k használatával olvassa be. Az termék részletes lapjáról származó termékazonosító az összes információ lekérdezésére szolgál.

## <a name="add-a-buy-box-module-to-a-page"></a>Vásárlásmező modul felvétele egy oldalra

A vásárlásmező modul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Hozzon létre egy **vásárlásmező töredék** nevű töredéket, majd adjon hozzá egy vásárlásmező modult.
1. A vásárlásmező **Média** helyén adjon hozzá egy médiatár modult.
1. A vásárlásmező modul **Tartalom** helyén adja hozzá a következő modulokat: termék címe, termékértékelés, termék ára, termékleírás, termék konfigurálása, hozzáadás a kosárhoz, felvétel a kívánságlistára és keresés az áruházban. A kívánt elrendezés elérése érdekében a **Tartalom** helyen belül átrendezheti a modulokat.
1. Válassza ki a keresés az áruházban modult. A modulon belüli helyen adjon hozzá egy felvételt az áruházban modult.
1. A felvétel az áruházban modulban található helyen adjon hozzá egy áruházkeresést a Bing Maps modullal.
1. Adja be a lapot, és tegye közzé.
1. Hozzon létre egy sablont a termék részletes lapjához, majd nevezze el **PDP-sablon** néven.
1. Adjon hozzá egy alapértelmezett lapot.
1. Az alapértelmezett lap **Fő** helyén adjon hozzá egy vásárlásmező töredékét.
1. Mentse a sablont, adja be és tegye közzé.
1. A most létrehozott sablon használatával hozzon létre egy **PDP-lap** nevű lapot.
1. Az új lap **Fő** helyén adjon hozzá egy vásárlásmező töredékét.
1. Mentse a lapot, és tekintse meg az előnézetét. Hozzáadja a **?productid=&lt;product id&gt;** lekérdezési karakterlánc paramétert az előnézeti lap URL-címéhez. A termékkontextus így az előnézeti lap betöltésére és megjelenítésére kerül felhasználásra.
1. Adja be a lapot, és tegye közzé. A termék részletes lapján meg kell jelennie vásárlásmezőnek.

## <a name="additional-resources"></a>További erőforrások

[Kezdő csomag áttekintése](starter-kit-overview.md)

[Tárolómodul](add-container-module.md)

[Kosármodul](add-cart-module.md)

[Fizetésmodul](add-checkout-module.md)

[Rendelésmegerősítés modul](order-confirmation-module.md)

[Fejlécmodul](author-header-module.md)

[Láblécmodul](author-footer-module.md)
