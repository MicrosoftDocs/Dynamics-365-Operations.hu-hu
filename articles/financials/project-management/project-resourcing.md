---
title: "Projekterőforrás"
description: "Ez a témakör a projekterőforrásokkal kapcsolatban tartalmaz információkat."
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8139134ed230cc1525c698fadb20309afee0a68f
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="project-resourcing"></a>Projekterőforrás

[!include[banner](../includes/banner.md)]

Ez a témakör a projekterőforrásokkal kapcsolatban tartalmaz információkat.

Az erőforrás felosztás kihívást jelent a projektkezelőknek és az erőforrás-kezelőknek a projekt tervezési szakaszában, mert itt meg kell határozniuk és fenn kell tartaniuk a megfelelő erőforrásokat a projekthez. A Microsoft Dynamics 365 for Finance and Operations Enterprise edition rendszerben a projektek esetében az erőforrás-képességek lehetővé teszik azon szerepkörök meghatározását, amelyek olyan ideiglenes erőforrásként vannak kezelve, amelyek fenntarthatók egy bizonyos előjegyzéshez vagy egy előjegyzés egy részéhez. Ezek az erőforrás-típusok teszik lehetővé a projektkezelőknek és az erőforrás-kezelőknek, hogy elvégezzék az alábbi feladatokat:

- Meghatározhatnak egy olyan szerepkört, amely rendelkezik a szükséges szakértelemmel az erőforrások megfeleltetéséhez.
- Felhasználhatnak szerepköröket a fenntartott erőforrásokon alapuló kezdeti előjegyzés-ütemezés meghatározásához.
- Költségbecslést végezhetnek, valamint meghatározhatják a kezdeti költségvetést a projekthez hozzárendelt szerepkörök és erőforrások alapján.
- Felhasználhatnak szerepköröket az egyes előjegyzésekhez szükséges erőforrás-fenntartások számának becsléséhez.
- Megbecsülhetik a szükséges erőforrásokat egy projekt teljes életciklusához.
- A kezdeti erőforrás-hozzárendelés használatával megtervezhetnek egy munkalebontási struktúrát (WBS).

[![Projekt élettartama](./media/projectresourcing02-1024x812.jpg)](./media/projectresourcing02.jpg)

A projekttervezés előrehaladtával a tervezett erőforrások helyettesíthetők a személyzettel ellátott erőforrásokkal. A projektmenedzser vissza is léphet és frissítheti az erőforrás-fenntartásokat a projekt bármely szakaszában.

## <a name="set-up-project-resources"></a>Projekterőforrások beállítása
Be kell állítania egy új naptárt és hozzá kell rendelnie egy alkalmazottat vagy egy dolgozót. A naptár a projekthez fenntartott erőforrások munkaidejének és a projektek ütemezésére lesz használva. A naptár beállítása alatt a projektvezető az erőforrás optimalizálásának részeként elvégezheti az erőforrás-kiegyenlítést. A naptár-ütemezés alapján korlátozások helyezhetők az erőforrásokra. Beállíthat egy naptárat a **Naptárak** oldalon.

Dolgozó projekt-erőforrásként való beállításakor választhat a vállalatnál dolgozó dolgozók közül, amelyhez beállítja az erőforrásokat. Másik megoldásként a szervezet más cégeinél dolgozó dolgozókat is választhat. Ezeket a dolgozókat vállalatközi erőforrásoknak nevezik.

Az alábbi eljárások bemutatják, hogyan állítható be egy dolgozó projekterőforrásként a vállalaton belül, és hogyan állítható be egy vállalatközi projekterőforrás.

### <a name="set-up-a-worker-as-a-project-resource"></a>Dolgozó beállítása, mint projekterőforrás

1. A **Dolgozók** oldalon, a **Dolgozók** listában jelölje ki azt a dolgozót, akit projekterőforrásként szeretne hozzáadni, majd nyissa meg a dolgozó rekordot.
2. A Műveleti ablaktáblán válassza a **Projekt** &gt; **Beállítás** &gt; **Projektbeállítás** lehetőséget.
3. Válasszon ki egy naptárt, és zárja be a lapot.

