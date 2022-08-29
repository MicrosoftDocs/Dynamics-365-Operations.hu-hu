---
title: Feladatrögzítő és Súgó a Retail Modern POS (MPOS) rendszerhez és a Cloud POS-hez
description: Ez a témakör a Feladatrögzítő és a Retail Modern POS Felhő POS használatát ismerteti.
author: josaw1
ms.date: 06/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: 1205393
ms.assetid: 2f13e9cf-55b5-458b-8c32-3f8cd98c9ecf
ms.search.industry: Retail
ms.search.form: RetailTerminalTable, SystemParameters
ms.openlocfilehash: 32d5c959c044a628a6ed1044b6e30f3363680293
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267458"
---
# <a name="task-recorder-and-help-for-retail-modern-pos-mpos-and-cloud-pos"></a>Feladatrögzítő és Súgó a Retail Modern POS (MPOS) rendszerhez és a Cloud POS-hez

[!include [banner](includes/banner.md)]

Ez a témakör a Feladatrögzítő és a Retail Modern POS Felhő POS használatát ismerteti.

## <a name="overview"></a>Áttekintés

A Retail Modern POS és a Cloud POS felületén elérhető Feladatrögzítő egy olyan új megoldás, melynek megalkotásakor a gyors reakció igényét tartottuk szem előtt. Rugalmas alkalmazásprogramozási felületet (API-t) biztosít a bővítés érdekében, illetve zökkenőmentes integrációt kínál az üzleti folyamatokat rögzítő ügyfelek számára. Ezenkívül a Feladatrögzítőnek a Microsoft Dynamics Lifecycle Services ([https://bpm.lcs.dynamics.com](https://bpm.lcs.dynamics.com/)) Üzletifolyamat-modellező eszközével való integrációja is megvalósult. A felhasználók ezért továbbra is multimédiás diagramokat készíthetnek az üzleti folyamatokról a felvételek segítségével, és ez alapján elemezhetik, illetve tervezhetik az alkalmazásaikat.

## <a name="architecture"></a>Felépítés

A Feladatrögzítő képes az ügyfélprogramban végzett felhasználói műveletek pontos rögzítésére. Minden egyes vezérlőelem értesíti a Feladatrögzítőt az adott felhasználói művelet végrehajtásáról. A vezérlőelem értesíti a Feladatrögzítőt az események megtörténtéről, és valós időben továbbítja az összes vonatkozó információt a megfelelő felhasználói műveletről. Ezen információkból a Feladatrögzítő rögzíteni tudja a felhasználói művelet típusát (például kattintás egy gombra, érték megadása vagy navigáció), továbbá minden olyan adatot, amely a felhasználói művelethez kapcsolódik (például a bemeneti adat értékét és típusát, a képernyőn szereplő kontextust vagy a rögzítés kontextusát). A Feladatrögzítő úgy tartja meg az információkat, hogy azok elég részletesek legyenek annak garantálásához, hogy a felvétel visszajátszásával végrehajtható legyen minden rögzített művelet pontosan ugyanúgy, ahogyan a felhasználó végrehajtotta őket. (A lejátszás funkció még nincs megvalósítva a Retail modern POS és a felhőalapú POS rendszerén.)

## <a name="basic-configuration"></a>Alapkonfiguráció

A feladatrögzítés pénztárnál való aktiválásához kövesse az alábbi lépéseket.

1. Kattintson a **Retail és Commerce** &gt; **Csatorna beállítása** &gt; **Pénztár beállítása** &gt; **Pénztárgépek** elemre.
2. Kattintson a jegyzékre a feladatrögzítés engedélyezéséhez.
3. A **Jegyzék** lapon, az **Általános** gyorslapon állítsa a **Feladatrögzítés engedélyezése** beállítást **Igen** értékre.
4. Kattintson a **Mentés** gombra.
5. Ugorjon a **Kiskereskedelem és kereskedelem** &gt; **Kiskereskedelem és kereskedelem informatika** &gt; **Elosztási ütemezés** pontra.
6. Válassza ki a **Jegyzékek (1090)** munkát, és kattintson a **Futtatás most** lehetőségre.

## <a name="create-a-recording"></a>Felvétel létrehozása

Kövesse ezeket a lépéseket, ha új felvételt szeretne létrehozni a Feladatrögzítő segítségével.

1. Indítsa el a Retail Modern POS vagy a felhőalapú POS rendszert, és jelentkezzen be.
2. A **Beállítások** oldalon, a **Feladatrögzítő** szakaszban kattintson a **Feladatrögzítő megnyitása** lehetőségre. Megjelenik a **Feladatrögzítő** ablaktábla. Ha a **Bezárás** gombra (**X**) kattint a jobb felső sarokban, azzal bezárhatja a **Feladatrögzítő** táblát, mielőtt elkezdene egy új felvételt. A tábla újbóli megnyitásához ismételje meg a 2. lépést.

    [![Feladatrögzítő tábla.](./media/newrecording-1024x450.jpg)](./media/newrecording.jpg)

3. Adja meg a felvétel nevét és leírását, majd kattintson az **Indítás** gombra. Amikor rákattint az **Indítás** gombra, elindul a rögzítési munkamenet.

    > [!NOTE]
    > Ha a **Bezárás** gombra (**X**) kattint a jobb felső sarokban, miközben a felvétel folyamatban van, akkor a **Feladatrögzítés** tábla bezáródik, ám a felvételi munkamenet nem marad abba. A Feladatrögzítő tábla újbóli megnyitásához kattintson a **Súgó** gombra (kérdőjel) a képernyő tetején.
    >
    > [![Kérdőjel.](./media/help.jpg)](./media/help.jpg)

4. Amikor rákattint a **Start** lehetőségre, a Feladatrögzítő rögzítés módba lép. A **Feladatrögzítő** ablaktábla olyan információkat és vezérlőket jelenít meg, amelyek kapcsolódnak a rögzítési folyamathoz.
5. Hajtsa végre azokat a műveleteket, amelyeket végre szeretne hajtani a Retail Modern POS vagy a felhőalapú POS kezelőfelületén.
6. Kattintson a **Leállítás** lehetőségre a rögzítési munkamenet leállításához.

## <a name="download-options"></a>Letöltési beállítások

A rögzítési munkamenet befejezésekor több lehetőség is megjelenik a felvétel letöltésére.

[![Letöltési beállítások.](./media/downlaod-options.jpg)](./media/downlaod-options.jpg)

### <a name="save-to-this-pc"></a>Mentés erre a PC-re

A felvételi csomag használatával lehetősége nyílik a Feladat-útmutató lejátszására, a felvétel karbantartására, illetve a felvétel megjegyzéseinek szerkesztésére. (Ez a funkció még nincs megvalósítva a Retail Modern POS és a felhőalapú POS rendszerén.)

### <a name="export-as-word-document"></a>Exportálás Word-dokumentumként

A felvételt Microsoft Word-dokumentumként mentheti. A dokumentum a rögzített lépéseket és képernyőképeket fogja tartalmazni.

### <a name="save-as-developer-recording"></a>Mentés fejlesztői felvételként

A nyers felvételt tartalmazó fájl hasznos a fejlesztési feladatokhoz, például tesztkód előállításához. (Ez a funkció még nincs megvalósítva.)

## <a name="recording-controls"></a>Rögzítési vezérlőelemek

[![Rögzítési vezérlőelemek.](./media/controls.jpg)](./media/controls.jpg)

### <a name="stop"></a>Leállítás

Kattintson a **Leállítás** lehetőségre a rögzítési munkamenet leállításához. Vegye figyelembe, hogy a munkamenet a befejezés után nem indítható újra. Ezért a leállítás előtt győződjön meg róla, hogy a rögzítés befejeződött.

### <a name="pause"></a>Szüneteltetés

Kattintson a **Szüneteltetés** lehetőségre a rögzítési munkamenet ideiglenes leállításához (szüneteltetéséhez) és a művelet folytatásához. A **Szüneteltetés** lehetőségre leadott kattintás után végrehajtott lépéseket a rendszer nem rögzíti.

### <a name="continue"></a>Folytatás

Ha folytatni szeretné a rögzítési munkamenetet a szüneteltetést követően, kattintson a **Folytatás** elemre.

### <a name="capture-screenshots"></a>Képernyőképek rögzítése

A Feladatrögzítő képes képernyőképek készítésére a Retail Modern POS kezelőfelületén az üzleti folyamat rögzítése során. A képernyőkép-rögzítés funkció bekapcsolásához állítsa a **Képernyőképek rögzítése** beállítást **Igen** értékre, majd végezze el a rögzítést. Amikor a rögzítés befejeződött, kattintson a **Leállítás** gombra, és töltse le a Word-dokumentumot. A dokumentum a lépéseket a megfelelő képernyőfelvételekkel együtt tartalmazza.

> [!NOTE]
> A Store Commerce, a Commerce Modern POS és a Felhő POS nem támogatja az képernyőkép funkcióját.

### <a name="start-task-and-end-task"></a>Feladat indítása és Feladat befejezése

Megadhatja a csoportosított lépések készletének első és utolsó elemét a **Feladat elindítása** és a **Feladat** **befejezése** gombokkal. Kattintson a **Feladat elindítása** lehetőségre a „Feladat elindítása” lépés hozzáadásához, majd hajtsa végre azokat a lépéseket, amelyeknek szerepelnie kell ebben a csoportban. Miután befejezte a csoport lépéseinek végrehajtását, kattintson a **Feladat befejezése** gombra. A feladatok segítenek az eljárások rendszerezésében. A feladatok beágyazhatók más feladatokba. Így könnyebben rendszerezhetők a nagyon hosszú és bonyolult üzleti folyamatok.

## <a name="adding-annotations"></a>Megjegyzések hozzáadása

A megjegyzés olyan további szöveg, amelyet hozzáadhat egy lépéshez a rögzítés során. Például a jegyzetek segítségével további környezetet vagy utasításokat biztosíthat a felhasználónak. Megjegyzéseket a lépések előtt vagy után adhat meg. Úgy adhat megjegyzést a lépésekhez, hogy rákattint a **Szerkesztés** gombra (ceruza szimbólum) a lépéstől jobbra.

[![Szerkesztés gomb egy lépésnél.](./media/annotate.jpg)](./media/annotate.jpg)

### <a name="texts-and-notes"></a>Szövegek és megjegyzések

A **Szövegek** és **Megjegyzések** mezők segítségével olyan szöveget adhat meg, amelyiket egy lépéshez társíthat egy Feladat-útmutatóban.

[![Szöveg és Megjegyzések mezők.](./media/annotatesteps.jpg)](./media/annotatesteps.jpg)

#### <a name="text"></a>Szöveg

A **Szöveg** mezőben beírt szöveg a lépés szövege *felett* jelenik meg a Feladat-útmutatóban. Ez a hely olyan szöveg számára megfelelő, amelyiket a felhasználónak a lépés végrehajtása előtt kell elolvasnia.

#### <a name="notes"></a>Jegyzetek

A **Megjegyzések** mezőben beírt szöveg a lépés szövege *alatt* jelenik meg a Feladat-útmutatóban. A megjegyzés szövegének elolvasásához a felhasználónak ki kell bontania a lépés szövegét az előugró ablakban. Ez a hely megfelelő további anyagok vagy egyéb olyan információ elolvasásához, amely hasznos lehet a felhasználó számára, de a felhasználó számára ez nem kötelező a művelet végrehajtásához.

## <a name="help-in-retail-modern-pos-and-cloud-pos"></a>A Retail Modern POS és a Cloud POS súgója

A saját feladatrögzítéseinek a Retail Modern POS és a felhőalapú POS Súgó ablakaiban való megjelenítéséhez annak érdekében, hogy ezáltal szövegként megtekinthetőek legyenek, a feladatrögzítést a saját BPM-tárába kell mentenie, majd ezután a súgórendszer paramétereit be kell állítania, hogy azok a BPM-tárára mutassanak. További tájékoztatást a következő témakörben talál: [Súgórendszer csatlakoztatása](../fin-ops-core/fin-ops/get-started/help-connect.md). A Retail Modern POS és a felhőalapú POS Súgó valós időben keres az LCS-ben. Az összes olyan BPM könyvtárban keres, amelyet kijelöltek a Commerce Súgó rendszerparaméterei között, és megjeleníti a releváns találatokat. A **Súgó** menü eléréséhez kattintson a **Súgó** gombra (kérdőjel) a képernyő tetején, majd írja be a folyamata nevét a keresőmezőbe, és nyomja le a Keresés gombot.

[![Súgó gomb.](./media/help.jpg)](./media/help.jpg)

Amikor a keresési eredmények között egy feladat-útmutatóra kattint, a lépéseket megtekintheti súgócikkként, vagy exportálhatja a lépéseket Word-dokumentumba.

> [!NOTE]
> A Retail Modern POS és a Cloud POS Súgója nem hozza fel a feladat-útmutatókat a képernyő vagy a végzett művelet alapján. A keresőmezőbe be kell írnia a folyamat nevét, majd kattintson a **Keresés** lehetőségre.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
