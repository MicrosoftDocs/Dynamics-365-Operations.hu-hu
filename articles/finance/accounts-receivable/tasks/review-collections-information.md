---
title: A beszedésekkel kapcsolatos adatok felülvizsgálata
description: Ez a témakör bemutatja a beszedési adatok, valamint a különböző beállítási lehetőségek és beszedési tranzakciók áttekintését.
author: ShivamPandey-msft
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustCollectionsPool, SysQueryForm, CustCollectionsAgent, OMTeamSelectMemberDialog, CustVendReportInterval, CustParameters, CustAgingSnapshot, CustVendAgingBucketLookUp, CustCollectionsPoolsListPage, CustCollectionsContactPart, CustCollections
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6a6916690b9571fcfe103506960032e19fe724df
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8876211"
---
# <a name="review-collections-information"></a>A beszedésekkel kapcsolatos adatok felülvizsgálata

[!include [banner](../../includes/banner.md)]

Ez a témakör bemutatja a beszedési adatok, valamint a különböző beállítási lehetőségek és beszedési tranzakciók áttekintését. Ez az eljárás az USMF bemutatócéget használja.

## <a name="create-customer-pools"></a>Vevőgyűjtők létrehozása
1. A navigációs ablaktáblán ugorjon a **Modulok > Követelések és beszedések > Beállítás > Vevőgyűjtők** lehetőségre.
- Ezen oldal segítségével létrehozhat vevőgyűjtőket, melyek olyan lekérdezések, amelyek meghatározzák a beszedési vagy korosítási folyamathoz megjeleníthető és kezelhető vevői számláknak egy csoportját. Használja a vevőgyűjtőket a **Beszedés** listaoldalon és a kapcsolódó listaoldalakon található adatok szűréséhez. Vevőgyűjtők segítségével továbbá szűrheti a vevői számlákat, amelyek akkor szerepelnek, ha korosítási pillanatképek kerülnek létrehozásra.  
- Vevőgyűjtők segítségével szűrheti a vevői számlákat, amelyek akkor szerepelnek, ha korosítási pillanatképek kerülnek létrehozásra.  
2. Válassza az **Új** lehetőséget.
3. Adjon meg egy értéket a **Csoportazonosító** mezőben.
4. Adjon meg egy értéket a **Csoport leírása** mezőben.
5. Kattintson a **Csoport feltételeinek kiválasztása** elemre.
6. Adjon meg egy értéket a **Feltétel** mezőben.
7. Válassza ki az **OK** lehetőséget.
8. Válassza ki a **Vevőgyűjtő előnézete** lehetőséget.

## <a name="create-collections-agents"></a>Pénzbehajtók létrehozása
1. A navigációs ablaktáblán ugorjon a **Modulok > Követelések és beszedések > Beállítás > Pénzbehajtók** lehetőségre.  
- Ezen oldal segítségével beállíthat dolgozókat beszedéskezelőknek és opcionálisan vevői gyűjtőket is társíthat hozzájuk. A *pénzbehajtó* olyan személy, aki a vevőkkel együttműködik, hogy a kifizetéseket kellő időben behajtsák.  
- Az ezen a lapon beállított beszedéskezelők automatikusan hozzáadódnak egy kinnlevőségkezelő csapathoz. Ha egy csapatot kiválasztanak a **Kötelezettségek paraméterei** oldal **Csapat** mezőjében, a pénzbehajtókat hozzáadja a rendszer a csapathoz. Ha nincs kiválasztott csapat, automatikusan új csapat jön létre Beszedések néven, és a beszedéskezelők ehhez a csapathoz kerülnek hozzáadásra.  
2. Válassza ki a kívánt ügynököt, majd a **Hozzáadás** elemet a lapon.
3. A **Készlet azonosítója** mezőben válassza ki a kívánt rekordot a legördülő menüből.
4. Jelölje be az **Alapértelmezett csoport** jelölőnégyzetet, vagy törölje a jelet.
- Jelölje be ezt az opciót a kiválasztott pénzbehajtóhoz tartozó összes vevőgyűjtő megjelenítéséhez a szűrőlistában. Ha ez a lehetőség nincs bejelölve, a szűrőlistákban csak a pénzbehajtóhoz rendelt vevőgyűjtők érhetők el.  

