---
title: "Súgó áttekintése"
description: "Ez a cikk a Microsoft Dynamics 365 for Operations Súgórendszer részeinek áttekintését tartalmazza. Azt is bemutatja, hogyan hozhat létre egyedi dokumentációkat és oktatóanyagokat a szervezete számára."
author: margoc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16381
ms.assetid: 018c148c-9cbd-41e0-8186-d75dbf66288f
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6f785ac8b9a8be503bf9122f21716f745b17115b
ms.openlocfilehash: f08434b4c818460009644e77da1b37ba86cc1d54
ms.contentlocale: hu-hu
ms.lasthandoff: 04/27/2017


---

# <a name="help-overview"></a>Súgó áttekintése

[!include[banner](../includes/banner.md)]


Ez a cikk a Microsoft Dynamics 365 for Operations Súgórendszer részeinek áttekintését tartalmazza. Azt is bemutatja, hogyan hozhat létre egyedi dokumentációkat és oktatóanyagokat a szervezete számára. 

A 365 for Operations teljesen új Súgórendszerrel rendelkezik, amely két fő részből áll:

-   Dokumentációs oldal
-   Feladat-útmutatók

A Dynamics 365 for Operations rendszer Súgó ablakából cikkeket és feladat-útmutatókat is elérhet, amint az az alábbi képernyőképen is látható. [![Súgó ablak](./media/help-pane-ops-task-guides-1024x741.png)](./media/help-pane-ops-task-guides.png) Ez a cikk ismerteti a Súgó rendszert, és leírja, hogyan hozhat létre testreszabott dokumentációt és továbbképzési forrásokat szervezetének.

