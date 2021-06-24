---
title: Pénzügyi konszolidáció és pénznemátváltás áttekintése
description: Ez a témakör leírja a pénzügyi konszolidálási és devizaátváltási tranzkaciókat a főkönyvben.
author: aprilolson
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 87bb31d6456356342773f38699a412aa72ea458e
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193905"
---
# <a name="financial-consolidations-and-currency-translation-overview"></a>Pénzügyi konszolidáció és pénznemátváltás áttekintése

[!include [banner](../includes/banner.md)]

Ez a témakör végigvezeti Önt a megközelítésen, amely mind a Microsoft Dynamics 365 Finance és pénzügyi jelentéskészítés a konszolidációhoz használt. Leírja, kapcsolódó többvállalatos jelentéskészítéssel, összesítéssel, eltávolítással és kisebbség kamattal kapcsolatos eseteket. Azt is bemutatja, hogyan kezelje a különleges helyzeteket, például ha jogi személyek különböző pénzügyi időszakokkal vagy a számlatükörrel rendelkeznek.

Ez a témakör a felhasználók és működési tanácsadók számára készült, és azt feltételezi, hogy olvasók általános ismeretekkel rendelkeznek a Pénzügy és pénzügyi jelentések terén. Az általános beállítások nincsenek bemutatva.

> [!NOTE]
> A *jogi személy* kifejezés a Finance esetében, míg a *vállalat* a Financial reportingban használatos. A témakör mindkét fogalmat használja. Azonban e témakör esetében azok jelentése megegyezik.

## <a name="audience"></a>Közönség
Ez a témakör a pénzüggyel és könyveléssel foglalkozó felhasználóknak és pályázati tanácsadóknak szól akik a Finance and Reporting és a Financial reporting eszközöket többvállalatos és többpénznemes adatokhoz szeretnék használni.

## <a name="approach"></a>Megközelítés
A Finance önálló jogi személyt használ a konszolidációs folyamatokhoz. Lehetővé teszi, hogy egyetlen-példányos konszolidációt de lehetővé teszi más forrásból származó adatok bevonását is. A konszolidációs folyamatot mindannyiszor kell futtatni, amikor módosítás történik a forrás jogi személynél.

Pénzügyi jelentések több vállalatot képes konszolidálni jelentés létrehozása során. Annak ellenére, hogy a data martban tárolt adatok verziókra vannak osztva és lehet exportálni is azokat, minden forrásvállalat, tulajdonosa és tárolója az adatoknak. A jelentés futtatható bármikor, akár percenként is (például). Számos további előnyt biztosít, például lehetséges leásni minden vállalathoz és dimenzióhoz is.

Felhasználók használhatják a Consolidate Online, Pénzügyi beszámolók eszközöket vagy azok kombinációját. A választás a vállalat szükségleteitől és a könyvvizsgálók igényeitől függ.

## <a name="consolidations"></a>Konszolidációk
A **Konszolidációk** modul több jogi személy konszolidálására kínál lehetőséget a konszolidálási folyamat során, és lehetővé teszi a vállalat mérlegének importálását vagy exportálásását. Beállíthat eltávolításokat és eltávolítás utáni naplókat is.

## <a name="benefits-of-using-consolidate-online"></a>Az Online konszolidálás használatának előnyei
A **Konszolidációk** modult használó ügyfelek számos előnyt élvezhetnek:

- **Adatok mélysége** –, Olyan összesített jelentéseket hozhat létre, amelyek a tényleges és költségvetési adatokat számlaszint és a dimenziószinten összesítik.
- **Dinamikus konszolidációk** – A Konszolidációk többször feldolgozhatók.
- **Könyvvizsgálati képességek** – A dimenziók és számlák elemzés és könyvvizsgálati célból fenn vannak tartva, és az egyenlegek dátum szerint vannak létrehozva.
- **Devizaátváltás** – Beállíthat számla-tartományokat és árfolyamokat forrásvállalat könyvelési pénzneme, és a konszolidációs vállalat könyvelési pénzneme közötti átváltáshoz.
- **Eltávolítások feldolgozása a konszolidált vagy eltávolítási vállalatban** – Az eltávolítások feldolgozása, és feladása egyetlen folyamatban történhet a konszolidáció során. Másik lehetőségként a javaslatot külön is futtathatja.

