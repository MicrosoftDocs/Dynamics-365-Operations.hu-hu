---
title: Számsorozatok konfigurálása raktári folyamatokhoz
description: Ez a témakör áttekintést nyújt azokról a funkciókról, amelyek számsorozat-bővítményeket biztosítanak az azonosítótábla-azonosítókhoz, a hullámcímke-azonosítókhoz, tárolóazonosítókhoz és a fuvarlevél-azonosítókhoz.
author: GarmMSFT
manager: tfehr
ms.date: 06/10/2020
ms.topic: configure-number-sequence-extensions
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSNumberSequenceExtension
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: 2512fc9b530530a9f82995a9eefcd59bbd518d96
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3975392"
---
# <a name="configure-number-sequences-for-warehouse-flows"></a>Számsorozatok konfigurálása raktári folyamatokhoz

[!include [banner](../includes/banner.md)]

A *számsorozat-bővítmények* funkció új konfigurációs lapot ad a Számsorozatok beállításához. Ez lehetővé teszi a GS1 által szabályozott azonosítók rugalmas konfigurálását, többek között a GS1-előtagokat és az ellenőrző számjegyeket (10. számú elem), valamint a meglévő Számsorozatokra hosszúsági korlátot alkalmaz.

A normál számsorozat-szegmensek nem alkalmasak a GS1 végrehajtására, mert nincs kiszámítva ellenőrző számjegy, és a vállalat GS1 előtagját manuálisan kell frissíteni.

Ez a funkciót következő képességeket adja hozzá:

- A fuvarlevél (BOL) azonosítóját előre lehet létrehozni.
- A rendszer egyedi számsorozatot hoz létre a szállítási tároló sorozatkódjának (SSCC) számaihoz.
- A GS1-nek megfelelő számsorozatok a BOL-és a SSCC-számokhoz is létrehozhatók. A funkció beépített támogatást ad hozzá az azonosítótábla-azonosítók, tárolóazonosítók, hullámcímke-azonosítók és BOL-azonosítók számára.
- Az azonosítótábla-azonosító számának konfigurálása rugalmas. Például felveheti vagy kizárhatja az alkalmazásazonosítókat (AI), például a kezdő nullákat (00).

Ez a funkció hatékonyabbá teszi a kartondobozok címkézését, és a rendszer által előállított új számok beállítását.

## <a name="turn-on-the-number-sequence-extensions-feature"></a>A számsorozat-bővítmények funkciójának bekapcsolása

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A funkció a következő módon jelenik meg:

- **Modul:** *Raktárkezelés*
- **Funkció neve:** *Számsorozat-bővítmények*

## <a name="set-up-the-feature"></a>A funkció beállítása

A rendszerben a számsorozat-bővítmények beállításához hajtsa végre az alábbi lépéseket.

1. Lépjen a **Raktárkezelés \> Beállítás \> Raktárkezelési paraméterek** részre.
1. Az **általános** lap **GS1 vállalati előtag** mezőjében, majd adja meg a vállalat GS1 előtagját. Ez az érték érinti az összes olyan számsorozatot, amelynél a GS1 előtag része egy szegmensnek.
1. Ha azt szeretné, hogy a program a hullámcímkékhez BOL-számokat generáljon, akkor a **jelentések** lapon jelölje be a **BOL-szám előállítása a hullámcímkék nyomtatásakor** jelölőnégyzetet.

    > [!NOTE]
    > Ez a jelölőnégyzet csak akkor érhető el, ha be van kapcsolva a [hullámcímke-nyomtatás](configure-wave-label-printing.md) funkció.

1. Lépjen a **Raktárkezelés** \> **Beállítás** \> **Számsorozat-bővítmények** pontra
1. A Műveleti ablaktáblán kattintson az **Alapértelmezett beállítás létrehozása** elemre. Létrejön egy GS1-kompatibilis BOL-számsorozat és három típusú SSCC-számsorozat. Ezek a számsorozatok figyelembe veszik a vállalat GS1-előtagjának hosszát.

    Az alapértelmezett számsorozatok testreszabásával és/vagy új sorozatok hozzáadásával kapcsolatos további tudnivalókat lásd a következő szakaszban. Ezeket a szekvenciákat akkor is eltávolíthatja, ha nincs rájuk szüksége.

1. Lépjen vissza a **Raktárkezelés \> Beállítás \> Raktárkezelési paraméterek** részre.
1. A **Számsorozatok** lapon válassza ki a megfelelő számsorozat-bővítményt, amellyel a azonosítótábla-azonosítók, a hullámcímke-azonosítój, tárolóazonosítók (ebben az esetben a megfelelő **SSCC-18 szám** sorozat) és/vagy a BOL-azonosítók (ebben az esetben a **BOL** - sorozat) számának létrehozásához használható. Alapértelmezés szerint a számsorozat-bővítmények csak az ilyen négyféle típusú azonosítók esetében támogatottak.

