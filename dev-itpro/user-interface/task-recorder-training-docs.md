---
title: "Dokumentáció vagy képzés létrehozása feladatrögzítések segítségével."
description: "Ez a témakör részletesen ismerteti, milyen Feladatrögzítő és segédvonalak feladat, feladat felvételek, létrehozása és testreszabásáról a Microsoft feladat útmutatók és azokat a Súgó."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysHelpSetup
audience: Application User, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 25391
ms.assetid: 59bf39f8-1464-441e-8b23-9a856c73471b
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b21fd97426b331726c12ea29f89817a46dd445c3
ms.openlocfilehash: 38bce4a843f0db575c8d1ba08b7dc2ece8366663
ms.lasthandoff: 03/31/2017


---

# <a name="create-documentation-or-training-using-task-recordings"></a>Dokumentáció vagy képzés létrehozása feladatrögzítések segítségével.
Ez a témakör részletesen ismerteti, milyen Feladatrögzítő és segédvonalak feladat, feladat felvételek, létrehozása és testreszabásáról a Microsoft feladat útmutatók és azokat a Súgó.

<a name="learn-about-task-recorder"></a>További tudnivalók a Feladatrögzítőről
-------------------------

A Feladatrögzítő, akkor tegye meg a termék felhasználói felület (UI) műveletek rögzítéséhez használt műveletek eszköz a Microsoft Dynamics 365. A Feladatrögzítő használatakor az összes, felhasználói felületben elvégzett, a szerveren végrehajtott esemény — beleértve az értékhozzáadást, beállítások megváltoztatását, adatok eltávolítását — rögzítésre kerül. A rögzített lépések összességét *feladatrögzítésnek*hívják. A Feladatrögzítő sokféleképpen használható:

-   **Feladatrögzítők feladat útmutatókként lejátszhatók.** Feladat segédvonalai a Dynamics 365 műveletek segítségével tapasztalat egy szerves részének. A feladat segédvonalra szüksége egy ellenőrzött, interaktív, interaktív élmény, üzleti folyamat lépésein. A felhasználónak teljesítenie kell minden lépést felugró kérdések (vagy "buborékdiagram") révén, amely keresztülmozog a felhasználói felületen és azon elemére mutat, amellyel a felhasználónak interakcióba kellene lépnie. "Buborék" is tartalmaz adatokat arról, hogyan kezelje az elem, mint például "Kattintson ide" vagy "Ebben a mezőben adjon meg egy értéket." Egy feladat útmutató ellen a felhasználó aktuális adatkészletre fut, és a bevitt adatokat menti a felhasználói környezet.
-   **Feladat felvétel eljárási lépések, a Súgó ablakban megjeleníthető.** A Súgó ablaktábla segítségével megkeresheti és feladat felvételek megjelenítéséhez. A Súgó ablak eléréséhez kattintson a **?** Ikon a felső navigációs sáv, vagy használhatja a billentyűparancs, **Ctrl + Shift +?**. A Súgó ablak rögzítése feladat lépéseit el tudja olvasni, vagy feladat útmutatóként a felvétel lejátszása, végigvezet a felhasználói felület mellett is dönthet.
-   **Feladatrögzítések BPM-be menthetők.** A feladatrögzítést hierarchiasorhoz is mentheti, a Lifecycle Services (LCS) szolgáltatásban lévő Üzletifolyamat-modellező (BPM) tárba. Felsorolt lépések és az üzleti folyamatok ábrája a rögzítésből kerül létrehozásra. Feladat felvétel BPM könyvtárba mentett Dynamics 365 műveletekhez, súgó jeleníthető meg.
-   **Feladatrögzítők Word dokumentumként menthetők.** Ez lehetővé teszi nyomtatható képzési útmutatók egyszerű létrehozását.