Meghatározhat alapértelmezett projekteket az erőforráshoz, mint előzetes hozzárendelés típus. Az előzetes hozzárendelések akkor használhatóak, ha az erőforrás-kezelő vagy a projektkezelő előre tudja, hogy az erőforrás milyen projekteken fog dolgozni. Az előzetes hozzárendelések alapulhatnak a projekttámogató vagy a vevő kérelmein. A projekt előzetes hozzárendeléséhez a **Projektek hozzárendelése** oldalon a **Projektek** lapon a **Fennmaradó projektet** listáján jelölje ki a megfelelő projektet.

### <a name="set-up-an-intercompany-resource"></a>Egy vállalatközi erőforrás beállítása

A munkavállaló vállalatközi erőforrásként való beállításakor el kell végezni a beállítást a kölcsönbe adó és a kölcsönbe vevő vállalatnál.

**A kölcsönbe adó vállalatnál**

1. A Finance and Operations rendszerben ellenőrizze, hogy a kölcsönbe adó vállalat ki legyen jelölve, majd végezze el az előző szakaszban leírt eljárást: „Dolgozó beállítása projekterőforrásként”.
2. A **Vállalatközi könyvelés** oldalon válassza az **Új** lehetőséget.
3. A **Jogi személy azonosítója** mezőben válassza ki a kölcsönbe adó vállalatot. Töltse ki a többi megfelelő mezőt, és válassza a **Mentés** elemet.
4. A **Transzferár** oldalon válassza az **Új** lehetőséget.
5. A **Kölcsönbe vevő jogi személy** mezőben válassza ki a megfelelő vállalatot.
6. Ha a kölcsönbe vevő vállalat számára csak az e szakasz elején létrehozott erőforrást szeretné kölcsönbe adni, az **Erőforrás** mezőben válassza ki a létrehozott erőforrás nevét. Ha a kölcsönbe adó vállalat összes erőforrását elérhetővé szeretné tenni a kölcsönbe vevő vállalat számára, hagyja üresen az **Erőforrás** mezőt.
7. A **Projektvezetési és könyvelési paraméterek** oldalon a **Vállalatközi** lapon állítsa a **Vállalatközi erőforrás-ütemezés és időnyilvántartások engedélyezése** mező értékét az **Igen** értékre.

**A kölcsönbe vevő vállalatnál**

- Az **Erőforrások listája** oldalon a keresési szűrőbe írja be a nevét a kölcsönbe adó vállalathoz létrehozott erőforrásnak annak az ellenőrzéséhez, hogy az erőforrás szerepel a kölcsönbe vevő vállalat erőforráslistájában.

## <a name="manage-resource-competencies"></a>Erőforrás-kompetenciák kezelése
Az erőforrás-kompetenciák az erőforrás-kezelés fontos részei. A kompetenciák használhatóak kiindulásként azon erőforrások megállapítására, amelyek rendelkeznek a megfelelő szakértelemmel, végzettséggel, tanúsítvánnyal és projekt tapasztalattal. Ezt az információt minden egyes erőforrás esetében be kell állítani, valamint rendszeresen kell frissíteni. Ezzel a módszerrel maximalizálhatja a képességeket, ha egy adott erőforrás kompetenciái a projekterőforrás hozzárendelése során teljesülnek.

[![Példák a szakértelmekre, tanúsítványokra, oktatásra, illetve projekttapasztalatra](./media/projectresourcing06-1024x383.jpg)](./media/projectresourcing06.jpg)

Az alábbi eljárások ismertetik, hogyan állítson be néhány kompetenciát az erőforrás részére.

Egy dolgozó részére a kompetenciák felállításához használhatja a **Dolgozók** listaoldalt az Emberi erőforrásoknál, vagy az **Erőforrások** listaoldalt a Projektvezetés és könyvelésnél. A következő eljárásokhoz a **Dolgozók** listaoldalt használjuk az Emberi erőforrásoknál.

### <a name="set-up-competencies-certificates"></a>Kompetenciák beállítása: Tanúsítványok

1. A **Dolgozók** listaoldalon válassza ki annak a dolgozónak a sorát, akihez tanúsítványi információt szeretne hozzáadni.
2. A Műveleti ablaktáblán a **Dolgozó** lapon a **Kompetenciák** csoportban válassza a **Tanúsítványok** lehetőséget.
3. Válassza az **Új**, majd a a **Tanúsítvány típusa** mezőt, és a **PMP** elemet.
4. A **Kezdő dátum** mezőben válassza a **2015/1/10** értéket, és válassza a **Mentés** lehetőséget.

