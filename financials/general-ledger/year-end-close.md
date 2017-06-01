---
title: "Év végi zárás"
description: "Ez a témakör Főkönyv év végi zárási eljárására vonatkozó folyamat beállítását és futtatását mutatja be."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerClosingSheet
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 50a6a23febc725eb05d30d5db4f97ca699607461
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="year-end-close"></a>Év végi zárás

[!include[banner](../includes/banner.md)]


Ez a témakör Főkönyv év végi zárási eljárására vonatkozó folyamat beállítását és futtatását mutatja be. 

A pénzügyi év végén le kell futtatni az év végi zárási folyamatot, a nyitóegyenlegek átviteléhez az új évbe. A legtöbb szervezet több alkalommal is lefuttatja az év végi zárás folyamatát. Az első alkalommal az egyenlegek átkerülnek az pénzügyi évbe. Az év végi zárás ezt követően tetszőleges alkalommal újra lefuttatható annak érdekében, hogy a korrekciós bejegyzések egyenlegeit átvihesse az új pénzügyi évbe. 

Az év végi zárás folyamata során kétféle lehetséges tranzakció hozható létre. Egy Nyitó tranzakció mindig létrejön, és használatával létrehozhatók a nyitó egyenlegek az új pénzügyi évre. A Nyitó tranzakció megjeleníti a mérleg főkönyvi számla szerinti egyenlegét az új pénzügyi évre, továbbá a nyereség/veszteség főkönyvi számla egyenlegeit a visszatartott bevételek főkönyvi számlájában az új pénzügyi évre vonatkozóan. A záró tranzakció opcionálisan létrejön annak érdekében, hogy a nyereség/veszteség számlák egyenlege lenullázódjon a lezárni kívánt pénzügyi évnél.

## <a name="prepare-to-run-the-year-end-close"></a>Felkészülés az év végi zárás lefuttatásához
Mielőtt futtatná az év végi zárás folyamatát, ellenőrizze a következő beállításokat: 

A **Fő számla** lapon:

-   Győződjön meg róla, hogy a **Főszámla típusa** meghatározása megfelelő minden egyes főszámlánál. A főszámla típusának segítségével határozza meg, hogy a főszámla egyenlege nyitó egyenlegként vagy fenntartott bevételként zárolva kerüljön-e át a Nyitott tranzakcióba.
-   A **Nyitó számla** mező használható arra, hogy átvigye a főszámla egyenlegét egy új számlára az év végi zárás során. Az új fő számla bekerül a **Nyitó számla** mezőbe. Ezt jellemzően a mérleg fő számláiként használja a rendszer olyankor, amikor a főszámla inaktívvá válik, és egy új fő számlát fog használni az új pénzügyi évben.

A **Főkönyvi paraméterek** oldalon, a **Pénzügyi év zárása** alatt:

-   Az **Évzáró tranzakciók törlése átvezetés közben** beállítással adható meg, hogy egy korábbi év végi zárás rendszer által generált Nyitó tranzakciója törlődjön-e az év végi zárás újabb futtatásakor. Ha a beállítás értéke **Igen**, akkor az előző Nyitó tranzakciót törli a rendszer, majd létrehoz egy újat a jelenlegi egyenlegek alapján. Ha a beállítás értéke **Nem**, akkor megmarad a korábbi Nyitó tranzakció, és létrejön még egy Nyitó tranzakció annak érdekében, hogy áthelyezhessék azokat a korrekciós tranzakciókhoz tartozó egyenlegeket, amelyeket az előző év végi zárás után adtak fel.
-   A **Záró tranzakciók létrehozása átvezetés közben** beállítás használatával hozhatók létre Záró tranzakciók a zárás alatt lévő pénzügyi évben annak érdekében, hogy az eredményszámlák egyenlegét ki lehessen nullázni. Ha a beállítás értéke **Igen**, akkor egyaránt létrejön a Nyitó tranzakció és a Záró tranzakció. Ha a beállítás értéke **Nem**, csak a Nyitó tranzakció jön létre a következő pénzügyi évben az egyenlegek átviteléhez. Az eredményszámla egyenlegei megmaradnak a pénzügyi év végén.
-   A **Pénzügyi év beállítása Véglegesen lezárt állapotúra** beállítás segítségével állítható pénzügyi év véglegesen lezárt állapotúra. Óvatosan használja ezt a beállítást, mert a véglegesen lezárt állapotú időszakok már nem nyithatók meg újra, és ennek következtében már nem lehet feladni korrekciókat a pénzügyi évhez. Az ajánlott gyakorlat a beállítás **Nem** értékre állítása.
-   **A bizonylatszám megadása kötelező** beállítás segítségével adható meg, hogy meg kell-e adni bizonylatszámot az év végi zárás folyamatának futtatásakor. Ajánlott a bizonylatszám kérése, mert ezáltal egyszerűen azonosítható a Nyitó tranzakció.