## <a name="create-aging-period-definition"></a>Korosítási időszak definíciójának létrehozása
1. A navigációs ablaktáblán ugorjon a **Modulok > Követelések és beszedések > Beállítás > Korosítási időszak definíciói** elemre.
- A korosítási időszakok definícióinak segítségével elemezheti a vevői és a szállítói számlák lejáratát a megadott dátum alapján. A korosítási időszakok definíciójában beállított minden korosítási időszak egy oszlopnak felel meg azon a listaoldalon, illetve azon a képernyőn vagy jelentésben, amelyben az elemzést végrehajtja.  
2. Válassza az **Új** lehetőséget.
3. Írjon be egy értéket a **Korosítási időszak definíciója** mezőbe.
4. Írjon egy értéket a **Leírás** mezőbe.
- Adja meg az időszak nevét, egységét és időközét minden egyes korosítási időszak esetén a korosítási időszak definíciójában. Az a sor, amelynél az Egység mező értéke 0 (zérus), mutatja az elemzés futásának dátumát. A 0 előtti sorok alapértelmezett értéke -1, a 0 után sorok alapértelmezett értéke pedig 1 az Egység mezőben, de módosíthatók. A sorok újrarendezéséhez válassza ki a **Fel** vagy **Le** lehetőséget. A 0 (zéró) sort nem lehet mozgatni.  
- Helyezze a kurzort oda, ahova be szeretné illeszteni az új sort, majd kattintson a **Hozzáadás** gombra.  
- Válasszon egy jelölőt a korosítási időszak **Beszedések** képernyőn és listalapon való feltüntetésére. Például választhat zöld jelölőt az aktuális időszakokhoz, sárga jelölőt a 30 napon túli időszakokhoz, és piros jelölőt a 90 napon túli időszakokhoz.  
- Válassza ki a korosítási időszak definíciójának nyomtatási irányát. Ez a beállítás határozza meg, milyen sorrendben jelennek meg az oszlopok a Vevők korosítása vagy a Szállítók korosítása jelentésen.  
  - Előre – A rendszer ugyanabban a sorrendben nyomtatja ki az oszlopokat, ahogyan a fejlécek a táblázatban jelennek meg, a legfelső sortól indulva.  
  - Vissza – A rendszer pont fordított sorrendben nyomtatja ki az oszlopokat, mint ahogyan a fejlécek a táblázatban megjelennek, a legalsó sortól indulva.    

## <a name="setup-collections-parameters"></a>Gyűjtőparaméterek beállítása
1. A navigációs ablaktáblán ugorjon a **Modulok > Követelések és beszedések > Beállítás > Kinnlevőségek paraméterei** elemre.
2. Válassza ki a **Beszedések** lapot.
3. Bontsa ki vagy csukja össze a **Beszedések alapértékei** szakaszt.
- Válasszon ki egy korosításiidőszak-definíciót a **Beszedések** képernyőn használandó alapértelmezett korosítási pillanatképhez.  
- Válasszon ki egy olyan csapatot, amelyhez a **Pénzbehajtó** képernyőn hozzá vannak rendelve pénzbehajtók. A listában csak olyan csapatok jelennek meg, amelyek Beszedések csapattípussal rendelkeznek.  
4. Bontsa ki vagy csukja össze a **Veszteségleírás** szakaszt.
- Válassza ki azt a napi főkönyvi naplókhoz beállított naplónevet, amelyet tranzakciók **Beszedések** képernyővel vagy kapcsolódó listaoldalakkal való leírásakor kíván használni.  
- Válassza ki az alapértelmezett okkódot, amelyet a rendszer a **Beszedések** képernyőn vagy a kapcsolódó listaoldalakon létrehozott leírási tranzakciók létrehozásakor használ.  
- Ezen opció bejelölésével külön naplósort hozhat létre az áfa számára, amikor veszteségleírási tranzakciót hoz létre a **Beszedések** lapon vagy kapcsolódó listalapon. Ha bejelöli ezt az opciót, akkor könnyebben nyomon követheti a forgalmiadó-összegeket a leírási tranzakciókban. A forgalmiadó-összegeket külön követheti nyomon, így egyszerűbben korrigálhatja a forgalmiadó-kötelezettségét az érintett periódusban.  
5. Bontsa ki vagy csukja össze az **E-mail-sablon** szakaszt.
- Válassza ki azt az e-mail-sablont, amelyet e-mail-üzenetek következővel történő küldésekor kíván használni: **E-mail > Tranzakciók** a kapcsolattartónak művelet a **Beszedések** képernyőn.  
- Válassza ki azt az e-mail-sablont, amelyet vevői számlakivonat-csatolmánnyal ellátott e-mail-üzenetek következővel történő küldésekor kíván használni: **E-mail > Kivonat** a kapcsolattartónak művelet a **Beszedések** képernyőn.  
- Válassza ki azt az e-mail-sablont, amelyet e-mail-üzenetek következővel történő küldésekor kíván használni: **E-mail > Üzletkötői tranzakciók** művelet a **Beszedések** képernyőn.  

