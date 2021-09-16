---
title: Alapértelmezett pénzügyi dimenziók a pénzügyi naplókban
description: Ez a témakör azokat a szabályokat írja le, amelyek meghatározzák a pénzügyi dimenziók értékeinek beállítását a pénzügyi naplókon keresztül bevitt tranzakciókon. A rögzített dimenziókat tartalmazó helyzetek részleteit is tartalmazza.
author: kweekley
ms.date: 09/04/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransDaily, LedgerJournalTransVendInvoice, LedgerJournalTransVendPaym, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 327bc27f068e1f9eefacc6b5defa27044cb1a77e
ms.sourcegitcommit: d420b96d37093c26f0e99c548f036eb49a15ec30
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/03/2021
ms.locfileid: "7472532"
---
# <a name="default-financial-dimensions-on-financial-journals"></a>Alapértelmezett pénzügyi dimenziók a pénzügyi naplókban

[!include [banner](../includes/banner.md)]

Ez a témakör azokat a szabályokat írja le, amelyek meghatározzák a pénzügyi dimenziók értékeinek beállítását a pénzügyi naplókon keresztül bevitt tranzakciókon (de nem a leltárnaplókon vagy a projektnaplókon keresztül). A rögzített dimenziókat tartalmazó helyzetek részleteit is tartalmazza.

## <a name="symptom"></a>Tünet

A pénzügyi dimenziók értékei nincsenek a vártnak megfelelően beállítva a pénzügyi napló Számláján vagy ellenszámlájában. Az alábbiakban bemutatunk két példát ezekre:

A bizonylatot egy naplóba viszik be, egy általános naplóba. A számla egy szállítói számla, az ellenszámla pedig egy bankszámla. A szállító pénzügyi dimenziói alapértelmezés szerint a számlán vannak megadva, de a bank pénzügyi dimenziói alapértelmezés szerint nem szerepelnek az ellenszámlán. Ehelyett a program alapértelmezés szerint beírja a számlán megadott értékeket az ellenszámlára.

Egy vevőhöz alapértelmezett pénzügyi dimenzióértékek vannak hozzárendelve, a bevételi fő számlához pedig egy rögzített, a részleghez tartozó dimenzióérték van hozzárendelve. A bizonylatot egy általános naplóba viszik be.  A számla a vevő számlája, az ellenszámla pedig egy főkönyvi számla, pontosabban a bevételi számla a rögzített dimenzióértékkel. A rögzített dimenzió nincs beállítva a bevétel fő számlájának ellenszámlájára. Ehelyett a Számla Részleg dimenzióértékét adja meg, ami a vevőtől jön.  A bizonylat feladása után a rendszer a feladott könyvelési bejegyzésben a rögzített dimenzióértéket használja, de a bizonylat továbbra is a vevő részlegének értékét jeleníti meg a bevételi számlán. 

Milyen szabályok vonatkoznak egy naplóban az utalványoknál beállított pénzügyi dimenzióértékre?

## <a name="resolution"></a>Megoldás

A következő szabályokat kell követni a pénzügyi dimenzióértékek alapértelmezett megadásához a bizonylat soraiban a pénzügyi naplókban, például az általános naplóban vagy a szállítói számlanaplóban. 

1. **Napló fejléce**

   - A napló fejlécének dimenziói alapértelmezés szerint a napló nevének dimenzióiból kerülnek be.

2. **Naplósor számlája**

   - A napló sor számla dimenziói alapértelmezés szerint a napló fejlécének dimenzióiból kerülnek be.
   - Ha bármelyik pénzügyi dimenzió üres, akkor a program alapértelmezés szerint vevői, szállítói, banki, tárgyieszköz-, projekt- és főkönyvi dimenziókból ad meg értékeket.

     - Ha a számlatípus **Főkönyv**, a főkönyvi számla rögzített dimenzióját a rendszer alapértelmezett dimenzióként kezeli a tranzakció bevitele során.
     - Ha a számla típusa **Vevő**, **Szállító**, **Bank**, **Tárgyi eszközök** vagy **Projekt**, akkor a fő számla még nem határozható meg. Következésképpen a számlához alapértelmezés szerint soha nem lesz rögzített dimenzió megadva.

