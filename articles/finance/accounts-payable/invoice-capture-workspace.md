---
title: Számlarögzítési megoldás munkaterülete
description: Ez a cikk a Számlarögzítés megoldás munkaterületről nyújt tájékoztatást.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4f3af7abf94542437be6132344d6bb7ffaf33d07
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690988"
---
# <a name="invoice-capture-solution-workspace"></a>Számlarögzítési megoldás munkaterülete

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="side-by-side-viewer-for-the-invoice-capture-solution"></a>Egymás mellett megjelenítő a Számlarögzítés megoldáshoz

A számlák rendszerbe történő bevitele jellemzően időigényes folyamat, amely hibákhoz vezethet, mivel a adminisztrátorok csak akkor gyűjtik össze a megfelelő információkat, ha több mellékletfájlt és ablakot is el kell navigálniuk. A oldali dokumentummegjelenítő jobb felhasználói élményben lesz része a számlákon való munkának, azáltal, hogy egyszerűbbé, hatékonyabbá és pontosabbra teszi a folyamatot.

Az egymás mellett megjelenítő dokumentummegjelenítő segítségével a felhasználók egymás mellett megtekinthetik az eredeti dokumentumot és a számlát. A számlaoldal az eredeti számladokumentumból származó adatokkal van megtöltve. A megjelenítő építi fel a kapcsolatot a számlaoldal mezői és az eredeti számladokumentum között. A megjelenítő a számlaoldalon talált hibák megkeresését is segíti.

### <a name="open-the-side-by-side-viewer"></a>A tekintő megnyitása

A Microsoft Dynamics 365 Pénzügyben az összesítő lapon vagy a számlalistaoldalon található listából meg lehet nyitni az egymás mellett megjelenítő megjelenítőt. Meg is nyithatja úgy, hogy duplán kattint egy rekordra,vagy duplán kattint a rekordra, vagy kiválasztja a számlaszámot.

### <a name="using-the-side-by-side-viewer"></a>A tekintőoldal használata

#### <a name="manually-review-an-invoice"></a>Számla manuális áttekintése

Az importált számladokumentumokat hibák vagy figyelmeztetések miatt manuálisan kell áttekinteni. A tekintőben a **dokumentumfejlécben** az Importált állapot fog jelenni, és az aktuális verzió az Eredeti **verzió lesz**.

Ha el kell kezdeni a számla áttekintését, válassza az Ellenőrzés **kezdete lehetőséget**. Minden mező szerkeszthetővé válik. Az **Állapot** mező módosítva az **Ellenőrzés** **·**, az Aktuális verzió mezőben pedig a **Módosított verzióra.**

#### <a name="view-and-work-with-messages"></a>Üzenetek megtekintése és a velük való munka

A felhasználóknak az üzenetpanelről kell elindítani az áttekintési folyamatot. A hibaüzeneteket piros X, a figyelmeztető üzeneteket háromszög, a tájékoztató üzeneteket pedig egy kör jelzi. A megbízhatósági pontszámhoz kapcsolódó üzenetek a konfigurációs csoportban beállított küszöbértéktől függően figyelmeztetésként vagy hibaként is besorolhatóak. A további tudnivalókat lásd [a Számlarögzítési megoldás konfigurációs csoportjaiban](invoice-capture-config-group.md).

A figyelmeztetéseket és hibaüzeneteket figyelmen kívül lehet hagyni az üzenetablakból, a számlafejlécből vagy a számlasorból. Ha egy üzenetet figyelmen kívül hagy, az üzenet nem jelenik meg hibaüzenetként vagy figyelmeztetésként, és a számla nem fog leállni az ellenőrzésen.

- Ha figyelmen kívül hagyja az üzenetpanelen látható üzeneteket, válassza a Kihagyás **lehetőséget**. A figyelmen kívül hagyott üzenetek alaphelyzetbe állításhoz válassza újra a Kihagyás **lehetőséget**. A típus ekkor hibáról vagy figyelmeztetésről információra változik.
- Ha figyelmen kívül hagyja a számlafejlécből vagy a számlasorból származó üzeneteket, válassza a Figyelmen kívül **hagyás** a mezőben lehetőséget. Az üzenetszimbólum eltűnik. Azonban akkor jelenik meg, ha az üzenet visszaáll az üzenetpanelről.

A számla fejlécmezőivel kapcsolatos üzenetek esetén, amikor az üzenetpanelen kiválasztja az üzenetet, a kurzor a fejlécszakasz megfelelő mezőjébe megjelenik.

#### <a name="proofread-and-edit-fields"></a>Lektorált és szerkesztett mezők

Ha egy mező értékét az eredeti számlából az optikai karakterfelismerési (OCR) karakterfelismerés segítségével olvassa be, akkor a mezőben egy szimbólum jelenik meg. Ha kiválasztja a szimbólumot, a dokumentummegjelenítő nagyításban segít a számlaadatok ellenőrzésében, és kijelöli azt a helyet, amelyből a mező értékét beolvassa.

A dokumentummegjelenítő eredeti nagyításra való visszaállításához hajtsa végre a következő lépések valamelyikét:

- Válassza ki ugyanazt a szimbólumot, amelyet korábban kiválasztott.
- A dokumentummegjelenítő jobb felső sarkában látható gomb kiválasztása.

