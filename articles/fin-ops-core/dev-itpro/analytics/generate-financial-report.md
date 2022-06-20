---
title: Pénzügyi jelentések létrehozása
description: Ez a cikk a pénzügyi jelentések létrehozásáról nyújt tájékoztatást.
author: jinniew
ms.date: 02/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 68843
ms.assetid: 271df6f4-12b7-4b3e-b2d7-36ea98ef1871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 59ec6978d83f5c51309bc7d90d47366774cb2880
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898827"
---
# <a name="generate-financial-reports"></a>Pénzügyi jelentések létrehozása

[!include [banner](../includes/banner.md)]

Ez a cikk a pénzügyi jelentések létrehozásáról nyújt tájékoztatást.

Jelentés létrehozásához nyissa meg a jelentésdefiníciót, és válassza a Jelentés létrehozása lehetőséget az **eszköztáron**. Megnyílik **a Jelentési** sor állapota lap, amely a jelentés várólistán való helyét jelzi.

A jelentés generálása során előfordulhat, **hogy a jelentési várólista következő állapotjelzői láthatók a jelentési várólista állapota** lapon.

| Állapot          | Állapot | Leírás|
|-----------------|--------|--------------------|
| Várakozási sor        | Ideiglenes |A jelentésdefiníciót a rendszer ellenőrzi, mielőtt a jelentést a generáló várólistába kerül.                    |
| Feldolgozási sorban          | Ideiglenes | A jelentés beírja a jelentés-generálási várólistát, és várakozás a feldolgozásra.                      |
| Feldolgozás alatt      | Ideiglenes | Ez az állapot általában a **Várakozási** sor állapot után következik, és általában végleges állapotra áll át, **amikor** a feldolgozás befejeződött.       |
| Utófeldolgozás | Ideiglenes | Ez az állapot a **Feldolgozás** állapot után következik, és jelzi, hogy a program össze gyűjti a jelentés adatait, de végrehajtottak műveleteket, például számítást és összesítést.            |
| Érvénytelenítés      | Ideiglenes | A jelentés a felhasználó kérése szerint érvénytelenül törlődik. Ez az állapot a felhasználó által kért érvénytelenítésből áll, amely várólistára **kerül** vagy feldolgozás **állapotban** van. A rendszer Megszakítva **állapotba** próbálja tenni a jelentést, hacsak a rendszer nem túl távol van, és egy másik állapotban kell véglegesítenie azt. |
| Törölve        | Végleges | A jelentés feldolgozása befejeződött, de egy felhasználó által kért leállítás miatt nem fejeződött be.            |
| Befejeződött       | Végleges | A jelentés használatra kész.                      |
| Sikertelen          | Végleges | A jelentés feldolgozása befejeződött, de nem sikerült, és nem lehet használni. |

Alapértelmezés szerint a létrehozott jelentés a Webes megjelenítőben nyílik meg. A jelentések generálása során a következő lehetőségek közül választhat:

- Állítson be egy ütemezést jelentés vagy jelentéscsoport automatikus létrehozásához
- Győződjön meg arról, hogy a jelentésből nem hiányoznak számlák vagy adatok, és ellenőrizze a jelentés pontosságát

Jelentés generálása esetén a program a jelentésdefiníciók lapjain megadott beállításokat használja.

## <a name="generate-a-financial-report"></a>Pénzügyi jelentés elkészítése

A pénzügyi jelentés készítéséhez lépjen a **Főkönyv** \> **Lekérdezések és jelentések** \> **Pénzügyi jelentések** részhez.

- Kattintson létrehozni kívánt jelentésre, és kattintson a **Létrehozás** lehetőségre.
- Töltse ki a **Jelentés dátuma** mezőt, majd kattintson az **OK** gombra.

A jelentés generálása után a jelentést a **Jelentések** szakaszban tekintheti meg.

A jelentéseknél a **Megtekintés** vagy **Törlés** lehetőség választható ki.

