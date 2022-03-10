---
title: Eszköz, piac és földrajzi hely megcélzása
description: Ez a témakör leírja, hogyan hozhat létre, szerkeszthet és kezelhet célközönségeket és célpontokat a Microsoft Dynamics 365 Commerce webhelykészítőben az eszközre, piacra és földrajzi helyre vonatkozó információk felhasználásával.
author: sushma-rao
ms.date: 02/03/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2021-07-31
ms.dyn365.ops.version: AX 10.0.21
ms.openlocfilehash: 0c8ceb5e59c801e0d3dbc3a57e54c40fa8d967ac
ms.sourcegitcommit: 1eef00796f7c5511f432b01800cdf8920992d7d5
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2022
ms.locfileid: "8090694"
---
# <a name="device-market-and-geolocation-targeting"></a>Eszköz, piac és földrajzi hely megcélzása

[!include [banner](includes/banner.md)]

Ez a témakör leírja, hogyan hozhat létre, szerkeszthet és kezelhet célközönségeket és célpontokat a Microsoft Dynamics 365 Commerce webhelykészítőben az eszközre, piacra és földrajzi helyre vonatkozó információk felhasználásával.

A Dynamics 365 Commerce lehetővé teszi, hogy a lap tartalmának variációit (ún. *célokat*) személyre szabja a vevők meghatározott csoportjai (ún. *célközönségek*) számára, hogy segítsen növelni a felhasználók elkötelezettségét és elégedettségét. Először vagy célközönséget, vagy célpontot hozhat létre. A sikeres megcélzáshoz azonban mindkét összetevőre szükség van.

A Commerce webhelykészítőben létrehozhat és kezelhet célközönségeket a vevői adatok, például a hely, az eszközinformációk, a bejelentkezési állapot és a vevő webes kéréseiből dinamikusan származtatott egyéb információk alapján. Az e-kereskedelmi modulok és töredékek célpontjait is létrehozhatja és kezelheti a Commerce webhelykészítőben.

**Jogi nyilatkozat:** Ön felelős azért, hogy ezt a funkciót az összes vonatkozó törvénynek és szabályozásnak megfelelően használja, beleértve a megcélzással és profilalkotással kapcsolatosakat is. 

## <a name="audiences"></a>Közönségek

A célközönség a felhasználók egy csoportja, és a csoporthoz való tartozást dinamikus szabályok határozzák meg. Ezek a szabályok egyszerű logikai tesztek, amelyeket a vevői kérelmekben vagy más elérhető szegmensekben rendelkezésre álló információkkal futtatnak. Több szabály kombinálható az ÉS/VAGY operátorok használatával.

A Commerce natívan támogatja az olyan alapvető szegmenseket, mint az eszközinformációk, a bejelentkezési állapot, a hivatkozó és a lekérdezési karakterlánc paraméterei. Támogatja továbbá a harmadik fél szolgáltatókkal való kapcsolat révén bővíthető szegmenseket is.

### <a name="basic-segments"></a>Alapvető szegmensek

Alapértelmezés szerint a következő szegmensek állnak rendelkezésre és szerepelhetnek a célközönség-definíciókban:

- **Bejelentkezett állapot** – Annak tesztelése, hogy a felhasználó hitelesített-e.
- **Eszköz platformja** – A következő eszköztípusok tesztelése:

    - Mobil
    - Asztali számítógép
    - Tablet
    - Egyéb

- **Eszköz operációs rendszere** – A következő operációs rendszerek tesztelése:

    - Windows
    - Linux
    - iOS
    - Android, Egyéb

- **Lekérdezési karakterlánc paraméterei** – A kulcs-érték pár meglétének tesztelése egy kérés URL-címének lekérdezési karakterlánc-paraméterében. Például a `www.fabrikam.com/en-us/request?promo=true` URL-címre írható egy szabály, amely azt vizsgálja, hogy a **promóció** paraméter értéke **igaz**-e.
- **Cookie** – A kérés URL-címében a tartományhoz beállított cookie-érték tesztelése. Például egy Fabrikam.com kérés tartalmazhat egy olyan cookie-t, amelynek a neve **CustomLayout** és az értéke **1**. A cookie-teszt ellenőrzi a cookie létezését, de nem hoz létre kifejezetten cookie-t. Az előző példában a JavaScriptnek korábban be kellett állítania a **CustomLayout** cookie-t egy másik modulból vagy más üzleti folyamatból.

    > [!NOTE]
    > Győződjön meg arról, hogy a cookie-k használata megfelel az alkalmazandó jogszabályoknak.

