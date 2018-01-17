---
title: "Vevői és szállítói kompenzáció beállítása"
description: "Ez a témakör arról nyújt információkat, hogy miként futtathat kompenzációs folyamatot az olyan szállítói és vevőszámlák esetében, amelyeknek elsődleges címe Magyarországon vagy Lengyelországban van."
author: mrolecki
manager: AnnBe
ms.date: 05/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustTable, CustVendCompensation, VendTable, CustTrans, VendTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations, Core
ms.custom: 1691503
ms.search.region: Hungary, Poland
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 4530f62ee25f4ac70005d11885762192d6baae11
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-customer-and-vendor-compensation"></a>Vevői és szállítói kompenzáció beállítása
Ez a témakör olyan információkat nyújt, amelyek segítségével lefuttathatja a kompenzációs folyamatot az olyan szállítói és vevőszámlák esetében, amelyeknek elsődleges címe Magyarországon vagy Lengyelországban van.

A kelet-európai felhasználóknak gyakran követeléseket és kinnlevőségeket kell kezelniük egy olyan vállalatnál, amely vevőként és szállítóként egyaránt regisztrálva van a rendszerben. Ez az elszámolási eljárás egy olyan jogi eljárást alkalmaz, amelynek elnevezése *kompenzáció* vagy *nettóérték-számítás*. 

## <a name="enabling-compensation"></a>Kompenzáció engedélyezése

### <a name="set-up-compensation-notes"></a>Kompenzációs megjegyzések beállítása
Beállíthat értesítéseket, amelyeket a rendszer kinyomtat a kompenzációs levél számára. Az **Adatlap megjegyzései** oldal a **Beállítás** > **Űrlapok** pontnál nyitható meg a következőknél: Kinnlevőségek, Kötelezettségek, illetve Projektvezetés és könyvelés.

Új formanyomtatvány létrehozásakor kiválaszthatja annak a kompenzációs levélnek a részét, amelynél a megjegyzést be szeretné állítani:

 - **Kompenzációs levél – fejléc** – A kompenzációs levél felső része, például a vállalatnév.
 - **Kompenzációs levél – kinnlevőség** – A kinnlevőséggel kapcsolatos kompenzációs levél szövege.
 - **Kompenzációs levél – kötelezettség** – A kötelezettséggel kapcsolatos kompenzációs levél szövege.
 - **Kompenzációs levél – egyenleg** – Az egyenleggel kapcsolatos kompenzációs levél szövege.

A formanyomtatvány és a nyelv minden megfelelő kombinációjához megadhat jegyzetet.

A formanyomtatvány alapja annak az egyenlegösszegnek a matematikai jele, amely a kompenzációs jelentésben található:

- Ha az egyenleg összege nullánál magasabb, akkor a kinnlevőségekkel kapcsolatos kompenzációs értesítést nyomtatja ki a rendszer.
- Ha az egyenleg összege nullánál alacsonyabb, akkor a kötelezettséggel kapcsolatos kompenzációs értesítést nyomtatja ki a rendszer.
- Ha az egyenleg összege megegyezik a kompenzációs levéllel, akkor az egyenlegértesítést nyomtatja ki a rendszer.

### <a name="set-up-a-vendor-and-a-customer"></a>Szállító és vevő beállítása
A jogi személyek és magánszemélyek vevőként vagy szállítóként adhatók hozzá a vállalathoz A kompenzációs opvió csak a kapcsolódó feleknél érhető el. A társítás beállításához nyissa meg a vevői vagy a szállítói fiókot, majd a **Vegyes** lapon, az **Átutalás** mezőcsoportban válasszon ki egy társított partnerszámlát: **Vevői számla** a szállítói alapadatokhoz vagy **Szállítói számla** a vevői alapadatokhoz.

### <a name="create-a-compensation-journal"></a>Kompenzációs napló létrehozása
Opcionálisan létrehozhat egy naplót, amelyet egy kompenzációs ajánlat bemutatására használ majd a rendszer. Fel is adhatja az ajánlatot, illetve kinyomtathat egy kompenzációs jelentést is. Lépjen az **Általános napló** > **Naplóbejegyzések** > **Általános naplók** ponthoz.

