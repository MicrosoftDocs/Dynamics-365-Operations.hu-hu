---
title: Sablonok és elrendezések áttekintése
description: Ez a cikk a következő sablonokról és elrendezésről ad le:Microsoft Dynamics 365 Commerce
author: phinneyridge
ms.date: 12/12/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: adf1585e418ca2d09065db03de72cb1bbfb3e614
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844620"
---
# <a name="templates-and-layouts-overview"></a>Sablonok és elrendezések áttekintése


[!include [banner](includes/banner.md)]

A sablonok a Microsoft Dynamics 365 Commerce oldal modelljének alapelemei. Ha a célja a webhelylétrehozási munkafolyamatok hatékonyságának és konzisztenciájának maximalizálása, fontos, hogy megtanulja, hogyan lehet a webhelyhez tartozó sablonok előnyeit kihasználni A sablon struktúrájával kapcsolatos korai döntések fontosak, és jelentősen befolyásolhatják a napi, szezonális és a webhely egészére vonatkozó márkafrissítések költségét és hatékonyságát. A jól strukturált sablonoknak egyéb előnyei is vannak. Például javítják a webhely egészére kiterjedő keresőmotor-optimalizálás (SEO) pontszámát, és minimalizálják a hibák számát.

A sablonokkal való munkavégzés elkezdéséhez jó módszer a sablonok és elrendezések funkcionális előnyeinek, a köztük lévő különbségeknek és a hierarchiának a megértése.

A következő ábra a megjelenített weboldalakhoz tartozó lapmodell-hierarchiát jeleníti meg.

![Lapmodell diagram.](../commerce/media/page-model-diagram.png)

| Entitás        | Alapfunkció |
|---------------|----------------|
| Sablon      | A sablonok meghatározzák a modul beállításait és az elrendezéskészletek és lappéldányok alapszerkezetét. |
| Elrendezés        | Az elrendezések a lap vagy a lapok egy csoportja számára határozzák meg a modulok végleges kijelölését és elrendezését. |
| Lappéldány | A lappéldányok az adott lapok adatait és tartalmát határozzák meg. |

## <a name="templates"></a>Sablonok

A sablonok a Dynamics 365 Commerce lapmodelljenek hierarchiájának tetején vannak, és a webhely-konfiguráció fontos korai lépései. Koncepciójuktól fogva a sablonok segítenek felügyelni a konzisztenciát származtatott elrendezések között azáltal, hogy meghatározzák az alapstruktúrát és szerkesztési lehetőségeket a lefelé irányuló elrendezések létrehozásához és oldallétrehozási munkafolyamatokhoz. A sablonok elősegítik a tartalom-létrehozási folyamat egyszerűsítését előre definiált, központilag kezelt elemekkel (például fej- és láblécek) és irányított létrehozási folyamatokkal, amelyek segítenek a modul konfigurációs lehetőségei megfeleljenek a márkaarculatnak.

### <a name="controlling-consistency"></a>Konzisztencia felügyelete

A sablon tervezésekor a legfontosabb üzleti döntés, az, hogy mekkora befolyása legyen a sablonnak az oldal létrehozási folyamatára. Egy sablon, amely mindent megenged a további felhasználónak a legegyszerűbben létrehozható sablontípus de előfordulhat, hogy hosszú távú következményekkel jár az ez alapján létrehozott oldalak karbantartása szempontjából. A jól megírt sablon útmutatást és egyszerű szerkesztési élményt nyújt, de a szerzők számára elég rugalmasságot biztosít a feladathoz. Mindezek a szempontok attól függenek, hogy a sablon milyen szintű felügyeletet kényszerít ki.

A sablonok a következőképpen segítenek abban, hogy a tartalomkészítők hatékonyabbak legyenek és megőrizzék a márkaarculatot:

- A lapon használható modulokat korlátozzák.
- Alapértelmezett modul és a konfigurációs lehetőségeket javasolnak.
- Explicit módon hajtanak végre néhány modult és konfigurációs beállítást, amelyek a sablon szintjén vannak szabályozva. Ezt a folyamatot a beállítás *zárolásának* is nevezik.

A következő példa azt mutatja be, hogyan lehet konfigurálni egy alapvető sablonok (X sablon):

