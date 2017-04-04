---
title: "Projekterőforrás"
description: "Ez a témakör ismerteti a projekt finanszírozása."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: cmercado
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: c29c95fc6abd13e668c44d3ccf437bb0e879e46b
ms.lasthandoff: 03/31/2017


---

# <a name="project-resourcing"></a>Projekterőforrás

Ez a témakör ismerteti a projekt finanszírozása.

Projektmenedzserek és erőforrás-kezelők a projekt tervezési szakasz során egy kihívás az erőforrás-elosztás, ahol kell megállapítani és fenntartani a megfelelő erőforrást a projekthez. Microsoft Dynamics 365 műveletekhez projektekhez képességek resourcing segítségével ideiglenes egy adott Eljegyzési, vagy annak egy részére egy felvételi lefoglalt erőforrásokat kezelik, szerepek meghatározása. Ezek az erőforrás-típusok teszik lehetővé a projektkezelőknek és az erőforrás-kezelőknek, hogy elvégezzék az alábbi feladatokat:

-   Meghatározhatnak egy olyan szerepkört, amely rendelkezik a szükséges szakértelemmel az erőforrások megfeleltetéséhez.
-   Szerepkörök segítségével megadhatja egy kezdeti kapcsolatfelvétel ütemterv lefoglalt erőforrások alapján.
-   Költségbecslést végezhetnek, valamint meghatározhatják a kezdeti költségvetést a projekthez hozzárendelt szerepkörök és erőforrások alapján.
-   Szerepkörök segítségével becsléséhez szükséges valamennyi pályázatát erőforrás-lefoglalások számát.
-   Megbecsülhetik a szükséges erőforrásokat egy projekt teljes életciklusához.
-   A kezdeti erőforrás-hozzárendelés használatával megtervezhetnek egy munkalebontási struktúrát (WBS).

[![Projekt életciklusában](./media/projectresourcing02-1024x812.jpg)](./media/projectresourcing02.jpg) 

A projekt tervezési bevételből tervezett erőforrások személyzettel erőforrásokat lehet cserélni. A projektmenedzser is vissza, és a resourcing foglalások frissítése a projekt szakaszai során.

## <a name="set-up-project-resources"></a>Projekterőforrások beállítása
Be kell állítania egy új naptárt és hozzá kell rendelnie egy alkalmazottat vagy egy dolgozót. A naptár segítségével a projekt és a munkaidő, a lefoglalt erőforrások a projekt ütemezése. A naptár beállítása alatt a projektvezető az erőforrás optimalizálásának részeként elvégezheti az erőforrás kiegyenlítést. A naptár-ütemezés alapján korlátozások helyezhetők az erőforrásokra. Állíthat be egy naptárt a a **naptárak** oldalon. 

A munkavállaló projekt erőforrásként beállításakor választhat, hogy a társaság, amelynek az erőforrások beállítása a munkavállalók vagy a szervezeten belüli más vállalatok munkavállalók is választhat. Ezek a vállalatközi erőforrásokat. Az alábbi eljárások bemutatják, hogyan állítható be egy munkavégző projekt erőforrásként a vállalaton belül és egy vállalatközi projekterőforrás beállítása.

### <a name="set-up-a-worker-as-a-project-resource"></a>Dolgozó beállítása, mint projekterőforrás

1.  A a **munkavállalók** a lap a **munkavállalók** listában, jelölje ki a dolgozó, projekt erőforrásként hozzáadni, és nyissa meg a dolgozó bejegyzést.
2.  Kattintson a műveletek ablaktábla **projekt**&gt;**a telepítő**&gt;**Project telepítő**.
3.  Válasszon ki egy naptárat, és zárja be a lapot.

Meghatározhat alapértelmezett projekteket az erőforráshoz, mint előzetes hozzárendelés típus. Az előzetes hozzárendelések akkor használhatóak, ha az erőforrás-kezelő vagy a projektkezelő előre tudja, hogy az erőforrás milyen projekteken fog dolgozni. Az előzetes hozzárendelések alapulhatnak a projekttámogató vagy a vevő kérelmein. A projekt előzetes hozzárendeléséhez a **Projektek hozzárendelése** oldalon a **Projektek** lapon a **Fennmaradó projektet** listáján jelölje ki a megfelelő projektet.

### <a name="set-up-an-intercompany-resource"></a>Egy vállalatközi erőforrás beállítása