- **Hivatkozó** – Ha egy felhasználó egy linket követve kéri a lapot, a hivatkozó annak a lapnak az URL-címe, amelyen a link el van helyezve.

### <a name="extensible-segments"></a>Bővíthető szegmensek

A Commerce lehetővé teszi az elérhető szegmensek listájának bővítését harmadik fél szegmensszolgáltatókhoz való csatlakozással. A szegmensszolgáltató leírja a rendelkezésre álló szegmensek típusait. A földrajzi hely vagy szegmentálás szolgáltatójához való csatlakozásról további információkat a [Csatlakoztatók konfigurálása és engedélyezése](e-commerce-extensibility/connectors.md) című témakörben talál.

> [!NOTE]
> - Ha egy külső szolgáltató engedélyezve van, előfordulhat, hogy olyan szolgáltatáshoz csatlakozik, amelynek teljesítménye kiszámíthatatlan. A jobb felhasználói élmény biztosítása érdekében, ha egy felhasználó olyan lapot kér, amely megcélzást tartalmaz, és a lap olyan célközönségre hivatkozik, amely egy harmadik fél szegmensszolgáltatót ellenőriz, a lap alapértelmezett verziója jelenik meg.
> - A felhasználónak hozzá kell járulnia a sütik engedélyezéséhez. A felhasználó böngészője ezután kérni fogja az összes szegmenst a megfelelő szolgáltatóktól, és az eredményeket egy cookie-ban helyezi el, amelyet visszaküld a felhasználónak. A lapra érkező későbbi kérések ezt az információt használják fel arra, hogy célzott tartalmat szolgáltassanak a felhasználónak. A cookie-k megfelelőségéről további információkat a [Cookie-k megfelelősége](cookie-compliance.md) című témakörben talál.

