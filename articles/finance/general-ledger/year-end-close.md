---
title: Év végi zárás
description: Ez a témakör Főkönyv év végi zárási eljárására vonatkozó folyamat beállítását és futtatását mutatja be.
author: kweekley
ms.date: 07/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerClosingSheet
audience: Application User
ms.reviewer: roschlom
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f5b4e8c5103a06f696f863b1eed40b3821f274d7
ms.sourcegitcommit: f2dfec2f4c427e37a574e6acdfaaf150bc92ebb6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/23/2021
ms.locfileid: "6661013"
---
# <a name="year-end-close"></a>Év végi zárás

[!include [banner](../includes/banner.md)]

Ez a témakör Főkönyv év végi zárási eljárására vonatkozó folyamat beállítását és futtatását mutatja be.

A pénzügyi év végén le kell futtatni az év végi zárási folyamatot, a nyitóegyenlegek átviteléhez az új évbe. A legtöbb szervezet több alkalommal is lefuttatja az év végi zárás folyamatát. Az első futtatás az új pénzügyi évre mozgatja át az egyenlegeket. A folyamat ezt követően tetszőleges alkalommal újra lefuttatható annak érdekében, hogy a korrekciós bejegyzések egyenlegeit átvihesse az új pénzügyi évbe.

Az év végi zárás folyamata során kétféle lehetséges tranzakció hozható létre. Egy Nyitó tranzakció mindig létrejön, és használatával létrehozhatók a nyitó egyenlegek az új pénzügyi évre. A Nyitó tranzakció megjeleníti a mérleg főkönyvi számla szerinti egyenlegét az új pénzügyi évre, továbbá a nyereség/veszteség főkönyvi számla egyenlegeit a visszatartott bevételek főkönyvi számlájában az új pénzügyi évre vonatkozóan. A záró tranzakció opcionálisan létrejön annak érdekében, hogy a nyereség/veszteség számlák egyenlege lenullázódjon a lezárni kívánt pénzügyi évnél.

## <a name="prepare-to-run-the-year-end-close"></a>Felkészülés az év végi zárás lefuttatásához

Mielőtt futtatná az év végi zárás folyamatát, ellenőrizze a következő beállításokat:

A **Fő számla** lapon:

- Ellenőrizze, hogy minden fő számlához helyesen van-e beállítva a **Fő számlatípus** mező. A főszámla típusa határozza meg, hogy a főszámla egyenlege nyitó egyenlegként vagy fenntartott bevételként zárolva kerüljön-e át a nyitó tranzakcióba.
- A főszámla egyenlege átvihető egy új számlára az év végi zárás során. Adja meg az új fő számlát a **Nyitó számla** mezőbe. Ezt jellemzően a mérleg fő számláiként használja ezt a mezőt a rendszer olyankor, amikor a főszámla inaktívvá válik, és egy új fő számlát fog használni az új pénzügyi évben.

A **Főkönyvi paraméterek** oldalon, a **Pénzügyi év zárása** alatt:

- Az **Meglévő év végi bejegyzések törlése az év ismételt zárása során** beállítással adható meg, hogy egy korábbi év végi zárás rendszer által generált nyitó tranzakciója törlődjön-e az év végi zárás újabb futtatásakor. Ha a beállítás értéke **Igen**, akkor az előző nyitó tranzakciót és az opcionális záró tranzakciókat törli a rendszer, majd létrehoz egy nyitóm vagy záró tranzakciót a jelenlegi egyenlegek alapján. Ha a beállítás értéke **Nem**, akkor megmarad a korábbi nyitó és opcionális záró tranzakciók megmaradnak , és létrejön még egy nyitó tranzakció annak érdekében, hogy áthelyezhessék azokat a korrekciós tranzakciókhoz tartozó egyenlegeket, amelyeket az előző év végi zárás után adtak fel.
- A **Záró tranzakciók létrehozása átvezetés közben** beállítás használatával hozhatók létre záró tranzakciók a zárás alatt lévő pénzügyi évben annak érdekében, hogy az eredményszámlák egyenlegét ki lehessen nullázni (0). Ha a beállítás értéke **Igen**, akkor egyaránt létrejön a nyitó tranzakció és a záró tranzakció. Ha a beállítás értéke **Nem**, csak a nyitó tranzakció jön létre a következő pénzügyi évben az egyenlegek átviteléhez. Az eredményszámla egyenlegei megmaradnak a pénzügyi év végén.
- A **Pénzügyi év beállítása Véglegesen lezárt állapotúra** beállítás segítségével állítható pénzügyi év véglegesen lezárt állapotúra. Ezt a beállítást körültekintően kell használni, mert a véglegesen lezárt állapotú időszakokat nem lehet újra megnyitni. A korrekciókat ezért nem lehet a pénzügyi évre feladni. Az ajánlott gyakorlat a beállítás **Nem** értékre állítása.
- A **Bizonylatszámot ki kell tölteni** opció el lett távolítva. Az év végi zárási folyamat futtatásakor bizonylatra van szükség. Ekkor a bizonylatszámot manuálisan kell megadni.

