---
title: Felhőalapú és peremhálózat skálázási egységek a gyártási és a raktárkezelési számítási feladatokhoz
description: Ez a témakör további információt biztosít a Felhőalapú és peremhálózati skálázási egységgel kapcsolatban a gyártási és raktárkezelési munkaterhelésekhez.
author: cabeln
manager: ''
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: cabeln
ms.search.validFrom: 2020-09-23
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 3a23ee452535423684c6d210a448ee768379fa08
ms.sourcegitcommit: 8eefb4e14ae0ea27769ab2cecca747755560efa3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/13/2020
ms.locfileid: "4516800"
---
# <a name="cloud-and-edge-scale-units-for-manufacturing-and-warehouse-management-workloads"></a>Felhőalapú és peremhálózat skálázási egységek a gyártási és a raktárkezelési számítási feladatokhoz

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

A felhőalapú és a peremhálózati skálázási egységek lehetővé teszik a különböző környezetek között az üzemi és raktári végrehajtási munkaterhelések felosztását. Ez a funkció javítja a teljesítményt, megakadályozhatja a szolgáltatás megszakadását, és maximalizálhatja az üzemidőt. A következő bővítmények biztosítják ezt:

- Felhőbeli skálázási egység bővítmény a következőhöz: Dynamics 365 Supply Chain Management
- Peremhálózati skálázási egység bővítmény a következőhöz: Dynamics 365 Supply Chain Management

A gyártással és elosztással foglalkozó vállalatoknak képesnek kell lenniük a kulcsfontosságú üzleti folyamatok futtatására nonstop, megszakítás nélkül és megfelelő méretben. A felhőalapú és a peremhálózati skálázási egységek lehetővé teszik a vállalatok számára, hogy megszakítás nélkül futtassák a kulcsfontosságú feladathoz kapcsolódó termelési és raktári folyamatokat, még akkor is, ha időnként hálózati kapcsolati vagy késleltetési problémák lépnek fel.

## <a name="public-preview-information"></a>Nyilvános előzetes verzióval kapcsolatos adatok

Az előzetes verzió egy környezettel rendelkezik, amely a Dynamics 365 Supply Chain Management környezet felhőalapú központjaként működik, és egy olyan környezet, amely felhőalapú skálázási egységként működik.

<!-- You will also be able to use Local Business Data (LBD) to configure an on-premises environment as an edge scale unit for the hub you received as part of the preview program.-->

### <a name="preview-availability"></a>Előzetes verzió megjelenése

A felhőalapú és a peremhálózati skálázási egységek előzetes verziója elérhetővé válik a Supply Chain Management meglévő vevői számára 2020 októberében.