## <a name="age-customer-balance"></a>Vevői egyenleg korosítása
1. A navigációs ablaktáblán ugorjon a **Modulok > Követelések és beszedések > Időszakos feladatok > Vevői egyenlegek korosítása** lehetőségre.
- Válassza ki a korosítási időszak definícióját. A korosítási pillanatkép folyamat a a kijelölt korosításiidőszak-definícióban meghatározott korosítási időszakok szerint korosítja a tranzakciókat.  
- Válassza ki a vevőgyűjtőt, vagy hagyja ezt a mezőt üresen, ha azt szeretné, hogy a rendszer az összes vevőre hozzon létre korosítási pillanatfelvételt. Ha egy vevőgyűjtő be van jelölve, akkor a korosítási pillanatkép folyamat csak az adott vevőgyűjtőhöz tartozó vevőkódokra vonatkozik. A kijelölt vevőgyűjtőnek Korosítási pillanatfelvétel típusúnak kell lennie.  
- A korosítási pillanatkép alapjául szolgáló dátum típusának megadása.  
  - Tranzakció dátuma – Az egyes tranzakció korosítása a tranzakció dátuma alapján.    
  - Határidő – Az egyes tranzakciók korosítása az esedékességi dátumuk alapján.    
  - Bizonylat dátuma – Az egyes tranzakciók korosítása a bizonylati dátumuk alapján.  
- Válassza ki a korosítási pillanatképhez aktuális dátumként használni kívánt dátumot. A korosítási időszakok számítása ezen a dátumon alapul.    
  - Mai dátum – A rendszerdátum használata. Akkor válassza ezt a lehetőséget, ha a feldolgozás ismétlődő kötegként van beállítva. Ha ezt a dátumot használja, az ismétlődő köteget rendszeres időközönként futtathatja, mindig az aktuális rendszerdátummal.    
  - Kiválasztott dátum – Egy szabadon választott dátum használata. Ha ezt a lehetőséget választja, akkor adjon meg egy korosítási dátumot is.  
2. Válassza ki az **OK** lehetőséget.

## <a name="view-aged-customer-balances"></a>Korosított vevői egyenlegek megtekintése
1. A navigációs ablaktáblán ugorjon a **Modulok > Követelések és beszedések > Beszedések > Korosított egyenlegek** lehetőségre.
- Ez a listalap a vevői egyenlegek és a korosított összegek korosítási időszak szerinti megtekintésére használható. A program egy korosítási pillanatképben tárolja ezt az információt. A korosítási időszakok meghatározása a korosítási időszak használt definíciója alapján történik. A korosítási időszak definíciója a vevőgyűjtőből származik, ha meg volt adva a gyűjtő lekérdezéséhez. Ha a vevőgyűjtő nem tartalmazza a korosítási időszak definícióját, akkor a program a korosítási időszaknak a Kinnlevőségek paraméterei képernyőn megadott alapértelmezett definícióját használja.  
2. Bontsa ki a **Névjegy** adatterületet. Itt a következő névjegyadatokat tekintheti meg:
- A vevő beszedési kapcsolattartója.  
- A vevőhöz tartozó alapértelmezett értékesítő.  
3. Bontsa ki a **Hitelkeret** adatterületet.
- Használja a **Hitelinformációk** adatterületet a hitelkeret és a vevő aktuális egyenlegadatainak megtekintéséhez.  