A **Pénzügyi naptár** oldalon:

- A következő pénzügyi évnek léteznie kell az év végi zárás lefuttatása előtt. Ellenkező esetben a nyitó egyenlegeket nem lehet létrehozni a nyitó időszakban.

A **Főkönyvi naptár** oldalon:

- Nem kötelező: A lezárás alatt lévő pénzügyi év **Várakoztatott** állapotra állítható annak érdekében, hogy ne lehessen új tranzakciókat beírni. Korrekciós bejegyzések azonosítását követően a várakoztatott időszakok újranyithatók annak érdekében, hogy korrekciós bejegyzéseket fel lehessen adni, még akkor is, ha az év végi zárás folyamatát már lefuttatták.

Az **Év végi zárósablon beállítása** lapon:

- Ha a **Főkönyv év végi fejlesztései** funkció be van kapcsolva, akkor az év végi lezárási sablon beállítási folyamata el van választva az év végi zárási folyamattól. A sablon az **Év végi zárási sablon beállítása** lapján határozható meg (**Főkönyv \> Főkönyv beállítása \> Év végi záró sablon beállítása**), vagy elérhető az év végi zárási folyamatból.

## <a name="define-year-end-close-templates"></a>Év végi zárás sablonjainak meghatározása

A rendszer konfigurálását követően futtatható az év végi zárás folyamata. Az **Év végi zárási sablon beállítása** oldalon meghatározható egy sablon azoknak a jogi személyeknek a csoportja számára, amelyeknél le lesz futtatva az év végi zárás folyamata. A sablont minden egyes év végi zárásnál alkalmazza a rendszer, de az módosítható a szervezet változásai esetén.

Először állítsa be a sablonhoz tartozó **Csoportnév** mező értékét, majd válassza ki a pénzügyi naptárat. A csoportnév azonosítja a jogi személyek mellékelt csoportját. Jogi személyek csoportjainak meghatározásakor ne feledje, hogy a jogi személyek csak akkor szerepelnek ugyanabban a csoportban, ha ugyanazt a pénzügyi naptárat választották ki számukra. A sablonok például megadhatók földrajzi adatok alapján, ezáltal különálló csoportok jönnek létre az Észak-Amerikai jogi személyei, az Európa és Közel-Keket (EMEA) jogi személyei, illetve az Ázsia-Csendes-Óceáni térség (APAC) jogi személyei számára.

Ezt követően hozzá lehet adni a jogi személyeket a sablonhoz. Jogi személyek hozzáadhatók szervezeti hierarchia vagy a kívánt jogi személyek kiválasztásával. Ha kiválaszt egy szervezeti hierarchiát, akkor csak azok az adott hierarchián belüli jogi személyek kerülnek a sablonhoz, akik a kijelölt pénzügyi naptárt használják. Ha jogi személyeket szeretne a sablonhoz adni, csak azonos pénzügyi naptárral rendelkező jogi személyeket vehet fel. Ugyanaz a pénzügyi év szükséges, mert az év végi zárás futtatása egy pénzügyi év kiválasztásával történik, amely naptárról naptárra változó lehet.

A jogi személyek felvétele után határozza meg a visszatartott bevételek főszámláját minden egyes jogi személyre vonatkozóan.

A **Pénzügyi dimenzió** lap segítségével meghatározható, hogy mely pénzügyi dimenziókat használja majd a rendszer a nyitó tranzakciónál. Kérjük, vegye figyelembe, hogy az ezen a lapon megadott beállítások csak a **Jogi személyek** rácsban kiválasztott jogi személyre vonatkoznak. A beállítást a rácsban szereplő minden egyes jogi személy esetében meg kell ismételni.

