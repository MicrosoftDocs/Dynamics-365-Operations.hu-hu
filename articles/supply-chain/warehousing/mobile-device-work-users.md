---
title: Mobileszköz felhasználói fiókjai
description: Ez a témakör azt ismerteti, hogyan lehet beállítani és kezelni azokat a felhasználói fiókokat, amelyek lehetővé teszik a dolgozók számára a raktári alkalmazásba bejelentkezést és az alkalmazás használatát.
author: MarkusFogelberg
ms.date: 09/15/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2021-09-15
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 9ff6752f303adab6c4c52f2f09eea1c0ae2e8e0a
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2021
ms.locfileid: "7647820"
---
# <a name="mobile-device-user-accounts"></a>Mobileszköz felhasználói fiókjai

[!include [banner](../includes/banner.md)]

Minden alkalommal, amikor egy dolgozó elkezdi használni a raktári alkalmazást, egy felhasználónév és egy jelszó használatával kell bejelentkeznie. A raktári alkalmazás bármennyi felhasználója társítható egy dolgozóhoz a rendszerben, és a raktárak általában az egyes raktári alkalmazás-felhasználókhoz vannak társítva. Az egyes dolgozókhoz különböző beállítások is konfigurálva vannak, amelyek meghatározzák a raktári alkalmazás használatának alapértelmezett és egyéb beállításait.

## <a name="set-up-the-required-worker-and-employee-records"></a>A szükséges dolgozó- és alkalmazottrekordok beállítása

A raktári alkalmazás felhasználóinak beállítása előtt minden dolgozónak már léteznie kell Supply Chain Management alkalmazottként vagy dolgozóként az **Emberi erőforrások** modulban.

## <a name="set-up-mobile-device-user-accounts"></a><a name="set-wma-users"></a>Mobileszköz felhasználói fiókjainak beállítása

Miután beállította a szükséges dolgozókat és alkalmazottakat az Emberi erőforrásokban, raktári alkalmazásfelhasználókat rendelhet hozzájuk, és egyéb beállításokat adhat meg, amelyek befolyásolják az alkalmazás használatát.

1. Ugrás a **Raktárkezelés \> Beállítás \> Dolgozó** elemre.
1. Meglévő dolgozó szerkesztéséhez jelölje ki azt a listaablakban. Jelölje be a Műveleti ablaktáblán az **Új** lehetőséget új rekord hozzáadásához.
1. Ha új dolgozót hoz létre, hajtsa végre a következő lépéseket:

    1. A **Dolgozó** mezőben válassza ki a célfelhasználót az alkalmazottak listájából.
    1. Válassza ki a **Kiválasztás** lehetőséget.
    1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