A jelentés létrehozásához a **Jelentéstervező** segítségével, nyissa meg a jelentésdefiníciót, majd kattintson a **Létrehozás** gombra az eszköztárban. Az ekkor megnyíló **Jelentés-várólista állapota** oldal mutatja a jelentés helyét a várólistában. Alapértelmezés szerint a létrehozott jelentés a Webes megjelenítőben nyílik meg.

## <a name="report-groups"></a>Jelentéscsoportok

A jelentéscsoportok funkció hatékony mód arra, hogy egyszerre több jelentést generáljon. Tegyük fel például, hogy a hónap végén a felhasználói minden hónapban nyolc jelentést generálnak. Hozzon létre egy Jelentéscsoportot, és ahelyett, hogy a csoport mind a nyolc jelentéséhez a **Létrehozás** lehetőséget választaná, válassza a jelentéscsoportban a **Létrehozás** lehetőséget, és a nyolc jelentés egy lépésben jön létre. Amikor a kiválasztott jelentéscsoportban a rendszer létrehozta a jelentéseket, az egyes jelentések megtekintéséhez a **Pénzügyi jelentések** (**Főkönyv > Lekérdezések és jelentések > Pénzügyi jelentések**) lehetőséget használhatja. A jelentéscsoport beállításához hajtsa végre az alábbi lépéseket.

1. A Jelentéstervezőben válassza ki a **Jelentéscsoportok** lehetőséget. 
2. Válassza ki a jelentéscsoportban szerepelteti kívánt, meglévő jelentésdefiníciókat. 
3. Válassza ki az egyes jelentésekből a vállalat-, adat- és dátumbeállítások felülbírálását, amit a csoportba szeretne felvenni.
   Javasoljuk, hogy minden jelentésnél állítsa be a következőket: **Vállalat**, **Időszak**, **Év** és **Részlet szintje**. 
4. Mentse a jelentéscsoportot.

## <a name="schedule-report-generation"></a>A jelentések létrehozásának ütemezése
Számos vállalat az üzleti céljainak megfelelő alapvető jelentéskészletet használ, és meghatározott időközönként futtatja a készletben lévő jelentéseket. Lehetősége van egy jelentés rendszeres (például napi, heti, havi vagy évi) létrehozásának beütemezésére. Ezt megadhatja egy jelentésre vonatkozóan, vagy egy több vállalatot tartalmazó teljes jelentéscsoportra vonatkozóan is. Meg kell adnia az összes meghatározott vállalat, például a jelentésfa-definícióban szereplő összes vállalat hitelesítő adatait. Ha a hitelesítő adatok nem érvényesek, a jelentés csak az Ön számára hozzáférhető adatokat jeleníti meg, például azt a vállalatot, amelybe az adott időpontban bejelentkezett. A kimeneti információ leolvasása elsőként a jelentéscsoportból, ezt követően pedig az egyes jelentésekből történik.

A jelentési ütemezések létrehozása és mentése után megjelennek a navigációs ablakban, a Jelentési ütemezések alatt. A jelentések rendszerezéséhez mappákat hozhat létre. Ha az ütemezésben szereplő egyik jelentés nem futtatható, a többi jelentés futtatása folytatódni fog.

> [!IMPORTANT]
> A jelentésütemezések létrehozásához, módosításához és törléséhez tervezői vagy rendszergazdai szerepkörrel kell rendelkeznie. Jelentés futtatásakor a annak a felhasználónak a hitelesítő adatait használja a rendszer a jelentés létrehozásához, aki az ütemezést készítette.

### <a name="create-a-report-schedule"></a>Jelentésütemezés létrehozása

