---
title: Dokumentáció vagy képzés létrehozása Feladatrögzítő segítségével
description: Ez a témakör azt ismerteti, hogy mik azok a Feladatrögzítő és a feladat-útmutatók, hogyan hozhat létre rögzítéseket, és hogyan szabhatja testre a Microsoft-feladatútmutatókat, illetve hogyan szerepeltesse azokat a Súgóban.
author: josaw1
ms.date: 03/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysHelpSetup
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.custom: 25391
ms.assetid: 59bf39f8-1464-441e-8b23-9a856c73471b
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 448c2b302136e595852c423d53e49adfcc40d12d
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8070526"
---
# <a name="create-documentation-or-training-with-task-recorder"></a>Dokumentáció vagy képzés létrehozása Feladatrögzítő segítségével

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Ez a témakör azt ismerteti, hogy mik azok a Feladatrögzítő és a feladat-útmutatók, hogyan hozhat létre feladatrögzítéseket, és hogyan szabhatja testre a Microsoft-feladatútmutatókat, illetve hogyan szerepeltesse azokat a Súgóban.

> [!IMPORTANT]
> Rögzítheti saját feladat-útmutatóit a Dynamics 365 Human Resources számára, de jelenleg nem mentheti őket az Üzletifolyamat-modellező (BPM) tárba, illetve nem nyithatja meg őket a Súgó ablaktáblából. Mentheti őket helyben vagy egy hálózati helyre, majd megnyithatja és újra lejátszhatja őket a Feladatrögzítő használatával. 

## <a name="learn-about-task-recorder"></a>További tudnivalók a Feladatrögzítőről

A Feladatrögzítő egy olyan eszköz, amellyel a termék felhasználói felületén (UI) elvégzett műveleteket jegyezheti fel. A Feladatrögzítő használatakor az összes, felhasználói felületben elvégzett, a szerveren végrehajtott esemény — beleértve az értékhozzáadást, beállítások megváltoztatását, adatok eltávolítását — rögzítésre kerül. A rögzített lépések összességét *feladatrögzítésnek* hívják. A Feladatrögzítő sokféleképpen használható:

-   **Feladatrögzítők feladat útmutatókként lejátszhatók.** A feladat-útmutatók a Súgó nyújtotta élmény szerves részét képezik. A feladat-útmutató irányított, vezérelt, interaktív élmény, amely végigvezet az üzleti folyamat lépésein. A felhasználónak teljesítenie kell minden lépést felugró kérdések (vagy "buborékdiagram") révén, amely keresztülmozog a felhasználói felületen és azon elemére mutat, amellyel a felhasználónak interakcióba kellene lépnie. A „buborékdiagram” arról is tájékoztatást ad, hogyan kellene interakcióba lépni az elemmel, például "Kattintson ide" vagy "Adjon meg egy értéket ebben a mezőben". A feladat-útmutató a felhasználó aktuális adathalmazára vonatkozóan fut és a bevitt adatok a felhasználó környezetében kerülnek mentésre.
-   **Feladatrögzítők Word dokumentumként menthetők.** Ez lehetővé teszi nyomtatható képzési útmutatók egyszerű létrehozását.

Létrehozhatja saját feladatrögzítését, lejátszhatja a Microsoft által biztosított feladatrögzítéseket vagy módosíthatja a Microsoft által biztosított feladatrögzítéseket a saját konfigurációja szerint. A Feladatrögzítővel kapcsolatos további információkért lásd: [Feladatrögzítő](task-recorder.md).

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
-   A feladatrögzítés mindegyik lépéséhez jegyzetet hozhat létre. Feladatútmutató lejátszáskor a jegyzetek "buborékdiagram"-ként jelennek meg, a lépéshez tartozó megjegyzésként szöveg alatt vagy felett. A Súgó ablakban szövegként való megtekintésekor a lépésben a jegyzetek sorközi szövegként jelennek meg. A leíráshoz hasonlóan, a megjegyzéseket is ajánlatos egy különálló dokumentumban megírni és elmenteni. A feladatrögzítés rögzítésekor, vágja ki és illessze be a jegyzeteket ebből a dokumentumból.