1. Az alapértelmezett profilokkal lehet végigvezetni a csomagolóállomáson dolgozó raktári dolgozót az ott megkövetelt folyamaton. Másik lehetőségként az alapértelmezett profil használható a dolgozó preferált profilbeállításának mentéséhez. A **Profil** gyorslapon állítsa be a következő mezőket:

    - **Tároló csomagolási irányelve** – Olyan tárolóra vonatkozó csomagolási házirend kiválasztása, amely meghatározza a tárolóknak a csomagolóállomáson való feldolgozásának módját. Az itt kiválasztott tároló csomagolási irányelv előre lesz jelölve a dolgozó számára a csomagolóállomás megnyitásakor. A további tudnivalókat lásd a következő blogbejegyzésben: [Továbbfejlesztett csomagolási funkciók](https://cloudblogs.microsoft.com/dynamics365/no-audience/2016/12/01/improved-packing-functionality-dynamics-365-for-operations-1611),
    - **Csomagolási profil azonosítója** – Válasszon egy csomagolási profilazonosítót, amely meghatározza a használt csomagolási házirendet és tárolóbeállításokat. Ha a kiválasztott csomagolási profil azonosítója tároló csomagolási irányelvhez van társítva, akkor ezen a lapon nem módosíthatja a **Tároló csomagolási irányelvének** beállítását.

1. Az **Alapértelmezett csomagolóállomás** gyorslapon állítsa be a következő mezőket, hogy meghatározza azt az alapértelmezett csomagolóállomást, amely akkor érvényes, ha a dolgozó bejelentkezik. Ha szükséges, a dolgozó választhat másik csomagolóállomást.

    - **Telephely** – Válassza ki azt a helyet, ahol az alapértelmezett csomagolóállomás található.
    - **Raktár** – Válassza ki azt a raktárat, ahol az alapértelmezett csomagolóállomás található.
    - **Hely** – az alapértelmezett csomagolóállomás kiválasztása.

1. A **Felhasználók** gyorslap segítségével bármilyen számú raktári alkalmazás felhasználói fiókot létrehozhat a kiválasztott dolgozóhoz. Minden számla adott raktárhoz vagy raktárakhoz van társítva. Az eszköztár segítségével felhasználói fiókokat adhat hozzá és távolíthat el, új jelszót állíthat be a kijelölt fiókhoz, illetve raktárakat rendelhet hozzá a kiválasztott fiókhoz. Minden egyes felhasználói fiókhoz beállíthatja a következő mezőket:

    - **Felhasználó azonosítója** – Adjon meg egy egyedi azonosítót.
    - **Felhasználónév** – Adja meg az azonosító nevét.
    - **Alapértelmezett raktár** – Állítsa be az alapértelmezett raktárat, ahol a dolgozó általában dolgozik. Az eszköztár segítségével további raktárakat rendelhet hozzá, a dolgozó pedig a mobileszköz menüpont **Raktár váltása** közvetett tevékenységének segítségével válthat a raktárak között.
    - **Menü neve** – Válassza ki a gyökérmenüt, amely a dolgozó kezdőlapja lesz. Az egyes dolgozók számára a gyökérmenü beállításának lehetősége hasznos, mivel segítségével szabályozható az egyes dolgozók által használható menüszerkezet. Például az olyan dolgozók menüje, akik csak a kimenő területen aktívak, az adott területre vonatkozó kimenő műveletekkel kapcsolatos feladatokhoz testreszabható.
    - **Inaktív** – A bejelölt jelölőnégyzet azt jelzi, hogy a felhasználói fiók inaktív. A felhasználói fiók automatikusan inaktiválódik, ha egy dolgozó többször is helytelen jelszót ad meg a raktári alkalmazásban. Azonban manuálisan is bejelölheti ezt a jelölőnégyzetet. Törölje a jelölést a jelölőnégyzetből, hogy a felhasználó újra aktív legyen.

1. A **Munka** gyorslapon állítsa be a következő mezőket:

    - **Kitárolási hely felülbírálatának engedélyezése** – A beállítás *Igen* értékével engedélyezheti a dolgozónak, hogy felülbírálja a kitárolási lépések helyét. Ez a képesség akkor lehet hasznos, ha a tényleges készlet nem felel meg a rendszer által ajánlott helynek.
    - **Betárolási hely felülbírálatának engedélyezése** – A beállítás *Igen* értékével engedélyezheti a dolgozónak, hogy felülbírálja a betárolási lépések helyét. Ez a képesség akkor lehet hasznos, ha a javasolt betárolási hely jelenleg megtelt vagy nem áll rendelkezésre, vagy ha az előkészítő helyek módosultak.
    - **Előírtnál nagyobb mennyiség kitárolás értékesítési rendelésekhez** – a beállítás *Igen* beállításával engedélyezheti a dolgozónak, hogy az értékesítési rendelések kitárolásakor nagyobb mennyiséget tároljon ki. További információ: [Értékesítési és áttárolási rendeléseknek az előírtnál nagyobb kitárolt mennyisége](over-picking-for-sales-and-transfer-orders.md).
    - **Előírtnál nagyobb mennyiség kitárolás átmozgatási rendelésekhez** – a beállítás *Igen* beállításával engedélyezheti a dolgozónak, hogy az értékesítési rendelések kitárolásakor nagyobb mennyiséget tároljon ki. További információ: [Értékesítési és áttárolási rendeléseknek az előírtnál nagyobb kitárolt mennyisége](over-picking-for-sales-and-transfer-orders.md).
    - **Készlet mozgatásának engedélyezése társított munkával** – A beállítás *Igen* értékre állításával engedélyezheti a dolgozónak, hogy olyan készletet helyezzen át, amely már le van foglalva, vagy már más munkához van társítva. További információ: [Készlet mozgatásának engedélyezése társított munkával a Raktárkezelésben](move-inventory-associated-work.md).
    - **Cikk újbóli manuális felosztásának engedélyezése** – állítsa ezt a beállítást *Igen* értékre, hogy engedélyezze a dolgozónak a cikkek manuális újrafelosztását rövid kitárolás során. A cikkek újrafelosztása irányítja a dolgozókat, hogy egy másik helyről tároljanak ki készletet. Bár az automatikus újraelosztás minden dolgozó számára elérhető, a manuális újraelosztáshoz explicit beállításokat kell megadni a dolgozóhoz. Hasznos lehet az egyes dolgozók számára manuális újrafelosztás engedélyezése, mivel így szabályozható, hogy az egyes dolgozók számára a láthatóság, amikor például a karanténból vagy ömlesztett tárolóból történő cikk-kitárolás a megbízható dolgozókra korlátozódik. A további tudnivalókat lásd a következő blogbejegyzést: [Automatikus és kézi cikk-újrafelosztás a rövid kitárolás során](https://cloudblogs.microsoft.com/dynamics365/no-audience/2016/11/07/automatic-and-manual-item-reallocation-during-the-short-picking-dynamics-365-for-operations-1611/).
    - **Ciklikusszámlálási felügyelő** – Az *Igen* beállítással a dolgozót ciklikusszámlálási felügyelőként állíthatja be. Ebben az esetben a dolgozó által a raktári alkalmazásban végrehajtása során alkalmazott ciklikusszámlálást azonnal jóváhagyják. A **Maximális százalékos korlát**, a **Maximális mennyiségi korlát** és a **Maximális értékhatár** mező nem számít az olyan dolgozók esetében, akiknél ez a beállítás *Igen* értékre van állítva.
    - **Maximális százalékarány korlátja** – Adja meg, maximum hány százalékkal térhet el egy ciklikus leltár az elvárt mennyiségtől, mielőtt a ciklikusleltár-felügyelő jóváhagyására lenne szükség.
    - **Maximális mennyiségi korlát** – adja meg azt a teljes mennyiséget, amellyel a beírt mennyiség eltérhet a várt mennyiségtől (egységben) anélkül, hogy a ciklusszámlálási felügyelőnek jóvá kell hagynia azt.
    - **Maximális értékhatár** – Adja meg, maximum mekkora készletköltséggel térhet el egy ciklikus leltár az elvárt mennyiségtől, mielőtt a ciklikusleltár-felügyelő jóváhagyására lenne szükség.

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. Ha új felhasználói fiókot adott hozzá, megjelenik a **Jelszó beállítása** párbeszédpanel, amelyen létrehozhatja azt az egyszerű jelszót, amellyel a felhasználó bejelentkezhet a mobilalkalmazásba. Adja meg kétszer az egyszerű jelszót, majd a folytatáshoz kattintson a **Jelszó mentése** gombra a folytatáshoz.

## <a name="set-the-language-number-formats-and-time-zone-for-each-warehouse-app-user"></a>Az egyes raktári alkalmazásfelhasználók nyelvének, számformátumának és időzónájának beállítása

Amikor egy dolgozó bejelentkezik a Warehouse Management mobilalkalmazásba, a nyelv, a számformátum és az időzóna úgy változik, hogy megfeleljen a dolgozó preferenciáinak. A [Mobileszköz felhasználói fiókok beállítása](#set-wma-users) szakasz 3. lépésében kiválasztott dolgozó fiókbeállításai határozzák meg a használt beállításokat. Ha minden felhasználóhoz külön beállításokat kell használnia, használjon különböző dolgozói fiókokat. Az alábbi művelet bemutatja, hogyan lehet módosítani a nyelvet, a számformátumokat és az időzónát minden egyes raktári alkalmazásfelhasználó esetében.

1. Ugrás a **Raktárkezelés \> Beállítás \> Dolgozó** elemre.
1. Keresse meg a beállítani kívánt dolgozó nevét. Győződjön meg róla, hogy a dolgozó rendelkezik a raktári alkalmazás minden olyan szükséges felhasználói fiókjával, amely fel van sorolva a **Felhasználók** gyorslapon. Hozzon létre új dolgozót, és/vagy szükség szerint adjon hozzá raktári alkalmazás felhasználói fiókokat a [Mobileszköz-felhasználói fiókok beállítása](#set-wma-users) szakaszban megadott lépések segítségével.
1. Ugrás a **Rendszerfelügyelet \> Felhasználók \> Felhasználók** elemre.
1. Válassza ki azt a felhasználói fiókot, ahol a **Személy** oszlopban látható a 2. lépésben talált dolgozó neve.

    > [!IMPORTANT]
    > A **Felhasználók lapon** felsorolt **Felhasználói azonosító** értékek *nem* kapcsolódnak az 1. lépésben megnyitott **Dolgozó** lap **Felhasználók** gyorslapján látható értékhez.

1. A műveleti ablaktáblán válassza ki a **Felhasználói beállítások** elemet.
1. A **Beállítások** lapon állítsa be a következő mezőket:

    - **Nyelv** – A dolgozó által előnyben részesített nyelv kiválasztása. Ez a mező a raktári alkalmazásban megjelenő dátumformátumot is szabályozza.
    - **Dátum, idő és szám formátuma** – A raktári alkalmazásban megjelenő számformátumokat meghatározó nyelv kiválasztása. A raktári alkalmazásban megjelenő dátum- és időformátumokat ténylegesen a **Nyelv** mező határozza meg, nem ez a mező.
    - **Időzóna** – Válassza ki azt az időzónát, amelyben a dolgozó dolgozik. Ez a mező hatással van minden olyan regisztrációs időbélyegzőre, amelyet a dolgozó az alkalmazás használatával hoz létre.

> [!NOTE]
> Bizonyos esetekben a raktári alkalmazás nem fog tudni olyan dolgozói beállításokat találni, amelyek meghatározzák a nyelvet, a számformátumokat és az időzónát. Az alábbi szabályokat kell betartani:
>
> - Ha az alkalmazás nem kapcsolódik egy Supply Chain Management környezethez (például az első alkalommal, amikor az alkalmazást a telepítés után elindítják), a helyi eszköz nyelvét használja a rendszer. Ha az eszköz nyelve megváltozik, az alkalmazás nyelve is megváltozik. A helyi eszköz nyelvének konfigurálásáról az eszköz és/vagy operációs rendszer dokumentációja tartalmaz további tájékoztatást.
> - Ha az alkalmazás Supply Chain Management környezethez csatlakozik, de nincs megadva semmilyen beállítás a bejelentkezett dolgozóra, a rendszer annak a fióknak alapján választja ki a nyelvet, a számformátumokat és az időzónát, amely az eszköz által a Supply Chain Management alkalmazáshoz használt ügyfélazonosítóhoz van társítva. További információ: [Felhasználói fiók létrehozása és konfigurálása a Supply Chain Management megoldásban](install-configure-warehouse-management-app.md#user-azure-ad).

> [!TIP]
> Ha azt veszi észre, hogy a raktári alkalmazás használatával készített regisztrációk időbélyegzői helytelenek, lehet, hogy módosítania kell annak a felhasználói fióknak az időzónáját, amelyet a dolgozók a Supply Chain Management alkalmazásba való bejelentkezésre és/vagy hitelesítésre használhatnak. Ahogy korábban említettük, az időzóna-beállítás lehet, hogy abból a felhasználói fiókból jön létre, amely a raktári alkalmazásba való bejelentkezésre használatos, a **Dolgozó** lapon megadott beállításoknak megfelelően. Másik lehetőségként, ha a felhasználói fiók nincs beállítva a **Dolgozó** lapon, akkor az időzóna abból a felhasználói fiókból származik, amely a hitelesítéshez használt ügyfélazonosítóhoz van társítva, az **[Azure Active Directory alkalmazások](install-configure-warehouse-management-app.md)** oldalon megadott beállításoknak megfelelően.