### <a name="set-up-competencies-skills"></a>Kompetenciák beállítása: Szakértelem

1. A **Dolgozók** listaoldalon győződjön meg arról, hogy az előző eljárásban használt dolgozó továbbra is ki van választva. Ezután a Műveleti ablaktáblán a **Dolgozó** lapon a **Kompetenciák** csoportban válassza a **Szakértelem** lehetőséget.
2. **Új** kiválasztása.
3. A **Szakértelem** mezőben válassza ki a **Projektvezetés** lehetőséget.
4. A **Szint** mezőben válassza az **5 Szakértő** lehetőséget.
5. A **Szint dátuma** mezőben válassza ki a **1-/14/2014** lehetőséget.
6. A **Tapasztalat (év)** mezőbe írja be, hogy **10**.
7. Válassza a **Mentés** gombot, majd zárja be az oldalt.

## <a name="create-a-new-project"></a>Új projekt létrehozása
1. A **Projektvezetés** oldalon válassza az **Új projekt** lehetőséget, és adja meg a következő értékeket:

    - **Projekt típusa:** Idő és anyag
    - **Projekt neve:** XYZ Frissítési Fázis 2
    - **Projektcsoport:** TM\_WIP
    - **Projektszerződés azonosítója:** 00000002

2. Válassza a **Projekt létrehozása** elemet.

### <a name="assign-a-resource-to-a-project"></a>Erőforrás hozzárendelése egy projekthez

1. A **Dolgozók** oldalon a **Dolgozók** listában válassza ki az ahhoz a dolgozóhoz tartozó rekordot, akihez korábban kompetenciákat állított be, majd nyissa meg azt.
2. A Műveleti ablaktáblán a **Projekt** lapon a **Beállítás** csoportban válassza a **Projekt hozzárendelése** lehetőséget.
3. Az **Erőforrás-ellenőrzés projekt-hozzárendelései** oldalon a **Projektek** lapon a **Projekt hozzáadása a kiválasztott projektekhez** mezőben alkalmazzon szűrőt az **XYZ frissítési szakasz 2** projektre.
4. A **Fennmaradó projektek** ablaktáblán válasszon ki egy projektet, majd válassza a nyílgombot, hogy hozzáadja azt a **Kiválasztott projektek** ablaktáblához.

Igény szerint hozzárendelhet kategóriákat egy erőforráshoz. A kategória típusa **Költség** vagy **Bevétel** lehet. A kategória típusát a szervezet határozza meg. Ha nincsenek az erőforráshoz hozzárendelt kategóriák, a Finance and Operations kikeresi az alapértelmezett óránkénti árat a költségekhez és bevételekhez.

### <a name="set-up-project-resource-and-role-characteristics"></a>Projekt erőforrások és szerepkör jellemzők beállítása

A projektvezető a projekterőforrás funkció segítségével hozhat létre a projekthez szükséges szerepköröket. A szerepkörök akkor használhatóak, ha a visszaigazolt erőforrások ismeretlenek az erőforrások fenntartásakor. A szerepkörök ideiglenes fenntarthatók tervezett erőforrásként, így tovább folytathatja a projekttervezést.

