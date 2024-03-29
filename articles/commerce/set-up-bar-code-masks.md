---
title: Vonalkódmaszkok beállítása
description: Ez a témakör azt ismerteti, hogyan lehet beállítani vonalkódmaszk-karaktereket, vonalkódmaszkokat, és hogyan lehet vonalkódmaszkokat vonalkódhoz rendelni.
author: BrianShook
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailBarcodeMaskCharacter, RetailBarcodeMaskSetup
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.custom: 265994
ms.assetid: 5831c74d-d2a1-4fa5-9a9a-a5aba8848381
ms.search.region: global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 97b490384cff27c60191a87dc623eb6a2ef868f0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853712"
---
# <a name="set-up-bar-code-masks"></a>Vonalkódmaszkok beállítása

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet beállítani vonalkódmaszk-karaktereket, vonalkódmaszkokat, és hogyan lehet vonalkódmaszkokat vonalkódhoz rendelni.

## <a name="set-up-bar-code-mask-characters"></a>Vonalkódmaszk-karakterek beállítása

A vonalkódmaszkok vonalkódok létrehozására és a pénztárnál beolvasott vonalkódok gyors azonosítására használhatók. A maszkok olyan karakterekből állnak, amelyek helyőrzőként szolgálnak, és kijelölik a létrehozandó vonalkódok formátumát. Vonalkódmaszk konfigurálásához be kell állítania a vonalkódmaszk-karaktereket. Lépjen a **Retail és Commerce** &gt; **Készletgazdálkodás** &gt; **Vonalkódok és címkék** &gt; **Maszkkarakterek** ponthoz. Új vonalkódmaszk-karakterek létrehozásához kattintson az **Új** gombra. Maszkkarakterek a következő vonalkódadatok jelölésére hozhatók létre .

| Mező            | Leírás |
|------------------|-------------|
| Termék          | Helyőrző a termékazonosító számára. |
| Bármely szám       | A vonalkódok véglegesen kódolt számának megadásához használatos. |
| Ellenőrző számjegy      | Azt jelzi, hogy egy vonalkódmaszkvonalkód formátuma ellenőrző számjegyet használ a vonalkód érvényességének megerősítésére. |
| Méret számjegy       | Egy méretet jelez egy olyan vonalkódnál, amely méretet tartalmazó termékváltozathoz készült. |
| Szín számjegy      | Egy színt jelez egy olyan vonalkódnál, amely színt tartalmazó termékváltozathoz készült. |
| Stílus számjegy      | Egy stílust jelez egy olyan vonalkódnál, amely méretet tartalmazó termékstílushoz készült. |
| EAN-licenckód | EAN-licenckódok számára kiállított EAN-licenc helyőrzője. |
| Ár            | Az árat jelzi az árat beépítetten tartalmazó vonalkódoknál. |
| Mennyiség         | A mennyiséget jelzi a mennyiséget/véletlenszerű súlyút beágyazottan tartalmazó vonalkódoknál. |
| Alkalmazott         | Az alkalmazott azonosítószámának vonalkódszegmensét jelzi a vonalkódos pénztári bejelentkezésnél. |
| Vevő         | Az ügyfélazonosító szegmensét jelzi. |
| Adatbevitel       | *Még nincs megvalósítva.* |
| Engedmény kódja    | *Elavult* a Dynamics 365 for Retail 2017 tavaszi kiadása óta. Korábban: Olyan vonalkód engedménykódját jelzi, amellyel engedményt adna egy pénztári tranzakcióhoz. |
| Utalványkód      | Olyan vonalkód engedménykódját jelzi, amelynek segítségével engedményt lehet hozzáadni egy rendeléshez. Ez lépett az engedménykód helyébe. |
| Ajándékutalvány        | Az ajándékutalvány számát jelzi, ha ajándékutalványt ad ki, vagy azzal fizet. |
| Hűségkártya     | Hűségkártyával rendelkező ügyfél hozzáadása egy tranzakcióhoz – később a hűségkártyával való fizetéseknél használható. |

## <a name="define-bar-code-masks"></a>Vonalkódmaszkok meghatározása

Miután megadta a vonalkódmaszk-karaktereket a szükséges vonalkódmaszkok számára, menjen a **Retail és Commerce** &gt; **Készletgazdálkodás** &gt; **Vonalkódok és címkék** &gt; **Vonalkódmaszk beállítása** ponthoz. Ezen az oldalon olyan vonalkódmaszkokat adhat meg, amelyek a korábban megadott karaktereket használják. Ezeket a vonalkódmaszkokat a vonalkódok generálásakor használja a rendszer, és segítenek azonosítani a pénztárban beolvasott vonalkódokat is.

1. Új vonalkódmaszk létrehozásához kattintson az **Új** gombra.
2. Adja meg az értékeket a **Maszkazonosító** és a **Leírás** mezőkben, and majd válassza ki a vonalkódmaszk típusát a **Típus** mezőben.
3. Az **Általános** szakaszban válasszon ki egy értéket a **Vonalkódszabvány** mezőben, majd adja meg a vonalkód előtagját, amennyiben szükséges.
4. A **Vonalkódmaszkszegmens** résznél adjon hozzá olyan vonalkódszegmenseket, amelyeket a létrehozandó vonalkódban fog használni.

Például, egy „Termék” maszkazonosítójú vonalkódmaszk létrehozásához a következőket kell tennie:

1. Hozzon létre egy új vonalkódmaszkot, és válassza ki a „Termék” típust.
2. Válasszon ki egy vonalkódszabványt, például a „Kód: 39” lehetőséget.
3. Adjon meg egy előtagot a vonalkód egyszerű azonosításához. Például „22”.
4. Adjon meg egy maszkszegmenst. A „Termék” maszkszegmens lesz kijelölve.
5. Adjon meg egy hosszúságot a termékszegmenshez, például „10”. A hosszúságnak meg kell egyeznie az üzletnél általánosan használt termékazonosító hosszúságával. A maszk előnézetként jelenik meg az **Általános** szakaszban, a **Maszk** alatt.

## <a name="assign-bar-code-masks-to-bar-codes"></a>Vonalkódmaszkok társítása vonalkódokhoz

A vonalkódokmaszkokat hozzá kell rendelni vonalkódokhoz ahhoz, hogy használni lehessen őket. Az előző példánál maradva, a vonalkódmaszk vonalkódhoz történő hozzárendeléséhez tegye a következőket:

1. Lépjen a **Szervezetadminisztráció** &gt; **Beállítás** &gt; **Vonalkódok** menüpontba. Új vonalkód létrehozásához kattintson az **Új** gombra.
2. Adjon meg értékeket a **Vonalkód** **beállítás** és a **Beállítás** mezőkben.
3. Az **Általános** szakaszban, a **Vonalkódtípus** mezőben válassza ki a „Kód: 39” lehetőséget. A **Maszk** **azonosító** mezőben válassza ki a korábban létrehozott „Termék” maszkot.
4. A **Méret** beállításnál adja meg a „12” értéket.
5. Kattintson a **Mentés** gombra.

A vonalkódmaszk mostantól a termékek vonalkódjainak létrehozására használható. A fenti lépések példák arra, hogyan hozhat létre vonalkódmaszkokat a termékek számára, de bemutatják azt is, hogyan hozhat létre vonalkódmaszkokat bármely más támogatott vonalkódtípushoz. A vonalkódmaszkokat, -típusokat és -hosszokat az adott környezetéhez kell igazítania.


[!INCLUDE[footer-include](../includes/footer-banner.md)]