A munkavállaló vállalatközi erőforrásként beállításakor ki kell töltenie a hitelezési és a hitelfelvétel vállalat beállítása. 

**A hitelezési vállalatnál:**

1.  Műveletek 365 Dynamics ellenőrizze, hogy a hitelező társaság van kijelölve, majd töltse ki a fenti eljárás "A munkavállaló a project erőforrás beállítása."
2.  Ugrás ** főkönyvi **&gt; ** könyvelési mátrix **&gt;**vállalatközi könyvelés**. Click **New**.
3.  A a ** jogalany ID ** mezőben, válassza ki a hitelt nyújtó vállalatot. Töltse ki a többi megfelelő mezőt, és kattintson a **Mentés**.
4.  Nyissa meg a ** projektek igazgatási és számviteli **&gt; ** a telepítő **&gt;**árak ** &gt;**átadási ár**.** **
5.  A a ** átadási ár ** képernyő, kattintson a **új**, és a ** kölcsönbe vevő jogi személy ** mezőben, válassza ki a megfelelő vállalatot.
6.  Ha azt szeretné, hogy a hitelfelvételi vállalat az erőforrás, az e szakasz elején létrehozott kölcsönözni csak a **erőforrás** mezőben, válassza ki a létrehozott erőforrás nevét. Ha az összes erőforrás a vállalat számára elérhetővé szeretné tenni a hitelfelvételi vállalat azt szeretné, hagyja a ** erőforrás ** a mező üres.
7.  Ugrás ** projektek igazgatási és számviteli **&gt; ** telepítő **&gt;**projekt management és könyvelési paraméterek**, és a ** vállalatközi ** lapon a ** vállalatközi erőforrás-ütemezés és a munkaidő-nyilvántartások ** mező **Igen**.

**A hitelfelvételi vállalatnál:**

1.  Keresse fel **projektek igazgatási és számviteli**&gt;**a Projekt-erőforrások**&gt;**Erőforrások lista**.
2.  A keresési szűrő írja be a nevét, ellenőrizze, hogy a neve szerepel az erőforráslista a hitelfelvételi vállalat hitelezési vállalat az előző eljárásban létrehozott erőforrás.

## <a name="manage-resource-competencies"></a>Erőforrás-kompetenciák kezelése
Erőforrás-kompetenciák erőforrás-kezelés alapvető részét képezik. A kompetenciák használhatóak kiindulásként azon erőforrások megállapítására, amelyek rendelkeznek a megfelelő szakértelemmel, végzettséggel, tanúsítvánnyal és projekt tapasztalattal. Ezt az információt minden egyes erőforrás esetében be kell állítani, valamint rendszeresen kell frissíteni. Ezzel a módszerrel maximalizálhatja a képességeket, ha egy adott erőforrás kompetenciái a projekterőforrás hozzárendelése során teljesülnek. [![Példák a képességek, tanúsítványok, oktatási és a projekttel kapcsolatos tapasztalatok](./media/projectresourcing06-1024x383.jpg)](./media/projectresourcing06.jpg) 

Az alábbi eljárások ismertetik, hogyan állítson be néhány kompetenciát az erőforrás részére. 

Egy dolgozó részére a kompetenciák felállításához használhatja a **Dolgozók** listaoldalt az Emberi erőforrásoknál, vagy az **Erőforrások** listaoldalt a Projektvezetés és könyvelésnél. Az alábbi eljárások esetében a **munkavállalók** az emberi erőforrások listája lapon használatos.

### <a name="set-up-competencies-certificates"></a>Kompetenciák beállítása: Tanúsítványok

1.  A **Dolgozók** listaoldalon válassza ki annak a dolgozónak a sorát, akihez tanúsítványi információt szeretne hozzáadni.
2.  A Műveleti ablaktáblán a **Dolgozó** lapon a **Kompetenciák** csoportban kattintson a **Tanúsítványok** lehetőségre.
3.  Kattintson az **Új** elemre.
4.  A **Tanúsítvány típusa** mezőben válassza ki a **PMP** lehetőséget.
5.  A **Kezdés dátuma** mezőben válassza ki a **10/1/2015** lehetőséget.
6.  Kattintson a **Mentés** gombra, majd zárja be az oldalt.

### <a name="set-up-competencies-skills"></a>Kompetenciák beállítása: Szakértelem