Hozzon létre saját feladat felvételek, Microsoft által biztosított feladat felvétel lejátszása vagy a Microsoft által biztosított feladat felvételek a konfigurációt megfelelően módosítani. A Feladatrögzítő kapcsolatos további tudnivalókért lásd: [műveletekhez 365 Dynamics Feladatrögzítő](task-recorder.md).

## <a name="plan-your-task-recording"></a>Tervezze meg feladatrögzítését
Ha új feladatrögzítést készít vagy a rögzítéseit Microsoft feladatrögzítőre alapozza, vegye figyelembe a következőket.

-   Úgy tervezze meg a felvételeit mint egy videót. Minden döntését előre hozza meg.
-   Nézze át az üzleti folyamatot egyszer vagy kétszer, felvétel készítése nélkül, a lépések megértése érdekében.
-   Ha felvétel előtt végigmegy a folyamaton, jegyezze meg hogy hol használt billentyűparancsot vagy az **Enter** billentyűt, így elkerülheti használatukat a tényleges rögzítés közben.
-   Azonosítsa a következőket:
    -   Szeretné csoportosítani a lépéseket alfeladatokba? Az alfeladatok a folyamat vizuálisan szétválasztott részei. Például ha feladatrögzítést hoz létre "Termék létrehozása és kiadása"-nak, szeretné csoportosítani a termék létrehozásához szükséges lépéseket, majd a termék kiadásához szükséges lépéseket. Az alfeladatok könnyebben olvashatóvá teszik a hosszabb folyamatokat.
    -   Szeretne hozzáadni a jegyzeteket, és ha igen, hol? További információ az "Ismerje meg a különböző jegyzettípusokat" című témakörben olvasható.
    -   Milyen értékeket ad meg a különböző mezőknek az üzleti folyamat teljesítése során? Tanácsos tudni, hogy mit fog kijelölni vagy beírni menet közben, így nem kell visszalépnie vagy nem véglegesíti a hibákat felvétel közben.

**Előre írja le jegyzeteit és a leírást**

-   Minden feladatrögzítés elején található egy leírásmező, amely lehetővé teszi a rögzítés bemutatását. Javasolt előre megírni és elmenteni a leírást egy külön dokumentumban, így bemásolhatja azt a feladatrögzítőbe rögzítés közben. Ezzel a módszerrel időt tölthet el a szöveg finomításával, a rögzítési folyamaton kívül. A szöveg kivágása és beillesztése a rögzítési folyamatot gyorsabbá és könnyebbé teszi.
-   A feladatrögzítés mindegyik lépéséhez jegyzetet hozhat létre. Feladatútmutató lejátszáskor a jegyzetek "buborékdiagram"-ként jelennek meg, a lépéshez tartozó megjegyzésként szöveg alatt vagy felett. A Súgó ablaktábla szövegként megtekintve lépésben szöveg szövegközi jegyzetek jelennek meg. A leíráshoz hasonlóan, a megjegyzéseket is ajánlatos egy különálló dokumentumban megírni és elmenteni. A feladatrögzítés rögzítésekor, vágja ki és illessze be a jegyzeteket ebből a dokumentumból.

**Ismerje meg a különböző jegyzettípusokat** A megjegyzések nem kötelezőek. Csak akkor adjon hozzá jegyzeteket, ha a felhasználó számára hasznos információt tartalmaznak.

-   **Cím**: A cím jegyzet fog megjelenni előtt a lépés szöveget, hogy a feladat a felvevő automatikusan generál. A feladat útmutató a cím jegyzet felett az automatikusan generált szöveg jelenik meg. E jegyzettípus használatával elmagyarázhatja, hogy a felhasználó miért is csinálja ezt a lépést, vagy további értelmezést adhat.

Ez a szerkesztési ablak látható jegyzet hozzáadásakor, rögzítés készítése közben. Írja be a címjegyzetet a **Cím** mezőbe. 

[![képernyő1](./media/screen1.png)](./media/screen1.png) 