[![Példa szerepkörre](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg) 

**Forgatókönyv:** Contoso egy olyan Idő- és anyagprojekt elvégzésére lett felvéve, amely rendelkezik egy jóváhagyott projekt alapszabállyal. A beosztott projektvezető továbbra is a projekt hatókörét tölti ki. Az erőforrás-kezelő jelenleg azokat a fenntartott erőforrásokat azonosítja, amelyek az új projekthez lesznek rendelve. A projekt kritikus jellege miatt a projekttámogató a Vezető projektmenedzser szerepkört kérte. Az erőforrás-kezelőnek új erőforrást kell szereznie, majd meghatároznia a szerepkört a rendszerben, hogy ha a beosztott projektvezetőnek szüksége lenne az erőforrás-információkra a projekttervezés alatt, akkor az rendelkezésre álljon.

Az alábbi lépések bemutatják, hogy az erőforrás-kezelő hogyan tud beállítani Vezető projektmenedzser szerepkört a rendszerben, valamint hogyan tud erőforrás jellemzőket társítani hozzá. A későbbiek folyamán a szerepkör használható lesz olyan kereséseknél, amelyek azon elérhető erőforrásokat keresik meg, amelyek megfelelnek a szükséges erőforrás kompetenciáknak.

1. A **Szerepkörök beállítása** oldalon válassza az **Új** lehetőséget, és adja meg a következő értékeket:

    - **Szerepkör-azonosító:** Vezető Projektmenedzser
    - **Leírás:** Vezető Projektmenedzser

2. Válassza a **Létrehozása** lehetőséget.
3. Válassza a **Vezető projektmenedzser** szerepkört, és válassza a **Jellemzők konfigurálása** lehetőséget.
4. A **Jellemzők típusa** mezőben válassza ki a **Szakértelem** lehetőséget.
5. Az **Elérhető jellemzők** mezőbe írja be a keresett szakértelem típusát.
6. A **Jellemző típusa** mezőben válassza ki a **Diploma** lehetőséget.
7. Az **Elérhető jellemzők** mezőbe írja be a keresett diploma típusát.

### <a name="assign-a-project-resource-to-a-project"></a>Projekterőforrás hozzárendelése egy projekthez

1. A **Minden projekt** oldalon válassza az **XYZ frissítési fázis 2** projektet.
2. A **Projektcsapat és ütemezés** fülön válassza a **Hozzáadás** lehetőséget.
3. A **Szerepkör** mezőben válassza a **Csapat tagja** lehetőséget.
4. Válassza a **Foglalás naptárból** lehetőséget.
5. Az **Erőforrás elérhetősége** lapon válassza a **Beállítások megtekintése** lehetőséget.
6. A **Nézet beállításának módosítása** lapon adja meg az alábbi értékeket:

    - **Dátumtartomány-nézet formátuma:** Nap
    - **Elérhetőség leírásának megjelenítése:** Igen
    - **Hátralévő kapacitás megjelenítése:** Igen

7. Az erőforrások listájából válasszon egy erőforrást.
8. Válassza a **Végleges lefoglalás** és a **Teljes kapacitás** lehetőségeket.


### <a name="assign-a-resource-to-a-default-role"></a>Erőforrás hozzárendelése egy alapértelmezett szerepkörhöz

A projekthez fenntartható erőforrásokon történő leásás segítheti a projektvezetőket és az erőforrás-kezelőket. Alapértelmezett szerepkört társíthat már meglévő, valamint újonnan szerzett erőforrásokhoz. Amikor például Danielt felvették, megfelelő tapasztalattal és készségekkel rendelkezett az üzleti elemző szerep betöltéséhez. Az erőforrás-kezelő ezt a szerepkört rendelte Danielhez alapértelmezett szerepkörként. Ezért az erőforrás-kezelő Danielt hozzáadta az üzleti elemzők készletéhez, akik rendelkezésre állnak a projekteken végzett munkához.

Erőforrás-fenntartás során a projektvezetők szűrhetik a szerepkör erőforrásait, amelyek rendelkezésre állnak projekteken való munkához. Ezeket az adatokat használhatják egy feltételként több kritérium felhasználásával történő döntéshozatal végrehajtásakor erőforrás teljesítése során. Más erőforrás tulajdonságait is hozzáadhatják a szűrőhöz meghatározott szakértelemmel, végzettséggel és adott projekttapasztalattal rendelkező erőforrások keresésekor.

**Eset:** Egy jóváhagyott projekt elindult, és a Vezető projektmenedzser szerepkört tervezett erőforrásként tartották fenn a projekt tervezési szakaszában. Az erőforrás-kezelő már megszerezte az erőforrást a Vezető projektmenedzser szerepkör betöltéséhez.

1. Az **Erőforráslista** oldalon válassza a **Daniel Goldschmidt** nevet.
2. Az **Erőforrás szerepköre** oldalon válassza az **Új** lehetőséget, és adja meg a következő értékeket:

    - **Hatályos:** adja meg a jelenlegi dátumot.
    - **Lejárat:** adja meg a **Soha** értéket.
    - **Szerepkör:** adja meg a **Vezető Projektmenedzser** lehetőséget.

3. Válassza a **Mentés** gombot, majd zárja be az oldalt.
4. A **Kompetenciák** lapon adja hozzá a **ProjectMgmt** szakértelem és **PMP** tanúsítványt.

## <a name="set-up-role-based-pricing"></a>Szerepköralapú árképzés beállítása
Minden költség, értékesítés, és transzferár beállítható szerepkörökhöz.

1. Az **Eladási ár (óra)** oldalon válassza az **Új** lehetőséget, és adjon meg egy érvényes dátumot.
2. A **Szerepkör** oszlopban válasszon szerepkört.
3. Az **Árképzés** oszlopban adja meg a kiválasztott erőforrás-szerepkör árát.

## <a name="form-a-project-team"></a>Projektcsapat kialakítása
A projektben korábban beállított szerepkörök használatához egy projektmenedzsernek a szerepköröket társítania kell a projekthez. Több szerepkör is hozzárendelhető egy projekthez. A félreértések elkerülése végett a Finance and Operations automatikusan felcímkézi e szerepköröket a foglalás során. Ha például a projektmenedzsernek három szoftverfejlesztőre van szüksége, a rendszer automatikusan létrehoz három szoftverfejlesztő szerepkört  **szoftverfejlesztő 1**, **szoftverfejlesztő 2** és **szoftverfejlesztő 3** címkékkel. Ha a szerepkör jellemzőit korábban beállították a szerepkörhöz, ezek szűrőként működnek erőforrás keresése során. A keresést finomíthatja a további szükség szerint további jellemzői lehet adni.

A beállítások megtekintése is testreszabható, hogy jobb áttekintést adjon a rendelkezésre álló erőforrásról. Lehetőség van óránkénti, napi, heti, havi, negyedéves vagy éves elérhetőség megjelenítésére. Lehetőség van megjeleníteni az elérhető és fennmaradó erőforrások kapacitását. Ez a beállítás jól használható időkezelésre tevékenységek idejének vagy erőforrás elérhetőségének becslésekor.

A projektmenedzser szerepkört választhat az oldalon, és ha elérhető szabad erőforrás, amely megfelel a követelménynek, válassza az erőforrás fenntartását a szerepkör betöltéséhez. Ne feledje, hogy az erőforrások fenntartása nem szükséges ezen a ponton a tervezési szakaszban. Amikor létrehoz egy WBS-t, a szerepkörök lecserélhetők a projekt személyzettel ellátott erőforrásaira. Ha a WBS-ben a szerepköröket lecserélték a személyzettel ellátott erőforrásokra, az erőforrás beállítása automatikusan frissíti a projektcsapat listáját és az ütemezést.

[![Projektcsapat listázása, amely tartalmazza a szerepköröket és a tényleges erőforrásokat](./media/projectresourcing03-1024x368.jpg)](./media/projectresourcing03.jpg) 

A projektmenedzser több lehetőséggel rendelkezik egy erőforrás projekthez történő lefoglalásához, például **Fennmaradó kapacitás**, **Teljes kapacitás**, **Kapacitás százaléka** és **Óraszám megadása**. Ezek a foglalási beállítások bármikor visszavonhatók, ha az erőforrás-hozzárendelések módosulnak. A foglalásnak két típusa támogatott:

- **Végleges lefoglalás** – Az erőforrás-fenntartást jóváhagyták és megerősítették, hogy az előjegyzésen dolgozni lehessen a megadott időtartamban.
- **Ideiglenes lefoglalás** – Az erőforrás-fenntartásokat feltételesen állították be, hogy az előjegyzéssel dolgozni lehessen a megadott időtartamban.

Az alábbi eljárás ismerteti, hogyan lehet projektcsapatot létrehozni.

### <a name="create-a-project-team"></a>Projektcsapat létrehozása.

1. Jelöljön ki egy projektet az **Összes projekt** listaoldalon, és válassza a **Szerkesztés** lehetőséget.
2. A **Projektcsapat és ütemezés** lapon a **Záró dátum ütemezése** mezőbe írja be az ütemezés kezdő dátumát, egy hónapot hozzáadva. Például ha az ütemezés kezdő dátuma 2017. június 24. (24/06/2017), írja be **24/07/2017**.
3. Válassza a **Hozzáadás** lehetőséget.
4. A **Szerepkör hozzáadása a projekthez** ablakban, a **Szerepkör** mezőben válassza a **Projektmenedzser** lehetőséget.
5. Válassza a **Szükséges kompetenciák** lehetőséget.
6. A **Jellemző választása** oldalon a Vezető projektmenedzser szerepkörhöz korábban beállított jellemzők alapértelmezés szerint be vannak jelölve. Válassza ki az **OK** lehetőséget.
7. A **Szerepkörök hozzáadása projekthez** oldalon az **Erőforrások száma** mezőbe írja be a következőt: **1**.
8. Az **Erőforrás** mezőben a keresés megjeleníti az összes erőforrást, amely a szükséges kompetenciákkal rendelkezik. Válassza a **Daniel Goldschmidt** nevet, majd válassza a **Létrehozás** lehetőséget.
9. A **Projekt** oldalon válassza a **Hozzáadás** lehetőséget.
10. A **Szerepkör hozzáadása a projekthez** ablakban, a **Szerepkör** mezőben válassza a **Csapattag** lehetőséget. Az **Erőforrások száma** mezőben adja meg a következőt: **5**.
11. Válassza a **Létrehozás** lehetőséget.
12. A **Projektek** oldalon válassza az **Erőforrás teljesítése** lehetőséget.

## <a name="resource-capacity-synchronization"></a>Erőforrás-kapacitás szinkronizálása
Az erőforrás-szinkronizálási folyamatok segítségével garantálható, hogy a naptár- és alapnaptáradatok a projekterőforrás-ütemezéssel összhangba kerülnek. Ha a naptár módosult, a folyamatok elvégzik a szükséges frissítéseket a projekterőforrások ütemezéséhez. A folyamatok a teljesítmény javításában is segítenek, mivel a naptár-erőforrásadatok szinkronizálása előre megtörténik. Ezért az erőforrás-ütemezési információk módosításai gyorsabban megtörténnek. Javasoljuk, hogy ne egyesével, hanem kötegként ütemezze a folyamatokat. Ellenkező esetben fennáll a kockázata annak, hogy valaki elfelejti az utolsó adatszinkronizálás inkluzív időpontját. Ha az inkluzív időpontokat nem használták, szünetek fordulhatnak elő a dátumszinkronizálás során.

![Naptár szinkronizálása](./media/projectresourcing04-1024x471.jpg)

### <a name="synchronize-resource-capacity-roll-ups"></a>Erőforrás kapacitás-összesítéseinek szinkronizálása

A szinkronizálási folyamat arra szolgál, hogy az összes naptári erőforrásadatot szinkronizálja. Ez az információ alapnaptár adatokat tartalmaz a projekt Erőforrásnaptár kapacitás tábláját ért bármely módosításról. Ha új erőforrások kerülnek a projekthez, a szinkronizálás biztosítja a frissített naptáradatok elérhetőségét. Ez a szinkronizálás bármikor megtehető.

Köteg használatát javasoljuk. A beállítások a kapacitásfoglalások szinkronizálása során érhető el.

1. Válassza a **Projektvezetés és könyvelés** &gt; **Időszakos** &gt; **Kapacitásszinkronizálás** &gt; **Erőforrás kapacitás-összesítéseinek szinkronizálása** lehetőségeket.
2. Állítsa be az alábbi táblázatban található lehetőségeket.

    | Lehetőség      | Leírás |
    |-------------|-------------|
    | Időszak kódja | Bejelölheti a Főkönyvi dátumtartomány kódját, és beállíthatja a szinkronizálási folyamat kezdő és záró dátumát erőforráskapacitás-összesítésekhez. |
    | Kezdő dátum  | Adja meg a szinkronizálási folyamat kezdő dátumát erőforráskapacitás-összesítésekhez. |
    | Befejezés    | Adja meg a szinkronizálási folyamat záró dátumát erőforráskapacitás-összesítésekhez. |

[![Szinkronizálási folyamat](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)

## <a name="set-up-roles-on-wbs-templates"></a>WBS sablonok szerepköreinek beállítása
A projektvezetők beállíthatnak olyan WBS-sablonokat, amelyek felhasználhatók új WBS-projektek létrehozásakor. A projektvezetők létrehozáskor szerepköröket adhatnak a sablonokhoz. Használja a következő eljárást, hogy szerepet rendeljen egy WBS-sablonhoz. 

1. Válassza a **Projektvezetés és könyvelés** &gt; **Beállítás** &gt; **Projektek** &gt; **Munkalebontási struktúra sablonjai** lehetőséget.
2. Válassza a **Részletek** lehetőséget a kiválasztott WBS-sablonnál.
3. Jelöljön ki egy feladatot a listán, majd a **Szerepkör** mezőben válassza ki a feladathoz társítandó szerepkört.

### <a name="work-with-a-wbs"></a>A WBS használata

Létrehozhat egy új WBS-t, vagy másolhat egyet egy meglévő WBS-sablonból. Egy projektvezető egyszerűen kezelheti az erőforrásokat szerepkörök hozzárendelésével új feladatokhoz a WBS rendszerében. Egy erőforrás beszerzését, vagy a feladathoz tartozó megerősített erőforrások azonosítását követően lecserélhetők a szerepkörök. Ez a rugalmasság a következő feladatok végrehajtását teszi lehetővé a projektmenedzsernek:

- Szükséges számú erőforrások azonosítása WBS munkacsomagok számára.
- Projektköltség becslése.
- Előzetes költségvetés megállapítása.
- Tevékenységi időtartam becslése, szerepkörök és erőforrások alapján.
- Projektvezetési tervek fejlesztése, a rendelkezésre álló projektinformációk alapján.

A WBS további lehetőségekkel bővült az erőforrás funkció jobb használhatósága érdekében.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Lehetőség</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Erőforrás-hozzárendelések</td>
<td>A hozzárendelt erőforrások, dátumok, óraszámok és feladatokhoz tartozó foglalástípus megtekintése a WBS-en.</td>
</tr>
<tr class="even">
<td>Csapat automatikus előállítása</td>
<td>Tervezett erőforrások automatikus hozzáadása társított feladattal rendelkező szerepkörök használatával. A Finance and Operations automatikusan javasol tervezett erőforrásokat, egy szerepkörökön alapuló több kritérium felhasználásával történő döntéshozatal használatával. Miután a szerepkörök és munka (órák) be lettek állítva a WBS-ben található feladatokhoz, és miután a struktúra ki lett adva, válassza a <strong>Csapat automatikus létrehozása</strong> lehetőséget. A tervezett erőforrások szükséges száma hozzáadódik a WBS-hez és a <strong>Projekt és csapat ütemezés</strong> laphoz.</td>
</tr>
<tr class="odd">
<td>Erőforrás (legördülő lista)</td>
<td>Az <strong>Erőforrás-hozzárendelés indítása </strong>lapon kiválaszthatja az erőforrásokat végleges vagy ideiglenes lefoglalásra, a megadott időtartam alapján. Módosíthatja a nézetbeállításokat, hogy megtekintse és beállítsa az erőforrás-tevékenységek időtartamát. Kiválaszthat és társíthat erőforrásokat a munkacsomag szintjén, a következő beállítások használatával:
<ul>
<li><strong>Elfogadás</strong> – A feladathoz társított erőforrásban bekövetkezett módosítások megerősítése.</li>
<li><strong>Mégse</strong> – A feladathoz társított erőforrásban bekövetkezett módosítások érvénytelenítése.</li>
<li><strong>Automatikus hozzárendelés</strong> – egy rendelkezésre álló, személyzettel ellátott, megfelelő szerepkörrel rendelkező erőforrást jelöl ki és rendel hozzá automatikusan a kiválasztott feladathoz.</li>
</ul></td>
</tr>
</tbody>
</table>

1. A **Minden projekt** oldalon válassza az **XYZ frissítési fázis 2** projektet.
2. Válassza a **Terv** &gt; **Tevékenységek** &gt; **Munkalebontási struktúra** lehetőséget.
3. Válassza az **Új** gombot, hogy a WBS-hez adja a következő elsőszintű tevékenységeket:

    - Indítás
    - Tervezés
    - Végrehajtás folyamatban
    - Rendszerfigyelés és ellenőrzés
    - Zárás

4. Állítsa be a dátumokat és a munkát (óra), ahogy az alábbi ábra.

    [![A dátumok és a munka beállítása](./media/projectresourcing10.jpg)](./media/projectresourcing10.jpg)

5. Válassza ki az **Indítás** tevékenység-sort, majd a **Szerepkör** mezőben válassza ki **Vezető Projektmenedzser** lehetőséget.
6. Válassza a **Közzététel** lehetőséget.
7. Ugyanabban a sorban az **Erőforrás** mezőben válassza ki a **Daniel Goldschmidt** lehetőséget, majd az **Elfogadás** elemet.
8. Válassza ki a **Tervezés** tevékenység-sort, majd a **Szerepkör** mezőben válassza ki az **Üzleti elemző** lehetőséget.
9. Válassza a **Közzététel**, majd a **Csapat automatikus előállítása** lehetőséget.
10. A megjelenő párbeszédpanelen válassza az **Igen** gombot.
11. Győződjön meg róla, hogy az **Erőforrás** mezőben az érték **Üzleti elemző 1**.
12. Az **Üzleti elemző 1** erőforráshoz nyissa meg a keresőt és válassza az **Erőforrás-hozzárendelések indítása** lehetőséget. Ezután válassza ki a dolgozót a feladathoz.
13. Válassza az **Ideiglenes hozzárendelés** &gt; **Teljes kapacitás** lehetőséget.

    > [!NOTE] 
    > Nem kap figyelmeztetést, hogy az adott erőforrás most 2, mivel az erőforrások száma 1 marad.

14. A **munkalebontási struktúra** oldalon érvényesítse a WBS erőforrás-hozzárendelését, és válassza a **Mentés** lehetőséget.

## <a name="resource-fulfillment-for-planned-resources"></a>A tervezett erőforrások erőforrás-teljesítése
Egy projektvezető megtervezheti a szükséges erőforrás-szerepköröket egy projekthez. Az erőforrás-kezelő ezeket a tervezett erőforrásokat kérelemként fogja látni az **Erőforrás teljesítése** oldalon, és tényleges erőforrásokat rendelhet hozzzájuk.

1. A **Minden projekt** oldalon válassza az **XYZ frissítési fázis 2** projektet.
2. Válassza a **Projekt** lehetőséget, majd a **Szerkesztés** elemet.
3. A **Projektcsapat és ütemezés** fülön válassza a **Hozzáadás** lehetőséget.
4. A **Szerepkörök hozzáadása** párbeszédpanelen jelölje ki a **Szoftverfejlesztő** szerepkört.
5. Válassza a **Létrehozás** elemet, majd zárja be a projektoldalt.
6. Az **Erőforrás teljesítése** oldalon válassza a **Szoftverfejlesztő 1** lehetőséget az **XYZ frissítési projekt fázis 2** projekthez.
7. Válasszon ki egy dolgozót, majd válassza a **Hozzárendelés** elemet.
8. Ellenőrizze, hogy a **Szoftverfejlesztő 1** sora el lett távolítva a **XYZ Frissítési projekt Fázis 2** projektből.
9. A **Projektcsapat és ütemezés** lapon ellenőrizze, hogy az **XYZ Frissítési Fázis 2** projekthez a dolgozó, akit kiválasztott az előző lépésben, hozzá lett adva úgy mint **Szoftverfejlesztő**.

## <a name="requests-for-project-resources"></a>Projekterőforrás-kérések
A projekterőforrás-ütemezési szolgáltatás csak a személyzettel ellátott erőforrások vagy előjegyzések elosztását engedi az erőforrás-kezelőknek. A funkció engedélyezéséhez végezze el a következő feladatokat, vagy győződjön meg arról, hogy befejeződtek:

- Számsorozatok beállítása.
- Munkafolyamatok beállítása a projektvezetéshez és a könyveléshez.
- Engedélyezze az erőforrás-kérelem munkafolyamatokat.

Miután az előző feladatok befejeződtek, elvégezheti az alábbi feladatokat, szükség szerint:

- Erőforrás-igénylés létrehozása ideiglenesen lefoglalt személyzettel ellátott erőforráshoz.
- Erőforrás-kérelmek figyelése.
- Erőforrás-kérelmek teljesítése.
- Személyzettel ellátott erőforrás kérése WBS-től.
- Erőforrások foglalása egy projekthez személyzettel ellátott erőforrások iránti kérelem nélkül.

## <a name="monitor-project-teams"></a>Projektcsoportok figyelése
1. A **Minden projekt** oldalon válassza a **Projektazonosító** hivatkozást az **XYZ Frissítési Fázis 2** projektnél.
2. A **Projektcsapat és ütemezés** gyorslapon győződjön meg róla, hogy a felsorolt projekterőforrások helyesek.