**Ismerje meg a különböző jegyzettípusokat** A megjegyzések nem kötelezőek. Csak akkor adjon hozzá jegyzeteket, ha a felhasználó számára hasznos információt tartalmaznak.

-   **Cím**: A címhez tartozó jegyzet a Feladatrögzítő által automatikusan létrehozott lépés szövege előtt jelenik meg. A feladat útmutatóban a címjegyzet az automatikus létrehozott szöveg felett jelenik meg. E jegyzettípus használatával elmagyarázhatja, hogy a felhasználó miért is csinálja ezt a lépést, vagy további értelmezést adhat.

Ez a szerkesztési ablak látható jegyzet hozzáadásakor, rögzítés készítése közben. Írja be a címjegyzetet a **Cím** mezőbe. 

[![A szerkesztési ablaktábla címjegyzettel.](./media/screen1.png)](./media/screen1.png) 

Így néz ki a feladat-útmutató „buborékdiagramjában” található címjegyzet. 

[![A címjegyzet megjelenése a feladatok útmutatóban.](./media/screen2.png)](./media/screen2.png)

-   **Megjegyzések:** A megjegyzéshez tartozó jegyzet a Feladatrögzítő által automatikusan létrehozott lépés szövege után jelenik meg. A feladat útmutatóban csak akkor lesz látható, ha a felhasználó rákattint a **Részletesebben** hivatkozásra a felada útmutató buborékdiagramjában. E típus használatával mindent leírhat, amit a felhasználónak tudnia kell a lépés teljesítéséhez.

Ez a szerkesztési ablak látható jegyzet hozzáadásakor, rögzítés készítése közben. Írjon be jegyzetet a megjegyzésekhez a **Megjegyzések** mezőbe. 

[![Szerkesztés ablaktábla megjegyzésekkel a Megjegyzések mezőben.](./media/screen3.png)](./media/screen3.png) 

Így néznek ki a feladat-útmutató „buborékdiagramjában” található jegyzetek.

[![A címmegjegyzések megjelenése a feladatok útmutatóban.](./media/screen4.png)](./media/screen4.png)

-   **Tájékoztató lépés**: Ezek a megjegyzések létrehozhatóak jobb kattintással egy vezérlőelemen vagy bárhol a képernyőn &lt; **Feladatrögzítő** &lt; **Tájékoztató lépés hozzáadása**. A tájékoztató lépések számozott lépésként jelennek meg bárhol, ahova beszúrta őket, még akkor is, ha művelet nem volt a felhasználói felületen rögzítve. Űrlapszíntű információs lépést adhat hozzá vagy információs lépéshez hozzárendelt vezérlést. Ha az információs lépés képernyőhöz van hozzárendelve, a feladat útmutató "buborékdiagramja" jelenik meg a képernyőn, kurzor nélkül, a feladat útmutató lejátszása közben. Ha az információs lépés vezérlőelemhez van társítva, a feladat útmutató "buborékdiagramja" a vezérlőelemre elemre mutat, a feladat-útmutató lejátszása közben. A Súgó ablaktáblán egy információs lépésről szóló jegyzet jelenik meg számozott lépésként az Ön által beírt szöveggel. Használja az információs lépéseket a felhasználó következő lépésre való felkészítésére, az alkalmazáson kívüli lépések leírására, vagy más rögzítésekre való hivatkozásra (hiperhivatkozások létrehozása a jegyzetekben nem lehetséges).

**Határozza meg, milyen hosszú legyen a felvétel**

-   A felhasználó általában vagy elolvassa vagy lejátssza a felvételt az elejétől a végéig, ezért ne kombináljon lépéseket vagy feladatokat, melyeket jobb külön elvégezni.
-   Lehetőleg ne rögzítsen több alfolyamatra kiterjedő hosszú változatokat. Például az "Üzleti ügyfélszolgálat működtetése" túl tág; válassza szét rövidebb feladatokra, például az "Visszáru elfogadása" és "Hozzáadás ajándékutalványhoz".
-   Ha egy feladat több különböző üzleti folyamat részeként hajtható végre, hozzon létre külön felvételt majd hivatkozzon rá a többi felvételben.
-   Ha a folyamat több olyan feladatot tartalmaz, amelyeket a személy egyszerre végez el, egy felvételen tarthatja a feladatokat, például a "Funkcióprofilok beállítása és hozzárendelése" esetében.
-   Ha olyasvalami, amit valaki csak egyszer végez el (például konfiguráció) és utána azonnal végrehajtható, de többször elvégezhető másik feladat, vagy magában is elvégezhető, válassza szét őket két feladatrögzítésre.