A **Mérlegdimenziók átvitele** beállítással adható meg, hogy a mérlegszámlákra feladott tranzakciók pénzügyi dimenziói megmaradjanak-e a nyitó tranzakciónál. Az ajánlott gyakorlat a beállítás **Igen** értékre állítása. A mérlegdimenziók beállítása nem befolyásolja a pénzügyi eredmény főkönyvi számláinak meglévő egyenlegeit. Ezeket az egyenlegeket a következő szakaszban meghatározott eredménydimenziók határozzák meg. Például a 2019-es pénzügyi év volt az első lezárt év, és az **Összes lezárása** lehetőséggel lettek kiválasztva a **Részleg** és **Költséghely** dimenziók a lezáráshoz. Ebben az esetben egy részleg és egy költséghely minden egyes kombinációjához külön bevételi számla jött létre a visszatartott eredményhez. A 2020-as pénzügyi évre vonatkozó év végi zárás futtatásakor az előző évből származó pénzügyi eredmény pontosan úgy marad, mint ahogy fel lett adva, még akkor is, ha a **Mérlegdimenziók átvitele** beállítása **Nem**. Az előző év végi zárásból származó mérleg szerinti eredményre feladott egyenlegek soha nem módosulnak.

Az **Eredménydimenziók átvitele** szakaszban adható meg, hogy a tranzakciók mely, az eredményszámlákra feladott pénzügyi dimenziói lesznek átküldve a visszatartott bevételek főszámlájára. Először azonosítsa a kiválasztott személyre releváns pénzügyi dimenziókat. Ezek a pénzügyi dimenziók magukban foglalnak minden olyan pénzügyi dimenziót, amelyet feladtak az év során; még akkor is, ha az adott pénzügyi dimenzió nem része egy aktív számlastruktúrának. Ezt követően minden egyes dimenziónál adja meg az **Egyetlen lezárása** vagy **Az összes lezárása** beállítást. Az alapértelmezett beállítás az **Összes lezárása**. Ez a beállítás megtartja az eredeti pénzügyi dimenzióértékeket a feladott tranzakcióknál, és segítségükkel hozza létre a nyitó egyenlegeket a visszatartott bevételek számláinál. A fenntartott bevételek különálló nyitó egyenlegei létrejönnek a pénzügyi dimenzióértékek minden egyedi kombinációjához. Az **Egyetlen lezárása** kiválasztása esetén minden, az adott pénzügyi dimenzióval feladott tranzakció összesítve lesz a fenntartott bevételek nyitó egyenlegében az **Egyetlen lezárása** után megjelenő mezőben. Tegyük fel például, hogy a pénzügyi év összes tranzakcióját a **Főszámla – Részleg** számlastruktúrával küldték be. A sablon **Részleg** pénzügyi dimenziója részénél az **Egyetlen lezárása** beállítás van kiválasztva, és a **100** érték van megadva dimenzióértéknek.. Ha a 200, 300 és 400 részlegekhez feladott összes bevétel 100 000 USD, akkor egy nyitó egyenleg jön létre a **Fenntartott bevételek – 100** részére. Ha az **Egyetlen lezárása** lehetőséget választja, és a pénzügyi dimenzió értékét üresen hagyja, akkor minden tranzakció úgy adódik fel, hogy az adott dimenzióérték üres lesz.

## <a name="run-the-year-end-close-process"></a>Év végi zárás folyamatának lefuttatása

Az év végi zárási sablonok létrehozása után kezdeményezheti az év végi lezárási folyamatot az **Év végi lezárás** lapon (**Főkönyv \> Időszak lezárása \> Év végi zárás**). Az év végi zárás futtatása előtt felvehet új év végi záró sablonokat, vagy módosíthatja a meglévő sablonokat úgy, hogy az **Év végi zárósablon beállítása** lehetőséget kiválasztva megnyitja a sablonok beállítási lapját.

Válassza ki az év végi zárósablont, majd a munkaablakban válassza az **Év végi zárás futtatása** lehetőséget. Válassza ki az összes jogi személyt vagy azon részhalmazukat, amelyeken futtatja az év végi zárást. Ha egy pénzügyi évre vonatkozóan először futtatja le az év végi zárást, valószínűleg ki fogja választani az összes jogi személyt annak érdekében, hogy kezdő egyenlegeket hozzon létre az összeshez. Ha korábban futtatta az év végi zárást, akkor úgy is dönthet, hogy a folyamatot csak azoknál a jogi személyeknél futtatja újra, amelyeknél a korrekciós bejegyzéseket beküldték.

Ezt követően válassza ki azt a pénzügyi évet, amelynél lefuttatja az év végi zárást. Ha a pénzügyi év utolsó időszakában egynél több záró időszak létezik, elérhetővé válik az **Időszak neve** mező. Ezt követően kiválaszthatja a zárás időszakot, amelyek a záró tranzakció könyveléséhez használ, ha a záró tranzakció létrehozásához meg van adva a beállítás.