1.  A **Dolgozók** listaoldalon győződjön meg arról, hogy az előző eljárásban használt dolgozó továbbra is ki van választva. A Műveleti ablaktáblán a **Dolgozó** lapon a **Kompetenciák** csoportban kattintson a **Szakértelem** lehetőségre.
2.  Kattintson az **Új** elemre.
3.  A **Szakértelem** mezőben válassza ki a **Projektvezetés** lehetőséget.
4.  A **Szint** mezőben válassza az **5 Szakértő** lehetőséget.
5.  A **Szint dátuma** mezőben válassza ki a **1-/14/2014** lehetőséget.
6.  A **Tapasztalat (év)** mezőbe írja be, hogy **10**.
7.  Kattintson a **Mentés** gombra, majd zárja be az oldalt.

## <a name="create-a-new-project"></a>Új projekt létrehozása
1.  Kattintson a **projekt igazgatási és számviteli**&gt;**munkaterületek**&gt;**a Projekt management**.
2.  Kattintson az **Új projekt** elemre, majd adja meg a következő értékeket:
    -   **Írja be a projekt** – idő- és anyagelszámolású
    -   **Projekt neve** -XYZ frissítése Phase 2
    -   **Projektcsoport** -TM\_a folyamatban lévő munka
    -   **Szerződés azonosítója a Project** -00000002
3.  Kattintson a **Projekt létrehozása** elemre.

### <a name="assign-a-resource-to-a-project"></a>Erőforrás hozzárendelése egy projekthez

1.  Kattintson a **az emberi erőforrások**&gt;**munkavállalók**&gt;**munkavállalók**.
2.  A **Dolgozók** listában válassza ki az ahhoz a dolgozóhoz tartozó rekordot, akihez korábban kompetenciákat állított be, majd nyissa meg azt.
3.  A Műveleti ablaktáblán a **Projekt** lapon a **Beállítás** csoportban kattintson a **Projekt hozzárendelése** lehetőségre.
4.  Az **Erőforrás-ellenőrzés projekt-hozzárendelései** oldalon kattintson a **Projektek** lapra.
5.  A a **a projekt hozzáadása a kijelölt projektek**, a projekt frissítése Phase 2 XYZ szűrő
6.  A **Fennmaradó projektek** ablaktáblán válasszon ki egy projektet, majd kattintson a nyílra, hogy hozzáadja azt a **Kiválasztott projektek** ablaktáblához.
7.  Zárja be a lapot.

Ha szükséges, hozzárendelhet kategóriákat egy erőforráshoz. A kategória típusa Költség vagy Bevétel lehet. Ezt a szervezet határozza meg. Ha az erőforráshoz nem rendelt kategóriák, Dynamics 365 műveletek az alapértelmezett kategória óránkénti árak költség és bevétel megvizsgál.

### <a name="set-up-project-resource-and-role-characteristics"></a>Projekt erőforrások és szerepkör jellemzők beállítása

A projektvezető a projekterőforrás funkció segítségével hozhat létre a projekthez szükséges szerepköröket. Szerepkörök használhatók, ha igazolt erőforrások még mindig ismeretlen források foglalásakor. Szerepkörök ideiglenesen foglalható tervezett erőforrásként, hogy a projekt tervezési szakaszában továbbra is. 