A következő alkalommal, amikor egy új szám jön létre a számsorozatok egyikéhez, a program az új logikát fogja használni.

> [!NOTE]
> Ha nem választja ki az azonosítótábla-azonosítók számsorozat-bővítményét, a rendszer az azonosítótábla-azonosítók létrehozásához használt jelenlegi szabályokat fogja használni. Ellenkező esetben a program a kiválasztott számsorozatot használja. A többi azonosító egyszerű számsorozatot fog használni addig, amíg meg nem alkalmaz rájuk számsorozat-bővítményt.

## <a name="create-and-edit-number-sequences"></a>Számsorozatok létrehozása és szerkesztése

Az előző részben létrehozta a számsorozatok alapértelmezett csoportját. Ez a szakasz bemutatja, hogyan kell definiálni az egyes számsorozatokat. Bemutatja az egyéni sorozatok létrehozását és az alapértelmezett vagy egyéni sorozatok szerkesztésének módját is.

A számsorozatok létrehozásához és szerkesztéséhez hajtsa végre az alábbi lépéseket.

1. Lépjen a **Raktárkezelés** \> **Beállítás** \> **Számsorozat-bővítmények** pontra.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A **számsorozat-bővítmény** mezőbe írja be az új sorozat nevét. Adjon meg egy leírást a **Leírás** mezőben.
1. Használja a **szegmensek** gyorslap eszköztárának gombjait a számozási formátum összeállításához a szegmensek hozzáadásával, törlésével és elrendezésével. A **Szegmens** mező mindegyik sorához társítson egy szegmens típust, hogy meghatározza a szegmens célját és tartalmát. Az alábbi táblázat ismerteti a választható szegmenstípusokat.

    | Szegmens típusa | Leírás |
    |---|---|
    | Állandó | Ez a szegmenstípus ugyanazt a konstans szöveget adja hozzá a sorban szereplő mindegyik létrehozott számhoz. Írja be a szükséges szöveget az **Érték** mezőbe. A **Hossz** mezőt a program automatikusan frissíti az **érték** mezőben megadott szöveg hosszára. |
    | Számsorozat | Az **érték** mezőbe írjon be egy számjelet ( *\#* ) az egyes karakterekhez, amelyeket a létrehozott sorrendben kell megjeleníteni. A számsorozat maga hosszabb számokat is létrehozhat, de csak a leginkább jobb oldali karakterek jelennek meg. A **Hossz** mezőt a program automatikusan frissíti az **érték** mezőben megadott számjelek számára.<p>Ha meg szeretne felelni az SSCC-18 számokra vonatkozó GS1-követelményeket, győződjön meg arról, hogy a szegmens hossza 16 mínusz a GS1-előtag hossza.</p> |
    | GS1-előtag | Ez a szegmens típus hozzáadja a **raktárkezelési paraméterek** lap **GS1 Company előtag** mezőjében megadott értéket. Az **Érték** mező a **Raktárkezelési paraméterek** lapon megadott értéket jeleníti meg , a **Hossz** mező pedig az érték karaktereinek számát. Mind az **Érték** mező, mind a **Hossz** mező írásvédett. |
    | Alkalmazásazonosító | Az **érték** mezőbe írja be az alkalmazás azonosítóját, amelyet a megfelelő GS1-irányelv határoz meg az ilyen típusú számsorozathoz. Írja be például a *00* értéket az SSCC esetén vagy a *420* értéket a BOL esetében. A **Hossz** mezőt a program automatikusan frissíti az **érték** mezőben megadott azonosító hosszára. |
    | Csomagolási típus | Az egyértelműen azonosítható cikkek esetében ez a szegmenstípus mezőértéket ad hozzá a megfelelő egységszekvencia-csoportból (az **Egységszekvencia-csoportok** lapról). (Ez a viselkedés megfelel az azonosítótábla-azonosítók meglévő logikájának.) A több raktározási egységet (SKU) tartalmazó azonosítótábla esetében ez a szegmenstípus alapértelmezés szerint *0* (nulla) értéked ad hozzá. Ehhez a szegmenstípushoz az **Érték** mező értéke mindig *P* , a **Hossz** mező értéke pedig mindig *1* .|
    | Ellenőrző számjegy | Ez a szegmenstípus egy ellenőrző számjegyet ad hozzá, amely a 10. számú maradékszámítás. (Ez a viselkedés megfelel az azonosítótábla-azonosítók meglévő logikájának.) Ehhez a szegmenstípushoz az **Érték** mező értéke mindig hiányjel ( *^* ), a **Hossz** mező értéke pedig mindig *1* . |

1. Ha meg szeretne tekinteni egy példát a végső számformátumra, tekintse át a **Szegmensek** gyorslap alján található **Formátum** mezőt.