## <a name="supported-consolidation-scenarios"></a>Támogatott konszolidációs esetek
Az alábbiakban talál néhány konszolidációs esetet, amelyeket az Online konszolidálás támogat:

- Egyszintű konszolidáció jogi személyek között
- Eltávolításokkal járó konszolidációk
- Kisebbség részesedés (ebben az esetben a kézi számítást és bevitelt kell használni a vállalathoz.)
- Több számlatükör jogi személyek között
- Különböző pénzügyi naptárak több jogi személy között
- Több jelentési pénznemet tartalmazó konszolidációk

## <a name="legal-entity-setup"></a>Jogi személy beállítása
Mielőtt feldolgozná a konszolidációt, be kell állítania a jogi személyt. A konszolidációt tetszőleges számú alkalommal futtathatja és az összes adat át lesz váltva forrásvállalat könyvelési pénzneméről a konszolidációs vállalat pénznemére. Emiatt a következő szervezeti felépítés esetében, he először az összes Észak-Amerikai vállalatot át kel váltania amerikai dollárba (USD) majd euróba (EUR), a szülő vállalat pénznemébe, legalább két konszolidációs vállalat szükséges.

![Szervezeti felépítés](./media/organizational-structure.png "Szervezeti felépítés")

Az előző szervezeti felépítés esetében rendelkeznie kell egy jogi személlyel az Észak-amerikai konszolidációhoz mivel a konszolidáció során a konszolidáció mindig forrásvállalat könyvelési pénznemből a konszolidációs vállalat pénznemére történik. Ebben a példában, ha az összes vállalat egyetlen konszolidációba kerül, a Mexikói leányvállalat át lesz váltva mexikói pesóból (MXN) EUR-ba, és nem a MXN-ből USD-be, majd EUR-ba.

A jogi személy létrehozásakor megadhatja, hogy a vállalat használatos lesz, mind a konszolidációs folyamathoz mind az eltávolítási folyamathoz, vagy csak egy folyamathoz. Az alábbi példában a vállalat mindkét folyamathoz használva lesz. Fontos megjegyezni, hogy a konszolidált vállalatban nem adhat fel napi naplókat de feladhatja azokat az eltávolítási vállalatban. Ezért érdemes lehet egy külön eltávolítási vállalatot létrehoznia.

![A konszolidációhoz és az eltávolításhoz egyaránt használt jogi személy](./media/sep-elimination-company.png "A konszolidációhoz és az eltávolításhoz egyaránt használt jogi személy")

## <a name="main-accounts-and-consolidation-account-groups"></a>Fő számlák és konszolidációs számlacsoportok
Ki kell választania a Számlatükör konszolidációkának módját. Fő számlák konszolidálása során három lehetősége van a konszolidálási folyamat során.

Az első lehetőség , hogy a fő számlákat a forrásvállalatoktól használja. Ebben az esetben minden vállalat minden számlája konszolidálva lesz. Ha például a készpénz az USMF vállalat számláján 100000 és a DEMF vállalat esetében 1100, a konszolidációs vállalat mindkét számlát tartalmazni fogja. Minden számlának saját egyenlege lesz.

A mási lehetőség az alapértelmezett konszolidációs számla megadása a **Fő számlák** oldalon. A számlát ekkor hozzá lesz rendelve a konszolidációs számlához. Ez a beállítás akkor lehet hasznos, ha különböző számlatükrök vannak, illetve a központ által meghatározott számlatükröt kell hozzárendelni.

![A fő számlák lapon megadott alapértelmezett konszolidációs számla](./media/main-accounts.png "A fő számlák lapon megadott alapértelmezett konszolidációs számla")

A harmadik lehetőség a konszolidációsszámla-csoportok használata. Tetszés szerinti számú konszolidációsszámla-csoportot határozhat meg. Majd, a **További konszolidációs számlák** lapon csak leképezheti a fő számlát a számlatükörből, ahhoz a számlához, amelyre szüksége van a csoporthoz.

