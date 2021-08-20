---
title: Egyéni mezők létrehozása és használata
description: Ez a témakör bemutatja, hogyan hozhat létre egyéni mezőket a felhasználói felületen, hogy az alkalmazást saját cégük igényeire szabhassa.
author: jasongre
ms.date: 05/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysCustomFieldManageFields
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-1-31
ms.dyn365.ops.version: Platform update 13
ms.openlocfilehash: c941fa30662ed54159e303bf2a944026900d8c04107bc800d109a80d9ef456a4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760710"
---
# <a name="create-and-work-with-custom-fields"></a>Egyéni mezők létrehozása és használata

[!include [banner](../includes/banner.md)]

Bár a mezők sokasága áll rendelkezésre az üzleti folyamatok széles körének kezeléséhez, néha szükség van arra, hogy a vállalat a rendszerben lévő további információkat is nyomon kövessen. Noha a programozók felhasználhatják ezeket a mezőket bővítményként a fejlesztőeszközökben, az egyéni mezők funkció lehetővé teszi a mezők közvetlen hozzáadását a felhasználói felületről, így a webböngészővel testreszabhatja az alkalmazást, hogy illeszkedjen a vállalkozáshoz.

*Csak a különleges jogosultságú felhasználók férhetnek hozzá ehhez a funkcióhoz.*

