---
title: A Modern POS (MPOS) bemutató adatképernyő-elrendezései
description: Ez a cikk a pénztári tapasztalatok bemutató adathalmazában szereplő képernyőelrendezésekkel kapcsolatban tartalmaz tájékoztatást Dynamics 365 Commerce.
author: josaw1
ms.date: 10/05/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailTillLayout
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2017-10-05
ms.dyn365.ops.version: Retail April 2017 update
ms.openlocfilehash: eb7a288b61e8b467dd8ad6a8f7dc42b7fca0d943
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897225"
---
# <a name="demo-data-screen-layouts-in-modern-pos-mpos-and-cloud-pos"></a>A Modern POS (MPOS) bemutató adatképernyő-elrendezései

[!include [banner](includes/banner.md)]

Ez a cikk a pénztári tapasztalatok bemutató adathalmazában szereplő képernyőelrendezésekkel kapcsolatban tartalmaz tájékoztatást Dynamics 365 Commerce.

## <a name="overview"></a>Áttekintés

Bemutató adatokhoz mellékelt Commerce minta képernyő-elrendezések különböző kiskereskedelmi szegmensekhez, áruházi dolgozói szerepkörökhöz és eszközökhöz optimalizált tartalmakat nyújtanak. Egyetlen elrendezés több elrendezésméretet és gombrácsok kombinációit tartalmazhatja, a fedezet biztosítása érdekében, miközben a dolgozók az eszközök és az állomások között mozognak. Ez a cikk be összefoglalja az elrendezések közötti különbségeket, a nekik megfelelő műveleteket és az általános tapasztalatokat.

![Párhuzamos eszközök bemutatóadat-elrendezései.](../commerce/media/demo-screen-layouts-fig-1-1.png)

## <a name="anatomy-of-a-screen-layout-id"></a>Képernyő-elrendezés azonosítójának szerkezete

A képernyő-elrendezések megkereséséhez kattintson a **Retail és Commerce** \> **Csatorna beállításai** \> **POS-beállítás** \> **POS** \> **Képernyő-elrendezések** lehetőségre.

![Képernyő-elrendezések oldal.](../commerce/media/demo-screen-layouts-fig-2-1.png)

A képernyő-elrendezés azonosítója legfeljebb 10 karaktert tartalmazhat. Az azonosító karakterlánc, amely három különböző adatot tartalmaz, a következő sorrendben:

1. Cég
2. Elrendezésverzió
3. Személyiség

### <a name="company"></a>Cég

| Levél | Cég         |
|--------|-----------------|
| A      | Kalandorbolt |
| G      | Gyár        |
| t      | Contoso         |

### <a name="layout-version"></a>Elrendezésverzió

| Verziószám | Leírás                                                                                |
|----------------|--------------------------------------------------------------------------------------------|
| 3              | A többféle eszközhöz és oldalarányhoz több képernyőméretet támogató alapverzió |
| 3.1            | Az alapverzió, amely további támogatást nyújt a **Javasolt termékek** panelhez        |
| 4              | A kiterjesztett változat a kiterjesztett Fabrikam frissített elrendezéshez                                  |

### <a name="persona"></a>Személyiség

| Rövidítés | Személyiség       | Tartalom |
|--------------|---------------|----------|
| CSH          | Pénztáros       | A pénztáros elrendezések minden tranzakciókkal kapcsolatos műveletet tartalmaznak, például a vevői rendeléseket, visszaküldéseket, engedmények, érvénytelenítéseket és ajándékutalványokat. Ezek az elrendezések a készletkezelés, például az árellenőrzés, a készletkeresések és leltározás napi feladatait is magukban foglalják. Alapvető műszakkezelés is rendelkezésre áll a következőkhöz: kezdő összegek, műszakok felfüggesztése és blokkolóóra. |
| MGR          | Üzletvezető | Az üzletvezető elrendezések minden tranzakciókkal kapcsolatos műveletet magukban foglalnak, amelyek a pénztáros elrendezésekben találhatók, és az adófelülírásokat is tartalmazza. Ezek az elrendezések a készletkezelés, például az árellenőrzés, a készletkeresések és leltározás napi feladatait is magukban foglalják. Műszakkezelés is rendelkezésre áll a következőkhöz: indítás, felfüggesztés és a műszak lezárása. Ezenkívül az elrendezések a bejegyzések, eltávolítások, fizetőeszköz-elszámolások és széf és banki műveletek pénztárgépfiókkal kapcsolatos műveleteit is tartalmazza. Végül ezek az elrendezések hozzáférést nyújtanak a teljesítményre vonatkozó jelentésekhez, és kinyomtathatóvá teszik az X és Z-jelentéseket. |
| STK          | Készletadminisztrátor   | A készletadminisztrátor elrendezések a készletkezelésre vannak optimalizálva. Tartalmazzák a napi feladatokhoz való hozzáférést az árellenőrzésekhez, a készletkeresésekhez, a kitároláshoz és a bevételezéshez, a leltározáshoz és csomagok szétszereléséhez. Ezek az elrendezések alapvető műszakműveleteket is kínálnak a blokkolóórához és a műszakok felfüggesztéséhez. Annak ellenére, hogy ezeket az elrendezéseket elsősorban háttérirodai feladatokra szánják, a készletadminisztrátorok ugyanazokat a műveleteket hajthatják végre, mint a pénztárosok a tranzakció képernyők esetében. |