## <a name="view-customer-collections-details"></a>Kintlevőségek részleteinek megtekintése
1. Győződjön meg róla, hogy a kívánt rekord ki van választva.
2. Az adott információ megtekintéséhez bontsa ki a **Cím**, **Névjegy**, **Korosítás** és **Hitelkeret** adatterületet.
3. A Művelet ablaktáblán válassza ki a **Beszedés** elemet.
- Frissítse a vevő korosítási pillanatképét, a tranzakciók dátumát az aktuális dátummal, mint korosítási dátummal összehasonlítva. Ha a korosítási pillanatkép több jogi személy adatait tartalmazza, akkor a frissített korosítási pillanatkép ugyanazoknak a jogi személyeknek az adatait fogja tartalmazni. Alapértelmezés szerint az összegek azon jogi személy könyvelési pénznemében tárolódnak, amelyikkel a korosítási pillanatkép frissítésekor bejelentkezett.  
- Válassza ki a korosítási időszak definícióját. Alapértelmezés szerint a korosítási időszaknak az a definíciója jelenik meg, amely a vevő korosítási pillanatképéhez van társítva. A korosítási időszak definíciója meghatározza a korosítási időszakokat és azokat az összegeket, amelyeket a **Korosított egyenlegek** és **Hitelinformációk** adatterületek jelenítenek meg.  
- A következő elemeket tartalmazó menü megnyitása:    
  - Vállalat – Összegek megjelenítése a Korosított egyenlegek és a Hitelinformációk adatterületekben a jogi személy könyvelési pénznemében.  
  - Vevő – Összegek megjelenítése a Korosított egyenlegek és Hitelinformációk Adatterületekben a vevő pénznemében.  
- Válasszon ki egy vagy több jogi személyt a vevő korosítási pillanatképében, amellyel kapcsolatos információkat meg szeretne tekinteni. A listában megjelenő jogi személyek kiválasztása a korosítási pillanatkép létrehozásakor történt.  
- A vevő kivonat megtekintése Microsoft Excel formátumban. Megválaszthatja a kivonatban szerepeltetni kívánt tranzakciótartomány kezdő dátumát, és eldöntheti, hogy csak nyitott tranzakciók szerepeljenek, vagy nyitott és kiegyenlített tranzakciók egyaránt. Ha a korosítási pillanatkép több jogi személyre vonatkozó adatot tartalmaz, minden jogi személyre vonatkozó tranzakció szerepel.  
- Nyissa meg a **Dokumentumok** képernyőt, ahol dokumentumokat és jegyzeteket hozhat létre vagy szerkeszthet.  
4. A Műveleti ablaktáblán válassza ki a **Kommunikáció** lehetőséget.  
- Nyissa meg az Outlook programot, ahol az e-mail üzenet küldhet a Névjegy mezőben megadott névjegynek. Ha nincs megadva beszedési kapcsolattartó, a vevő elsődleges címe lesz használatban. Ha nincs megadva elsődleges kapcsolattartó, az e-mail-üzenetek a **Kapcsolattartók** képernyőn elsőként szereplő címre lesznek küldve. A kiválasztott tranzakciókat csatolmányként tartalmazza az üzenet. A csatolmány Excel formátumú és három munkalapot tartalmaz. A vevőknek küldött e-mail-üzenetekhez használt sablon megadható a **Kinnlevőségek paraméterei** képernyőn.  
- Ez a gomb nem érhető el, ha az ezen a képernyőn kiválasztott ügyfél nem rendelkezik beállított e-mail címmel.  
- Készítsen elő egy kivonatot, és nyissa meg az Outlook programot, ahol a kivonatot csatolmányként tartalmazó e-mailt küldhet a **Névjegy** mezőben megadott címre. Ha nincs megadva beszedési kapcsolattartó, a vevő elsődleges címe lesz használatban. Ha nincs megadva elsődleges kapcsolattartó, az e-mail-üzenetek a **Kapcsolattartók** képernyőn elsőként szereplő címre lesznek küldve.  
- Ez a gomb nem érhető el, ha az ezen a képernyőn kiválasztott ügyfél nem rendelkezik beállított e-mail címmel.  
- Nyissa meg az Outlook programot, ahol e-mail üzenetet küldhet annak az alkalmazottnak, aki a vevőhöz hozzárendelt értékesítési csoport üzletkötőjeként van megadva. Amennyiben ki vannak választva tranzakciók, ezeket csatolmányként tartalmazza az üzenet. A csatolmány Excel formátumú és két munkalapot tartalmaz. Az értékesítőknek küldött e-mail-üzenetekhez használt sablon megadható a **Kinnlevőségek paraméterei** képernyőn.  
- Ez a gomb nem érhető el, ha az ezen a képernyőn megjelenített értékesítő nem rendelkezik beállított e-mail címmel.  
- A vevőhöz tartozó tranzakciók megjelenítése és az ezeken való műveletek végrehajtása. Amennyiben központosított kifizetéseket használ, minden, a vevő korosítási pillanatképében szereplő jogi személyre vonatkozó adat szerepel. Korlátozhatja a jogi személyek adatait a **Kiválasztás** csoport **Vállalat** elemének kiválasztásával a műveleti ablaktáblán.  
- Módosítsa a kiválasztott tranzakció beszedési állapotát.    
  - Nem vitatott – nem történt beszedési művelet a tranzakcióval kapcsolatban.    
  - Vitatott – a vevő értesítette, hogy probléma merült fel a tranzakcióval kapcsolatban.    
  - Ígért kifizetésű – a vevő elfogadta a tranzakció összegének kifizetését.    
  - Megoldott – a tranzakcióval kapcsolatos összes problémát megoldották, és nincs szükség további beszedési műveletre.  