**Döntse el, hol induljon a rögzítés a felhasználói felületen** Az oldal, amelyiken éppen van a feladatrögzítés indításakor, hatással van arra, hogy a feladatrögzítés melyik lapra vonatkozóan van megjelenítve. Például ha azt szeretné, hogy a feladatrögzítés a Súgó ablakban jelenjen meg, amikor a felhasználó a Főkönyvi paraméterek lapra kattint, a rögzítést a Főkönyvi paraméterek lapon kell kezdenie. **Felvétel mentése .axtr fájlként** Ha befejezte egy feladatrögzítés létrehozását vagy szerkesztését, több lehetősége is van, hogy hogyan szeretné letölteni vagy menteni a felvételt. Letöltheti a fájlt feladatrögzítő-csomagként (.axtr), nyers felvételfájlként (.xml), Word-dokumentumként vagy mentheti a fájlt egy LCS-tárba. Célszerű a feladatrögzítést mindig feladatrögzítő-csomagként menteni. Ez megkönnyíti a fájl karbantartását ha a későbbiekben jegyzetek vagy eljárások megváltoztatására lenne szükség. Ha Word-dokumentumként szeretné letölteni a fájlt, feladatrögzítő-csomagként is mentse azt.

## <a name="create-your-task-recording"></a>Hozza létre saját feladatrögzítését
Részletes leírásért lásd: [Feladatrögzítő erőforrásai](task-recorder.md).

## <a name="copy-and-customize-microsofts-task-recordings"></a>A Microsoft feladatrögzítéseinek másolása és testreszabása
Letöltheti és szerkesztheti a Microsoft feladatrögzítéseit a saját képzési anyagaihoz és súgódokumentációjához történő felhasználás érdekében. A Microsoft feladatrögzítéseinek letöltéséhez kövesse az alábbi lépéseket:

1.  Nyissa meg a Feladatrögzítőt. A Feladatrögzítő a **Beállítások** menüben található.
2.  A Feladatrögzítő ablakban kattintson a **Felvétel karbantartása** lehetőségre.
3.  A **Hol található a felvétel** területen, kattintson a **LCS-tárban található** lehetőségre.
4.  Kattintson **Válassza ki az LCS-tárat** lehetőségre.
5.  Jelölje ki a Microsoft globális könyvtárat.
6.  A fastruktúrában válassza ki azt az üzleti folyamatok tára alcsomópontot, amelyhez a feladatrögzítés hozzá van rendelve.
7.  Kattintson az **OK** gombra.
8.  Kattintson a **Start** parancsra.
9.  Ezen a ponton lépésenként haladjon végig a felvételen és változtassa meg bármelyik lépést az újrarögzítés közben. **Megjegyzés**: Ha csak a felvétel szövegét szeretné módosítani, megnyithatja a felvételt **Felvétel jegyzeteinek rögzítése** módban, és mentheti azt.
10. Miután a felvétel végig lejátszásra került, kattintson **Leállítás** elemre a képernyő tetején található Feladatrögzítő sávon.
11. Válassza ki, hogyan szeretné menteni a feladatrögzítést



## <a name="additional-resources"></a>További erőforrások

[Súgórendszer](../../fin-ops/get-started/help-overview.md)

[A Súgórendszer csatlakoztatása](../../fin-ops/get-started/help-connect.md)

[Feladatrögzítő](task-recorder.md)

[Multimédiás súgótémakörök létrehozása a Feladatrögzítővel (külső hivatkozás)](https://mbspartner.microsoft.com/AX/Videos/970)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]