A mezők szükség szerint szerkeszthetők. A program automatikusan menti a módosításokat, amikor a kurzor kilép egy mezőből. A mező jobb látható szimbóluma azt jelzi, hogy a mezőt manuálisan frissítették. Az oldal frissítése után a program eltávolítja a szimbólumot.

#### <a name="check-an-invoice-to-get-up-to-date-messages"></a>Számla ellenőrzése a naprakész üzenetek fogadása

Mező szerkesztésekor a mező értéke frissül, de új ellenőrzési üzenetek nem jönnek létre. Ha naprakész az ellenőrzési üzenetekről, válassza a Csekk **lehetőséget**. A program frissíti az üzenetpanelen, a számlafejlécben és a számlasorok üzeneteit.

#### <a name="complete-the-review"></a>Az ellenőrzés befejezése

Az ellenőrzés befejezéséhez válassza a Teljes **ellenőrzés lehetőséget**. A rendszer ellenőrzi a számlákat. Ha bármilyen hiba történik, a dokumentum állapota ellenőrzésen **marad**, és megjelenik egy üzenetsáv. Az üzenetpanelen, valamint a számla fejlécében és sorában található összes üzenet automatikusan frissül, hogy tájékoztatást nyújtson a sikertelen érvényesség-ellenőrzés okairól.

Miután az összes blokkolási hibát kijavította, az ellenőrzés végretehet egyezést. A dokumentum állapota Ellenőrzésre **módosul**, és a mezők többé nem szerkeszthetők. Az ellenőrzés újraindításához válassza újra az **Ellenőrzés kezdete** gombot.

#### <a name="generate-a-pending-vendor-invoice-in-finance"></a>Függőben lévő szállítói számla létrehozása a Pénzügyben

Ha a számladokumentumot a kapcsolódó pénzügyi környezetbe kell elküldeni, válassza a Generálás **lehetőséget**. Ha nem sikerül a számla létrehozása, egy hibaüzenet jelenik meg az üzenetsávon.

#### <a name="void-an-invoice"></a>Számla érvénytelenítése

Számla érvénytelenítéshez válassza az Érvénytelenítés **lehetőséget**. Az érvénytelenített számlákat nem lehet áttekintani, **és nem jelennek meg a Számlák kézi áttekintő** listában.

### <a name="validation-logic"></a>Ellenőrzési logika

Az oldali megjelenítő egyes kulcsmezői nem léteznek a számla-előkészítési adatokban, de a pénzügyben a függő számlák létrehozásához szükségesek. Ezek a mezők az aktuális számla-előkészítési adatok és a Pénzügy területről származó alapadatok kombinációjából származnak.

A származtatott mezők a jogi személy, **a** **szállítói** számla és a cikkszám **.** A következő sorrendben kell származtatni őket. Ha egy mező származtatása sikertelen, a folyamat leáll.

1. **Jogi személy** – a jogi személy elsőként van származtatással. Ha a jogi személyhez aktív hozzárendelési szabály található, akkor a jogi személy származtatása a vállalat neve és a vállalat címe alapján történik.
2. **Szállítói** számla – ezután a szállítói számla egy aktív hozzárendelési szabály, valamint a származtatott jogi személy, a szállító neve és a szállítói cím kombinációja alapján származtatott.
3. **Cikkszám** – végül a cikknév az előkészítésből származik, az alábbi háromféle információtípus alapján:

    - Konfigurált hozzárendelési szabály
    - A származtatott jogi személy
    - A származtatott szállítói számla

Ellenőrzés futtatásához válassza a Ellenőrzés **stb**. lehetőséget a tekintőben. Az ellenőrzés jelenleg a következő ellenőrzéseket végzi:

- **Kötelező ellenőrzés** – ez az ellenőrzés ellenőrzi az egymás mellett megjelenítő megjelenítő kötelező mezőit. A felhasználók kiválaszthatja, hogy mely mezők kötelezőek a Konfiguráció **beállítási lapján**.
- **Megbízhatósági pontszám** – a felhasználók beállíthatja a figyelmeztetési küszöbértéket és a hibahatárt a megbízhatósági pontszámra. Ez az ellenőrzés a küszöbértékek alatti OCR-től származó megbízhatósági pontszámra fókuszál. Az ellenőrzés eredménye alapján hibaüzenetek vagy figyelmeztetések jelennek meg.
- **Jogi személy** – ez az ellenőrzés azt ellenőrzi, hogy a jogi személy a Pénzügyben van-e. Ha a jogi személy nem létezik a pénzügyi környezetben, az ellenőrzés sikertelen lesz.

Ha az egymás mellett megjelenítőt első alkalommal használják, **és** a felhasználó a Csekk lehetőséget választja, akkor a származtatási és ellenőrzési folyamatok lefutnak. Ha a számlák pontosak, akkor az ellenőrzési folyamat akkor fut le, amikor a felhasználó a Teljes ellenőrzés lehetőséget **választja**. Akkor is lefut, ha a felhasználó a Szállítói számla **létrehozása lehetőséget választja**.

A származtatási folyamat az ellenőrzési folyamat előtt történik, és minden figyelmeztetés vagy hiba az ellenőrzési folyamatból jön. A rendszer naplózza a figyelmeztetéseket és a hibákat a Pénzügy naplóban.
