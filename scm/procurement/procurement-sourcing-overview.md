---
title: "A Beszerzés és forrás modul áttekintése"
description: "A cikk áttekintést nyújt a beszerzés és forrás modulban elérhető funkciókról."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 58021
ms.assetid: eea24e23-a803-4de0-a218-6485757cde1b
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 758c516b378b4858c248fbca2befc6b9c47cc32a
ms.lasthandoff: 03/31/2017


---

# <a name="procurement-and-sourcing-overview"></a>A Beszerzés és forrás modul áttekintése

A cikk áttekintést nyújt a beszerzés és forrás modulban elérhető funkciókról.

A Beszerzés és forrás modul kezeli az összes lépést a termék- és szolgáltatásigény azonosításától, a termék beszerzésén keresztül egészen a kézhezvételig, számlázásig, illetve a szállító felé esedékes kifizetés feldolgozásáig. A beszerzési folyamatokat beszerzési irányelvek és munkafolyamatok megadásával tudja az üzleti igényekhez igazítani.

## <a name="identifying-a-need-for-product-and-services"></a>Termék- és szolgáltatásigény azonosítása
A termékre vagy szolgáltatásra vonatkozó igény felmerülhet *igénylések* következtében, például amikor egy alkalmazottnak szüksége van egy adott termékre. Létre tud hozni *Termékkatalógusokat *a rendelkezésre álló termékek közül történő választás elősegítése érdekében, illetve nyújthat be igénylést a katalógusból még nem elérhető termékek kapcsán, ily módon téve lehetővé, hogy a beszerzési részleg megvizsgálja a termék beszállításának lehetőségét.  

*Költekezési határok *segítségével tudja korlátozni az igénylésekhez kapcsolódó költéseket, a *beszerzési munkafolyamat *pedig lehetővé teszi, hogy a megrendelés végrehajtása jóváhagyáshoz legyen kötve. Szükség esetén tud megadni költségvetésialap-felosztásokat is.  
  
A beszerzési részleg azonosítja a szükséges termékek és szolgáltatások lehetséges szállítóit, mely alapján elképzelhetően *ajánlatkérést *küld több potenciális szállító részére. Lehetőség nyílik az igénylendő termék specifikációinak megosztására, a potenciális szállítók pedig meg tudják tekinteni ezeket, és ellenőrizni tudják, hogy képesek-e azoknak megfelelő terméket szállítani le. A szállítók visszaküldik az ajánlataikat, melyeket a beszerzési részleg elbírál, majd kiválasztja a beszerzés céljából használni kívánt szállítót.  

A beszerzési rendelések tartalmaznak egy olyan lehetőséget, amely, az átfogóbb ajánlatkérési folyamat helyett, egy *beszerzési értesítőt *küld ki a szállítóknak. A beszerzési értesítő az olyan feltételek feltérképezését szolgálja, mint az ár, az engedmények, illetve a rendelés leszállítási dátuma. Ha szállítók használatára vannak beállítva a **szállító** portál, * * beszerzési lekérdezési funkciók le vannak tiltva. Ebben az esetben a rendelés a** Szállítói** portálon kerül megosztásra, a *visszaigazolási kérés* kiküldését követően pedig a szállító képes közvetlenül visszaigazolni a rendelést.  

*Szállítói katalógusok *segítségével információt tud gyűjteni az általuk forgalmazott termékválasztékról. A szállítók maguk tudják közzétenni a saját katalógusukat, így könnyebb a katalógus naprakészen tartása. Egy termékhez csatolhat *engedélyezett szállítói listát* is, ami elősegítheti a szállító kiválasztását új beszerzési rendelések megnyitásakor, illetve a nem kívánt szállítók mellőzését.

## <a name="procurement"></a>Beszerzés
Több módon is tud létrehozni *Beszerzési rendelést *, például az alábbiak szerint:

-   A beszerzési igényel, amely megállapította, hogy egy igény szerint az Alaptervezés az eredményét. Ez a folyamat a tervezett beszerzési rendeléseket hoz létre, és ezek felszabadul, amikor a beszerzési rendelések jönnek létre.
-   Beszerzést eredményező beszerzési igénylések feldolgozása következtében.
-   Beszerzési szerződések feldolgozása során, ahol is a rendszer beszerzési rendeléseket hoz létre megállapodásokból származó kiadott megrendelések formájában. Erre jellemzően akkor kerül sor, ha beszerzési szerződéseket használ a keretrendelések jelölésére.
-   Manuálisan, amikor is a létrehozott beszerzési rendelés nem alapul másik dokumentumon.

A *beszerzési jóváhagyási munkafolyamatok* segítségével konfigurált beszerzési rendeléseket jóvá kell hagyni azok jóváhagyottként történő rögzítése előtt, és csak ezután kerülhet sor a megrendelés további feldolgozására.  

A beszerzési rendelések *Jóváhagyása* megerősíti, hogy szerződéses viszony áll fenn a szállítóval. A beszerzési rendelés ezután fokozatosan több állapoton halad keresztül, mígnem végül számlázásra vagy törlésre kerül.  

A beszerzési rendelés létrehozásakor a mezők többsége a szállítóra vonatkozó tárolt adatok az alapértelmezett értékekkel előre a **szállítók** oldalon. Ennek megfelelően, Önnek csak egy korlátozott számú mezőt kell kitöltenie a beszerzési rendelésen, de akár felül is írhatja az alapértelmezett értékeket.

### <a name="prices-and-discounts"></a>Árak és engedmények