### <a name="example-layout"></a>Példa elrendezés

Íme egy példa, a Gyár vállalat képernyőelrendezés-azonosítója, 4-as elrendezésverzió, az üzletvezető személyiséggel:

F4MGR

A következő ábrán a Gyár üzletvezetőjének üdvözlőképernyője látható.

![A Fabrikam üzletvezetőjének üdvözlőképernyője.](../commerce/media/demo-screen-layouts-fig-2-2.png)

## <a name="layout-sizes"></a>Elrendezési méretek

### <a name="full-vs-compact-layouts"></a>Teljes és kompakt elrendezések összehasonlítása

A képernyő-elrendezés konfigurációkat tartalmazhat a teljes és kompakt eszközök számára. Ezért a felhasználó hozzárendelhető egyetlen képernyő-elrendezéshez, amely a különböző méretek és formátumok mindegyikén működik az üzletben.

- **Modern POS - teljes** - A teljes elrendezések általában a nagyobb kijelzők esetén használhatók a legjobban, például az asztaliszámítógép-monitorokon vagy a táblagépeken. A felhasználók kiválaszthatják a felhasználóifelület-elemeket, amelyeket az elrendezés tartalmaz, megadhatják az elemek méretét és elhelyezését, és konfigurálhatják a részletes tulajdonságaikat. A teljes elrendezések az álló és a fekvő konfigurációkat egyaránt támogatják.
- **Modern POS – kompakt** - A kompakt elrendezések általában a telefonokhoz és kis táblagépekhez használhatók a legjobban. A tervezési lehetőségek korlátozottak a kompakt eszközök esetében. A felhasználók beállíthatják az oszlopokat és a mezőket a bevételezés és az összegek panelekhez.

### <a name="screen-resolutions-that-are-provided"></a>A biztosított képernyőfelbontások

Az alábbi táblázat bemutatja a jellemző képernyőfelbontásokhoz rendelkezésre bocsájtott elrendezésméreteket.

| Elrendezés típusa | Feloldás | Képarány | Cél kijelző          |
|-------------|------------|--------------|-------------------------|
| Tömörítés\*   | 480 × 853  | 16:9         | Telefonok                  |
| Teljes        | 1024 × 768 | 4:3          | Táblagépek                 |
| Teljes\*      | 1280 × 720 | 16:9         | Táblagépek                 |
| Teljes        | 1366 × 768 | 16:9         | Táblagépek, nagyobb képernyők |
| Teljes        | 1440 × 960 | 3:2          | Táblagépek, nagyobb képernyők |
| Teljes\*      | 1536 × 864 | 16:9         | Táblagépek, nagyobb képernyők |

\*Ezek a további elrendezési méretek csak a Kalandorbolt és a Gyár elrendezésekben érhetők el.

> [!TIP]
> A pénztár automatikusan kiválasztja az elrendezésméreteket, az aktuális alkalmazásablak képernyőfelbontásához elérhető legközelebbi méret alapján. A jelenleg használt képernyőelrendezés-azonosító és elrendezésfelbontás megkereséséhez a Modern POS (MPOS) vagy Retail Cloud POS (CPOS) esetében nyissa meg a **Beállítások** oldalt, majd tekintse meg a **Munkamenet adatai** szakaszt. A jelenlegi alkalmazás vagy böngészőkeret tényleges ablakfelbontása is megtekinthető. Ezeket az adatokat begyűjtve az elrendezéstartalom forrásának megkereséséhez menjen a **Csatorna beállítása** \> **POS beállítása** \> **POS** \> **Képernyő-elrendezések** menübe.

![Képernyő-elrendezések és elrendezésfelbontások/méretek a Commerce és a POS esetében.](../commerce/media/demo-screen-layouts-fig-3-1.png)

## <a name="companies-and-brands"></a>Vállalatok és márkák