A [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/v2) környezetben való telepítésre az októberi előzetes verzió 10.0.15-ös kiadásához/Platform update 39-hez való hozzáféréséhez részt kell vennie a Supply Chain Management előzetes verzió korai hozzáférési programjában (más néven PEAP). A PEAP-hoz akkor csatlakozhat, ha már tagja a tágabb [Dynamics Insider Programnak](https://experience.dynamics.com/insider). Egyszerűen válassza ki a „Finance & Operations: Preview early access program (PEAP)” nevű meghatározott programot.

> [!IMPORTANT]
> A Supply Chain Management skálázásiegység-képessége csak akkor elérhető, ha elfogadja a [Felhőalapú és peremhálózati előzetes verzió feltételeit a Finance and Operations szolgáltatásnál](https://Aka.ms/SCMCnETerms).

### <a name="data-processing-for-the-preview"></a>Adatfeldolgozás az előzetes verzióhoz

A nyilvános előzetes verzió során bizonyos felügyeleti szolgáltatások csak az Egyesült Államokban lesznek szolgáltatva. Azonban amikor a funkció nyilvánosan megjelenik, ezek a felügyeleti szolgáltatások a Supply Chain Management által támogatott összes földrajzi területeken elérhetők lesznek. Ez hatással van a skálázásiegység-kezelő által használt felügyeleti adatok átvitelére és tárolására, többek között a következőkre:

- A bérlőnevek és azonosító
- Az LCS projektazonosítókra
- Bejelentkezéshez használt rendszergazdai e-mail-címek
- A központ és a skálázási egységek környezeti azonosítói
- Számításifeladat-konfigurációk
- Összegyűjtött mérőszámok (például a késleltetés és a teljesítmény), amelyek a térképelemzési oldalon láthatók

A program a előzetes verziós környezet leállításakor törli az Egyesült Államokbeli adatközpontba átvitt és ott tárolt adatokat.

### <a name="sign-up-for-the-preview"></a>Regisztrálás az előzetes verzióra

A Supply Chain Management felhőbeli és peremhálózati előzetes verziójára való regisztrációhoz a szervezetnek már rendelkeznie kell élő Supply Chain Management felhőbeli környezettel.

A skálázási egység lehetőségei jelenleg nyilvános előzetes verziójúak. A regisztrációkor egy felhasználói fiókot kell használnia a megadott bérlőn. Ezenkívül projekttulajdonosnak vagy környezeti rendszergazdának kell lennie az LCS-ben az adott bérlőben egy aktív Dynamics 365 LCS projektnél.

Amikor feliratkozik az előzetes verzióra, kiválaszthatja a bérlőt, és áthaladhat a feliratkozás lépésein. Amint a Microsoft lefoglalhatja az előzetes verzió kapacitást, akkor egy e-mailt küld Önnek, amely tartalmazza a megfelelő LCS-projekthez tartozó létesítési adatokat és promóciós (promó) kódokat két környezethez. Ezt követően a üzembe helyezheti a két környezetet 2. szintű tesztkörnyezetként. Ezek a környezetek 60 napig érvényesek a promóciós kódok létrehozási dátumától. Ne használja a két környezetet addig, amíg a következő bekezdésben ismertetett lépés be nem fejeződik.

Miután megerősíti a Microsoftnak, hogy a két környezet üzembe helyezése megtörtént a promóciós kódokkal, az egyik környezetet a rendszer a központként való használatra konfigurálja, a másikat pedig a skálázási egységként való használatra. Ezt követően konfigurálhatja a skálázási egységeket, és üzembe helyezheti a kiválasztott raktárkezelési és gyártási munkaterheléseket a [Scale Unit Manager portál](https://aka.ms/SCMSUM) használatával.

Az előzetes verziós környezeteket a 60 nap után automatikusan törli a program. Előfordulhat azonban, hogy előbb törölni kell, ha úgy tűnik, hogy nincsenek használatban. Az előzetes verziós környezetek törlése után új előzetes verzió telepítéshez regisztrálhat és várólistára kerülhet.

Az előzetes verzióra történő feliratkozáshoz nyissa meg a [Scale Unit Manager portált](https://aka.ms/SCMSUM).

### <a name="limitations-that-apply-during-the-preview-period"></a>Az előzetes verziós időszakban alkalmazott korlátozások

> [!IMPORTANT]
> Az adott funkció előzetes verziós programjának kezdeti fázisánál a Microsoft csak a felhőalapú skálázási egységekkel rendelkező központokat támogatja, a peremhálózati skálázási egységekkel rendelkező központokat. A helyszínen telepített peremhálózati skálázási egységek előreláthatólag a program következő fázisában válnak elérhetővé.

Mivel a felhőbeli és peremhálózati skálázási egységek előzetes funkciók, a hozzájuk kapcsolódó szolgáltatások jelenleg korlátozott számú országban és régióban elérhetők. A felhő és peremhálózati skálázáso egységek esetén megerősíti, hogy meggértette, hogy a konfigurációval és a felhőbeli és peremhálózati skálázási egységek feldolgozásával kapcsolatos adatok egy részét az USA-ban található adatközpontban tárolhatjuk. A felhőalapú és peremhálózati skálázási egységek engedélyezésével elfogadja a [Felhőalapú és peremhálózati előzetes verzió feltételei a Finance and Operations szolgáltatáshoz](https://Aka.ms/SCMCnETerms). Ha többet szeretne megtudni a felhő- és peremhálózati skálázási egységekről, olvassa el a [dokumentációt](https://aka.ms/scmcne).

Az Ön adatainak védelme fontos a Microsoft számára. További információért olvassa el [adatvédelmi nyilatkozatunkat](https://aka.ms/privacy).

> [!IMPORTANT]
> Néhány üzleti funkció nem teljes mértékben támogatott a nyilvános előzetes verzióban, ha számítási feladatokat skálázási egységeken használja. Az egyes funkcionális számítási feladatokkal kapcsolatos további információhoz olvassa át a jelen témakörben alább található szakaszokat.

## <a name="scale-units-and-dedicated-workloads"></a>Skálázási egységek és dedikált számítási feladatok

:::image type="content" source="./media/cloud_edge-HeroDiagram.png" alt-text="Dynamics 365 skálázási egységekkel":::

A skálázási egységek kiterjesztik a központi Supply Chain Management központ környezetét a dedikált feldolgozási kapacitás hozzáadásával. A skálázási egységek futhatnak a felhőben. Alternatív megoldásként a helyi létesítmény peremhálózatán is futhatnak. A skálázási egységek ideiglenesen leválaszthatók a központi környezetről. Amikor csatlakoztatva vannak, a skálázási egységek megkapják a hozzárendelt számítási feladatok dedikált feldolgozásának futtatásához szükséges összes információt.

:::image type="content" source="media/cloud_edge-previewoptions.png" alt-text="Skálázási egység beállításai a nyilvános előzetes verzióban":::

A nyilvános előzetes verzióhoz konfigurálhatja a központi környezetet a felhőbeli skálázási egységen kiválasztott számítási feladatokkal a Scale Unit Manager portál használatával. Előzetes verzió résztvevői, akik hozzáférnek a helyi üzleti adatok (LBD) helyszíni környezethez, konfigurálhatják az LBD-környezetet, mint egy peremhálózati skálázási egység.

A számítási feladat egy meghatározott üzleti funkciókészlet, amelyet figyelembe lehet venni, és egy skálázási egységre delegálható. Jelenleg az előzetes funkciók kétféle számítási feladatokat tartalmaz:

- Gyártásvégrehajtás
- Raktárkezelés

A számítási feladatok minden típusából hozzárendelhet egy skálázási egységhez. 

### <a name="dedicated-manufacturing-execution-workload-capabilities-in-a-scale-unit"></a>Dedikált gyártási végrehajtási számítási feladatok képességei egy skálázási egységben

A gyártás végrehajtásához a felhő- és peremhálózati skálázási egységek a következő képességeket biztosítják, még akkor is, ha a peremhálózati egységek nem kapcsolódnak a felhőhöz:

- A gépkezelők és az üzemirányítók hozzáférhetnek az üzemeltetési termelési tervhez.
- A gépkezelők diszkrét és folyamatgyártási feladatok futtatásával naprakészen tarthatják a tervet.
- Az üzemvezető módosíthatja az üzemeltetési tervet.
- A dolgozók hozzáférhetnek a munkaidőhöz és a jelenléthez a peremhálózati érkezéskori és távozáskori blokkoláshoz a megfelelő dolgozói fizetésszámítás biztosítása érdekében.

További információt a [gyártási skálázási egység számítási feladatának részletei](cloud-edge-workload-manufacturing.md) című témakörben talál.

### <a name="dedicated-warehouse-management-workload-capabilities-in-a-scale-unit"></a>Dedikált raktárkezelési számítási feladatok képességei egy skálázási egységben

A raktárkezeléshez a felhő- és peremhálózati skálázási egységek a következő képességeket biztosítják, még akkor is, ha a peremhálózati egységek nem kapcsolódnak a felhőhöz:

- Az értékesítési rendelésekhez és a szükségletek feltöltéséhez kiválasztott hullámos módszerek feldolgozása engedélyezve van.
- A raktári dolgozók a raktári alkalmazás használatával futtathatják az értékesítési és igény szerinti feltöltési raktári munkát.
- A raktári dolgozók a raktári alkalmazás segítségével érdeklődhetnek az aktuális készletről.
- A raktári dolgozók a raktári alkalmazás segítségével létrehozhatnak és futtathatnak készletmozgatásokat.
- A raktári dolgozók regisztrálhatnak beszerzési rendeléseket és betárolási munkát végezhetnek a raktári alkalmazás használatával.

További információt a [raktári skálázási egység számítási feladatának részletei](cloud-edge-workload-warehousing.md) című témakörben talál.

## <a name="onboard-scale-units-for-your-supply-chain-management-environment"></a>Skálázási egységek előkészítése a Supply Chain Management környezethez

### <a name="deploy-the-preview-for-cloud-and-edge-scale-units"></a>Az előzetes verzió üzembe helyezése felhőalapú és peremhálózati skálázási egységekhez

A következő ábrán a felhőalapú skálázási egységek nyilvános előzetes verziójának regisztrációs és kiépítési folyamata látható.

:::image type="content" source="media/cloud_edge-previewsignup.png" alt-text="Az előzetes verzió feliratkozási lépései":::

### <a name="select-your-lcs-project-tenant-and-the-detailed-preview-process"></a>Válassza ki az LCS-projekt bérlőjét és a részletes előzetes verzió folyamatot

A nyilvános előzetes verzióban a [Scale Unit Manager portál](https://aka.ms/SCMSUM) megjeleníti azoknak a bérlőknek a listáját, amelyeknek a fiókja a része, és ahol Ön egy LCS-projekt tulajdonosa vagy környezeti rendszergazdája.

Ha a keresett bérlő nem szerepel a listában, nyissa meg az [LCS](https://lcs.dynamics.com/v2) szolgáltatást, és győződjön meg arról, hogy ön vagy az adott bérlő LCS-projektjének környezeti rendszergazdája, vagy a projekt tulajdonosa. Vegye figyelembe, hogy csak az Azure Active Directory (Azure AD) fiókok a kiválasztott bérlőből jogosultak a regisztrációs élmény befejezéséhez.

> [!NOTE]
> Miután alkalmazta a módosításokat az LCS-re, akár 30 percet is igénybe vehet, amíg a bérlők listája tükrözi a módosításokat.

Minden bérlő esetében a lista a regisztrációs állapotot jeleníti meg.

:::image type="content" source="media/cloud_edge-Signup1.png" alt-text="Regisztrálási beállítás a bérlő számára":::

Válassza a **Kattintson ide a regisztrációhoz** hivatkozást az LCS bérlő regisztrálásához az előzetes verzióban való részvételhez. El kell fogadnia a feltételeket. Meg kell adnia egy üzleti e-mail-címet is, ahol a Microsoft elküldheti az előzetes verziós regisztrációs folyamathoz kapcsolódó kommunikációt.

:::image type="content" source="media/cloud_edge-Signup2.png" alt-text="Regisztrálási elküldés a bérlő számára":::

A Microsoft áttekinti a kérést, és a regisztrációs űrlapon megadott címre küldött e-mailben tájékoztatja a következő lépésekről.

Miután hozzáférést kapott az előzetes programhoz, két promóciós kódot kap az LCS projekthez. Most már használhatja ezeket a promóciós kódokat két környezet üzembe helyezéséhez az LCS-ben. A környezetekben a 10.0.15-ös vagy újabb PEAP-kiadást kell használniuk. Ha befejezte a promóciós kódok alkalmazását, értesítse a Microsoftot (az utasításoknak megfelelően), hogy befejezhessük az előzetes funkciók környezetének engedélyezését. A Microsoft tudatja Önnel, ha ez a konfigurációs lépés befejeződött.

Most már elkezdheti konfigurálni a skálázási egységeket és a számítási feladatokat az előzetes verziós környezetben.

> [!IMPORTANT]
> A felhőalapú skálázási egységek konfigurálásakor [a Skálázásiegység-kezelő portálon minden szükséges lépést elvégezhet](#scale-unit-manager-portal).
<!-- >
> If want to use edge scale units with your preview deployment, you must do all scale unit configuration in the user interface on the hub as described in [Configure the hub environment for use with edge scale units](cloud-edge-edge-scale-units-lbd.md#configure-the-hub-environment). You can't use Scale Unit Manager portal if you include an edge scale unit. -->

### <a name="manage-cloud-scale-units-and-workloads-by-using-the-scale-unit-manager-portal"></a><a name="scale-unit-manager-portal"></a>Felhőalapú skálázási egységek és számítási feladatok kezelése a Skálázásiegység-kezelő portál használatával

Nyissa meg a [Skálázásiegység-kezelő portált](https://aka.ms/SCMSUM), és jelentkezzen be a bérlői fiókjával. A **Skálázási egységek konfigurálása** lapon hozzáadhat egy központi környezetet, ha az még nem szerepel a listán. Ezután kiválaszthatja a központot, amelyet a skálázási egységekkel és a számítási feladatokkal konfigurálni kíván.

:::image type="content" source="media/cloud_edge-Manage.png" alt-text="Skálázásiegység- és számításifeladat-kezelési élmény":::

Ha egy vagy több, a topológiában elérhető skálázási egységet szeretne hozzáadni, válassza a **Skálázási egységek hozzáadása** lehetőséget. Az előzetes verzióban látnia kell a felhőalapú skálázási egységet, amely telepített az egyik promóciós kódból, amelyet az előzetes verziós program részeként kapott.

<!-- > [!IMPORTANT]
> In the public preview, the Scale Unit Manager portal shows the cloud scale unit that you received as part of the preview program. Any edge scale unit that you created based on an LBD configuration can't be managed in the Scale Unit Manager portal yet. For configuration details, see [Deploy custom edge scale units on custom hardware using LBD](cloud-edge-edge-scale-units-lbd.md) -->

A **Definiált számítási feladatok** lapon a **Számítási feladatok létrehozása** gombbal hozzáadhat egy raktárkezelési vagy gyártási végrehajtási számítási feladatot az egyik skálázási egységhez. Minden számítási feladathoz meg kell adnia a számítási feladatok tulajdonában lévő folyamatok kontextusát. A raktárkezelési munkaterhelések esetében a kontextus egy adott hely és jogi személy adott raktára. Gyártási végrehajtási számítási feladatok esetén a kontextus egy jogi személy adott helye.

:::image type="content" source="media/cloud_edge-DefineWorkload.png" alt-text="Számítási feladat létrehozása":::

> [!IMPORTANT]
> Az előzetes verzióban a Skálázásiegység-kezelő portál nem teszi lehetővé a számítási feladatok eltávolítását a skálázási egységekből, illetve a skálázási egység hozzárendelésének megszüntetését a központból a hozzárendelés befejezése után. Ha el kell távolítania egy hozzárendelést, forduljon a kapcsolattartóhoz az előzetesprogram-kezelés esetében.

<!-- ### Create an edge scale unit using your custom on-premises hardware appliance

In the public preview, you can create on-premises edge scale units on your custom hardware using the LBD environments. For details, see [Deploy custom edge scale units on custom hardware using LBD](cloud-edge-edge-scale-units-lbd.md). -->
