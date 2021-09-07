---
title: Az adószámítás első lépései
description: Ez a témakör bemutatja, hogyan állítsuk be az adószámítást.
author: wangchen
ms.date: 08/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: intro-internal
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1ddbb22d4f7c6108ca93b415276c53794b5450dd
ms.sourcegitcommit: 03f53980a4bc67b73ac2be76a3b3e7331d0db705
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/18/2021
ms.locfileid: "7394509"
---
# <a name="get-started-with-tax-calculation"></a>Az adószámítás első lépései

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Ez a témakör az adószámítással kapcsolatos első lépésekről nyújt tájékoztatást. Végigvezeti Önt a Microsoft Dynamics Lifecycle Services (LCS), a Regulatory Configuration Service (RCS), a Dynamics 365 Finance és a Dynamics 365 Supply Chain Management konfigurációs lépésein. Ezt követően áttekinti a Finance és a Supply Chain Management tranzakcióiban az adószámítási funkciója használatának közös folyamatát.

A beállítás négy fő lépésből áll:

1. Az LCS-ben telepítse az Adószámítás bővítményt.
2. Az RCS-ben állítsa be az adószámítás funkciót. Ez a beállítási adat nem specifikus jogi személyre. Megosztható a Finance és a Supply Chain Management jogi személyei között.
3. A Finance és a Supply Chain Management alkalmazásokban állítsa be az adószámítási paramétereket jogi személy szerint.
4. A Finance és a Supply Chain Management alkalmazásban hozzon létre tranzakciókat, például értékesítési rendeléseket, és az adószámítás segítségével határozza meg és számítsa ki az adókat.

## <a name="prerequisites"></a>Előfeltételek

Mielőtt a témakörben leírt eljárásokat elvégezhetné, az egyes környezettípusok esetében előfeltételeknek kell teljesülniük.

### <a name="for-a-production-environment"></a>Termelési környezetben

Termelési környezetben a következő előfeltételeknek kell teljesülniük:

- Hozzá kell férnie az LCS-fiókjához, és rendelkeznie kell egy telepített LCS-projekttel, amely Tier 2 vagy annál magasabb szintű környezetet tartalmaz, és a Dynamics 365 10.0.21-es vagy újabb verzióját futtatja.
- Létre kell hoznia egy RCS-környezetet a szervezet számára, és hozzáféréssel kell rendelkeznie a fiókjához. Az RCS-környezet létrehozásával kapcsolatos további információkért lásd a [Regulatory Configuration Service áttekintése](rcs-overview.md) című részt.
- A következő funkciókat az üzleti igényeknek megfelelően be kell kapcsolni a bevezetett pénzügyi vagy Supply Chain Management környezet **funkciókezelési** munkaterületén:

    - Áfaszámítás
    - Több áfaregisztrációs szám támogatása
    - Adó az átmozgatási rendelésben
    - EU értékesítési lista átvitele csak az adóügyi tranzakciók alapján
    - Intrastat jelentés több adószám szerint
    - EU értékesítési lista jelentése több adószám szerint
    - Forgalmiadó-bevallás több adószám szerint

- A következő funkciókat be kell kapcsolni a telepített RCS-környezet **funkciókezelési** munkaterületén.

    - Globalizációs funkciók

### <a name="for-a-test-environment-public-preview"></a>Tesztkörnyezethez (nyilvános előnézet)

A tesztkörnyezethez a következő előfeltételeknek kell teljesülniük:

- Hozzá kell férnie az LCS-fiókjához, és rendelkeznie kell egy telepített LCS-projekttel, amely Tier 2 vagy annál magasabb szintű környezetet tartalmaz, és a Dynamics 365 10.0.18-as verzióját futtatja a KB4616360 vagy egy későbbi verzióval.
- Létre kell hoznia egy RCS-környezetet a szervezet számára, és hozzáféréssel kell rendelkeznie a fiókjához. Az RCS-környezet létrehozásával kapcsolatos további információkért lásd a [Regulatory Configuration Service áttekintése](rcs-overview.md) című részt.
- A <taxcalc@microsoft.com> e-mail címen kapcsolatba kell lépnie a Microsofttal, hogy engedélyezze a repülést a telepített pénzügyi vagy Supply Chain Management környezetben.
- A következő funkciókat az üzleti igényeknek megfelelően be kell kapcsolni a bevezetett pénzügyi vagy Supply Chain Management környezet **funkciókezelési** munkaterületén:

    - Áfaszámítás
    - Több áfaregisztrációs szám támogatása
    - Adó az átmozgatási rendelésben
    - EU értékesítési lista átvitele csak az adóügyi tranzakciók alapján
    - Intrastat jelentés több adószám szerint
    - EU értékesítési lista jelentése több adószám szerint
    - Forgalmiadó-bevallás több adószám szerint