Minden fiktív vállalat eltérő kiskereskedelmi szegmenst céloz, és termékkatalógusokat tartalmaz, amelyet a vállalat piacához vannak beállítva. Minden vállalat rendelkezik egy egyedi vizuális márkával, amely a termékeire jellemző. A kiemelés színe, a sötét és a világos téma és a reális tapasztalatokat biztosító fényképek a márkaelemek közé tartoznak.

### <a name="company-segment-and-visual-characteristics"></a>Vállalati szegmens és vizuális jellemzők

| Cég         | Tárolóhely | Szegmens        | Kiemelés | Téma |
|-----------------|----------|----------------|--------|-------|
| Kalandorbolt | Seattle  | Sportcikkek | Kék   | Sötét  |
| Fabrikam        | San Francisco  | Divatáru        | Zöld  | Világos |
| Contoso         | Boston   | Elektronika    | Piros    | Sötét  |

> [!NOTE]
> A két főmárka a Kalandorbolt és a Gyár. A Contoso elérhető, de nem minden elrendezés áll rendelkezésre.

Az alábbi ábrákon a három fiktív vállalat üdvözlőoldalára és tranzakciós lapjára láthatók példák.

### <a name="adventure-works"></a>Adventure Works

![Bemutató adatok – az Adventure Works üdvözlőoldala.](../commerce/media/demo-screen-layouts-fig-4-1a.png)

![Bemutató adatok – az Adventure Works tranzakciós oldala.](../commerce/media/demo-screen-layouts-fig-4-1b.png)

### <a name="fabrikam"></a>Fabrikam

![Bemutató adatok – a Fabrikam üdvözlőoldala.](../commerce/media/demo-screen-layouts-fig-4-2a.png)

![Bemutató adatok – a Fabrikam tranzakciós oldala.](../commerce/media/demo-screen-layouts-fig-4-2b.png)

### <a name="contoso"></a>Contoso

![A Contoso bemutató adatelrendezései.](../commerce/media/demo-screen-layouts-fig-4-3.png)

## <a name="user-sign-in-matrix"></a>Felhasználói bejelentkezési mátrix

A különböző képernyő-elrendezésekhez felhasználókat is rendelkezésre bocsájtunk. Az alábbi táblázat használatával hozzáférhet a képernyők bármelyikéhez. Csak jelentkezzen be egy megfelelő operátorazonosítóval.

| Cég         | Képernyő-elrendezés azonosítója | Személyiség       | Operátorazonosító           |
|-----------------|------------------|---------------|------------------------|
| Kalandorbolt | A3MGR            | Üzletvezető | 000154, 000137, 000073 |
| Kalandorbolt | A3CSH            | Pénztáros       | 000150, 000175, 000165 |
| Kalandorbolt | A3STK            | Készletadminisztrátor   | 000155, 000181, 000152 |
| Fabrikam        | F4MGR            | Üzletvezető | 000160, 000713         |
| Fabrikam        | F3CSH            | Pénztáros       | 000161, 000113, 000114 |
| Fabrikam        | F3STK            | Készletadminisztrátor   | 000164, 000112, 000123 |
| Contoso         | C3MGR            | Üzletvezető | 000100, 000111         |
| Contoso         | C3CSH            | Pénztáros       | 000110, 000120         |
| Contoso         | Nem alkalmazható   | Készletadminisztrátor   | Nem alkalmazható         |

> [!TIP]
> A legjobb eredmények érdekében aktiváljon a megfelelő üzletben egy pénztárgépet, és a vállalatot annak a személyiségnek a vállalatára állítsa, amellyel be kíván jelentkezni. Ezzel a módszerrel segíthet garantálni, hogy vizuális profil és a márkázás egységes legyen a tapasztalat egészében. Például ha a pénztárosi elrendezést szeretné kipróbálni a Gyár esetében, aktiválnia kell egy pénztárgépet a houstoni üzletben.

<!-- Hiding until the content page is available on CustomerSource -->

<!-- ## Reference icons and images -->

<!-- The screen layouts, button grids, and visual profiles were created using images and icons that can be found in **Retail and Commerce \> Channel setup \> POS setup \> POS \> Images**. -->

<!-- ![Images in Dynamics 365 Commerce.](../commerce/media/demo-screen-layouts-fig-5-1.png) -->

<!-- Use the [POS Icon and Image Mapping](../commerce/media/POS_Icon_and_Image_Mapping.xlsx) reference spreadsheet to locate operation icons, reference photos, swap logos, or provide new images of your own that can be referenced in custom designs. -->

<!-- END HIDDEN CONTENT -->


[!INCLUDE[footer-include](../includes/footer-banner.md)]