3. **Naplósor ellenoldali számla**

 - Először a naplósor ellenszámla dimenziói alapértelmezés szerint a naplósor Számla dimenzióiból kerülnek be.

 - Ha bármelyik pénzügyi dimenzió üres, a következő alapértelmezett beírás a vevői, szállítói, banki, tárgyieszköz-, projekt- vagy főkönyvi dimenziókból jön.
   1. Ha az ellenoldali számla típusa **Főkönyv**, a főkönyvi számla rögzített dimenzióját a rendszer alapértelmezett dimenzióként kezeli a tranzakció bevitele során. Ha egy dimenzióérték alapértelmezés szerint már bekerült a Számláról, akkor a fő számla alapértelmezett vagy rögzített dimenzióértéke nem írja felül a meglévő értéket.
   2. Ha az ellenszámla **vevői**, **szállítói**, **banki**, **tárgyieszköz** vagy **projekt** típusú, a fő számla még nem ismert, így az ellenszámlánál soha nem lesz alapértelmezett rögzített dimenzió.

4. **Feladás**

    1. A feladás során a könyvelési bejegyzés minden sorának fő számláját (mind a számla, mind az ellenoldali számla) kiértékeli a rendszer, és meghatározza, hogy van-e rögzített dimenzióérték. Ha meg van adva egy rögzített dimenzió, minden meglévő vagy üres értéket felülír ezzel a rögzített dimenzióértékkel.

        Feladás után a rögzített dimenzióérték **nem** jelenik meg a naplósorok között. Ehelyett a könyvelési bejegyzésen jelenik meg, amikor a feladás után megtekinti a bizonylatot.

    2. A feladás során alapértelmezés szerint nincs megadva más dimenzióérték, beleértve a feladás során hozzáadott további főkönyvi számlák értékeit is, mint például a fillér kerekítési számlák vagy a vállalatközi fizetendő és esedékes számlák értékei. A további főkönyvi számlák alapértelmezett dimenzió bejegyzéseit a rendszer a Számláról vagy ellenoldali számlákról veszi.

A dimenzióértékek alapértelmezés szerinti megadása céljából a napló alapértelmezett folyamata nem tudja megállapítani, hogy egy üres dimenzióértéket szándékosan üresen hagytak-e, vagy hogy az alapértelmezett bejegyzés nem készült el. Ha egy dimenzióérték szándékosan üresen marad, akkor alapértelmezés szerint a korábban ismertetett alapértelmezési sorrend alkalmazásával lehet megadni egy értéket. Ha a dimenzió értékének üresnek kell lennie, lehet, hogy olyan dimenziót kell létrehoznia, amely **0** (nulla) vagy **Üres** értékű, hogy használható legyen üres dimenzió helyett.

Tekintse át az alábbi eseteket a pénzügyi dimenzió alapértelmezett sorrendjét bemutató példákkal.

### <a name="scenario-1"></a>1. eset

Menjen a **Főkönyv \> Naplóbeállítás \> Naplónevek** elemre, és válassza ki a **GenJrn** napló nevet. Ezután a **Pénzügyi dimenziók** Gyorslapon adja meg a következő értékeket az alapértelmezett pénzügyi dimenziókhoz:

- **BUSINESSUNIT** 001
- **DEPARTMENT:** 024

[![Naplónevek oldal](./media/financial-dimension-defaulting-jrnl-names-01.png)](./media/financial-dimension-defaulting-jrnl-names-01.png)

Menjen a **Főkönyv \> Naplóbejegyzések \> Főkönyvi napló** elemre, és hozzon létre egy új főkönyvi naplót, amely a **GenJrn** napló nevet használja. A dimenziók bevitele alapértelmezés szerint a naplónévből (LedgerJournalName tábla) kerül a naplófejlécbe (LedgerJournalTable tábla), ahogyan az a **Pénzügyi dimenziók** lapon látható.

[![Pénzügyi dimenziók lap a Főkönyvi naplók oldalon](./media/financial-dimension-defaulting-genrl-jrnl-02.png)](./media/financial-dimension-defaulting-genrl-jrnl-02.png)

Lépjen a **Sorok** elemre. A **Számlatípus** mezőben válassza a **Főkönyv** lehetőséget, majd a **Számla** mezőbe írja be ezt: **170150**. Ezután a **Tab** billentyűre kattintva lépjen ki a mezőből. A dimenziók alapértelmezés szerint a napló fejlécéből kerülnek be. Ebből következően a **Számla** értéke így jelenik meg: **170150-001-024**.