## <a name="help-on-docsmicrosoftcom"></a>Súgó a docs.microsoft.com-on
A docs.microsoft.com webhely ([docs.microsoft.com/dynamics365/operations](/dynamics365/#pivot=solutions&panel=solutions_operations) a Dynamics 365 for Operations termékdokumentációjának elsődleges forrása. A webhely a következő funkciókat ajánlja:

-   **Hozzáférés a legfrissebb tartalmakhoz** – A webhely lehetőséget ad a termékdokumentációk gyorsabb, rugalmasabb létrehozására, szállítására és frissítésére. Ezért segítségével garantálható, hogy a legfrissebb technikai információkhoz jut hozzá.
-   **Szakértők által írt tartalmak** – A WEBHELY szélesebb körű termékdokumentációkat kínál, amelyeket a közösség tagjai a Microsofton kívül és belül is bővíthetnek.
-   **Hozzáférés különböző tartalmakhoz** – A webhely lehetővé teszi, hogy gyorsan hozzáférjen különböző tartalmakhoz a Dynamics 365 for Operations rendszerben, például Microsoft Office Vegyes prezentációk, feladatsúgók, videók és témakörök.
-   **Üzleti folyamatokat támogató tartalmak** – A webhely tartalmaz üzleti folyamat központú tartalmakat, amelyek előnyt jelentenek az Üzletifolyamat-modellező (BPM) programban a Microsoft Dynamics Lifecycle Services szolgáltatásokhoz (LCS).

A korábbi súgó wiki teljes tartalmát átvittük dokumentumokba. Nagy örömmel mutatjuk be az új weboldalt, és reméljük, hogy Ön is örömét leli majd benne.

### <a name="when-can-we-use-it"></a>Mikor tudjuk használni?

Most is olvashat tartalmi dokumentumokat – teljesen nyílt hozzáférésű, kereshető, nem szükséges bejelentkezés. Használhatja a kedvenc keresőmotorját a tartalmak kereséséhez. Ha bejelentkezik, kommentálhatja is a weboldal cikkeit.


## <a name="task-guides"></a>Feladat-útmutatók
A Feladat-útmutató egy kontrollált, irányított, interaktív tapasztalat, amely végigvezeti a feladat vagy az üzleti folyamat lépésein. A Súgó ablakban megnyithatja (lejátszhatja) a Feladat-útmutatót. Amikor először kattint a Feladat-útmutatóra a Súgó ablakban, láthatja lépésenként a feladathoz tartozó utasításokat. A honosított Feladat-útmutatók már elérhetőek. [![Feladat-útmutató olvasási nézete](./media/task-guide-ops-1024x742.png)](./media/task-guide-ops.png) Az irányított, interaktív tapasztalat megkezdéséhez kattintson a **Feladat-útmutató indítása** lehetőségre a Súgó ablak alján. Egy fekete mutató nyílik meg, és jelzi a végrehajtott műveleteket. Kövesse a felhasználói felületen megjelenő utasításokat, és adja meg az adatokat az utasításoknak megfelelően. [![Feladat-útmutató lépésre vonatkozó utasítása](./media/task-guide-step-1-ops.png)](./media/task-guide-step-1-ops.png) **Fontos:** A Feladat-útmutató lejátszásakor megadott adatok valósak. Ha gyártási területen van, az adatok a használt vállalathoz kerülnek bejegyzésre.

### <a name="it-all-begins-with-task-recorder"></a>A Feladatrögzítővel kezdődik

Feladat útmutatókat a Feladatrögzítővel lehet létrehozni. A Feladatrögzítő használatakor minden, Dynamics 365 for Operations rendszer felhasználói felületén végrehajtott művelet (pl. menük kiválasztása, beállítások változtatása és adatok megadása) rögzítésre kerül. A rögzített lépések összességét feladatrögzítésnekhívják. Amint az előző szakaszban leírtuk, a feladatrögzítések a Súgo ablakban játszhatók le feladat útmutatókként. Ugyanakkor vannak más lehetőségek a feladatrögzítések használatához:

-   **Feladatrögzítések BPM-re** – Egy feladatrögzítést elmenthet egy hierarchiasorhoz a BPM könyvtárban LCS formátumban. Amikor a feladatrögzítést menti a BPM-be, egy folyamatábra-diagramm jön létre és jelenik meg, a rögzítés lépéseivel egyet. **Megjegyzés:** Feladatrögzítés megjelenítéséhez és lejátszásához a Dynamics 365 for Operations rendszer Súgó lehetőségében a rögzítést a BPM könyvtárba kell menteni.
-   **Feladatrögzítések mentése Word dokumentumokként** – Ha a feladatrögzítést Microsoft Word dokumentumként menti, akkor könnyedén létrehozhat nyomtatható továbbképzési útmutatókat a vállalata számára.

A Feladatrögzítővel kapcsolatos további információkért lásd: [Feladatrögzítő a Dynamics 365 for Operations rendszerben](../user-interface/task-recorder.md).

### <a name="creating-customized-task-recordings"></a>Testreszabott feladatrögzítések létrehozása

Létrehozhatja a saját feladatrögzítéseit vagy letölthet és testreszabhatja a Microsoft rögzítéseit. Emiatt egyéni Súgót hozhat létre szervezetének, amely tükrözi a Dynamics 365 for Operations rendszer egyéni implementációját. Feladatrögzítés a Dynamics 365 for Operations rendszer Súgójában való megjelenítéséhez és feladatrögzítésként való lejátszásához a rögzítést el kell menteni egy BPM könyvtárba az LCS szolgáltatásban. Ha partnerként hozzájárul egy könyvtárral egy vállalati tár kialakításához, valamint beilleszti azt egy megoldásba, akkor az a vevői számára elérhetővé válik. Teljes körű utasítások: [Feladatrögzítések használata dokumentációhoz vagy továbbképzéshez](../user-interface/task-recorder.md).

## <a name="in-product-help"></a>Termékbe épített Súgó
Ha szeretné megtekinteni a Súgó tartalmát a Dynamics 365 for Operations rendszerben, akkor kattintson a **Súgó** (**?**) ikonra, és válassza a Súgó lehetőséget, vagy nyomja meg a Ctrl+Shift+? billentyűkombinációt. Mindkét esetben a Súgó ablak nyílik meg. A Súgó ablakból elérhet cikkeket és feladat-útmutatókat. [![Súgó ablak](./media/help-pane-wiki-1024x684.png)](./media/help-pane-wiki.png)

### <a name="accessing-articles-from-the-help-pane"></a>Cikkek elérése a Súgó ablakból

A Súgó ablakból hozzáférhet a Dynamics 365 for Operations kliensre vonatkozó cikkekhez. Amikor először nyitja meg a Súgó ablakot, a **Wiki** lapra való kattintáskor a Dynamics 365 for Operations rendszer aktuális oldalához kapcsolódó cikkek jelennek meg. Amennyiben nem találhatók cikkek, kulcsszavak beírásával módosíthatja a keresést. Amikor rákattint egy cikkre a Súgó ablakban, akkor egy új lap nyílik meg a böngészőben, és megjeleníti a cikket. 

### <a name="accessing-task-guides-from-the-help-pane"></a>Feladat-útmutatók elérése a Súgó ablakból

Mielőtt Feladat-útmutatókat nyit meg a Súgó ablakban, a Rendszergazdának a Dynamics 365 for Operations rendszerben a **Rendszer paraméterei** lapon be kell állítania néhány paramétert. **Megjegyzések:**

-   A Súgó konfigurálásához be kell lépnie egy ugyanattól a bérlőtől származó számlába, amelyben a Dynamics 365 for Operations rendszer is telepítve van.
-   Helyi virtuális merevlemezen (VHD) futó Dynamics 365 for Operations példánnyal nem lehet csatlakozni az LCS-könyvtárhoz.

[![Rendszerparaméterek – súgó beállításai](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) A **Rendszerparaméterek** lapon végezze el az alábbi lépéseket:

1.  **Fontos:**Amikor első alkalommal nyitja meg a Súgó lapot, kapcsolódnia kell a Lifecycle Services szolgáltatáshoz. Ügyeljen arra, hogy az űrlap közepén levő hivatkozásra kattintson, várja meg a kapcsolatot, zárja be a párbeszédpanelt, majd kattintson az OK gombra a paraméter-űrlap eléréséhez.[![Kapcsolódás az LCS-szolgáltatáshoz](./media/connect-to-lcs-crop-1024x365.png)](./media/connect-to-lcs-crop.png)
2.  A csatlakozáshoz válassza ki a Lifecycle Services-projektet.
3.  Válassza ki a BPM könyvtárakat (a kiválasztott projekten belül) amelyekből szeretné előhívni a rögzítéseket.
4.  Adja meg a BPM könyvtárak megjelenítési sorrendjét. Ez meghatározza a sorrendet, amelyben a feladatrögzítések megjelennek a Súgó ablakban.

Miután egy Rendszergazda végrehajtotta ezeket a lépéseket, nyissa meg a Súgó ablakot, és kattintson a **Feladat-útmutatók** lapra. Ekkor megjelennek a Dynamics 365 for Operations rendszer aktuális oldalához kapcsolódó Feladat-útmutatók. Amennyiben nem találhatók Feladat-útmutatók, kulcsszavak beírásával módosíthatja a keresést. Miután rákattint egy Feladat-útmutatóra a Súgó ablakában, a Súgó ablak lépésekre lebontva megjeleníti az utasításokat, továbbá lehetősége van a feladat-útmutató lejátszására is. [![Feladat-útmutató olvasási nézete](./media/task-guide-ops-1024x742.png)](./media/task-guide-ops.png)

### <a name="where-are-the-translated-task-guides"></a>Hol találhatóak a honosított Feladat-útmutatók?

A Feladat-útmutatók a címükben az „Minden nyelv” fordulatot viselő könyvtárakban érhetők el. Ha szeretné a honosított Feladat-útmutató súgóját látni a Dynamics 365 for Operations rendszerben, győződjön meg arról, hogy csatlakozva van a megfelelő könyvtárhoz. Minden felhasználó esetében a **Beállítások** &gt; **Beállítások** menüben található nyelvi beállítások határozzák meg a Feladat-útmutató nyelvét. 
-   Ha egy Feladat-útmutató le van fordítva, akkor a megnyitásakor kiválasztott nyelven fog megjelenni a Feladat-útmutató teljes szövege.
-   Ha egy Feladat-útmutató még nincs lefordítva, akkor a megnyitásakor a kiválasztott nyelven csak néhány szöveg (a vezérlők szövegei) fog megjelenni.

## <a name="additional-resources"></a>További erőforrások
Az alábbi táblázat olyan webhelyeket sorol fel, ahol Dynamics 365 for Operations tartalmak találhatók. A tartalom-webhelyek a vevő-életciklus támogatásához vannak elrendezve. Mindegyik fázishoz különböző webhelyek nyújtanak támogatást. A név mellett közvetlenül csillaggal (\*) jelölt webhelyeken a szolgáltatástervvel társított felhasználói fiókkal lehet belépni.

| Telephely                                                                     | Leírás                                                                                                                                                                                                                                |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Docs.microsoft.com](/dynamics365/#pivot=solutions&panel=solutions_operations) | Állomások vagy hivatkozások az összes termékdokumentációhoz a Dynamics 365 for Operations rendszerben.                                                                                                                                                               |
| [Lifecycle Services](http://lcs.dynamics.com/en/)\*                      | Felhőalapú együttműködési munkaterület biztosít, amelyet a vevők és a partnerek a 365 for Operations projektek kezelésére használhatnak az értékesítés előtti műveletektől a megvalósításig és műveletekig. Ez a webhely az implementáció minden fázisában hasznos. |
| [CustomerSource](http://www.customersource.com/)\*                       | Részletes oktatóanyagokat tartalmaz, ez a Dynamics 365 for Operations rendszer legfontosabb támogató webhelye. Bizonyos erőforrásokhoz való hozzáférés bejelentkezéshez kötött.                                                                      |
| [Támogatási blog](http://aka.ms/AXSupportBlog)                              | Tippeket és trükköket tartalmaz, amelyeket a Dynamics 365 for Operations támogató csapata jelentetett meg.                                                                                                                                                  |
| [MSDN](http://aka.ms/AXMSDN)                                             | Előző verziók tartalmait tárolja, amelyeket a fejlesztők számára írtak.                                                                                                                                                                       |
| [TechNet](http://aka.ms/TechNet)                                         | Előző kiadások tartalmait tárolja, amelyek számítástechnikai szakértőknek és az alkalmazás felhasználóinak készült.                                                                                                                                           |
| [Dynamics Közösség](http://community.dynamics.com/)                  | Blogokat, fórumokat és videókat tárol.                                                                                                                                                                                                           |
| [Microsoft.com/Dynamics/](http://www.microsoft.com/dynamics/)                 | Értékelések és eladási információk érhetők el.                                                                                                                                                                                                 |



<a name="see-also"></a>Lásd még
--------

[A Dynamics 365 for Operations súgórendszere (letölthető adatlap)](https://mbs.microsoft.com/files/public/CS/AX2012R3/DynamicsAXHelpSystemFactSheet.pdf)

[Feladatrögzítő a Microsoft Dynamics 365 for Operationsben](../user-interface/task-recorder.md)

[Dokumentáció vagy képzés létrehozása feladatrögzítések segítségével.](../user-interface/task-recorder.md)

[Új vagy frissített Feladat-útmutatók (2016). november](new-task-guides-november-2016.md)
[Új vagy frissített Feladat-útmutatók (2016. augusztus)](new-updated-task-guides-available-august-2016.md)
[Új vagy frissített Feladat-útmutatók (2016. május)](new-updated-task-guides-available-may-2016.md)
[Új Feladat-útmutatók (2016. február)](new-task-guides-available-february-2016.md)