1. A Jelentéstervező **Fájl** menüjében kattintson az **Új** lehetőségre, majd válassza a **Jelentésütemezés** lehetőséget. Megnyílik az **Új Jelentésütemezés** párbeszédpanel.
2. A **Beállítások** pontban válasszon ki egy ütemezni kívánt jelentést vagy jelentéscsoportot. Csak annak a vállalatnak vagy építőelemnek a jelentései, illetve jelentéscsoportjai érthetők el, amelybe be van jelentkezve.
3. A jelentésütemezés bekapcsolásához jelölje be az **Aktív** jelölőnégyzetet. A jelentésütemezéseket csak a jelentés létrehozója vagy a rendszergazda kapcsolhatja be vagy ki.
4. Kattintson az **Engedélyek** gombra a vállalati hitelesítő adatok beviteléhez. Bejelentkezési adatait alapértelmezés szerint ahhoz a vállalathoz használhatja, amelybe bejelentkezett. Amennyiben más vállalatok is szerepelnek, például a jelentési fák definícióiban, válassza ki a következőt: **Különálló hitelesítő adatok használata**, majd adja meg a jelentésütemezésben szereplő minden más vállalat hitelesítő adatait. Választhatja a **Windows-hitelesítés** lehetőséget, vagy írja be minden vállalathoz a felhasználónevet és a jelszót. Az ezekhez a vállalatokhoz tartozó hitelesítő adatok mentéséhez jelölje be a **Hitelesítő adatok mentése** jelölőnégyzetet, majd kattintson az **OK** gombra a párbeszédpanel bezárásához.
5. A **Gyakoriság** lehetőségen belül az **Ismétlődés kezdete** mezőben válassza ki az ütemezés kezdő dátumát. Alapértelmezés szerint az ügyfélszámítógép aktuális rendszerdátuma van kiválasztva.
6. A **Jelentés futtatása ekkor:** mezőben válassza ki a jelentés futtatásának kívánt időpontját. Ha az aktuális rendszeridőnél korábbi időpontot ad meg, a jelentés a következő ütemezett időpontban fog futni.
7. Az **Ismétlődési szabály** területen adja meg, milyen gyakran fusson a jelentés. Alapértelmezés szerint a **Naponta** lehetőség van kiválasztva és az Időtartam (napok) értéke 1. Egyéb lehetőségek: hetente, havonta és évente.
8. Az Ismétlődés tartománya területen adja meg, hogy mikor kell befejeződnie a jelentés létrehozásának.

    - **Nincs záró dátum** – a jelentésütemezés határozatlan ideig fut.
    - **Ismétlődések számának beállítása** – a jelentésütemezés a megadott számú alkalommal lefut, majd inaktiválódik.
    - **Befejezés ekkor:** – a jelentésütemezés a megadott dátummal befejeződik.

9. Válassza a **Mentés** lehetőséget. A **Mentés másként** párbeszédpanelen írja be a jelentésütemezés egyedi nevét és leírását.

Jelentésütemezés másolásához tervező vagy a rendszergazda szerepkörrel kell rendelkeznie. A jelentés még abban az esetben is megtartja a jelentést létrehozó felhasználó hitelesítő adatait, ha a jelentésütemezést egy rendszergazda módosította.

### <a name="copy-a-report-schedule"></a>Jelentésütemezés másolása

1. A Jelentéstervező navigációs ablakában kattintson a **Jelentésütemezések** lehetőségre, és nyisson meg egy másolni kívánt jelentésütemezést.
2. A **Fájl** menüben kattintson a **Mentés másként** lehetőségre, majd adja meg az ütemezés új nevét és leírását a **Mentés másként** párbeszédpanelen. Kattintson az **OK** gombra, és az új ütemezés megjelenik a navigációs ablakban.
3. Az új ütemezésben igény szerint módosítsa a mezőket és adatokat, majd kattintson a **Mentés** gombra az eszköztáron, vagy kattintson a **Mentés** lehetőségre a **Fájl** menüben.

Jelentésütemezést csak a jelentésütemezés tulajdonosa vagy egy rendszergazda szerepkörű felhasználó törölhet.

### <a name="delete-a-report-schedule"></a>Jelentésütemezés törlése

1. A Jelentéstervező navigációs ablakában kattintson a **Jelentésütemezések** lehetőségre.
2. Válassza ki a törölni kívánt jelentésütemezést, majd kattintson a **Törlés** gombra, vagy nyomja meg a **Delete** billentyűt.
3. A törlés megerősítésének párbeszédpanelén kattintson az **Igen** gombra, hogy véglegesen törölje a jelentésütemezést. Ha nincs engedélye az ütemezés törlésére, egy üzenet jelenik meg, és a jelentés nem törlődik.