![Hozzárendelés a További konszolidációs számlák lapon](./media/additional-consolidation-accounts.png "Hozzárendelés a További konszolidációs számlák lapon")

## <a name="consolidating-online"></a>Online konszolidáció
Az online konszolidáció részleteinek megadásával kapcsolatosan lásd: [Online pénzügyi konszolidációk](./consolidate-online.md).

## <a name="managing-consolidation-transactions"></a>Konszolidációs tranzakciók kezelése
A konszolidáció eredményének megtekintésének többféle módja is van:

- Pénzügyi jelentés készítése a konszolidációs vállalatra nézva.
- Ellenőrizze a **Főkönyvi kivonat** listaoldalt a konszolidációs vállalatban+.
- Konszolidációs tranzakciók listájában a **Konszolidációk** oldalon megtekintheti a dátum szerint létrehozott egyenelegeket minden egyes forrásvállalathoz minden egyes időszakra.

    ![Konszolidációs tranzakciók a Konszolidációk oldalon](./media/managing-consolidation-transactions.png "Konszolidációs tranzakciók a Konszolidációk oldalon")

A Konszolidáció újrafuttatásához egyszerűen feldolgozhatja a konszolidációt. Azt is megteheti, hogy először kijelöli a **Tranzakciók eltávolítása** lehetőséget a **Konszolidációk** oldalon.
Abban az esetben, ha a konszolidált számlán szereplő egyenlegek nem pontosak, korrigálhatja őket a **Záró időszaki kiigazítások** lapon.

## <a name="consolidate-with-import"></a>Konszolidálás importálással
A Konszolidálás importálással funkció úgy működik, mint az Online konszolidálás funkció. Amikor kiválasztja a jogi személyeket, tallóz az adatokat tartalmazó forrásfájlhoz.

## <a name="export-company-balances"></a>Vállalati egyenlegek exportálása
A Vállalati egyenlegek exportálása funkció is úgy működik, mint az Online konszolidálás funkció. Amikor kiválasztja a jogi személyeket, látható a kimenet elérési útja.

## <a name="elimination-rules"></a>Eltávolítási szabályok
Vállalatközi tranzakciók eltávolításához, létrehozhat egy eltávolítási szabályt. Másik lehetőségként létrehozhat egy manuális eltávolítási manuális bejegyzés mely eltávolítási vállalatként van kijelölve. Ha létrehoz egy eltávolítási szabályt, akkor két lehetőség áll rendelkezésre az eltávolítás módjához: **Nettó változás** és **Rögzített**.

### <a name="set-up-elimination-rules"></a>Eltávolítási szabályok beállítása
Eltávolítási szabályok beállításakor a Finance alkalmazásban létrehozhat egy pénzügyi dimenziót kifejezetten eltávolítás céljából. A legtöbb ügyfél ezt a pénzügyi dimenziót **Kereskedelmi partnernek** vagy valami hasonlónak nevezi el. Ha úgy dönt, hogy nem használ pénzügyi dimenziókat, úgy ügyeljen, hogy rendelkezzen olyan fő számlával, amely csak vállalatközi tranzakciókhoz használatos.

Az eltávolítási beállítások a **Beállítás** területen találhatók a **Konszolidáció** modulban. Miután megadta a szabály leírását, ki kell választania a vállalatot, amelyben az eltávolítási napló közzé lesz téve. A kiválasztott vállalat olyan legyen, amelynél a **Pénzügyi eltávolítási folyamatokhoz** lehetőség ki van választva a jogi személy beállításainál.

Igény szerint beállíthatja az eltávolítási szabály érvényessége kezdetének és lejáratának dátumát. Az **Aktív** lehetőséget **Igen** értékre kell állítania, ha azt szeretné, hogy az eltávolítási szabály elérhető legyen az eltávolítási javaslati folyamat során. Válassza ki az **Eltávolítás** típus naplónevét.

![Eltávolítási szabály alapvető tulajdonságai](./media/ledger-elimination-rule-journal.png "Eltávolítási szabály alapvető tulajdonságai")

