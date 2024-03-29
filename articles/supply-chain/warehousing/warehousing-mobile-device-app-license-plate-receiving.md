---
title: Azonosítótábla-bevételezés a Warehouse Management mobilalkalmazás használatával
description: Ez a cikk bemutatja, hogy hogyan lehet beállítani a Raktárkezelés mobilalkalmazást, amely a fizikai készlet bevételezéséhez egy tábla bevételezését támogatja.
author: perlynne
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSParameters, WHSRFMenuItem, WHSLicensePlate, WHSPackingStructure
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-03-31
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 657c29ec6ddfb2be918424e06eaf219f51a30a02
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2022
ms.locfileid: "9069062"
---
# <a name="license-plate-receiving-via-the-warehouse-management-mobile-app"></a>Azonosítótábla-bevételezés a Warehouse Management mobilalkalmazás használatával

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja a Raktárkezelés mobilalkalmazás beállítását, amely lehetővé teszi a fizikai készlet bevételezéséhez az tábla-bevételezés folyamatának alkalmazását.

Ezen funkció segítségével gyorsan rögzítheti az előzetes kiszállítási értesítéshez (ASN) kapcsolódó bejövő készlet bevételezését. A rendszer automatikusan létrehoz egy ASN-t, ha a raktárkezelési folyamatok (WMS) az átvezetési rendelés szállításában használatosak. A beszerzési rendelés folyamatahoz egy ASN manuálisan is rögzíthető, vagy automatikusan importálható a bejövő ASN adatentitás folyamata segítségével.

Az ASN-adatok a rakományokhoz és a szállítmányokhoz a *csomagolási struktúrákon* keresztül kapcsolhatók, ahol a raklapok (a szülő azonosítótáblák) tartalmazhatnak eseteket (beágyazott azonosítótáblák).

> [!NOTE]
> Hogy csökkentse a készlettranzakciók számát, amikor beágyazott azonosítótáblákkal rendelkező csomagolási struktúrák vannak használatban a rendszer rögzíti a fizikai aktuális készletet a szülő azonosítótáblára. Ha azt szeretné, hogy a rendszer a tényleges aktuális készletet a szülő rendszámtábla és a beágyazott rendszámtábla között a csomagolási struktúra adatainak megfelelően mozgassa, a mobileszköznek egy olyan menüelemet kell biztosítania, amely a *Csomagolás beágyazott azonosítótáblákhoz* munkalétrehozási folyamaton alapul.

## <a name="warehousing-mobile-device-app-processing"></a>Raktározási mobileszköz-alkalmazásos feldolgozás

Amikor egy dolgozó beolvas egy bejövő azonosítótábla-azonosítót, a rendszer inicializál egy azonosítótábla-bevételezési folyamatot. Az információ alapján az azonosítótábla tartalma (az ASN-ből érkező adatok) fizikailag regisztrálva lesz a bejövő dokk helyén. A következő folyamatok függenek az üzletifolyamat-igényeitől.

## <a name="work-policies"></a>Munkairányelvek

Ahogy például a *Készként jelentés* mobileszköz-menüelem folyamatnál, az azonosítótábla-fogadó folyamat több munkafolyamatot támogat a megadott beállítások alapján.

### <a name="work-policies-with-work-creation"></a>Munka-létrehozással kapcsolatos munkairányelvek

Ha egy munkát létrehozó munkairányelv alapján regisztrálja a bejövő cikkeket, akkor a rendszer minden regisztrációhoz létrehozza és menti az elraktározási munkarekordokat. Ha az *Azonosítótábla bevételezése és eltárolása* munkafolyamatok végzi, a regisztrációt és az eltárolást egyetlen műveletként kezeli a rendszer, egyetlen mobileszköz-menüelemet használva. Ha az *Azonosítótábla bevételezése* folyamatot használja, akkor a bevételezési és elraktározási folyamatok két különböző raktári műveletként kezeli a rendszer, és mindegyik saját mobileszköz menüelemmel rendelkezik.

### <a name="work-policies-without-work-creation"></a>Munka-létrehozás nélküli munkairányelvek