A **Pénzügyi naptár** oldalon:

-   A következő pénzügyi évnek léteznie kell az év végi zárás lefuttatása előtt. A következő pénzügyi év megadása kötelező annak érdekében, hogy létre lehessen hozni a kezdő egyenlegeket a nyitó időszakban.

A **Főkönyvi naptár** oldalon:

-   Nem kötelező: A lezárás alatt lévő pénzügyi év **Várakoztatott** állapotra állítható annak érdekében, hogy ne lehessen új tranzakciókat beírni. Korrekciós bejegyzések azonosítását követően a Várakoztatott időszakok újranyithatók annak érdekében, hogy korrekciós bejegyzéseket adhasson fel, még akkor is, ha az év végi zárás folyamatát már lefuttatták.

## <a name="define-year-end-close-templates"></a>Év végi zárás sablonjainak meghatározása
A rendszer konfigurálását követően futtatható az év végi zárás folyamata. Az **Év végi zárás** oldalon meghatározható egy sablon azoknak a jogi személyeknek a csoportja számára, amelyeknél le lesz futtatva az év végi zárás folyamata. A sablont minden egyes év végi zárásnál alkalmazza a rendszer, de az módosítható a szervezet változásai esetén. 

Először határozza meg a sablonhoz tartozó **Csoportnév** értékét, majd válassza ki a pénzügyi naptárat. A csoportnév azonosítja a jogi személyek mellékelt csoportját.  A sablonok például megadhatók földrajzi adatok alapján, ezáltal különálló csoportok jönnek létre az Észak-Amerikai jogi személyei, az EMEA térség jogi személyei, illetve az APAC térség jogi személyei számára. 

Ezt követően hozzá lehet adni a jogi személyeket a sablonhoz. Jogi személyek hozzáadhatók szervezeti hierarchia vagy a kívánt jogi személyek kiválasztásával. Ha kiválaszt egy szervezeti hierarchiát, akkor csak azok az adott hierarchián belüli jogi személyek kerülnek a sablonhoz, akik a kijelölt pénzügyi naptárt használják. Ha jogi személyeket szeretne a sablonhoz adni, csak azonos pénzügyi naptárral rendelkező jogi személyeket vehet fel. Ugyanaz a pénzügyi év szükséges, mert az év végi zárás futtatása egy pénzügyi év kiválasztásával történik, amely naptárról naptárra változó lehet. 

A jogi személyek felvétele után határozza meg a visszatartott bevételek főszámláját minden egyes jogi személyre vonatkozóan. Az **Utolsó év végi zárás dátuma** mező értéke frissül minden egyes alkalommal, amikor lefuttatják az év végi zárás folyamatát a jogi személyre vonatkozóan. 

A **Pénzügyi dimenzió** lap segítségével meghatározható, hogy mely pénzügyi dimenziókat használja majd a rendszer a Nyitó tranzakciónál. Kérjük, vegye figyelembe, hogy a megadott beállítások csak a **Jogi személyek** rácsban kiválasztott jogi személyre vonatkoznak. A beállítást a rácsban szereplő minden egyes jogi személy esetében meg kell ismételni. 

A **Mérlegdimenziók átvitele** beállítással határozható meg, hogy a mérlegszámlákra feladott tranzakciók pénzügyi dimenziói megmaradjanak-e a Nyitó tranzakciónál. Az ajánlott gyakorlat a beállítás **Igen** értékre állítása. Az **Eredménydimenziók átvitele** beállítás segítségével adható meg, hogy a tranzakciók mely, az eredményszámlákra feladott pénzügyi dimenziói lesznek átküldve a visszatartott bevételek főszámlájára. Először azonosítsa a kiválasztott személyre releváns pénzügyi dimenziókat. Ez magában foglal minden olyan pénzügyi dimenziót, amelyet feladtak az év során; még akkor is, ha az adott pénzügyi dimenzió nem része egy aktív számlastruktúrának. Ezt követően minden egyes dimenziónál adja meg az **Egyetlen lezárása** vagy **Az összes lezárása** beállítást.  Az alapértelmezett érték **Az összes lezárása**, ami megtartja az eredeti pénzügyi dimenzióértékeket a feladott tranzakcióknál, és segítségükkel hozza létre a nyitó egyenlegeket a visszatartott bevételek számláinál. A fenntartott bevételek különálló nyitó egyenlegei létrejönnek a pénzügyi dimenzióértékek minden egyedi kombinációjához. Az **Egyetlen lezárása** kiválasztása esetén minden, az adott pénzügyi dimenzióval feladott tranzakció összesítve lesz a fenntartott bevételek nyitó egyenlegében az **Egyetlen lezárása** után megadott mezőben. Tegyük fel például, hogy a pénzügyi év összes tranzakcióját a Főszámla – Részleg számlastruktúrával küldték be. A sablon Részleg pénzügyi dimenziója részénél az **Egyetlen lezárása** beállítás van kiválasztva, és a 100-as érték van megadva. Ha a 200, 300 és 400 részlegekhez feladott összes bevétel 100 000 USD, akkor egy nyitó egyenleg jön létre a Fenntartott bevételek – 100 részére. Ha az **Összes lezárása** lehetőséget választja, és a pénzügyi dimenzió értékét üresen hagyja, akkor minden tranzakció úgy adódik fel, hogy az adott dimenzióérték üres lesz. 