- Az X sablon minden származtatott elrendezésének rendelkeznie kell egy fejléctárolóval, egy törzsszövegtárolóval és egy lábléctárolóval.
- Az X sablonban a fejléctároló konfigurációja zárolva van, és csak magában az X sablonban módosítható. Minden származtatott elrendezés és lap mindig ezt a fejlécet alkalmazza.
- A szövegtörzs tároló legalább egy modult igényel, de legfeljebb tíz modult tartalmazhat. Ezeket a modulokat az alsóbb elrendezések és lapok határozzák meg.
- A szövegtörzs tároló esetében a hős, a funkció, a körhinta és a szalagcím modul elérhető.
- A lábléctároló az X-es sablonban van beállítva, de az alsóbb elrendezések és lapok felülbírálhatják.

A példában szereplő sablon egyszerű struktúrát és beállításokat határoz meg a későbbi tartalomszerzők számára. Figyelje meg, hogy a lap egyes részei (ebben az esetben a fejléc) teljes mértékben definiáltak és zároltak a sablonban, és a későbbi szerzők nem módosíthatják őket. Más részeket (ebben az esetben a szövegtörzset) a későbbi szerzők definiálhatják a meghatározott iránymutatásokon belül (ebben az esetben az adott típusú modulok minimális száma és maximális száma van meghatározva). És a többi rész (ebben az esetben a lábléc) a sablonban van definiálva, de a további szerzők felülbírálhatják őket.

A webhelyek és a márkák adminisztrátorának számára fontos első lépés a megfelelő a megszorítások és rugalmasság közötti helyes egyensúly meghatározása az oldalszerzők számára. A sablonok használatakor ez az egyensúly teljesen konfigurálható. Ez a beállítás hatással van arra, hogy a lap elemeit központilag frissítik-e (a sablonban zárolva van), vagy az egyes származtatott szinteken a laphierarchia alsóbb szintjein.

A sablonok használatának megkezdéséhez [Munka a sablonokkal](work-with-templates.md).

## <a name="layouts"></a>Elrendezések

Az elrendezések a következő szintet jelentik a lapmodell hierarchiájában a sablonok alatt. Mivel a sablon határozza meg, hogy az egyes oldalakhoz mely modulok engedélyezettek, az elrendezés a modulok explicit kiválasztása és elrendezése. A lapok a következő szintet jelentik a lapmodell hierarchiájában az elrendezések alatt. Ezek határozzák meg modulok lokalizált tartalmát, amelyek ki vannak jelölve az elrendezésben.

A következő példa az előző szakasz példasablonján alapul, és azt mutatja, hogyan lehet beállítani egy alapvető elrendezést:

- Az elrendezés szülő sablonja megköveteli, hogy a szövegtörzs tárolók száma egy és tíz modul között legyen. Ezek a modulok csak a hős, a funkció, a körhinta és a szalagcím modulok lehetnek. Ennek megfelelően az elrendezés a modulok következő kiválasztását és elrendezését határozhatja meg:

    - A törzsszöveg tároló első modulja egy szalagcímmodul, és azt egy hősmodul és két funkciómodul követi.
    - Az első funkciómodul balra igazított, és a második funkciómodul jobbra igazított.

- Annak ellenére, hogy egy alapértelmezett élőláb a szülő sablonból származik, a sablon szerzője nem zárolta a láblécet. Ennek megfelelően az elrendezés felülírhatja egy másik lábléctöredék definiálásával.

A példában szereplő elrendezés határozza meg a származtatott oldalak moduljainak végleges elrendezését. A sablonhoz hasonlóan egy elrendezés is definiálhat alapértelmezett vagy zárolt modul tulajdonságokat, amelyeket a származtatott oldalak mindig örökölnek (például a funkciómodulok igazítása). Az elrendezés minden moduljához a tényleges tartalom vagy adat a hierarchiában lejjebb van meghatározva, az egyes származtatott példányokban. Fontos különbség az, hogy az elrendezések közvetlenül nem tartalmaznak honosítható tartalmakat, míg a származtatott oldalaik igen. Az elrendezés elsődleges funkciója a saját származtatott oldalain található modulok végleges elrendezésének és alapértelmezett beállításainak meghatározása.