### <a name="credentials-and-report-schedules"></a>Hitelesítő adatok és jelentésütemezések

Amennyiben nem adja meg a jelentésekben szereplő összes vállalathoz szükséges hitelesítő adatokat, a jelentésütemezés mentésekor a következő üzenet jelenik meg: „Meg kell adnia az ebben a jelentésütemezésben szereplő vállalatokra vonatkozó hitelesítési adatokat. Kattintson az Engedélyek gombra a hitelesítő adatok megadásához.”

Például egy felhasználó bejelentkezik az A vállalatba a felhasználónevének és a jelszavának megadásával. A felhasználó létrehoz egy ütemezést egy olyan jelentéshez, amely több vállalattól való adatgyűjtésre használ egy jelentési fa definíciót. A jelentésütemezés mentésekor a rendszer figyelmezteti a felhasználót, hogy adja meg a jelentésfa-definícióban meghatározott egyéb vállalatokhoz szükséges hitelesítő adatokat. A hitelesítő adatok lejárata után a jelentés ütemezésében érintett jelentések csak a hitelesítő adatok frissítése után jönnek létre. Megjelenik egy üzenet a jelentés-várólistán, jelezve, hogy az engedélyeket frissíteni kell. A jelentésütemezés sikertelen lesz, amennyiben a következő esetek közül bármelyik teljesül (mivel ezekhez hitelesítő adatok szükségesek):

- Új vállalatot adtak hozzá egy egyedi jelentés jelentési fájához.
- Módosult egy jelentés egy jelentéscsoportban.
- Egy vállalat új jelentése lett hozzáadva egy jelentéscsoporthoz.

A folytatáshoz kattintson az **Engedélyek** gombra a **Jelentés ütemezése** párbeszédpanelen, majd adja meg a megfelelő hitelesítő adatokat.

## <a name="missing-account-analysis-feature"></a>Hiányzó számlák elemzése funkció
Rákereshet egy építőelem-csoport minden sordefiníciójában, jelentésifa-definíciójában és jelentésdefiníciójában az esetleges hiányzó pénzügyi számlákra és dimenziókra. Akkor hasznos, ha rövid idő alatt több számla vagy építőelem létrehozását vagy frissítését hajtja végre, és ellenőrizni akarja, hogy a jelentéseiben minden új információ szerepel.

A hiányzó számlákat a sordefiníció vagy jelentési fa definíciójának legalacsonyabb és legmagasabb értékei határozzák meg, majd megjeleníti azoknak a számláknak a listáját, amelyek nem a sordefinícióban vagy a jelentési fa definíciójában vannak, hanem a pénzügyi adatokban. Ha egy hiányzó számla nagyobb vagy kisebb, mint a sordefinícióban szereplő érték, akkor a számla nem szerepel a hiányzó számlák listájában.

> [!TIP]
> Érvényesítési célból ezt a folyamatot mindig érdemes lefuttatni havi jelentések előállítása előtt, illetve új építőelemek létrehozásakor.

Értéktartományokat tartalmazó jelentésekből kevésbé valószínű, hogy hiányzik számla. Amikor lehetséges, az épületblokkban található tartományok használatával lehet az új számlákat a létrehozáskor szerepeletni. Ha valamely jelentésdefiníció a @ANY vállalatra van beállítva, akkor bejelentkezhet egy adott vállalatba, és lefuttathatja a hiányzó számlák elemzését arra a vállalatra.

> [!NOTE]
> Ha új vállalat hozzáadására került sor, hozzá kell adnia azt a meglévő jelentések jelentési fáihoz, különben a vállalat nem fog szerepelni a hiányzó számla elemzésben.

### <a name="run-missing-account-analysis"></a>Hiányzó számla elemzés futtatása