Az év végi zárás folyamata nem felel meg a számlastruktúráknak. Ez azért van, mert a számlastruktúrák módosulhatnak egy pénzügyi év során, és az adott módosítások miatt nem mindig azonosítható a releváns számlastruktúra.  A nyitó tranzakciók létrehozásakor az egyenlegek előrekerülnek a pénzügyi dimenziókkal, ahogyan azok meg vannak határozva az év végi zárás sablonjában. A kezdő egyenlegek bejegyzései olyan pénzügyi dimenziókat is tartalmazhatnak, amelyek már nincsenek a jelenlegi számlastruktúrában, illetve azokat a szegmenskombinációkat, amelyek már nem érvényesek a jelenlegi számlastruktúrában. Ha szervezete ki szeretne zárni egy pénzügyi dimenziót a fenntartott bevételek nyitóegyenlegénél, állítsa a pénzügyi dimenziót **Egyetlen lezárása** értékre, és hagyja üresen a dimenzióértéket.

## <a name="run-the-year-end-close-process"></a>Év végi zárás folyamatának lefuttatása
Az év végi zárás sablonjainak létrehozását követően az év végi zárás folyamata a **Pénzügyi év futtatása** lehetőség Művelet panelen történő kiválasztásával indítható el. Válassza ki az összes jogi személyt vagy azon részhalmazukat, amelyeken futtatni kívánja az év végi zárást. Amikor egy pénzügyi évre vonatkozóan először futtatja le az év végi zárást, valószínűleg ki fogja választani az összes jogi személyt annak érdekében, hogy kezdő egyenlegeket hozzon létre az összes jogi személyhez. Ha ismét lefuttatja az év végi zárást, akkor úgy is dönthet, hogy a folyamatot csak azoknál a jogi személyeknél futtatja le, amelyeknél a korrekciós bejegyzéseket beküldték. 

Válassza ki azt a pénzügyi évet, amelynél le szeretné futtatni az év végi zárást. Ha egynél több zárási időszak létezik a pénzügyi év utolsó időszakára, akkor az **Időszak neve** mező elérhetővé válik, és Ön kiválaszthatja, hogy melyik zárási időszak küldje be a Záró tranzakciót, amennyiben a beállítások szerint létre kell hozni azt. 

Adjon meg egy bizonylatszámot, ami lehet, hogy kötelező, az Általános főkönyv paramétereinek beállításai alapján. Ugyanazt a bizonylatszámot használja a rendszer az év végi zárás folyamatához kiválasztott minden jogi személy esetében. A bizonylatszám létrehozásához nem használatos számsorozat. Ajánlott eljárás megadni egy bizonylatszámot még akkor is, amikor az nem kötelező. A bizonylatszámszám megadása leegyszerűsíti a Nyitó tranzakció kikeresését az új pénzügyi évben. Ha nem ad meg bizonylatszámot, akkor a bizonylat üres lesz a Nyitó tranzakciónál. 

Ha sztornózni szeretne egy előző év végi zárást a kiválasztott pénzügyi évre vonatkozóan, állítsa az **Előző zárás visszavonása** beállítást **Igen** értékre. Az év végi zárás visszavonásra kerül, de a folyamat bármikor újrafuttatható. Ha visszavon egy év végi zárást, akkor nem lesz elérhető az **Utolsó év végi zárás dátuma** értéke. 

Az év végi zárás folyamata alapértelmezés szerint kötegelt módban fut. A kötegelt módban való futtatás az ajánlott eljárás, mert ez lehetővé teszi a további tevékenységekhez való visszatérést. Miután befejeződött az év végi zárás folyamata, az **Utolsó év végi zárás dátuma** mező frissül a munkamenet dátumával.

További tudnivalókért lásd: [A főkönyv lezárása időszak végén](close-general-ledger-at-period-end.md).