Az alapvető tulajdonságok megadása után a tényleges feldolgozási szabályokat a **Sorok** gombra elem kiválasztásával határozhatja meg. Két opció létezik eltávolításokhoz: a eltávolíthatja a nettó változás összegét, vagy meghatározhat egy rögzített összeget.

Válassza ki a forrásszámlákat. Helyettesítő karakterként használhat csillag (\*) karaktert. Ebben a példában az **1\**_a felosztás adatforrásaként minden olyan számlát használni fog, amelynek _* 1**-gyel kezdődik a száma.

A forrásszámlák kiválasztása után a **Számla meghatározása** használatával határozza meg a célvállalat használt számláját. Válassza a **Forrás** lehetőséget, ha ugyanazt a fő számlát szeretné használni, mint ami a forrásszámlában van megadva. Ha a **Felhasználó által meghatározott** lehetőséget választja, akkor meg kell adnia egy célszámlát.

![Főkönyvi eltávolítási szabálysor oldala](./media/ledger-elimination-rule-line.png "Főkönyvi eltávolítási szabálysor oldala")

A **Dimenzió meghatározása** mező úgy működik, mint a **Számla meghatározása** mező. Válassza a **Forrás** lehetőséget, így ugyanazokat a dimenziókat fogja használni a célvállalatnál és a forrásvállalatnál. Ha a **Felhasználó által meghatározott** lehetőséget választja, a **Cél dimenziói** menüpont kiválasztásával meg kell adnia a célvállalat dimenzióit. Majd válassza ki a forrásdimenziókat és a pénzügyi dimenziókat, valamint az eltávolítás forrásához használt értékeket.

### <a name="process-elimination-transactions"></a>Eltávolítási tranzakciók feldolgozása
Kétféleképpen dolgozhatja fel az eltávolítási tranzakciókat. A tranzakció feldolgozható az online konszolidáció során, vagy egy eltávolítási napló létrehozásával és az eltávolítási javaslati folyamat futtatásával. Ez a szakasz a második lehetőséggel foglalkozik.

Egy eltávolítási vállalatként meghatározott vállalatnál válassza az **Eltávolítási napló** lehetőséget a **Konszolidáció** modulban. Miután kiválasztotta a napló nevét kattintson a **Sorok** elemre. A javaslat futtatásához válassza a **Javaslatok** \> **Eltávolítási javaslat** lehetőséget.

Válassza ki a konszolidált adatok forrásaként szolgáló vállalatot, majd válassza ki a feldolgozni kívánt szabályt. Adja meg az eltávolítási összegek kereséséhez definiált dátumtartomány kezdő és záró dátumát. A **Főkönyvi feladási dátum** mező határozza meg a napló a főkönyvbe történő feladásának dátumát. Amikor kiválasztja az **OK** lehetőséget, áttekintheti az összegeket és feladhatja a naplót.

> [!NOTE]
> Az eltávolítási napló számlaértékek összegét a forrástranzakciók pénznemében és nem az alapértelmezett pénznemben jeleníti meg. Az eltávolítási napló összegeinek áttekintésekor előfordulhat, hogy félrevezetőnek találja ezt a viselkedést.

További információk és példák: [Eltávolítási szabályok](./elimination-rules.md).

## <a name="currency-revaluation-in-a-consolidation-company"></a>Devizaátértékelés konszolidált vállalatban
Ha egy könyvelési pénznemből egy másikba konszolidál adatokat és megváltozik az árfolyam, devizaátértékelést kell futtatnia, hogy a számlaegyenlegek átértékelése megfelelően történjen. Az adatok eredeti konszolidációja során használja a **Devizaátváltás** lapot, ahol kiválaszthatja a kezdeti árfolyamot, amely használva lesz a konszolidációs folyamat kezdeti átváltásához. Ha új árfolyamot ad meg (például következő hónapban), át kell értékelnie a számlaegyenlegeket. A nem realizált nyereség vagy nem realizált veszteség ezután az új árfolyam és dátumnak megfelelően frissül.

A Devizaátértékeléssel a konszolidált vállalatban kapcsolatos további tudnivalókat lásd: [Devizaátértékelés konszolidált vállalatban](currency-revaluation-consolidation-company.md).