Ezután adjon meg egy bizonylatszámot. Ugyanazt a bizonylatszámot használja a rendszer az év végi zárás folyamatához kiválasztott minden jogi személy esetében. A bizonylatszám létrehozásához nem használatos számsorozat.

Az év végi zárás folyamata alapértelmezés szerint kötegelt módban fut. Ennek megfelelően a kezdeményezést követően visszatérhet más tevékenységekhez.

Mivel a számlastruktúrák a pénzügyi év folyamán változhatnak, nem mindig lehet azonosítani a megfelelő számlastruktúrát. Ebből következően az év végi zárás folyamata nem felel meg a számlastruktúráknak. A nyitó tranzakciók létrehozásakor az egyenlegek előrekerülnek a pénzügyi dimenziókkal, ahogyan azok meg vannak határozva az év végi zárás sablonjában. A kezdő egyenlegek bejegyzései olyan pénzügyi dimenziókat is tartalmazhatnak, amelyek már nincsenek a jelenlegi számlastruktúrában, illetve azokat a szegmenskombinációkat, amelyek már nem érvényesek a jelenlegi számlastruktúrában. Ha szervezete ki szeretne zárni egy pénzügyi dimenziót a fenntartott bevételek nyitóegyenlegénél, állítsa be a pénzügyi dimenziót **Egyetlen lezárása** értékre, és hagyja üresen a dimenzióértéket.

A folyamat befejezése után egy rekord jön létre a jogi személy és a pénzügyi év minden egyes kombinációjához. Csak azon jogi személyek rekordjait látja, amelyekhez hozzáféréssel rendelkezik. Minden rekord tartalmazza a folyamat futásának rendszerdátumát és időpontját, valamint közvetlen kapcsolatot az év végi lezáráshoz létrehozott bizonylatokkal.

[![Az Év végi zárás előzményei gyorslapon létrehozott rekordok az Év végi zárás oldalon](./media/run-yr-end-close.png)](./media/run-yr-end-close.png)

Ha újrafuttatja az év végi zárást, a jogi személy és a pénzügyi év egyes kombinációihoz egy vagy több rekord fog látni attól függően,hogy a **Meglévő év végi bejegyzések törlése az év ismételt zárása során** lehetőségnél milyen beállítást adott meg a **Főkönyvi paraméterek** oldalon:

- Ha ennek a lehetőségnek a beállítása **Igen**, az előző év végi zárás bizonylata törölve lesz. A rekord **Sztornózottként** van megjelölve, és a sztornírozás megtörténtének dátumával és dátumával lesz megjelölve. Emellett a bizonylatszámra mutató hivatkozás is törlődik. Amikor az év végi lezárás befejeződik, a létrehozott új bizonylathoz új rekord jön létre.
- Ha a beállítás **Nem**, az előző év végi zárás rekordja megmarad a bizonylatra mutató hivatkozással együtt. Minden alkalommal, amikor az év végi zárás újrafuttatásra kerül, egy új rekord jön létre, az új bizonylatok hivatkozásával együtt.

## <a name="reverse-the-year-end-close-process"></a>Év végi zárás folyamatának sztornírozása

Az **Év végi zárás** oldalon visszavonhatja az év végi zárásokat. Válassza ki a jogi személy és egy pénzügyi év kombinációjának rekordját, amelyet sztornírozni kell, majd válassza az **Év végi zárás visszavonása** lehetőséget. A sztornírozási folyamat törli a pénzügyi évre létrehozott összes nyitó és záró bizonylatot. A rekord **Sztornózottként** van megjelölve, és a sztornírozás megtörténtének dátumával és dátumával lesz megjelölve. Emellett a bizonylatszámra mutató hivatkozás is törlődik. Az év végi zárás folyamatához hasonlóan a sztornírozás kötegelt módban fut.

A rács fölött elérhető **Visszavont megjelenítése** jelölőnégyzettel elrejtheti vagy megtekintheti a visszavont év végi zárási folyamatok rekordjait. Az **Év végi zárási visszavonásas** folyamat futtatása után lehet, hogy be kell jelölnie a **Visszavont megjelenítése** jelölőnégyzetet, hogy a rekord látható legyen. Az egyéb adatok megtekintéséhez további szűrőket is be lehet állítani.

[![A Visszavontak megjelenítése jelölőnégyzet használata a sztornírozott év végi zárási folyamatok rekordjainak az Év végi zárási oldalon való megjelenítése](./media/rvrs-yr-end-close.png)](./media/rvrs-yr-end-close.png)

További tudnivalókért lásd: [A főkönyv lezárása időszak végén](close-general-ledger-at-period-end.md) és [A pénzügyi év lezárása](tasks/close-fiscal-year.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