Ez a hierarchia két okból is hatékony. Először is, az azonos szülő sablonnal rendelkező elrendezéseket kompatibilisként vannak kezelve az elrendezésváltások során. Ennek megfelelően a lapok elrendezését ugyanabból a sablon-hierarchiából származó másik elrendezésre lehet módosítani, anélkül, hogy újra létre kellene hozni a lapszintű tartalmat. Ezt a lehetőséget kihasználhatja az időszakos tervezési frissítésekhez, kísérletekhez, illetve a webhely tartós áttervezéséhez. Másodszor: az elrendezések egy másik módot kínálnak egy lapcsoport közös elemeit központi módosítására, anélkül, hogy az egyes lapokat frissíteni kellene. Ha például egy termékkategória olyan 1 000 lapot tartalmaz, amelyek ugyanazt az elrendezést használják, akkor a modulok az elrendezésben is átrendezhetők és a módosítás azonnal megjelenik mind az 1 000 származtatott lapon.

Ezen hierarchia megértésével egy agilis és hatékony webhely-szerkezetet állíthat be, amely elősegíti a költségtakarékosságot, méretezhető, és jobb eredményeket biztosít, ahogy a webhely idővel fejlődik.

### <a name="preset-and-custom-layouts"></a>Előre beállított és egyéni elrendezések

A webhely elrendezései lehetnek *előre beállítottak* vagy *egyéniek* is:

- Az **előre beállított** elrendezések lehetővé teszik olyan laplétrehozási munkafolyamat alkalmazását, ahol az összes modul ki van választva és el van rendezve, és csak az adatbevitel szükséges. Ezen módszer segítségével időt takaríthat meg, ha sok lapot olyan kell létrehozna, amelyeknek ugyanazok az elrendezési követelményei. Az előre beállított elrendezések egy-a-többhöz kapcsolatban állnak a származtatott lapokkal. Emiatt egyetlen előre beállított elrendezéssel lehet központilag vezérelni a modulok elrendezését több száz vagy több ezer származtatott oldalra vonatkozóan.
- Az **Egyéni elrendezések** lényegében egyszer használatos elrendezések, amelyeket egyetlen lapra ágyaznak be. Nem jelennek meg a beállításként, ha más új lapok jönnek létre, illetve elrendezés-váltási szituációkban sem. Ennek a megközelítésnek az az előnye, hogy egy szerző egy egyéni elrendezést használó lap létrehozásával kísérletezhet. Ezt követően, ha a szerző újra fel szeretné használni az elrendezést más oldalakra, akkor egyszerűen konvertálható előre beállított elrendezéssé. Az új előre beállított elrendezést a program az ugyanabból a sablon-hierarchiából származó lapok esetében, valamint az elrendezési váltási forgatókönyvekben beállításként elérhetővé teszi. Ez fordítva is működik, tehát az előre beállított elrendezések leágaztathatók egyéni elrendezésekhez. Ily módon a szerző leválaszthatja a lapot az előre beállított elrendezésből, és új, egyszer használatos egyéni elrendezést hozhatnak létre. (Ez az új egyéni elrendezésre továbbra is vonatkoznak a szülő weboldal korlátozásai.)

Az előre beállított elrendezések és az egyéni elrendezések a szerkesztési eszköztár különböző részein szerkeszthetők. Mivel az egyéni elrendezések nem rendelkeznek függőségekkel más lapokon, közvetlenül a lap szerkesztőjében szerkeszthetők. Ebben az esetben transzparens leginkább az elrendezés megléte a felhasználó számára, és csak a lapszintű tulajdonságokban és az elrendezési beállításokon keresztül érhető el. Mivel azonban az előre beállított elrendezések módosításai hatással lehetnek a származtatott elemekre, az elrendezésszerkesztőben kell azokat szerkeszteni, ahol a közzétételi műveletek figyelembe veszik a lefelé irányuló, a származtatott oldalakra gyakorolt hatásokat.

A következő ábrák az előre beállított és az egyéni elrendezések eseteit mutatják be.

![Előre beállított és egyéni elrendezési szituációk.](../commerce/media/template-figure1.png)

Az előre beállított elrendezések használatához lásd: [Az előre definiált elrendezésekhasználata](work-with-layouts.md).

## <a name="additional-resources"></a>További erőforrások

[Sablonok használata](work-with-templates.md)

[Előre beállított elrendezések használata](work-with-layouts.md)

[A közzétételi csoportokkal végzett munka](publish-groups.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]