Így néz ki a feladat-útmutató „buborékdiagramjában” található címjegyzet. 

[![képernyő2](./media/screen2.png)](./media/screen2.png)

-   **Megjegyzések:** A megjegyzéshez tartozó jegyzet a Feladatrögzítő által automatikusan létrehozott lépés szövege után jelenik meg. A feladat útmutatóban csak akkor lesz látható, ha a felhasználó rákattint a **Részletesebben** hivatkozásra a felada útmutató buborékdiagramjában. E típus használatával mindent leírhat, amit a felhasználónak tudnia kell a lépés teljesítéséhez.

Ez a szerkesztési ablak látható jegyzet hozzáadásakor, rögzítés készítése közben. Írjon be jegyzetet a megjegyzésekhez a **Megjegyzések **mezőbe. 

[![screen3](./media/screen3.png)](./media/screen3.png) 

Ez az a notes jegyzet néz a feladat Guide "buborék".

[![screen4](./media/screen4.png)](./media/screen4.png)

-   **INFO lépés**: A jegyzet jobb gombbal a vezérlőelem, vagy bárhol a képernyőn hozza létre &lt;**a Feladatrögzítő**&lt; ** info lépés hozzáadása. ** Információ lépéseket jelennek meg egy számozott lépés bármely pontján szúrunk be, annak ellenére, hogy nem lett felvéve a felhasználói felületen. Űrlapszíntű információs lépést adhat hozzá vagy információs lépéshez hozzárendelt vezérlést. Ha az információs lépés képernyőhöz van hozzárendelve, a feladat útmutató "buborékdiagramja" jelenik meg a képernyőn, kurzor nélkül, a feladat útmutató lejátszása közben. Egy info lépés társítva egy vezérlőelemet, a feladat útmutató "buborék" az a tevékenység útmutató lejátszáskor fog mutatni a vezérlőhöz. A Súgó ablaktábla info lépés jegyzet fog megjelenni számozott lépésben beírt bármilyen szövegre. Ezen információ lépéseket Dynamics 365 műveletek kívül kell elvégezni, vagy lehet hivatkozni más felvételek (bár nem hozható létre hyperinks jegyzetek.) szükséges lépések leírása a következő lépéseket a felhasználótól.

**Határozza meg, milyen hosszú legyen a felvétel**

-   A felhasználó általában vagy elolvassa vagy lejátssza a felvételt az elejétől a végéig, ezért ne kombináljon lépéseket vagy feladatokat, melyeket jobb külön elvégezni.
-   Lehetőleg ne rögzítsen több alfolyamatra kiterjedő hosszú változatokat. Például az "Üzleti ügyfélszolgálat működtetése" túl tág; válassza szét rövidebb feladatokra, például az "Visszáru elfogadása" és "Hozzáadás ajándékutalványhoz".
-   Ha egy feladat több különböző üzleti folyamat részeként hajtható végre, hozzon létre külön felvételt majd hivatkozzon rá a többi felvételben.
-   Ha a folyamat több olyan feladatot tartalmaz, amelyeket a személy egyszerre végez el, egy felvételen tarthatja a feladatokat, például a "Funkcióprofilok beállítása és hozzárendelése" esetében.
-   Ha olyasvalami, amit valaki csak egyszer végez el (például konfiguráció) és utána azonnal végrehajtható, de többször elvégezhető másik feladat, vagy magában is elvégezhető, válassza szét őket két feladatrögzítésre.