Az azonosítótábla-bevételezési folyamat munka létrehozása nélkül is használható. Ha olyan munkairányelveket határoz meg, amelyeknek *Átmozgatási bevételezés* és/vagy *Beszerzési rendelések* munkarendelési típusa van, és az *Azonosítótábla bevételezése (és eltárolása)* folyamatot használja , akkor a következő két Warehouse Mobile App folyamat nem hozza létre a munkát. Helyette csak a bejövő tényleges készletet fogja regisztráltatni az azonosítótábla a bejövő fogadó dokknál.

- *Azonosítótábla bevételezése*
- *Azonosítótábla bevételezése és eltárolása*

> [!NOTE]
> - Meg kell határoznia a munkairányelvhez legalább egy helyet a **Raktári helyek** szakaszban. Nem határozhatja meg ugyanazt a helyet több munkairányelvhez.
> - A Warehouse mobileszköz menüelemek **Címkenyomtatás** lehetősége nem nyomtat azonosítótábla címkét munka létrehozása nélkül.

Ha azt szeretné, hogy ez a funkció elérhető legyen a rendszerben, akkor be kell kapcsolni az *Azonosítótábla fogadásával kapcsolatos fejlesztések* funkciót a [szolgáltatáskezelésben](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="receive-inventory-on-a-location-that-doesnt-track-license-plates"></a>Készlet fogadása olyan helyen, amely nem követi nyomon az azonosítótáblákat

Lehetőség van arra, hogy olyan raktári helyet alkalmazzon, amelyet a rendszer hozzárendelt egy helyprofilhoz, még ha az **Azonosítótábla követésének használata** nincs is bekapcsolva. Ezért a készlet vételekor közvetlenül regisztrálhat egy helyen aktuális készletet munka létrehozása nélkül.

## <a name="add-mobile-device-menu-items-for-each-receiving-location-in-a-warehouse"></a>Mobileszköz-menüelemek hozzáadása a raktárban található összes bevételezési helyhez

Az *Azonosítótábla fogadásával kapcsolatos fejlesztések* funkció lehetővé teszi, hogy a raktárban található bármelyik helyen fogadjon úgy, hogy hozzáad egy helyspecifikus azonosítótábla fogadás és betárolás menüelemet Warehouse mobilalkalmazáshoz. Korábban a rendszer csak az egyes raktárakhoz megadott alapértelmezett helyeken támogatta a fogadást. Ha azonban ez a funkció be van kapcsolva, akkor az azonosítótábla fogadás és betárolás mobileszköz-menü elemek most már rendelkezésre bocsátják az **Alapértelmezett adatok használata** beállítást, amely lehetővé teszi, hogy az egyes menüelemekhez egyéni rendeltetési helyet válasszanak. (Ez a beállítás már elérhető volt más típusú menüelemekhez.)

Ha azt szeretné, hogy ez a funkció elérhető legyen a rendszerben, akkor be kell kapcsolni az *Azonosítótábla fogadásával kapcsolatos fejlesztések* funkciót a [szolgáltatáskezelésben](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="show-or-skip-the-receiving-summary-page"></a>A bevételezési összesítő lap megjelenítése vagy kihagyása

Az *Annak szabályzása, hogy meg legyen-e jelenítve egy fogadás összegzése lap a mobileszközökön* funkció használatával kihasználhatja egy további részletes Raktárkezelés mobilalkalmazás-folyamat előnyeit az azonosítótábla-fogadási folyamat részeként.

Ha ez a funkció be van kapcsolva, akkor az azonosítótábla fogadására és betárolására szolgáló menüelemek tartalmazzák a **Fogadó összesítő lap megjelenítése** beállítást. Ez a beállítás a következő lehetőségeket biztosítja:

- **Részletes összefoglalás megjelenítése** – Az azonosítótábla fogadása során a dolgozók egy külön lapot fognak látni, amely a teljes ASN-információt jeleníti meg.
- **Az összefoglalás kihagyása** – A dolgozók nem fogják látni a teljes ASN-információt. A raktári dolgozók nem állíthatnak be intézkedési kódot sem, illetve kivételeket adhatnak meg a bevételezési folyamat során.

Ennek a funkciónak a használatához be kell-e kapcsolva lennie a *rendszernek ahhoz,* hogy megjelenítsen-e fogadó összefoglaló oldalt a mobileszköz-szolgáltatásban. Az Ellátásilánc-kezelés 10.0.21-es verziója szerint ez a funkció alapértelmezés szerint be van kapcsolva. A 10.0.25-ös ellátásilánc-kezelésben ez a funkció kötelező, és nem lehet kikapcsolni. Ha 10,0,25-ösnél régebbi verziót futtat, *akkor a rendszergazdák be- vagy kikapcsolhatják ezt a funkciót, ha a vezérlő segítségével eldöntik, hogy megjeleníti-e a fogadó összesítő oldalt a*[Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületének mobileszköz-szolgáltatásán.

## <a name="prevent-transfer-ordershipped-license-plates-from-being-used-at-warehouses-other-than-the-destination-warehouse"></a>Átmozgatási rendeléssel szállított azonosítótáblák használatának megakadályozása a célraktártól eltérő raktárban

Az azonosítótábla-bevételezési folyamat nem használható, ha az ASN tartalmaz egy rendszámtábla-azonosítót, amely már létezik, és tényleges aktuális adatokkal rendelkezik egy olyan raktári helyen, amely nem az a raktári hely, ahol az azonosítótábla regisztrációja történik.

Az átmozgatási rendelés esetében, amikor az átmozgatási raktár nem követi nyomon az azonosítótáblákat (és ezért nem követi a tényleges aktuális készletet azonosítótáblánként) használhatja a *Átmozgatási rendeléssel szállított azonosítótáblák használatának megakadályozása a célraktártól eltérő raktárban* funkciót, amellyel megakadályozható az átvitel alatt lévő azonosítótáblák tényleges aktuális frissítése. Ahhoz, hogy ez a funkció használható legyen, be kell kapcsolva lennie a rendszernek ahhoz, *hogy* a szállított át szállított rendelési táblákat a célraktár funkciótól különböző raktárakban használják. A 10.0.25-ös ellátásilánc-kezelésben ez a funkció kötelező, és nem lehet kikapcsolni. Ha 10.0.25-ösnél régebbi verziót futtat, [akkor](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) a rendszergazdák a Funkciókezelés munkaterületén való kereséssel kapcsolják be és kapcsolják ki a funkciót.

Ha elérhetővé szeretné tenni ezt a funkciót, hajtsa végre az alábbi lépéseket.

1. Lépjen a **Raktárkezelés \> Beállítás \> Raktárkezelési paraméterek** részre.
1. Az **Általános** lap **Azonosítótáblák** gyorslapján a következő értékek valamelyikére állítsa be a **Tranzitraktár azonosítótábla-irányelvei** mezőt:

    - **Nem nyomon követett rendszámtábla újrafelhasználásának engedélyezése** – A rendszer ugyanúgy működik, mint amikor a *Átmozgatási rendeléssel szállított azonosítótáblák használatának megakadályozása a célraktártól eltérő raktárakban* funkció nem érhető el. Ez az érték az alapértelmezett beállítás a funkció első aktiválása alkalmával.
    - **Nem nyomon követett azonosítótáblák újrahasznosításának megakadályozása** – Csak a szállítót azonosítótáblákhoz kapcsolódó aktuális frissítések engedélyezettek a cél raktárban mindaddig, amíg az átmozgatási rendelés nem érkezett meg.

## <a name="more-information"></a>További információ

A mobileszköz-menüelemek beállításával kapcsolatos további tudnivalókat lásd: [Mobileszközök beállítása raktári munkához](configure-mobile-devices-warehouse.md).

A *Készként jelentéssel* termelési forgatókönyvvel kapcsolatos további tudnivalókat lásd a [Raktári munkairányelvek áttekintése](warehouse-work-policies.md).

További információ a bejövő rakományok kezeléséről: [Beszerzési rendelések bejövő rakományának kezelése a raktárban](inbound-load-handling.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]