Az árak és engedmények rész a szállító által vállalat árakról, engedményekről és visszatérítési feltételekről nyújt tájékoztatást. Az árak és engedmények részt jelölhetik *kereskedelmi* *megállapodások*. A kereskedelmi megállapodások olyan szállítói árlisták, melyek rögzítik az árakat vagy engedményeket, valamint a megállapodás konkrét érvényességi idejét. Az árak és engedmények rögzíthetők és jelölhetők *beszerzési szerződések *, illetve olyan feltételek segítségével, mint például adott mennyiségű vagy értékű áru megvásárlására vonatkozó olyan vállalások, melyek a kialkudott feltételek alapfeltételei. A szállítókkal kötött *visszatérítési megállapodások *lehetővé teszik, hogy bizonyos termékek vagy termékcsoportok beszerzése esetén a szállító, a vásárolt termékek értéke vagy mennyisége alapján, visszatérítsen egy bizonyos összeget.

### <a name="delivery-options"></a>Szállítási lehetőségek

A beszerzési rendeléshez kapcsolódó szállítási folyamat tekintetében több lehetőség áll a rendelkezésére. A megrendelt termékeket fel tudja osztani *szállítási* ütemezésekbe, mely esetben a megrendelt mennyiség tervezett szállítása különböző időpontokban történik. További szállítási lehetőség az értékesítési rendelésből indított *közvetlen szállítás*, mely esetén a rendszer automatikusan létrehozza az értékesítési rendeléshez kapcsolódó szállítólevelet, a termék átvételének, a értékesítési rendelésben történő rögzítésével egy időben. A beszerzési rendelés lehet része egy *vállalatközi rendelésláncnak *is, más néven vállalatközi beszerzési rendelésnek, mely esetben a termékrendelés egy megfelelő vállalatközi értékesítési rendelésből kerül rendezésre. Ebben az esetben automatikusan sor kerül bizonyos lépések végrehajtására a kapcsolódó vállalatközi rendelések között.

### <a name="supplementary-items"></a>Kiegészítő cikkek

A termékekhez be tud állítani *kiegészítő cikkek* is. Ennek célja a megrendelésre kerülő termékhez kapcsolódó további termékekre vonatkozó javaslattétel. A további termékek lehetnek szükségesek, vagy opcionálisak. Bizonyos esetekben a hozzáadott kiegészítő cikkek lehetnek egy másik, megvásárolt termék mellé adott ingyenes termékek.

### <a name="purchase-order-charges"></a>Beszerzési rendelés költségei

A beszerzési rendeléshez hozzárendelhet díjakat is. Ez történhet automatikusan, automatikus díjak beállításával, vagy a díjak manuális hozzáadása útján. A díjakat a rendeléshez a fejléc szintjén, illetve a rendelési sor szintjén is hozzá tudja rendelni. A díjak könyvelése kapcsán több beállítási lehetőség áll a rendelkezésére. Be tudja például állítani, hogy egy díj termékköltségként kerüljön lekönyvelésre. Ilyen esetben a díjat a rendelés jóváhagyása előtt hozzá kell rendelni a rendelési sor szintjén. Egy másik opció abban segíti Önt, hogy a rendelési fejlécből osszon fel díjakat a sorokba.

## <a name="product-receipt-and-invoicing"></a>A termék bevételezése és számlázása
A fizikai termékekre vonatkozó beszerzési rendelések jellemzően szükségessé teszik a raktárban végrehajtott *beérkezésregisztrációt*, majd a *termékbevételezés *regisztrációját a rendelés kapcsán. Az igénylések alapján létrejövő beszerzési rendelések konfigurációját be tudja úgy állítani, hogy a terméket igénylő munkavállaló részéről szintén szükséges legyen a *bevételezés-visszaigazolás*.  

Egyes beszerzési rendelésekben olyan termékek is szerepelnek, amelyek szolgáltatások, vagy raktári bevételezést nem igénylő egyéb nem fizikai termékek. Az ilyen termékek létrehozhatók szolgáltatásként, vagy használhat közvetlenül *beszerzési kategóriákat *az ilyen rendelésekre vonatkozó beszerzési rendelésen. Az ilyen rendelések esetén a termékbevételezés néha kihagyásra kerül, és a program közvetlenül leszámlázza a rendelést, vagy a termékbevételezés regisztrálása a beszerzési rendelésben történik, korábbi beérkezési regisztráció nélkül.  

A termékbevételezés adott célra vonatkozó automatikus felhasználást eredményezhet. Ilyen például a közvetlen kiszállításos felhasználás, a projektet érintő felhasználás, illetve a termék tárgyi eszközként történő lekönyvelése.  

Amikor a szállítótól beérkezik a* szállítói számla*, úgy annak első rögzítése történhet a *számlajegyzékbe *, a beszerzési rendeléstől függetlenül, hogy az aztán később kerüljön jóváhagyásra a beszerzési rendeléshez kapcsolódó rekordként. A szállítói számla a beszerzési rendeléssel együtt történő rögzítése magában foglalja a termékbevételezés és a számla egyeztetését is.  

A beszerzési rendelésben tud *könyvelési felosztást* adni meg annak rögzítésére, hogy az milyen főkönyvi könyvelést igényel, illetve hogy hogyan történik a költségvetési források felosztása, ha szerepel ilyen tétel a konfigurációjában.  

A leszámlázott beszerzési rendelések a kötelezettséget rögzítik a szállítói számlába a kötelezettségeken belül, ahol lehetőség nyílik a *sz*á*llítói kifizetés *feldolgozására.

## <a name="vendor-performance"></a>Szállító teljesítménye
A teljesítményt, illetve a beszerzés felülvizsgálatát *beszerzési és kötelezettségjelentések* támogatják, melyek kitérnek a költések, illetve a szállítói teljesítmény elemzésére is.