**Jogi nyilatkozat:** Ha engedélyezi ezt a funkciót, az Ön adatai megosztásra kerülnek az Ön által kiválasztott harmadik fél rendszerekkel. Ön ellenőrzi, hogy ha vannak ilyenek, milyen adatokat ad át a harmadik félnek. Ön tudomásul veszi, hogy a harmadik fél adatkezelési és megfelelőségi előírásai eltérhetnek a Microsoft Dynamics 365 Commerce szabványaitól. Az Ön adatainak védelme fontos a Microsoft számára. Ha többet szeretne megtudni, olvassa el az [Adatvédelmi és sütikről szóló nyilatkozatunkat](https://privacy.microsoft.com/privacystatement).

### <a name="create-an-audience-in-site-builder"></a>Célközönség létrehozása a webhelykészítőben

Ha célközönséget szeretne létrehozni a Commerce webhelykészítőben, kövesse az alábbi lépéseket.

1. A bal oldali navigációs ablaktáblán válassza a **Célcsoportok** lehetőséget.
1. Válassza az **Új** lehetőséget.
1. Adja meg a célközönség nevét. Opcionálisan címkéket és leírást is hozzáadhat.
1. Válassza a **Létrehozás**, majd az **Új szabályblokk hozzáadása** lehetőséget. A szabályblokk olyan szabályok gyűjteménye, amelyeket ÉS feltételek kötnek össze. Több olyan szabályblokkot is létrehozhat, amelyek között VAGY feltételek vannak.
1. Válassza ki a szegmensek adatforrását, majd adja meg a szegmens nevét, operátorát és értékeit. Egy szabályblokkban több szabályt is létrehozhat és törölhet, illetve egész szabályblokkokat hozhat létre és törölhet. A szabályblokkokat igény szerint felfelé vagy lefelé is mozgathatja.

    > [!NOTE]
    > Egy listában legfeljebb 100 érték lehet, és minden listaelem legfeljebb 50 karaktert tartalmazhat.

1. Ha elégedett a célközönség konfigurációjával, válassza a **Szerkesztés befejezése** lehetőséget. Ezután választhatja a **Közzététel** lehetőséget, hogy a célközönség elérhetővé váljon egy élő célpontban való használatra. Alternatívaként a céllal együtt közzéteheti a célközönséget is. 

Célközönség szerkesztéséhez válassza ki a **Célközönség** lapon a hozzá tartozó hiperhivatkozást, majd a megjelenő célközönség-szerkesztőben válassza a **Szerkesztés** lehetőséget. A célközönségre hivatkozó célpontok és lapok listájának megtekintéséhez jelölje ki a célközönséget a célközönséglista nézetben, majd válassza a **Hozzárendelések megtekintése** lehetőséget. Célközönség törléséhez a célközönséglista nézetben vagy a célközönség-szerkesztőben szüntesse meg a célközönség közzétételét, ha már közzétette, majd válassza a parancssor **Törlés** lehetőségét.

> [!NOTE]
> A célközönség egy webhelyszintű koncepció a Commerce webhelykészítőben. Ugyanazt a célközönséget több célpont között is megoszthatja.

### <a name="rename-an-audience-in-site-builder"></a>Közönség átnevezése a Webhelykészítőben

Ha át szeretne nevezni egy meglévő közönséget a Commerce webhelykészítőben, kövesse az alábbi lépéseket.

1. A bal oldali navigációs ablaktáblán válassza a **Célcsoportok** lehetőséget.
1. Válassza ki az átnevezni kívánt közönségszegmens nevét.
1. Válassza ki **Szerkesztés** hogy elkezdje a közönség szerkesztését.
1. A közönség tulajdonságai ablaktáblában válassza ki a toll szimbólumot a közönség neve mellett.
1. Szükség szerint szerkessze a közönség nevét.
1. Jelölje be a pipát a névváltoztatás megerősítéséhez.
1. Válassza a **Szerkesztés befejezése** lehetőséget.

## <a name="targets"></a>Célok

A célpont az a felhasználói élmény, amelyet egy vagy több kiválasztott célközönség tagjainak mutatunk meg. Tartalmazhatja egy vagy több modul variációit egy lapon vagy egy töredékben. 

A célpontok számára ütemezést határozhat meg, hogy megadja, mennyi ideig maradjanak aktívak. Vegye figyelembe, hogy ez a művelet elkülönül a közzétételi csoport ütemezésének műveletétől, amely azt határozza meg, hogy egy tartalomgyűjtemény mikor legyen közzétéve. Előnézetben is megtekintheti a célpontokat, hogy lássa, hogyan fognak kinézni a kiválasztott célcsoportok tagjai számára. Ezenfelül rangsorolhatja a célpontokat, hogy meghatározza, ütközés esetén melyik célpont jelenjen meg.

### <a name="create-a-target"></a>Célpont létrehozása

A Commerce webhelykészítőben lévő lapmodulok célhéjának létrehozásához kövesse az alábbi lépéseket.

1. A bal oldali navigációs ablakban válassza ki a **Oldalak** lehetőséget. Ezután válassza ki annak a lapnak a hiperhivatkozását, amely a megcélozni kívánt modulokat tartalmazza.
1. Válassza a **Szerkesztés** lehetőséget az oldal szerkesztésre való kijelöléséhez.
1. A **Célpont** menüben válassza az **Új célpont** lehetőséget egy új célhéj létrehozásához. Igény szerint több célpontot is létrehozhat egy lapon.
1. Adja meg a célpont nevét és leírását, majd válassza a **Tovább** gombot.
1. Válassza a **Hozzáadás** lehetőséget a célzott tartalmat megtekintő célközönségek belefoglalásához, vagy a célközönségek kizárásához. Majd válassza a **Következő** lehetőséget.

    > [!NOTE]
    > A célközönség hozzárendelése opcionális lépés a célpontok létrehozása során. Mielőtt azonban közzéteszi a célpontot, legalább egy célközönséget fel kell tüntetnie, hogy a megcélzott felhasználói csoportok biztosan lássák a megcélzott tartalmat.

1. Az időzóna, valamint a kezdő és záró dátum és időpont kiválasztásával határozza meg a célpont megjelenítésének időablakát. Beállíthatja a célpontot úgy, hogy az ablak alatt mindig megjelenjen, vagy kiválaszthat bizonyos napokat és időpontokat. Ha befejezte, válassza a **Tovább** lehetőséget.

    > [!NOTE]
    > A megadott időpontok és időzónák globálisak. Ha különböző helyszíneket szeretne különböző időpontokban vagy különböző időzónákban célba venni, akkor különböző célpontokat kell létrehoznia, és minden egyes helyszínhez meg kell határoznia a kívánt ütemezést.

1. Tekintse át a részleteket, és ha minden rendben van, válassza a **Célpont élmény létrehozása**, majd a **Célpontra ugrás** lehetőséget. Létrejön a célhéj. Most már hozzáadhat modulokat.
1. Válassza ki a megcélzandó modult, jelölje ki a három pontot (**...**), majd válassza a **Hozzáadás az aktuális célponthoz** lehetőséget. Ha szülőmodult céloz meg, annak minden gyermeke a célpont részévé válik. A megcélzott modulok zöld színnel vannak kiemelve.
1. Végezze el a szükséges tartalmi frissítéseket a megcélzott modulon, és szükség szerint adjon hozzá további modulokat a célponthoz. Ezután válassza a **Mentés** lehetőséget a módosítások mentéséhez.
1. Mielőtt közzéteszi a célpontot, mindenképpen válassza az **Előnézet** lehetőséget a parancssoron, hogy áttekintse. Ezután kiválaszthatja a következő lehetőségek egyikét:

    - **Alap előnézet** – Válassza ezt a lehetőséget, ha csak a kiválasztott variációt (alapértelmezett lap vagy célpont) szeretné előnézetben megjeleníteni, a kapcsolódó célközönségek nélkül.
    - **Speciális előnézet** – Válassza ezt a lehetőséget, ha egy lapon több célpont van, és azokat egy kiválasztott célközönség-csoporthoz tartozó felhasználóként vagy egy adott napon/időpontban szeretné előnézetben megjeleníteni. Válassza a **Tovább** gombot a releváns célközönségek listájából való kiválasztáshoz. A szűrő eltávolításával az összes célközönség közül is választhat.

1. Ha elégedett a célkonfigurációval, akkor közzé kell tennie az oldalt, hogy a célpont éles legyen. Válassza a **Közzététel** lehetőséget a célpont azonnali élesítéséhez. Alternatívaként használhat közzétételi csoportot is, hogy ütemezze az oldal élesítésének időpontját. A közzétételi csoportokkal kapcsolatos további tudnivalókat lásd: [Munka a közzétételi csoportokkal](publish-groups.md).

A töredékeket is megcélozhatja. Az eljárás hasonló. Az 1. lépésben azonban a bal oldali navigációs ablaktáblában a **Lapok** helyett a **Töredékek** lehetőséget válassza.

> [!NOTE]
> Hogy elkerülje a metrikáira gyakorolt negatív hatást, egy lapon vagy egy töredékben is lehet kísérlet vagy célpont. Nem lehet egyszerre kísérlete és célpontja is.

### <a name="manage-targets"></a>Célok kezelése

A célpontok szerkesztéséhez, duplikálásához vagy törléséhez lépjen az alapértelmezett lapra vagy töredékre, és kövesse az alábbi lépéseket.

1. A legördülő menüben válassza a **Célpont**, majd a **Célpontok kezelése** lehetőséget.
1. Válassza ki a szerkeszteni, duplikálni vagy törölni kívánt célpontot.
1. Ha több célpont van ugyanabban a modulban, vagy ha több célpontnak egymással ütköző ütemezése van, válassza a **Célpontok rangsorolása** lehetőséget, hogy megadhassa a megjelenítési sorrendet. Ha több célpontot ad hozzá egy lapon vagy egy töredékben, a **Célpontok rangsorolása** gomb is megjelenik az értesítési sávban, hogy emlékeztesse a célpontok prioritizálására. Ha nincs megadva prioritás, alapértelmezés szerint a legutóbbi célpont kerül kiválasztásra.

### <a name="localize-targets"></a>Célpontok honosítása

A lapokon és töredékekben lévő célpontok automatikusan megjelennek az XLIFF-fájlok honosítási célú exportálásakor és importálásakor. Ha azonban valamelyik területi beállításra nincs szükség, a lokalizált XLIFF-fájlok importálása után törölheti a célpontokat.

> [!NOTE]
> A célpontok kezelése csatornánként és területi beállításonként történik. Az egyik csatornán vagy területi beállításban lévő célpontokon végrehajtott módosítások nem kerülnek át automatikusan más csatornákra vagy területi beállításokba.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