## <a name="record-transactions"></a>Tranzakciók rögzítése
Általában minden, a kapcsolódó vevői és szállítói számlákra rögzített számla elérhetők, és használható kompenzációra: 

 - Értékesítési számlák (**Kinnlevőségek** > **Rendelések** > **Minden értékesítési rendelés**)
 - Szabadszöveges számlák (**Kinnlevőségek** > **Számlák** > **Kizárólag szabadszöveges számlák**)
 - Szállítói számlák (**Kötelezettségek** > **Beszerzési rendelések** > **Minden beszerzési rendelés**)
 - Projekt értékesítési számlái (**Projektvezetés és könyvelés** > **Projektszámlák** > **Projekt számlajavaslatai**)

Bármely nyitott vevői és szállítói tranzakciót is használhat a kompenzációs folyamatban. Ezen tranzakciók közé tartoznak azok a kifizetések és számlák is, amelyek rögzítése a naplókon keresztül történik. 

## <a name="process-a-compensation-letter"></a>Kompenzációs levél feldolgozása
Ha van nyitott vevői és szállítói tranzakciója, akkor elindíthatja a kompenzációs folyamatot. Nyissa meg a **Minden vevő** vagy **Minden szállító** oldalt, majd kattintson a **Tranzakciók** elemre az összes partnertranzakció áttekintéséhez. Válasszon ki egy vagy több nyitott tranzakciót (olyan tranzakciót, amelynek egyenlege nem 0 [zéró]). Ezután kattintson a **Kompenzáció** lehetőségre a **Vevő és szállító tranzakciói - visszatérítés** oldalon. Ezen az oldalon két rács található – egy a vevői tranzakciók és egy a szállítói tranzakciók számára. Az egyik rácson a kiválasztott tranzakciók láthatók. A másik rács a kompenzációra rendelkezésre álló tranzakciókat jeleníti meg. Beállíthat egy vagy több tranzakciót a kompenzációra való megjelöléshez. Miután befejezte tranzakciók kiválasztását, kattintson a **Kompenzáció létrehozása** lehetőségre. A megjelenő párbeszédpanelen a következő mezőket állíthatja be:

 - **Napló** – Új napló készítéséhez válasszon egy naplónevet.
 - **Napló kötegszáma** – Válassza ki egy létező napló kötegszámát.
 - **Tranzakció dátuma** – A naplóbejegyzések tranzakciódátuma.
 - **Térítés jelentésének nyomtatása** – Ezzel az opcióval kinyomtathat egy jelentést, amelyet a rendszer elküld az együttműködő félnek elfogadásra.

Ha beállít egy értéket mind a **Napló**, mind a **Napló kötegszáma** mezőnél, akkor a szám élvez prioritást. Emiatt a tranzakciók létrehozása ebben a naplóban történik, és nem egy új naplóban.

## <a name="process-compensation"></a>Folyamat kompenzáció
Miután létrehozott egy kompenzációs ajánlatot egy naplónál, és az együttműködő fél elfogadta a kompenzációs javaslatát, az általános naplóba léphet, és utána tranzakciókat adhat fel a főkönyvbe a kompenzációk rögzítéséhez. Ha újra kell nyomtatnia egy kompenzációs jelentést, kattintson a **Nyomtatás** > **Kompenzációs levél** pontra egy általános naplósor oldalán.


## <a name="frequently-asked-questions"></a>Gyakori kérdések
**K: Kompenzálhatok tranzakciókat több szállítónál és ügyfélszámlánál egyidejűleg?**

**V:** Egy szállítói számla és egy vevőszámla között lehet átutalási kapcsolat. Emiatt egyidejűleg egy-egy fiók között dolgozhatja fel a kompenzációt.

**K: Használhatok külföldi tranzakciókat a kompenzációnál?**

**V:** Alapértelmezés szerint a kompenzációs funkciót a helyi pénznemben lévő tranzakciók számára terveztük. Használhat ugyanakkor devizatranzakciókat is. Azonban egy általános naplóban meg kell adnia egy átváltási árfolyamot a létrehozandó kompenzációajánlatokra vonatkozóan.

**K: Minden országban vagy régióban rendelkezésre áll a kompenzáció funkciója?**

**V:** A kompenzáció funkció csak azoknál a jogi személyeknél áll rendelkezésre, amelyeknek elsődleges címe Magyarországon vagy Lengyelországban van.