- A következő funkciókat be kell kapcsolni a telepített RCS-környezet **funkciókezelési** munkaterületén.

    - Globalizációs funkciók

## <a name="set-up-tax-calculation-in-lcs"></a>Állítsa be az adószámítást az LCS-be.

1. Jelentkezzen be az [LCS-be](https://lcs.dynamics.com)
2. Végezze el a Microsoft Power Platform integráció beállítását. További informáciért lásd: [Bővítmények áttekintése](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).
3. Válassza ki az egyik telepített környezetet, majd válassza az **Új bővítmény telepítése** lehetőséget.
4. Válassza az **Adószámítás** lehetőséget.
5. Olvassa el és fogadja el a feltételeket, majd válassza a **Telepítés** lehetőséget.

## <a name="set-up-tax-calculation-in-rcs"></a>Állítsa be az adószámítást az RCS-be.

Az ebben a szakaszban található lépések nem egy adott jogi személyhez kapcsolódnak. Ezt az eljárást csak egyszer kell elvégeznie, és az RCS bármely jogi személyében elvégezheti.

1. Bejelentkezés az [RCS](https://marketing.configure.global.dynamics.com/) alkalmazásba.
2. Az **Elektronikus jelentéskészítés** munkaterületen adjon hozzá egy új konfigurációszolgáltatót. Használja a vállalat nevét a szolgáltató neveként. További információért tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.
3. Jelölje ki az éppen létrehozott konfigurációs szolgáltatót, majd válassza a **Beállítás aktívként** lehetőséget.
4. Jelölje ki **a Microsoft** konfigurációs szolgáltatót, majd válassza az **Adattárak** lehetőséget.
5. A **Típus** mezőben válassza ki a **Globális** lehetőséget.
6. Válassza ki a **Megnyitás** lehetőséget.
7. Válassza az **Adóadatok modell** lehetőséget, bontsa ki a fájlfát, majd válassza az **Adókonfiguráció** lehetőséget.
8. Válassza ki a megfelelő adókonfigurációs verziót a Pénzügyi verzió alapján, majd válassza az **Importálás** lehetőséget.

    | Kiadás verziója | Adókonfiguráció                       | Modell leképezése                   |
    | --------------- | --------------------------------------- | ------------------------------- |
    | 10.0.18         | Adókonfiguráció - Európa 30.12.82     |                                 |
    | 10.0.19         | Adószámítási konfiguráció 36.38.193 |                                 |
    | 10.0.20         | Adószámítási konfiguráció 40.43.208 |                                 |
    | 10.0.21         | Adószámítási konfiguráció 40.46.212 | Dataverse Modell leképezése 40.46.9 |

9. A **Globalizációs funkciók** munkaterületen válassza a **Funkciók** lehetőséget, majd jelölje ki az **Adószámítás** lapot, és válassza a **Hozzáadás** lehetőséget.
10. Válassza ki az alábbi szolgáltatástípusok valamelyikét:

    - **Új funkció** – Hozzon létre egy üres tartalmú funkcióbeállítást.
    - **Meglévő funkció alapján** – Hozzon létre egy funkciót egy meglévő funkcióból, és másolja a tartalmat a meglévő funkcióbeállításból.

11. Adja meg a funkció nevét és leírását, majd válassza a **Funkció létrehozása** lehetőséget.

    A funkció létrehozása után a program automatikusan létrehoz egy piszkozatverziót. Az **Ezt a verziót lekérdezni** opciót választva a tervezetet bármely elkészült verzióra újraalapozhatja.

12. Jelölje ki a funkció piszkozatverzióját, majd kattintson a **Szerkesztés** gombra. Ki van töltve az **Adószámítás beállítása** lap.
13. Válassza a **Konfiguráció verziója** lehetőséget. Látnia kell a 8. lépésben importált konfigurációverziót.

    A Microsoft alapértelmezett adókonfigurációt biztosít az adószámításhoz. Ez a konfiguráció az adószámítási viselkedések legtöbb követelményét lefedi. A piaci visszajelzések alapján frissítjük majd. Ha ki kell bővítenie a konfigurációt, hogy megfeleljen bizonyos követelményeknek, a [Bővítmény létrehozása adószolgáltatásban](./tax-service-add-data-fields-tax-integration-by-extension.md) rész tartalmaz információt azzal kapcsolatosan, hogyan hozhatja létre és jelölheti ki a saját adókonfigurációját.

14. A **Konfigurációs verzió** kiválasztása után számos további fül jelenik meg. Kövesse az itt látható sorrendet a kötelező lap beállításának befejezéséhez.

    **Kötelező beállítás**

    - **Adókódok** - Adókódok törzsadatainak karbantartása. Az ezen a lapon létrehozott összes adókód automatikusan szinkronizálódik a Pénzügyekkel, amikor engedélyezi az aktuális verziót.
    - **Adócsoport** - Adja meg az adócsoport törzsadatait és a csoporthoz tartozó adókódokat.
    - **Tételadó-csoport** - A tételadó-csoport törzsadatainak és a csoporthoz tartozó adókódoknak a meghatározása.

    **Nem kötelező beállítások**

    - **Adócsoport alkalmazhatósága** - Adja meg az adócsoportot meghatározó mátrixot. Ha ebben a mátrixban nincs olyan alkalmazhatósági szabály, amely megfelelne a Dynamics 365-ből származó adóköteles dokumentumnak, az Adószámítás az adóköteles dokumentum sorban szereplő alapértelmezett értéket használja.
    - **Tételadó-csoport alkalmazhatósága** - Határozza meg a tételadó-csoportot meghatározó mátrixot. Ha ebben a mátrixban nincs olyan alkalmazhatósági szabály, amely megfelelne a Dynamics 365-ből származó adóköteles dokumentumnak, az Adószámítás az adóköteles dokumentum sorban szereplő alapértelmezett értéket használja.
    - **Ügyfél adóregisztrációs számának alkalmazhatósága** - Ha egy ügyfélhez több adóregisztrációs szám tartozik, az Adószámítás automatikusan meghatározza a helyes adóregisztrációs számot. Az ezen a lapon található mátrixban határozza meg a meghatározáshoz használandó szabályokat. Ellenkező esetben a Finance és a Supply Chain Management továbbra is az adóköteles dokumentumok alapértelmezett adószámát használja az értékesítési tranzakciókhoz.
    - **Szállítói adóregisztrációs szám alkalmazhatósága** - Ha egy szállítóhoz több adóregisztrációs szám tartozik, az Adószámítás automatikusan meghatározza a helyes adóregisztrációs számot. Az ezen a lapon található mátrixban határozza meg a meghatározáshoz használandó szabályokat. Ellenkező esetben a Finance és a Supply Chain Management továbbra is az adóköteles dokumentumok alapértelmezett adószámát használja a vásárlási tranzakciókhoz.
    - **Listakód alkalmazhatósága** - A **Listakód** mező értékének automatikus meghatározása rugalmasabb és konfigurálhatóbb szabályok segítségével. Az ezen a lapon található mátrixban határozza meg a meghatározáshoz használandó szabályokat. Ellenkező esetben a Finance és a Supply Chain Management továbbra is az adóköteles dokumentumok alapértelmezett kódját használja.

14. Az **Adókódok** lapon válassza a **Hozzáadás** lehetőséget, és adja meg az adókódot és a leírást.
15. Válassza az **Adózási összetevő** lehetőséget. Az adózási összetevő a kiválasztott adózási konfiguráció előző verziójában definiált módszerek csoportja. A következő adózási összetevők állnak rendelkezésre:

    - Nettó összeg alapján
    - Bruttó összeg alapján
    - Mennyiség alapján
    - Árrés alapján
    - Adó az adón

16. Válassza a **Mentés** lehetőséget. A kiválasztott adózási összetevő alapján további mezők válnak elérhetővé.
17. Az áfakód jellegének azonosításához használja a következő beállításokat:

    - Mentességet élvez
    - Használati adó
    - Fordított fizetés
    - Az alapösszeg kiszámításából való kizárás

    Használati adó forgatókönyvhöz állítson be egyetlen adókódot, amelynek pozitív adókulcsa van, és jelölje meg **Használati adónak**.

    Fordított adózás esetén állítson be két adókódot, amelyek közül az egyik pozitív adókulcsot tartalmaz, a másikhoz negatív adókulcs tartozik, de azonos áfaértékkel. A negatív adókód megjelölése **Fordított áfás**. A fordított áfa megoldásával kapcsolatos további tudnivalókat a Finance alkalmazásban lásd: [Fordított áfamechanizmus az ÁFA/GST sémához](emea-reverse-charge.md).

    Egyes adótípusok esetében, amelyeket ki kell zárni az adóalapösszeg kiszámításából az árat tartalmazó tranzakciók esetében (például a vámot egyes országokban vagy régiókban), jelölje be a **Kizárás az alapösszeg kiszámításából** jelölőnégyzetet. További információért erről a paraméterről lásd: [Adó kiszámítása az ár tetején, ha az Árak tartalmazzák az adókat engedélyezve van.](global-exclude-from-tax-base-amount-calculation.md)

    Adómértékek és az adóösszeg-korlátok karbantartása ehhez az adókódhoz.

18. Ismételje meg a 14.–17. lépéseket az összes szükséges adókód hozzáadásához.
19. Az **Adócsoport** lapon jelölje ki az **Adócsoport** oszlopot, adja hozzá a mátrixhoz bemeneti feltételként, majd adjon hozzá sorokat az adócsoport törzsadatok karbantartásához.

    Íme, egy példa.

    | Adócsoport    | Adókódok           |
    | ------------ | ------------------- |
    | DEU_Domestic | DEU_VAT19; DEU_VAT7 |
    | DEU_EU       | DEU_Exempt          |
    | BEL_Domestic | BEL_VAT21; BEL_VAT6 |
    | BEL_EU       | BEL_Exempt          |

20. A **Tételadó-csoport** lapon jelölje ki a **Tételadó-csoport** oszlopot, adja hozzá a mátrixhoz bemeneti feltételként, majd adjon hozzá sorokat a tételadó-csoport törzsadatok karbantartásához.

    Íme, egy példa.

    | Tétel adócsoport | Adókódok                                    |
    | -------------- | -------------------------------------------- |
    | Teli           | DEU_VAT19; BEL_VAT21; DEU_Exempt; BEL_Exempt |
    | Csökkentett        | DEU_VAT7; BEL_VAT6; DEU_Exempt; BEL_Exempt   |

21. Az **Adócsoport alkalmazhatósága** lapon jelölje ki a megfelelő adócsoport meghatározásához szükséges oszlopokat, majd válassza a **Hozzáadás** gombot. Adja meg vagy válassza ki az egyes oszlopok értékeit. Az **adócsoport** mező lesz ennek a mátrixnak a kimenete. Ha ez a lap nincs beállítva, akkor a tranzakciósoron lévő forgalmiadó-csoportot kell használni.

    Íme, egy példa.

    | Üzleti folyamat | Szállítás kiindulási helye | Szállítás célhelye | Adócsoport    |
    | ---------------- | --------- | ------- | ------------ |
    | Értékesítés            | DEU       | DEU     | DEU_Domestic |
    | Értékesítés            | DEU       | FRA     | DEU_EU       |
    | Értékesítés            | BEL       | BEL     | BEL_Domestic |
    | Értékesítés            | BEL       | FRA     | BEL_EU       |

22. A **Tétel adócsoport alkalmazhatósága** lapon jelölje ki a helyes adókód meghatározásához szükséges oszlopokat, majd válassza a **Hozzáadás** gombot. Adja meg vagy válassza ki az egyes oszlopok értékeit. Ennek a mátrixnak a kimenete a **tételadó-csoport** mező lesz. Ha ez a lap nincs beállítva, akkor a tranzakciósoron lévő tétel forgalmi adócsoportját kell használni.

    Íme, egy példa.

    | Cikk kódja | Tétel adócsoport |
    | --------- | -------------- |
    | D0001     | Teli           |
    | D0003     | Csökkentett        |

    Az adókódok Adószámításban történő meghatározásáról további információt az [Értékesítési adócsoport és tétel értékesítési adócsoport meghatározási logikája](global-sales-tax-group-determination.md) című témakörben talál.

23. Állítsa be a vevői adóregisztrációs számok, a szállítói adóregisztrációs számok és a listakódok alkalmazhatóságát az üzleti igények alapján.
24. Válassza a **Mentés** gombot, majd zárja be az oldalt.
25. Válassza az **Állapot módosítása** \> **Teljes** lehetőséget. Ha az állapot **Kész** állapotúra változik, akkor a verzió már nem szerkeszthető.
26. Válassza az **Állapot módosítása** \> **Közzététel** lehetőséget. Az adófunkció beállításnak ez a verziója a globális tárházba lesz felküldve, és a Finance-ban minden jogi személy számára látható lesz.

## <a name="set-up-tax-calculation-in-dynamics-365"></a>Adószámítás beállítása a Dynamics 365-ben

Miután befejezte a beállítást az RCS-ben, az adófunkció közzétett verziója lesz. Hajtsa végre az alábbi lépéseket, ha be szeretné állítani az adószámítást a Finance-ban.

Az ebben a szakaszban található beállításokat jogi személy végzi. Be kell állítania mindegyik jogi személyhez, amelynél engedélyezni szeretné az adószámítást a Finance-ben.

1. A Pénzügyek menüpontban lépjen az **Adó** \> **Beállítás** \> **Adókonfiguráció** \> **Adószámítási paraméterek** menüpontba.
2. Az **Általános** lapon állítsa be a következő mezőket:

    - **Adószámítási szolgáltatás engedélyezése** - Jelölje be ezt a jelölőnégyzetet a jogi személy adószámításának engedélyezéséhez. Ha az aktuális jogi személyhez nincs engedélyezve, a jogi személy továbbra is a meglévő adómotor használatával határozza meg és számítja ki az adót.
    - **Funkció beállítása** – A közzétett adófunkció beállítás és verzió kiválasztása a jogi személyhez. A közzétett adó funkció beállításához és befejezéséhez kapcsolódó további tudnivalókat lásd a témakör előző szakaszában.
    - **Üzleti folyamat** – az engedélyezni kívánt üzleti folyamatok kiválasztása.

3. A **Számítás** lapon határozza meg a jogi személy elvárt kerekítési szabályát. A kerekítési logikával kapcsolatos további információkért lásd: [Adószámítás kerekítési szabályok](https://go.microsoft.com/fwlink/?linkid=2166988).
4. Adja meg a **Hibakezelés** lapon a jogi személy elvárt hibakezelési módját. Három lehetőség áll rendelkezésre:

    - Nincs
    - Figyelmeztetés
    - Hiba

    A **Részletek** szakaszban minden egyes eredménykódhoz beállíthat egy hibakezelési módszert. Alternatívaként, ha egyes eredménykódok nem szinkronizálódnak az adószámítási szolgáltatásból, az **Általános** részben beállíthat egy alapértelmezett módszert.

5. A **Többszörös áfa-regisztráció** lapon külön-külön bekapcsolhatja a HÉA-nyilatkozat, az EU értékesítési lista és az Intrastat funkciót, hogy többszörös áfa-regisztráció esetén is dolgozhasson. A több HÉA-regisztrációra vonatkozó adóbevallással kapcsolatos további információkért lásd: [Több HÉA-regisztrációra vonatkozó bevallás](emea-reporting-for-multiple-vat-registrations.md).
6. Mentse a beállítást, és ismételje meg az előző lépéseket minden további jogi személy esetében. Amikor egy új verzió megjelenik, és azt szeretné, hogy azt alkalmazzák, állítsa be az **Adószámítási paraméterek** lap **Általános** lapján a **Jellemző beállítása** mezőt (lásd a 2. lépést).

## <a name="transaction-processing"></a>Tranzakciófeldolgozás

Miután elvégezte az összes beállítási műveletet, az Adószámítás segítségével meghatározhatja és kiszámíthatja az adót a Pénzügyekben. A tranzakciók feldolgozásának lépései változatlanok maradnak. A Finance 10.0.21-as verziója a következő tranzakciókat támogatja:

- Értékesítési folyamat

    - Értékesítési ajánlat
    - Értékesítési rendelés
    - Visszaigazolás
    - Kitárolási lista
    - Szállítólevél
    - Értékesítési számla
    - Jóváírás
    - Visszárurendelés
    - Fejlécdíj
    - Sorköltség

- Beszerzési folyamat

    - Beszerzési rendelés
    - Visszaigazolás
    - Bevételezések listája
    - Termékbevételezés
    - Beszerzési számla
    - Fejlécdíj
    - Sorköltség
    - Jóváírás
    - Visszárurendelés
    - Beszerzési igénylés
    - A beszerzési igénylési sor díja
    - Ajánlatkérés
    - Ajánlatkérés fejlécének díja
    - Ajánlatkérés sorának díja

- Készletfolyamat

    - Átmozgatási rendelések – szállítás
    - Átmozgatási rendelés - bevételezés