[![Főkönyvi napló sorai a Naplóbizonylat oldalon](./media/financial-dimension-defaulting-jrnl-vchr-03.png)](./media/financial-dimension-defaulting-jrnl-vchr-03.png)

Módosítsa a **Számla** értékét erre: **170150-001-023**. Írjon be egy terhelendő vagy egy jóváírandó összeget. Az **Ellenszámla** mezőben válassza a **Főkönyv** lehetőséget, majd az **Ellenszámla** mezőbe írja be ezt: **600150**. A dimenzióértékek alapértelmezés szerint a számláról kerülnek be. Ebből következően az **Ellenszámla** értéke így jelenik meg: **600150-001-023**.

### <a name="scenario-2"></a>2. eset

Használja ugyanazokat a pénzügyi dimenziókat, amelyeket az 1. esetnél a napló nevéhez definiált. Ezután menjen a **Kinnlevőségek \> Vevők \> Összes vevő** elemre, és határozza meg az US-001 vevő alapértelmezett pénzügyi dimenzió értékeit. A vevői adatok megnyitásához válassza ki a vevőt. A **Pénzügyi dimenziók** lapon tartsa meg a **BUSINESSUNIT** dimenzió alapértelmezett értékét (**001**). Adja hozzá a **COSTCENTER** dimenziót, és adja meg értékként ezt: **007**.

Hozzon létre egy új főkönyvi naplót, ami a **GenJrn** napló nevet használja. A **Pénzügyi dimenziók** lapon módosítsa az alapértelmezett **BUSINESSUNIT** értéket **001**-ről **002**-re.

Lépjen a **Sorok** elemre. A **Számlatípus** mezőben válassza ki a **Vevő** lehetőséget, majd a **Számla** mezőbe írja be ezt: **US-001**. A nem főkönyvi számlatípusok pénzügyi dimenzióinak megtekintéséhez válassza a **Pénzügyi dimenziók \> Számla** lehetőséget. A következő alapértelmezett bejegyzések vannak megadva a pénzügyi dimenzióértékeknél:

- **BUSINESSUNIT:** 002 – az alapértelmezett bejegyzés a napló fejlécéből. A **001**-es érték alapértelmezés szerint nincs megadva az US-001 vevőtől, mert már korábban meg lett adva egy alapértelmezett érték.
- **COSTCENTER:** 007 – az alapértelmezett bejegyzés az US-001 vevő beállításaiból.
- **DEPARTMENT:** 024 – az alapértelmezett bejegyzés a napló fejlécéből.

A sorba visszatérve az **Ellenszámla típusa** mezőben válassza a **Főkönyv** lehetőséget, majd az **Ellenszámla** mezőbe írja be ezt: **600150**. A következő alapértelmezett pénzügyi dimenzióértékek vannak megadva a soron:

- **BUSINESSUNIT:** 002 – az alapértelmezett bejegyzés a számla pénzügyi dimenzióiból. (Eredetileg a napló fejlécéből került be alapértelmezettként.)
- **DEPARTMENT:** 024 – az alapértelmezett bejegyzés a számla pénzügyi dimenzióiból. (Eredetileg a napló fejlécéből került be alapértelmezettként.)
- **COSTCENTER:** 007 – az alapértelmezett bejegyzés a számla pénzügyi dimenzióiból. (Eredetileg a vevőről került be alapértelmezettként.)

### <a name="scenario-3"></a>3. eset

A 2. esethez használt naplóban adjon hozzá egy új sort. A **Számlatípus** mezőben válassza a **Főkönyv** lehetőséget, majd a **Számla** mezőbe írja be ezt: **170150**. Törölje az alapértelmezett dimenzióértékeket, hogy csak a 170150 fő számla maradjon. Az **Ellenszámla típusa** mezőben válassza a **Vevő** lehetőséget, majd az **Ellenszámla** mezőbe írja be ezt: **US-001**. A következő alapértelmezett bejegyzések vannak megadva a pénzügyi dimenzióértékeknél:

- **BUSINESSUNIT:** 002 – az alapértelmezett bejegyzés a naplófejlécből kerül be, mert a Számla dimenzióértéke üres. A **001**-es érték alapértelmezés szerint nincs megadva az US-001 vevőtől, mert egy alapértelmezett érték már korábban át lett véve a napló fejlécéből. Ha a **BUSINESSUNIT** értéke szándékosan lett üresen hagyva, az ellenszámla pénzügyi dimenzióját is el kell távolítania.
- **COSTCENTER:** 007 – az alapértelmezett bejegyzés az US-001 vevőről kerül át, mert a Számla dimenzióértéke és a napló fejlécének dimenzióértéke üres. Ha a **COSTCENTER** értéke szándékosan lett üresen hagyva, az ellenszámla pénzügyi dimenzióját is el kell távolítania.
- **DEPARTMENT:** 024 – az alapértelmezett bejegyzés a naplófejlécből kerül be, mert a Számla dimenzióértéke üres. Ha a **DEPARTMENT** értéke szándékosan lett üresen hagyva, az ellenszámla pénzügyi dimenzióját is el kell távolítania.

### <a name="scenario-4"></a>4. eset

Használja ugyanazokat az alapértelmezett pénzügyi dimenzióértékeket, amelyeket az 1. és 2. forgatókönyvben a napló nevéhez és a vevőhöz definiált. Ezután határozzon meg egy rögzített dimenzióértéket a **BUSINESSUNIT** dimenzióhoz a 170150-es fő számlán. Lépjen a **Főkönyv \> Számlatükör \> Számlák \> Fő számlák lehetőségre**. A **Fő számla** mezőben válassza a **170150**-et, majd a **Jogi személy szintű felülbírálás** lapon válassza ki a **Hozzáadás** lehetőséget. Válassza ki jogi személyként az **USMF**-et, majd a **Hozzáadás** lehetőséget. Válassza ki azt a rekordot, majd az **Alapértelmezett dimenziók** lehetőséget. Módosítsa a **BUSINESSUNIT** dimenziót **Rögzített érték**-re, és adja meg értékként ezt: **003**.

Hozzon létre egy új főkönyvi naplót, ami a **GenJrn** napló nevet használja. Távolítsa el az összes alapértelmezett dimenzióértéket a **Pénzügyi dimenziók** lapon.

Lépjen a **Sorok** elemre. A **Számlatípus** mezőben válassza a **Főkönyv** lehetőséget, majd a **Számla** mezőbe írja be ezt: **170150**. Ezután a **Tab** billentyűre kattintva lépjen ki a mezőből. A 170150-es számlához a fő számla beállításaiból alapértelmezettként bekerülnek a dimenzióértékek. Ezért a **Számla** értéke így jelenik meg: **170150-003-**.

Módosítsa a **Számla** értékét erre: **170150-004-**. **A naplófunkció nem akadályozza meg egy rögzített dimenzióérték módosítását.** Írjon be egy terhelendő vagy egy jóváírandó összeget. Az **Ellenszámla** mezőben válassza a **Főkönyv** lehetőséget, majd az **Ellenszámla** mezőbe írja be ezt: **170250**. A 004-es pénzügyi dimenzióérték a Számláról kerül be alapértelmezettként. Ezután adja fel a dokumentumot. A naplóban válassza a **Bizonylat** lehetőséget. A feladás során a **BUSINESSUNIT** érték visszaáll a rögzített **003** dimenzióértékre.

Amikor visszatér a bizonylathoz a naplóban, a **BUSINESSUNIT** dimenzió **nem** tükrözi a rögzített dimenzióértéket. Itt mindig az az érték lesz, ami a feladás előtt szerepelt a képernyőn. A feladási folyamat nem módosítja a bizonylaton megadott adatokat. Feladáskor csak a könyvelési bejegyzés módosul.

## <a name="developer-notes"></a>Fejlesztői megjegyzések

Ha Ön fejlesztő, és meg szeretné nézni az alapértelmezési folyamat kódját, nézze át a következő módszereket:

- **LedgerJournalEngine.accountModified()** – ez a módszer az elsődleges számla dimenzió alapértelmezési folyamatának fő belépési pontja, ami a standard minden naplóra (és bizonyos naplótípusokkal felülírható).
- **LedgerJournalEngine.offsetAccountModified()** – ez a módszer az ellenszámla dimenzió alapértelmezési folyamatának fő belépési pontja.