[![Példa egy szerepkör](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg) 

**Forgatókönyv:** Contoso egy olyan Idő- és anyagprojekt elvégzésére lett felvéve, amely rendelkezik egy jóváhagyott projekt alapszabállyal. A beosztott projektvezető továbbra is a projekt hatókörét tölti ki. Az erőforrás-kezelő adott munkát az új projektben lefoglalt erőforrások jelenleg azonosítja. A projekt szponzor kért, a projekt kritikus jellege miatt a szerepkörök egyike a vezető projektmenedzser. Az erőforrás-kezelő kell szerezni az új erőforrás, és meghatározza a szerepkör a rendszer abban az esetben, ha a kezdő projektmenedzser igényel a projekt tervezése során az erőforrásadatokat. 

A következő lépések bemutatják, hogyan az erőforrás-kezelő beállítása vezető projekt vezető szerepét és jellemzők erőforrás társítása. A későbbiek folyamán a szerepkör használható lesz olyan kereséseknél, amelyek azon elérhető erőforrásokat keresik meg, amelyek megfelelnek a szükséges erőforrás kompetenciáknak.

1.  Kattintson a **projektek igazgatási és számviteli**&gt;**a telepítő**&gt;**erőforrásokat**&gt;**szerepkörök beállítása**.
2.  Kattintson az **Új** elemre, majd adja meg a következő értékeket:
    -   **Szerepkör-azonosító** -projekt vezető
    -   **Leírás** -projekt vezető
3.  Kattintson az **Új** > lehetőségre.
4.  Válassza ki a **Vezető projektmenedzser** szerepkört, és kattintson a **Jellemzők konfigurálása** lehetőségre.
5.  A **Jellemzők típusa** mezőben válassza ki a **Szakértelem** lehetőséget.
6.  Az **Elérhető jellemzők** mezőbe írja be a keresett szakértelmet.
7.  A **Jellemző típusa** mezőben válassza ki a **Diploma** lehetőséget.
8.  Az **Elérhető jellemzők** mezőbe írja be a keresett diploma típusát.
9.  Zárja be az oldalt az **OK** gombra kattintva.

### <a name="assign-a-project-resource-to-a-project"></a>Projekterőforrás hozzárendelése egy projekthez

1.  Kattintson a **projekt igazgatási és számviteli**&gt;**közös**&gt;**projektek**&gt;**minden projekt**, és nyissa meg a **XYZ frissítése Phase 2** projekt.
2.  A **Projektcsapat és ütemezés** fülön kattintson a **Hozzáadás** lehetőségre.
3.  A **Szerepkör** mezőben válassza a **Csapat tagja** lehetőséget.
4.  Kattintson a **Foglalás naptárból** lehetőségre.
5.  Az **Erőforrás elérhetősége** lapon kattintson a **Beállítások megtekintése** lehetőségre.
6.  A **Nézet beállításának módosítása** lapon adja meg az alábbi értékeket:
    -   **Dátum tartomány nézet formátumát** - nap
    -   **Rendelkezésre állás-leírások megjelenítése** - Igen
    -   **Fennmaradó kapacitás megjelenítése** - Igen
7.  Az erőforrások listájából válasszon egy erőforrást.
8.  Kattintson a **kemény könyv**&gt;**teljes kapacitás**.
9.  Zárja be a lapot.

### <a name="assign-a-resource-to-a-default-role"></a>Erőforrás hozzárendelése egy alapértelmezett szerepkörhöz

Projekt- vagy erőforrás-menedzserek könnyebben részletező le lehet foglalni egy projekt erőforrásait tovább. Alapértelmezett szerepkört társíthat már meglévő, valamint újonnan szerzett erőforrásokhoz. Például Daniel utasokkal volt a tapasztalat és készségek üzleti elemző szerepét töltik be. Az erőforrás-kezelő a Daniel's alapértelmezett szerepkörként e szerepkörhöz rendelve; Ezért az erőforrás-kezelő Daniel hozzá egy címkészletet üzleti elemzők, akik rendelkezésére projekten dolgozik. 

Erőforrás-foglaláshoz során a projektmenedzserek szerepkör projekten dolgozik, a rendelkezésre álló erőforrások végezhet. Ezeket az adatokat használhatják egy feltételként több kritérium felhasználásával történő döntéshozatal végrehajtásakor erőforrás teljesítése során. Más erőforrás tulajdonságait is hozzáadhatják a szűrőhöz meghatározott szakértelemmel, végzettséggel és adott projekttapasztalattal rendelkező erőforrások keresésekor. 

**Forgatókönyv:** egy jóváhagyott projekt indult, és a magas rangú project manager szerepkör tervezett erőforrásként, a projekt tervezési szakasza során fenntartott. Az erőforrás-kezelő már megszerezte az erőforrást a Vezető projektmenedzser szerepkör betöltéséhez.

1.  Kattintson a **projektek igazgatási és számviteli**&gt;**a Projekt-erőforrások**&gt;**erőforrások listájában**.
2.  Az **Erőforrás** listán válassza a **Daniel Goldschmidt**nevet.
3.  Kattintson a **a Project erőforrás**&gt;**kezelése**&gt;**erőforrás szerepkör**.
4.  Kattintson az **Új** elemre, majd adja meg a következő értékeket:
    -   **Hatékony** - (aktuális dátum)
    -   **Lejárati** - soha nem
    -   **Szerepkör** -projekt vezető
5.  Kattintson a **Mentés** gombra, majd zárja be az oldalt.
6.  A **Kompetenciák** lapon adja hozzá a **ProjectMgmt** szakértelem és **PMP** tanúsítványt.

## <a name="set-up-role-based-pricing"></a>Szerepköralapú árképzés beállítása
Minden költség, értékesítés, és transzferár beállítható szerepkörökhöz.

1.  Kattintson a **projekt igazgatási és számviteli**&gt;**a telepítő**&gt;**árak**&gt;**eladási ár (óra)**.
2.  Click **New**.
3.  Adja meg az érvénybelépés dátumát.
4.  A **Szerepkör** oszlopban válasszon szerepkört.
5.  Az **Árképzés** oszlopban adja meg a kiválasztott erőforrás-szerepkör árát.

## <a name="form-a-project-team"></a>A projektcsapat űrlap
A korábban beállított árkombinációknak projektben szerepkörök használatához egy projektmenedzser a szerepek kell társítania a projekt. Egy projekt több szerepkör is rendelhető, és a műveletek Dynamics 365 automatikusan ezeket a szerepköröket a problémák elkerülése érdekében a foglalás során. Például ha a projektmenedzser igényel három szoftverfejlesztő, három szoftver mérnök-szerepkörök szoftver mérnök 1, 2 szoftver mérnök, és szoftver mérnök 3 feliratuk szerint automatikusan generál. Ha a szerepkör jellemzőit korábban beállították a szerepkörhöz, ezek szűrőként működnek erőforrás keresése során. A keresést finomíthatja a további szükség szerint további jellemzői lehet adni. 

A beállítások megtekintése is testreszabható, hogy jobb áttekintést adjon a rendelkezésre álló erőforrásról. Lehetőség van óránkénti, napi, heti, havi, negyedéves vagy éves elérhetőség megjelenítésére. Lehetőség van megjeleníteni az elérhető és fennmaradó erőforrások kapacitását. Ez a beállítás jól használható időkezelésre tevékenységek idejének vagy erőforrás elérhetőségének becslésekor. 

A projektmenedzser is az oldalon szerepkör kijelölése és a rendelkezésre álló erőforrás, amely megfelel a szükséglet esetén jelöljük ki egy erőforrást lefoglalni. Ne feledje, hogy az erőforrás nem foglalható ezen a ponton a tervezési szakaszban. A WBS létrehozásakor szerepkörök lecserélheti személyzettel erőforrásokat a projekthez. Ha szerepköröket cseréli, amelyek a WBS személyzettel erőforrások, az erőforrások beállítása automatikusan frissíti a projektcsapat listázása és az ütemezés. 

[![Szerepkörök és a tényleges erőforrásokat tartalmazó projekt team listázása](./media/projectresourcing03-1024x368.jpg)](./media/projectresourcing03.jpg) 

A projektmenedzser több lehetőséggel rendelkezik egy erőforrás projekthez történő lefoglalásához, például **Fennmaradó kapacitás**, **Teljes kapacitás**, **Kapacitás százaléka** és **Óraszám megadása**. Ezek a foglalási beállítások bármikor visszavonhatók, ha az erőforrás-hozzárendelések módosulnak. A foglalásnak két típusa támogatott:

-   **Kemény könyv** – az erőforrás-foglaláshoz jóváhagyott és a megadott ideig foglalkoztatni munkát erősíteni.
-   **Lágy könyv** – az erőforrás-foglalások feltételesen volt beállítva a megadott időre foglalkoztatni munkát.

Az alábbi eljárás ismerteti, hogyan lehet projektcsapatot létrehozni.

### <a name="create-a-project-team"></a>Projektcsapat létrehozása.

1.  Jelöljön ki egy projektet az **Összes projekt** listaoldalon, és kattintson a **Szerkesztés**lehetőségre.
2.  A a **csoport és az ütemezés a projekt** lapon, az a **ütemezés kezdő dátuma** mezőjébe írja be az ütemezés kezdő dátuma plusz egy hónap. Például, ha az ütemezés kezdő dátuma nem 2017. június 24. (24/06/2017), adja meg **24/07/2017**.
3.  Click **Add**.
4.  A **Szerepkör hozzáadása a projekthez** ablakban, a **Szerepkör **mezőben válassza a **Projektmenedzser** lehetőséget.
5.  Kattintson a **Szükséges kompetenciák** lehetőségre.
6.  A **Jellemző választása** oldalon a Vezető projektmenedzser szerepkörhöz korábban beállított jellemzők alapértelmezés szerint be vannak jelölve. Kattintson az **OK** gombra.
7.  A **Szerepkörök hozzáadása projekthez** oldalon az **Erőforrások száma** mezőbe írja be a következőt: **1**.
8.  Az **Erőforrás** mezőben a keresés megjeleníti az összes erőforrást, amely a szükséges kompetenciákkal rendelkezik. Válassza a **Daniel Goldschmidt** nevet, majd kattintson a **Létrehozás** lehetőségre.
9.  Kattintson a **Projekt** lapra, majd a **Hozzáadás** lehetőségre.
10. A **Szerepkör hozzáadása a projekthez** ablakban, a **Szerepkör** mezőben válassza a **Csapattag** lehetőséget. Az **Erőforrások száma** mezőben adja meg a következőt: **5**.
11. Kattintson az **Új** > lehetőségre.
12. A **Projektek** oldalon kattintson az **Erőforrás teljesítése** lehetőségre.

## <a name="resource-capacity-synchronization"></a>Erőforrás-kapacitás szinkronizálása
Az erőforrás-szinkronizálási folyamatok segítségével garantálható, hogy a naptár- és alapnaptáradatok a projekterőforrás-ütemezéssel összhangba kerülnek. Ha a naptár módosult, a folyamatok elvégzik a szükséges frissítéseket a projekterőforrások ütemezéséhez. A folyamatok javítják továbbá a teljesítményt, mert a naptár erőforrásadatait előre szinkronizálják, így az erőforrásütemezési információk frissítései gyorsabban lezajlanak. Javasoljuk, hogy ne egyesével, hanem kötegként ütemezze a folyamatokat. Ellenkező esetben fennáll a kockázata annak, hogy valaki elfelejti az utolsó adatszinkronizálás inkluzív időpontját. Ha az inkluzív időpontokat nem használták, szünetek fordulhatnak elő a dátumszinkronizálás során.

### <a name="calendar-synchronizationmediaprojectresourcing04-1024x471jpg"></a>![Naptár szinkronizálása](./media/projectresourcing04-1024x471.jpg)

**Synchronize resource capacity roll-ups**

A szinkronizálási folyamat arra szolgál, hogy az összes naptári erőforrásadatot szinkronizálja. Ez az információ alapnaptár adatokat tartalmaz a projekt Erőforrásnaptár kapacitás tábláját ért bármely módosításról. Új erőforrások hozzáadása a project programban, ha szinkronizálás biztosítja, hogy a frissített adatok érhető el. Ez a szinkronizálás bármikor megtehető. 

Köteg használatát javasoljuk. A beállítások a kapacitásfoglalások szinkronizálása lehetőségnél érhető el.

-   Kattintson a **projekt igazgatási és számviteli**&gt;**időszakos**&gt;**kapacitás szinkronizálás**&gt;**szinkronizálása az erőforrás-kapacitás-összesítésben**.

| Lehetőség | Leírás                                                                                                                                                                                          |
|--------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Igen    | Szinkronizálja az összes erőforrásadatot a naptárral és az alapnaptár-információval, és cserélje le az összes információt a projekterőforrás kapacitásnaptárában.                                                  |
| Szám     | Szinkronizálja az erőforrásadatot dátumintervallum-kód és meghatározott kezdő és záró dátum szerint. Ez a beállítás nem távolítja el a meglévő adatokat, és csak az újonnan hozzáadott erőforrások adatait frissíti. |

[![A szinkronizálási folyamat](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)

## <a name="set-up-roles-on-wbs-templates"></a>WBS sablonok szerepköreinek beállítása
A projektvezetők beállíthatnak olyan WBS-sablonokat, amelyek felhasználhatók új WBS-projektek létrehozásakor. A projektmenedzserek adhat hozzá szerepköröket a sablon létrehozásakor. A következő eljárással szerepkör hozzárendelése a WBS-template.* * **

1.  Kattintson a **projekt igazgatási és számviteli**&gt;**a telepítő**&gt;**projektek**&gt;**munkalebontási struktúra sablonjai**.
2.  Kattintson a **Részletek** lehetőségre a kiválasztott WBS-sablonnál.
3.  Jelöljön ki egy feladatot a listán, majd a **Szerepkör** mezőben válassza ki a feladathoz társítandó szerepkört.

### <a name="work-with-a-wbs"></a>A WBS használata

Létrehozhat egy új WBS-t, vagy másolhat egyet egy meglévő WBS-sablonból. Egy projektvezető egyszerűen kezelheti az erőforrásokat szerepkörök hozzárendelésével új feladatokhoz a WBS rendszerében. Egy erőforrás beszerzését, vagy a feladathoz tartozó megerősített erőforrások azonosítását követően lecserélhetők a szerepkörök. Ez a rugalmasság a következő feladatok végrehajtását teszi lehetővé a projektmenedzsernek:

-   Szükséges számú erőforrások azonosítása WBS munkacsomagok számára.
-   Projektköltség becslése.
-   Előzetes költségvetés megállapítása.
-   Tevékenységi időtartam becslése, szerepkörök és erőforrások alapján.
-   Projektvezetési tervek fejlesztése, a rendelkezésre álló projektinformációk alapján.

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
<td>Tervezett erőforrások automatikus hozzáadása társított feladattal rendelkező szerepkörök használatával. 365 Dynamics műveletek automatikusan felajánlja a tervezett erőforrások szerepkörök alapján több feltétel határozat elemzés segítségével. Miután a szerepkörök és munka (órák) be lettek állítva a WBS-ben található feladatokhoz, és a struktúra ki lett adva, kattintson a <strong>Csapat automatikus létrehozása</strong> lehetőségre. A tervezett erőforrások szükséges száma hozzáadódik a WBS-hez és a <strong>Projekt és csapat ütemezés</strong> laphoz.</td>
</tr>
<tr class="odd">
<td>Erőforrás (legördülő lista)</td>
<td>Az <strong>Erőforrás-hozzárendelés indítása </strong>lapon kiválaszthatja az erőforrásokat végleges vagy ideiglenes lefoglalásra, a megadott időtartam alapján. Módosíthatja a nézetbeállításokat, hogy megtekintse és beállítsa az erőforrás-tevékenységek időtartamát. Kiválaszthat és társíthat erőforrásokat a munkacsomag szintjén, a következő beállítások használatával:
<ul>
<li><strong>Elfogadás</strong> – A feladathoz társított erőforrásban bekövetkezett módosítások megerősítése.</li>
<li><strong>Mégse</strong> – A feladathoz társított erőforrásban bekövetkezett módosítások érvénytelenítése.</li>
<li><strong>Automatikus kiosztása</strong> – ezt a beállítást választja, egy rendelkezésre álló személyzettel erőforrás a kijelölt feladathoz megfelelő szerepkörrel rendelkező.</li>
</ul></td>
</tr>
</tbody>
</table>

1.  Kattintson a **projekt igazgatási és számviteli**&gt;**projektek**&gt;**minden**.
2.  Válassza ki a listából az **XYZ Frissítési Fázis 2** projektet.
3.  Kattintson a **tervezett**&gt;**tevékenységek**&gt;**munkalebontási szerkezet**.
4.  Kattintson az **Új** gombra, hogy a WBS-hez adja a következő elsőszintű tevékenységeket:
    -   Indítás
    -   Tervezés
    -   Végrehajtás folyamatban
    -   Rendszerfigyelés és ellenőrzés
    -   Közeli

5.  A dátumok és erőkifejtés (óra), ahogy az a következő képernyőkép. [![Beállítás, a dátumok és tevékenységi](./media/projectresourcing10.jpg)](./media/projectresourcing10.jpg)
6.  Válassza ki az **Indítás** tevékenység-sort, majd a **Szerepkör** mezőben válassza ki **Vezető Projektmenedzser** lehetőséget.
7.  Kattintson a **Közzététel** gombra.
8.  Ugyanabban a sorban az **Erőforrás** mezőben válassza ki a **Daniel Goldschmidt** lehetőséget.
9.  Kattintson az **Elfogadás** gombra.
10. Válassza ki a **Tervezés** tevékenység-sort, majd a **Szerepkör** mezőben válassza ki az **Üzleti elemző** lehetőséget.
11. Kattintson a **Közzététel**, majd a **Csapat automatikus előállítása** gombra.
12. A megjelenő párbeszédpanelen kattintson az **Igen** gombra.
13. Győződjön meg róla, hogy az **Erőforrás** mezőben az érték **Üzleti elemző 1**.
14. Az **Üzleti elemző 1** erőforráshoz, nyissa meg a keresőt és kattintson **Erőforrás-hozzárendelések képernyő indítása**.
15. Válasza ki a dolgozót a feladathoz.
16. Kattintson a **lágy hozzárendelése**&gt;**teljes kapacitás**.
17. Kattintson a **Mentés** gombra és zárja be az oldalt. 

> [!NOTE] 
> Egy figyelmeztetés, hogy a megadott erőforrás már 2, nem kap, mert az erőforrások száma 1 helyen marad.
18. Az a **munkalebontási struktúra **oldalon, a WBS-t az erőforrás-hozzárendelés ellenőrzése, és kattintson **Mentés**.

## <a name="resource-fulfillment-for-planned-resources"></a>A tervezett erőforrások erőforrás-teljesítése
Egy projektvezető megtervezheti a szükséges erőforrás-szerepköröket egy projekthez. Az erőforrás-kezelő ezeket a tervezett erőforrásokat kérelemként fogja látni az **Erőforrás teljesítése** oldalon, és tényleges erőforrásokat rendelhet hozzzájuk.

1.  Kattintson a **projekt igazgatási és számviteli**&gt;**projektek**&gt;**minden**.
2.  Válassza ki a listából az **XYZ Frissítési Fázis 2** projektet.
3.  Kattintson a **Projekt** lehetőségre.
4.  Kattintson a **Szerkesztés**lehetőségre.
5.  A a **csoport és az ütemezés a projekt** lap ** ** kattintson a **hozzáadása**.
6.  A **Szerepkörök hozzáadása** párbeszédpanelen jelölje ki a **Szoftverfejlesztő** szerepkört.
7.  Kattintson az **Új** > lehetőségre.
8.  Zárja be a projektlapot.
9.  Kattintson a **projektek igazgatási és számviteli**&gt;**a Projekt-erőforrások**&gt;**erőforrás teljesítési**.
10. Válassza ki a **Szoftverfejlesztő 1** lehetőséget az **XYZ Frissítési projekt Fázis 2** projekthez.
11. Válasszon ki egy dolgozót, majd kattintson a **Hozzárendelés** gombra.
12. Ellenőrizze, hogy a **Szoftverfejlesztő 1** sora el lett távolítva a **XYZ Frissítési projekt Fázis 2** projektből.
13. A **Projektcsapat és ütemezés** lapon ellenőrizze, hogy az **XYZ Frissítési Fázis 2** projekthez a dolgozó, akit kiválasztott a 11. lépésben hozzá lett adva, úgy mint egy **Szoftverfejlesztő**.

## <a name="requests-for-project-resources"></a>Projekterőforrások iránti kérelmek
A projekt erőforrás-ütemezési szolgáltatásaira csak az erőforrás-kezelők bekapcsolódása vagy projektek személyzettel erőforrások elosztása támogatja. A funkció engedélyezéséhez a következő feladatokat, vagy győződjön meg arról, hogy azok befejeződtek.

-   Számsorozatok beállítása.
-   Projektvezetési és számviteli munkafolyamatok beállítása.
-   Erőforrás-kérelem munkafolyamata engedélyezése.

Vagy ellenőrzött vagy a fenti műveletek végrehajtása, után kitöltheti az alábbi feladatok, szükség szerint.

-   Ideiglenes személyzettel erőforrás létrehozása erőforrás-igénylést.
-   Erőforrás-kérések figyelése.
-   Erőforrás-kérelmek teljesítése.
-   WBS személyzettel erőforrások kérnie.
-   Könyv erőforrások személyzettel erőforrás iránti kérelem nélküli projekt.

## <a name="monitor-project-teams"></a>Monitor projekt csapatok
1.  Kattintson a **projekt igazgatási és számviteli**&gt;**projektek**&gt;**minden**.
2.  A projektek listájában kattintson a **Projektazonosító** hivatkozásra az **XYZ Frissítési Fázis 2** projektnél.
3.  A **Projektcsapat és ütemezés** gyorslapon győződjön meg róla, hogy a felsorolt projekterőforrások helyesek.