1. A Jelentéstervezőben kattintson az **Eszközök** lehetőségre, majd a **Hiányzó számla elemzés** lehetőségre.
2. A **Vállalat szűrő** mezőben válasszon ki egy vállalatot, amely szerint szűrni kívánja az eredményeket, vagy válassza az **Összes (nincs szűrés)** lehetőséget az összes elérhető vállalat eredményeinek megjelenítéséhez.
3. A **Dimenziószűrő** mezőben válasszon ki egy dimenziót, amely szerint szűrni kívánja az eredményeket, vagy válassza az **Összes (nincs szűrés)** lehetőséget minden elérhető dimenzió minden dimenzióadatának megtekintéséhez.
4. A **Csoportosítás alapja:** mezőben válasszon ki egy lehetőséget az eredmények rendezéséhez. Az eredmények rendezhetők az érintett építőelem szerint, illetve dimenzió- és értékkészlet szerint.
5. Tekintse át a megjelenített eredményeket. Amikor kiválaszt egy elemet a felső ablaktáblában, az alsó ablaktáblában további információ jelenik meg a kivételről. Láthatók például a kapcsolódó dimenziók, értékek és jelentések.
6. Az érintett elem megnyitásához kattintson a listaablakon megjelenített társított ikonra, vagy kattintson a jobb egérgombbal az elemre és válassza a **Megnyitás** lehetőséget. Több elem kijelöléséhez tartsa lenyomva a **Ctrl** billentyűt, miközben az alsó ablakban kiválasztja az elemeket.
7. Ha olyan értékeket, épületblokkokat vagy jelentéseket ad vissza, amelyek nem szerepelnek az elemzésben, **kattintson** a jobb gombbal a cikkre, és válassza a Kihagyás lehetőséget, **vagy** jelölje be a Cikk kizárása jelölőnégyzetet a cikk listából való eltávolításához. A kizárt cikkek nem szerepelnek a lista frissítéseknél. Több elem kijelöléséhez tartsa lenyomva a **Ctrl** billentyűt, miközben az alsó ablakban kiválasztja az elemeket. Az összes elem megtekintéséhez, beleértve azokat az eredményeket is, amelyeket korábban kizárt az elemzésből, jelölje be a **Kizárt építőelemek és értékek megjelenítése** jelölőnégyzetet, majd kattintson a **Frissítés** gombra.
8. Válassza **a Frissítés** lehetőséget a már megott kivételek frissítéshez. Kattintson az **Igen** gombra az összes eredményre vonatkozó teljes frissítés végrehajtásához, vagy kattintson a **Nem** gombra a kiválasztott elemekre vonatkozó részleges frissítés végrehajtásához.

    > [!NOTE]
    > A program automatikusan frissíti a képernyőt megnyitáskor, kivéve ha az meg volt nyitva az utolsó 15 percben.

9. Amikor megoldódtak a problémák, kattintson az **OK** gombra a párbeszédpanel bezárásához.

## <a name="keyboard-shortcuts-for-missing-account-analysis"></a>Billentyűparancsok a hiányzó számla elemzéshez
Hiányzó számla elemzésekor a következő billentyűparancsok használhatók.

| Művelet                           | Nyomja meg a(z)  billentyűt |
|--------------------------------------|----------------------------|
| Szűrés vállalat szerint                    | ALT + C                      |
| Szűrés dimenzió szerint                  | ALT + D                      |
| A Csoportosítás alapja mező kiválasztása            | ALT + G                      |
| Kizárt építőelemek és értékek megjelenítése      | ALT + S                      |
| Eredmények frissítése                      | ALT + R                      |
| A kijelölt építőelem kizárása  | ALT + X                      |
| A kijelölt sordefiníció kizárása  | Ctrl + B                     |
| A kijelölt dimenzióérték kizárása | Ctrl + D                     |
| A kijelölt jelentésdefiníció megnyitása  | Ctrl + R                     |
| A kijelölt sordefiníció megnyitása     | Ctrl + O                     |


## <a name="additional-resources"></a>További erőforrások

[Pénzügyi jelentéskészítés](financial-reporting-intro.md)

[A Report Designer felhasználói kezelőfelülete](report-designer-interface.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