**Döntse el, ha a felhasználói felület, a felvétel elkezdéséhez** az oldalon, nem a feladat felvétel rögzítés megkezdése érint melyik oldal a feladat útmutató jelenik meg. Például ha azt szeretné, hogy a feladat felvétele a Súgó ablakban szereplő kattintáskor súgó a főkönyvi paraméterek lapon, el kell indítania a felvétel a főkönyvi paraméterek lapon. **Felvétel mentése .axtr fájlként** Ha befejezte egy feladatrögzítés létrehozását vagy szerkesztését, több lehetősége is van, hogy hogyan szeretné letölteni vagy menteni a felvételt. Letöltheti a fájlt feladatrögzítő-csomagként (.axtr), nyers felvételfájlként (.xml), Word-dokumentumként vagy mentheti a fájlt egy LCS-tárba. Célszerű a feladatrögzítést mindig feladatrögzítő-csomagként menteni. Ez megkönnyíti a fájl karbantartását ha a későbbiekben jegyzetek vagy eljárások megváltoztatására lenne szükség. Ha Word-dokumentumként szeretné letölteni a fájlt, feladatrögzítő-csomagként is mentse azt.

## <a name="create-your-task-recording"></a>Hozza létre saját feladatrögzítését
Részletes segédlet lépések, lásd [létrehozása a feladat felvétel](task-recorder.md).

## <a name="copy-and-customize-microsofts-task-recordings"></a>A Microsoft feladatrögzítéseinek másolása és testreszabása
Töltse le, és szerkesztheti a Microsoft feladat felvétel a saját súgóját vagy képzési anyagok segítségével. A Microsoft feladatrögzítéseinek letöltéséhez kövesse az alábbi lépéseket:

1.  Műveletek 365 Dynamics nyissa meg a Feladatrögzítő. A Feladatrögzítő a **Beállítások** menüben található.
2.  A Feladatrögzítő ablakban kattintson a **Felvétel karbantartása** lehetőségre.
3.  A **Hol található a felvétel** területen, kattintson a **LCS-tárban található** lehetőségre.
4.  Kattintson **Válassza ki az LCS-tárat** lehetőségre.
5.  Jelölje ki a Microsoft globális könyvtárat.
6.  A fastruktúrában válassza ki azt az üzleti folyamatok tára alcsomópontot, amelyhez a feladatrögzítés hozzá van rendelve.
7.  Kattintson az **OK** gombra.
8.  Kattintson a **Start**parancsra.
9.  Ezen a ponton lépés a felvétel módosítása lépések végrehajtása közben újra felvesz keresztül. **Megjegyzés:**: Ha csak szeretnénk változtatni a szöveget a felvétel, megnyithatja a felvétel a **a felvétel jegyzetek szerkesztése** mód, majd mentsük.
10. Miután a felvétel végig lejátszásra került, kattintson **Leállítás** elemre a képernyő tetején található Feladatrögzítő sávon.
11. Válassza ki, hogyan szeretné menteni a feladatrögzítést

## <a name="include-your-task-recordings-in-the-help-pane"></a>A feladat felvételek bevonni a Súgó ablaktábla
Saját egyéni feladat felvételek megjelenítése a Súgó ablaktábla így lejátszási feladat segédvonalakként, vagy megtekinthető szövegként, a feladat felvételek saját BPM könyvtárba menteni, és frissítse a BPM tárban mutasson a Súgó rendszer paraméterek. További tudnivalókért lásd: [kapcsolódás a súgóban.](../get-started/help-connect.md)

<a name="see-also"></a>Lásd még
--------

[365 Dynamics műveletek Súgó](..\get-started\help-overview.md)

[Csatlakozás a Súgó](..\get-started\help-connect.md)

[A Feladatrögzítő 365 Dynamics műveletek](task-recorder.md)

[Nemrégiben tevékenység író szolgáltatások](\core\get-started\recently-added-editing-features-in-task-recorder)

[A Dynamics AX (külső hivatkozás) feladatrögzítővel életciklus szolgáltatások belül új képzési könyvtárak létrehozása](https://docs.com/mufife/163372c6-f366-4c5a-94fa-93e2c25f878a/creating-new-training-libraries-for-dynamics-ax)

[Hozzon létre Rich súgótémakörök Feladatrögzítő (külső hivatkozás)](https://mbspartner.microsoft.com/AX/Videos/970)