Árfolyam-korrekció működésével a **főkönyv** modulban kapcsolatos további információért , lásd: [Főkönyvi devizaátértékelés](./foreign-currency-revaluation-general-ledger.md).

### <a name="additional-information"></a>További információk
- Minden feladási réteg konszolidálva lesz, amikor a konszolidáció feldolgozásra kerül.
- Eltávolítási naplók csak az Aktuális rétegben lehet feladni.
- Csak a működési egyenlegek lesznek konszolidálva. Ezért nyitó egyenlegek megtekintéséhez továbbra is futtatnia kell az év végi zárást a konszolidációs vállalatnál.
- A konszolidált vállalatban nem adhat fel napi naplókat de feladhatja azokat az eltávolítási vállalatban.
- Egy konszolidált vállalat egyenlegeinek helyesbítéseit csak a **Záró időszaki kiigazítások** lapon lehet végrehajtani. 

## <a name="benefits-of-using-financial-reporting-for-financial-consolidations-and-currency-translation-or-to-complement-consolidate-online-for-consolidated-reporting"></a>A Pénzügyi jelentések használatának előnyei a pénzügyi konszolidálások és devizaátváltás során, vagy az online konszolidáció kiegészítéséhez konszolidált jelentéskészítés során.
Azok az ügyfelek, akik Pénzügyi jelentéseket használnak a pénzügyi konszolidálások és devizaátváltás során, vagy az online konszolidáció kiegészítéséhez konszolidált jelentéskészítés során számos előnyt élvezhetnek.

- **Adatok mélysége** –, Olyan összesített jelentéseket hozhat létre, amelyek a tényleges és költségvetési adatokat számlaszint és a dimenziószinten összesítik. A Finance esetében ezeket az adatok a költségvetés-ellenőrzés és a költségvetés-tervezés adatait is tartalmazzák.
- **Dinamikus Konszolidációk** – A Konszolidációk bármikor és a szervezeti hierarchia bármely szintjén levégezhetők.
- **Teljes Könyvvizsgálati képességek** – Minden dimenzió, számla elemzés és tranzakciós adat meg van tartva elemzés és könyvvizsgálat céljából. Mindemellett a Pénzügyi jelentések teljes leásást biztosít az eredeti tranzakcióhoz bármely konszolidált jogi személy esetében.
- **Gördülékeny devizaátváltás** – A Finance alkalmazással minimális beállítás után átválthatja bármelyik Pénzügyi jelentést bármelyik jelentési pénznembe amely be van állítva. Mindemellett a programban korlátlan számú jelentési pénznemet beállíthat.
- **Eltávolításiok feladása a forrásnál** – Létrehozhat és nyomtathat eltávolítási jelentéseket az eltávolítási tranzakciók ellenőrzéséhez. Ezt követően feladhatja az új eltávolításokat szokásos vállalatközi tranzakcióként. Használhat eltávolítási jogi személyt minden olyan tranzakcióhoz használhatja, amelyekre nincs szüksége jogi személyeinél.

## <a name="supported-consolidation-scenarios-for-financial-reporting"></a>Támogatott konszolidációs esetek a pénzügyi jelentéskészítéshez

Az alábbiakban néhány az konszolidációs esetet, amelyeket a Financial reporting támogat:

- Egyszintű és többszintű konszolidáció jogi személyek között
- Szervezeti struktúrákat használó konszolidációk, amelyek jogi személyekből lettek létrehozva
- Eltávolításokkal járó konszolidációk
- Kisebbségi részesedés
- Több számlatükör jogi személyek között
- Különböző pénzügyi naptárak több jogi személy között
- Több jelentési pénznemet tartalmazó konszolidációk
- Üzleti egység konszolidációi

## <a name="generating-consolidated-financial-statements"></a>Konszolidált pénzügyi kimutatások generálása
További információért azzal kapcsolatosan, hogy hol generálhat konszolidált pénzügyi kimutatásokat, lásd: [Konszolidált pénzügyi kimutatások létrehozását](./generating-consolidated-financial-statements.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]