- Nyisson meg egy menüt, és válasszon egyet a következő elemek közül annak meghatározására, hogy mely tranzakciók jelenjenek meg ezen az űrlapon:    
  - Nyitott – Csak ki nem egyenlített tranzakciók megjelenítése.    
  - Nyitott és lezárt – minden tranzakciót megjelenít, a kiegyenlítettet és a nem kiegyenlítettet is.  
- A kiválasztott fizetés feldolgozása, mint elégtelen fedezettel (NSF) rendelkező kifizetés.    
  - Ez a gomb csak akkor érhető el, ha a kiválasztott tranzakció egy kifizetés a kifizetési naplóba beírva (követelés számla nélkül), a tranzakcióhoz hozzá van rendelve egy bankszámla, és a kifizetést korábban nem vonták vissza.  
- Írja le a kijelölt tranzakciókat.  
- Jelölje be a kiválasztott tranzakciókat kiegyenlítendőként.  
- Nyissa meg az **Eredeti dokumentum** képernyőt, amelyben megtekintheti és kinyomtathatja a kijelölt tranzakció dokumentumát.  
- A következő elemeket tartalmazó **menü** megnyitása:    
  - Beszedés – Csak a Beszedések képernyőn létrehozott tevékenységek megjelenítése.    
  - Mind – A vevő összes tevékenység megjeleníti, függetlenül attól, hogy a tevékenységeket hol hozta létre.  
- A következő elemeket tartalmazó **menü** megnyitása:    
  - Nyitott – Csak a nem lezárt tevékenységek megjelenítése.    
  - Nyitott és lezárt – megjeleníti az összes tevékenységet, az állapotukra való tekintet nélkül.  
- Válassza ki a vevőhöz rendelt beszedési eseteket, vagy hagyja üresen a mezőt. Ha az eset be van jelölve, csak a tranzakciók és az esethez kapcsolódó tevékenységek jelennek meg ezen a képernyőn.  
5. Válassza ki a **Lista megjelenítése** lehetőséget.
- Válasszon egy vevőszámlát, vagy fogadja el az alapértelmezett adatot. Alapértelmezés szerint ez az a kiválasztott vevőszámla a listaoldalon vagy a képernyőn, amelyről megnyitotta a képernyőt. Ha a képernyőt egy listaoldalról nyitotta meg, a vevők a listában azok a vevők, amelyeket szerepeltet a gyűjteményékben, amelyek ezen az oldalon szerepelnek.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