Ez a videó megmutatja, milyen egyszerű egy Egyéni mező hozzáadása az oldalhoz: [Egyéni mező hozzáadása](https://www.youtube.com/watch?v=gWSGZI9Vtnc).

## <a name="creating-custom-fields"></a>Egyéni mezők létrehozása

Miután azonosította azokat a további információkat, amelyeket követni szeretne az alkalmazásban, a megfelelő táblában létrehozhatja az egyéni mezőt, és ezt az új mezőt megjelenítheti egy oldalon.

A következő lépések leírják az egyéni mező létrehozásának és a mező képernyőre helyezésének folyamatát.

1. Keresse meg az képernyőt, ahol az új mezőre szükség van.
2. Mivel a végcél az egyéni mező megjelenítése egy képernyőn, az egyedi mezők létrehozásának kezdőpontja a személyre szabási folyamat része. Nyissa meg a személyre szabási eszköztárat a **Beállítások**, majd a **Képernyő személyre szabása** lehetőséggel.
3. Kattintson a **Beillesztés**, majd **Mező** lehetőségre.
4. Válassza ki a képernyő azon részét, ahol elérhetővé szeretné tenni az új mezőt. A kiválasztás után a **Mezők beillesztése** párbeszédablak megjeleníti a meglévő mezők listáját, amelyek beilleszthetők a képernyő kiválasztott részére.
5. Győződjön meg róla, hogy az Önt érdeklő mező még nem létezik a listában. Ha létezik, egyszerűen jelölje ki a listában a mezőt, és kattintson a **Beillesztés** elemre.
6. Kattintson az **Új mező létrehozása** gombra a lista felett, hogy elindítsa az egyéni mező létrehozásának folyamatát. Ennek hatására megnyílik az **Új mező létrehozása** párbeszédpanel.

    Ha nem látja az **Új mező létrehozása** gombot, nem rendelkezik a szükséges engedélyekkel a funkció használatához.

7. Az **Új mező létrehozása** párbeszédpanelen adja meg a következő adatokat.
   
    1. Válassza ki az adatbázistáblát, amelyhez ezt a mezőt hozzá kívánja adni. Ne feledje, hogy csak az egyéni mezőket támogató táblák jelennek meg a legördülő listában. A támogatott táblázatok technikai részleteit az alábbi részben találja.

    2. Válassza ki az új mező adattípusát. Az elérhető adattípusok: jelölőnégyzet, dátum, dátum és időpont, tizedes szám, szám, választólista és szöveg.

        - Ha a szöveg adattípust választja, megadhatja a mezőben megadható szöveg maximális hosszát is.
        - Ha a választólista adattípust választja, kiválaszthatja a mezőben érvényes értékek listáját is.

    3. Adjon nevet, címkét és súgószöveget a mezőnek. A név megegyezik az adatbázisban található fizikai mezőnévvel, míg a címke és a súgószöveg a felhasználói felületen mutatják be ezt a mezőt.

8. Ha ez az egyetlen mező, amelyet létre kíván hozni ezen a képernyőn, kattintson a **Mentés** elemre. Ha szeretne létrehozni további mezőket is, kattintson a **Mentés és új** elemre, és ugorjon vissza a 7. lépésre. Ne feledje, hogy jelenleg **táblánként 20 egyedi mező** hozható létre.
9. Az **Új mező létrehozása** párbeszédpanel bezárásával visszatér a **Mezők beillesztése** párbeszédpanelre. Az újonnan hozzáadott egyéni mezők automatikusan bejelölésre kerülnek az képernyőre illesztendő mezők listáján.
10. Kattintson a **Beillesztés** elemre a megjelölt mező a képernyő kijelölt területére történő beszúrásához.
11. **Opcionális lehetőség:** Engedélyezze az **Áthelyezés** módot a személyre szabási eszköztáron az új mezők a kijelölt terület kívánt helyére való áthelyezéséhez. Lásd [A felhasználói felület testreszabása](personalize-user-experience.md) című részt a képernyők személyes használatra való optimalizálására szolgáló személyre szabási szolgáltatások használatáról.

> [!WARNING]
> Hogy egy oldalhoz hozzáadott egyéni mezőkben lehet-e értékeket megadni, az attól függ, hogy az egyéni mezőhöz társított tábla szerkeszthető-e vagy írásvédett. Ha a társított tábla írásvédett, akkor a hozzá kapcsolódó összes mező (az egyéni mezők is) írásvédett.


## <a name="sharing-custom-fields-with-other-users"></a>Egyéni mezők megosztása más felhasználókkal

Miután létrehozott egy egyéni mezőt, és megjelenítette egy oldalon, érdemes megadnia ezt az új mezőt is tartalmazó frissített oldalnézetet a rendszer többi felhasználójának. Ez kétféleképpen érhető el a termék személyre szabási képességeinek használatával:

- A javasolt útvonal **egy olyan egyéni mezőt tartalmazó [mentett nézet](saved-views.md) közzététele**, amelyet az oldalon felvettek a megfelelő felhasználócsoport számára. Ha a mentett nézetek funkció nincs engedélyezve, a rendszergazda a Személyre szabás űrlapon alkalmazhatja a személyre szabást a kívánt felhasználók számára. További részletek: [A felhasználói élmény testreszabása](personalize-user-experience.md).
- Alternatívaként exportálhatja a módosításokat (úgynevezett *személyre szabásokat*), elküldheti őket egy vagy több felhasználónak, és e felhasználók mindegyike importálhatja a módosításokat. A személyre szabási eszköztáron található **Kezelése** opcióval bonyolítható a személyes beállítások exportálása és importálása.

## <a name="managing-custom-fields"></a>Egyéni mezők kezelése

A rendszerben található összes egyéni mező kezelése a Rendszerfelügyeleti modul **Egyéni mezők** lapján végezhető el. Ez az oldal számos funkcióhoz nyújt hozzáférést a felhasználók számára, többek között:

- A rendszerben lévő minden egyéni mező listájának megjelenítése.
- Meglévő egyéni mezők korlátozott szerkesztése.
- Egyéni mezők törlése.
- Egyéni mezők közzététele adatentitásoknak.
- Egyéni mezők címkéinek és súgószövegeinek fordításai.

### <a name="viewing-all-custom-fields"></a>Minden egyéni mező megtekintése

Az **Egyéni mezők** lap megjeleníti a rendszerben meghatározott összes egyéni mezőt. Egyszerűen válassza ki a táblát, amely érdekli, és az oldal frissül, és megjeleníti az adott táblához társított egyéni mezők listáját. Egyéni mező kiválasztása a listából lehetővé teszi, hogy megtekinthesse a mező minden részletét.

### <a name="editing-custom-fields"></a>Egyéni mezők szerkesztése

Egyéni mező létrehozása után az egyedi mezőre vonatkozó egyes adatok csak az **Egyéni mezők** oldalon módosíthatók.

Ezeket az attribútumokat *módosíthatja*:

- Címke
- Súgószöveg
- Hossz, szövegmezőknél

Az alábbi attribútumok szerkesztésére *nincs* lehetőség:

- Mezőnév
- Adattípus

Ezenkívül a választólista mezők esetében az egyéni mező érvényes értékeinek sorrendje átrendezhető, és új értékek adhatók hozzá; azonban a listán szereplő értékek nem távolíthatók el. Ne feledjen kattintani a **Módosítások alkalmazása** elemre, ha befejezte a mezők szerkesztését egy adott táblázatnál, hogy a változásokat elmentse.

### <a name="exposing-custom-fields-on-data-entities"></a>Egyéni mezők közzététele adatentitásoknak

Azt is fontos, hogy az egyéni mezők láthatók legyenek az adatentitásokon. Az adatentitások az [Office-integráció áttekintése](../../dev-itpro/office-integration/office-integration.md) funkcióban, valamint adatok importálásánál/exportálásánál használatosak.

Kövesse az alábbi lépéseket az egyéni mező egy adatentitáson való megjelenítéséhez:

1. Válassza ki az egyéni mezőt az **Egyéni mezők** képernyőn.
2. Bontsa ki az **Entitások** szakaszt az érintett entitások megjelenítéséhez.
3. Kattintson a **Szerkesztés** gombra.
4. Módosítsa a **Engedélyezett** mezőt és jelölje ki minden entitásnál amelyet közzé kíván tenni ehhez a mezőhöz.
5. A változtatások mentéséhez kattintson a **Módosítások alkalmazása** gombra.

### <a name="allowing-custom-fields-to-be-displayed-in-other-languages"></a>Egyéni mezők más nyelveken történő megjelenítésének engedélyezése

Mivel az egyes mezőkhöz különböző nyelveken beszélő felhasználók férhetnek hozzá, az **Egyéni mezők** biztosít egy olyan mechanizmust, amely lehetővé teszi, hogy az egyéni mező címkéje és súgószövege lefordítható legyen más nyelvekre.

Egyéni mezők más nyelvekre történő lefordításához a folyamat a következő lépésekből áll:

1. Válassza ki az egyéni mezőt az **Egyéni mezők** oldalon.
2. Válassza a **Fordítások** gombot a műveleti ablakban. Ennek hatására megnyílik egy legördülő menü, benne az ehhez a mezőhöz már meglévő fordításokkal.
3. A **Nyelv** legördülő menü mutatja a nyelveket, amelyekre a fordítások már rendelkezésre állnak.

    Ha meglévő fordítást szeretne szerkeszteni, válassza ki a kívánt nyelvet a menüből, és módosítsa a címke és a súgó szövegét.

    Ellenkező esetben kattintson a **Nyelv hozzáadása** gombra, válassza ki a kívánt nyelvet a menüből, és adja meg a a címke- és súgószöveghez tartozó lefordított értékeket.

4. Amikor végzett, kattintson az **OK** gombra.

### <a name="deleting-custom-fields"></a>Egyéni mezők törlése

Bizonyos ritka esetekben dönthet úgy, hogy egy egyéni mezőre már nincs többé szükség. Ha ez bekövetkezik, a rendszergazda választhatja a mező törlését az **Egyéni mezők** oldalon. Ehhez az szükséges, hogy győződjön meg róla, hogy a helyes mező be van jelölve, kattintson a **Törlés** elemre, kattintson az **Igen** elemre a törlés megerősítéséhez, és végül kattintson a **Módosítások alkalmazása** lehetőségre.

> [!NOTE]
> Ezt a műveletet nem lehet visszavonni, és a mezőhöz társított adatok véglegesen törlődnek az adatbázisból.

## <a name="appendix"></a>Melléklet

### <a name="why-cant-i-enter-a-value-in-my-custom-field"></a>Miért nem lehet értéket megadni az egyéni mezőben? 

Ha az oldal szerkesztési módban van, de mégsem tud beírni értéket az egyéni mezőbe, akkor lehet, hogy a mezőhöz hozzáadott tábla jelenleg írásvédett. Egy tábla minden mezője írásvédett lesz, ha a biztonsági tábla írásvédettként van konfigurálva az oldalon.   

### <a name="who-can-create-custom-fields"></a>Ki hozhat létre egyedi mezőket?

A rendszer védelme érdekében alapértelmezés szerint csak a rendszergazdák képesek egyedi mezőket létrehozni. Azonban a szervezet által szükségesnek ítélt kiemelt felhasználóknak a rendszergazda jogot adhat egyéni mezők létrehozására a **Futásidejű testreszabás kiemelt felhasználónál** biztonsági szerepkör használatával. Az e biztonsági szerepkör nélküli felhasználók nem tudnak létrehozni egyéni mezőket, de továbbra is megtekinthetik és haszálhatják a rendszer más felhasználói által hozzáadott egyéni mezőket.

### <a name="what-tables-support-custom-fields"></a>Milyen táblák támogatják az egyéni mezőket?

Teljesítmény- és a műszaki okok miatt jelenleg csak a következő feltételeknek megfelelő táblák engedélyezik az egyéni mezők hozzáadását.

- A táblának címkéje alapján e csoportok egyikébe kell tartoznia:

    - Csoport
    - WorksheetHeader
    - Fő
    - Vegyes
    - Paraméter
    - Hivatkozás
    - TransactionHeader

- A tábla nem bővíthet másik táblát.
- A tábla nem lehet rendszertáblaként megjelölve.
- A tábla nem lehet ideiglenes tábla.

### <a name="can-i-reference-custom-fields-from-the-developer-tools"></a>Hivatkozhatok a fejlesztői eszközökből egyéni mezőkre?  

Az egyéni mezők csak a felhasználói felületen kezelhetők, és kód nem hivatkozhat rájuk. 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
