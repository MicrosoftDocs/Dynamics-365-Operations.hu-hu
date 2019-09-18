---
title: Bevezetési útmutatók és sablonok szerkesztése a Dynamics 365 for Talent - Onboard szolgáltatásban
description: Ez a témakör azt mutatja be, hogyan lehet tevékenységeket és egyéb információkat hozzáadni a Microsoft Dynamics 365 for Talent - Onboard felvételi útmutatóihoz és sablonjaihoz.
author: andreabichsel
manager: ''
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-06-19
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 68afc5d789d1f4af67cd2ec73eb0e073efad0761
ms.sourcegitcommit: 4ff8c2c2f3705d8045df66f2c4393253e05b49ed
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2019
ms.locfileid: "1864393"
---
# <a name="edit-onboarding-guides-and-templates-in-dynamics-365-for-talent-onboard"></a>Bevezetési útmutatók és sablonok szerkesztése a Dynamics 365 for Talent: Onboard szolgáltatásban

[!include [banner](includes/banner.md)]

Miután létrehozta a felvételi útmutatót vagy sablont a Microsoft Dynamics 365 for Talent: Onboard szolgáltatásban, hozzá kell adnia egy bevezetést, a tevékenységeket, a kapcsolattartókat és az erőforrásokat. Az Onboard segítségével multimédiás tartalmakat adhat felvételi útmutatóihoz, például a következő lehetőségek közül választhat:

- YouTube-videók
- Microsoft Sway-bemutatók
- Microsoft PowerApps-alkalmazásoknak
- Microsoft Stream-videók
- Microsoft Forms-űrlapok
- Iframe elemek webes tartalommal

## <a name="edit-introductions-or-activities-imported-from-a-template"></a>Sablonból importált bevezetések és tevékenységek szerkesztése

Ha sablon alapján hoz létre felvételi útmutatót, vagy ha egy sablonból tevékenységeket importál egy másikba, akkor az importált tevékenységeknél **Zárolás** gomb látható. Ezeket *felügyelt tevékenységeknek* nevezzük.

[![Felügyelt tevékenységek](./media/onboard-edit-guide-managed-activities.png)](./media/onboard-edit-guide-managed-activities.png)

Felügyelt tevékenység kiválasztása esetén a tevékenység tetején látható a forrássablon.

[![Felügyelt tevékenység forrása](./media/onboard-edit-guide-managed-activity-source.png)](./media/onboard-edit-guide-managed-activity-source.png)

Ha egy sablonban szerkeszt egy tevékenységet, az Onboard a sablonon alapuló összes sablonnál és elküldetlen útmutatónál érvényesíti a módosításokat. Ha egy Ön által szerkesztett sablon alapján kiválasz egy nem elküldött útmutatót, majd kiválasztja a **Tevékenységek** lapot az útmutatóban, akkor értesítés jelenik meg arról, hogy módosult az útmutató. Az értesítés elvetéséhez kattintson az **OK** gombra. 

[![Értesítés módosításról](./media/onboard-edit-guide-change-notification.png)](./media/onboard-edit-guide-change-notification.png)

A frissített tevékenységek mellett megjelenik egy fekete pötty.

[![Módosult tevékenység](./media/onboard-edit-guide-changed-activity.png)](./media/onboard-edit-guide-changed-activity.png)

Az eredeti sablonon kívül nem szerkesztheti a felügyelt tevékenységeket, kivéve, ha hozzá kíván adni egy megbízottat, egy esedékességi dátumot vagy más információt a tevékenység jobb oldali szakaszában.

Ha egy felügyelt tevékenységet szeretne szerkeszteni, vagy ha nem szeretné, hogy egy tevékenység frissítéseket kapjon a sablonból, válassza ki a **Zárolás** gombot az adott tevékenységnél. A **Zárolás** gomb eltűnik. A tevékenység kezelését a továbbiakban már nem az eredeti sablon végzi, és a továbbiakban nem fog kapni a sablonból származó frissítéseket. A tevékenységhez tartozó módosítások nincsenek hatással az eredeti sablonra.

Ha egy tevékenységet töröl egy útmutatóból, és átküldi az adott útmutató sablonjának változásait, akkor a program az útmutatóban is törli a tevékenységet.

> [!NOTE]
> A kapcsolattartók és az erőforrások nem kezelhetők a sablonokkal. Ezenkívül a szakaszok nem kezelhetők, így ha egy sablonban hozzáad vagy szerkeszt egy szakaszt, akkor a módosítások nem kerülnek át a sablont használó egyik útmutatóba vagy sablonba sem.
> 
> Ha új tevékenységeket ad egy sablonhoz, akkor az új tevékenységeket a program a sablon alapján átirányítja az útmutatókhoz és a sablonokhoz, és az új tevékenységek a lap tetején jelennek meg.

## <a name="import-activities-from-another-template"></a>Tevékenységek importálása egy másik sablonból

Egy vagy több sablonból származó tevékenységeket importálhat egy útmutatóba vagy sablonba.

1. Jelölje ki a szerkeszteni kívánt sablont vagy útmutatót.

2. Válassza ki a **Tevékenységek** lapot.

3. Válassza az **Importálás** lapot a jobb oldali szakaszon.

   [![Tevékenységek importálása](./media/onboard-edit-guide-import-activities.png)](./media/onboard-edit-guide-import-activities.png)

4. A feladatok új lapon történő előnézetéhez válassza ki a **Megnyitás új lapon** gombot bármelyik sablonon.

   [![Tevékenységek importálása](./media/onboard-edit-guide-preview-activities.png)](./media/onboard-edit-guide-preview-activities.png)

5. Húzza a kívánt sablont az útmutató azon részére, ahol szeretné, hogy a tevékenységek megjelenjenek. Folytassa az útmutató vagy a sablon szerkesztését.

Az importált tevékenységek **Zárolás** gombot tartalmaznak, amely jelzi, hogy az adott tevékenységeket az a sablon kezeli, ahonnan az importálást végezte. Ha módosítja az importált sablont, akkor ezek a tevékenységek frissülnek abban a sablonban is, amelyikbe importálta őket. A változtatások azonban nem kerülnek át automatikusan minden olyan útmutatóba, amely az importált sablonból jön létre.

## <a name="push-changes-from-a-template-to-other-templates-or-guides"></a>Sablonbeli módosítások elküldése más sablonokba vagy útmutatókba

Ha szerkeszt egy olyan sablont, amely más sablonok vagy útmutatók által használt tevékenységeket tartalmaz, akkor a változtatásokat érvényesítenie kell, ha azt szeretné, hogy megjelenjenek a többi sablonban vagy útmutatóban.

Ha nem tudja biztosan, hogy a sablonban szereplő tevékenységeket használják-e más sablonok vagy útmutatók, akkor válassza az **Itt használatos** lehetőséget annak megtekintéséhez, hogy hol jelennek meg az adott tevékenységek.

   [![Azon útmutatók és sablonok megtekintése, melyekben szerepelnek tevékenységek](./media/onboard-edit-guide-view-used-in.png)](./media/onboard-edit-guide-view-used-in.png)

A módosítások érvényesítése:

1. A változtatások mentéséhez kattintson a **Mentés** gombra. Ha ezt nem teszi meg, a program a következő lépésben megkérdezi, hogy menti-e a változtatásokat.

2. Válassza a **Módosítások áttolása** lehetőséget.

   
## <a name="add-or-edit-an-introduction"></a>Bevezetés hozzáadása vagy szerkesztése

1. A **Bevezetés** lapon adja meg az útmutató címét és egy nyitó üzenetet. A minta szövegének használatához válassza az **Adott üzenet használata** lehetőséget.

    [![Bevezetés lap az Onboard sablonban](./media/onboard-template-introduction.png)](./media/onboard-template-introduction.png)

2. A formázás gombjaival a szükséges szöveget kiemelhet, valamint képeket és hivatkozásokat is felvehet.
3. A munka mentéséhez válassza a **Mentés** elemet.

## <a name="add-or-edit-activities"></a>Tevékenységek hozzáadása és szerkesztése

1. A **Tevékenységek** lapon húzza a jobb oldali elemeket a szerkesztési területre.
2. Az útmutató szakaszokba történő rendezéséhez húzza az **Új szakasz** elemet a szerkesztési területre, és adjon meg egy nevet és opcionálisan egy leírást a szakaszhoz.

    ![[Új szakasz hozzáadása a felvételi útmutatóhoz vagy sablonhoz] (./media/onboard-edit-add-section.png)](./media/onboard-edit-add-section.png)

3. Ha az új alkalmazott számára elvégzendő tevékenységeket szeretne hozzáadni, húzza az **Új tevékenység** elemet a szerkesztési területre, és adja meg a tevékenység nevét és leírását.

    ![[Új tevékenység hozzáadása a felvételi útmutatóhoz vagy sablonhoz] (./media/onboard-edit-add-activity.png)](./media/onboard-edit-add-activity.png)

4. Multimédiás tartalom hozzáadása a felvételi útmutatóhoz:

    - A YouTube-videoklipek hozzáadásához húzza a **YouTube** elemet a szerkesztési területre, adja meg a tevékenység nevét és leírását, és adja meg a YouTube-videoklip URL-címét.
    - A Sway-bemutató vagy -hírlevél hozzáadásához húzza a **Sway** elemet a szerkesztési területre, adja meg a tevékenység nevét és leírását, és adja meg az Sway-bemutató vagy -hírlevél beágyazott URL-jét.
    - Ha PowerApps-alkalmazást szeretne hozzáadni, húzza át a **PowerApps** elemet a szerkesztési területre, adja meg a tevékenység nevét és leírását, majd válassza ki a PowerApps-alkalmazást, illetve írja be a PowerApps-alkalmazásazonosítót.
    - A Microsoft Stream-videoklipek hozzáadásához húzza a **Microsoft Stream** elemet a szerkesztési területre, adja meg a tevékenység nevét és leírását, és adja meg a Microsoft Stream-videoklip URL-címét.
    - Microsoft Forms-űrlap hozzáadásához húzza a **Microsoft Forms** elemet a szerkesztési területre, adja meg a tevékenység nevét és leírását, adja meg a Microsoft Forms-űrlap URL-címét, majd adja meg a képernyőterület méretét.
    - Webes tartalmat tartalmazó iframe hozzáadásához húzza a **Webes tartalom (iframe)** elemet a szerkesztési területre, adja meg a tevékenység nevét és leírását, adja meg a webes tartalom URL-címét, majd adja meg a képernyőterület méretét.

    ![[Multimédiás tartalom hozzáadása a felvételi útmutatóhoz vagy sablonhoz](./media/onboard-edit-add-rich-content.png)](./media/onboard-edit-add-rich-content.png)

2. Nem kötelező: az egyes tevékenységektől jobbra található területen a tevékenységet hozzárendelheti egy adott személyhez vagy szerepkörhöz, hozzáadhatja a határidőt és a kapcsolattartót, és hozzárendelheti a kategória színét. Ha egy tevékenységet egy személyhez vagy egy szerepkörhöz rendel, akkor minden egyes személyhez létrejön egy-egy feladat. Ez a feladat az Onboard **Feladatok** menüjében jelenik meg.

    [![Tevékenység hozzárendelése a felvételi útmutatóban vagy sablonban](./media/onboard-assign-activity.png)](./media/onboard-assign-activity.png)

3. A munka mentéséhez válassza a **Mentés** elemet.

Tevékenység vagy szakasz törléséhez válassza a **Törlés** gombot (kuka szimbólum) a tevékenység vagy szakasz jobb felső sarkában.

A tevékenységek és szakaszok átrendezéséhez húzza át őket egy új helyre.

## <a name="add-or-edit-contacts"></a>Névjegyek hozzáadása és szerkesztése

Felvehet kapcsolattartókat, akik segíthetik az új alkalmazott sikerességét már az első naptól kezdve. Ezek a kapcsolattartók lehetnek toborzók, csapattársak, segítők, mentorok, adminisztrátorok és informatikai szakemberek is.

1. A **Névjegyek** lapon válassza az **Új névjegy** elemet.
2. A **Csapattag hozzáadása** párbeszédpanelen írja be a kapcsolattartó nevét vagy e-mail-címét, adja meg azt a rövid leírást, amely leírja, hogy a kapcsolattartó milyen módon segít az új alkalmazottnak, majd válassza a **Hozzáadás** elemet. 

    ![[Névjegyek hozzáadása a felvételi útmutatóhoz vagy sablonhoz] (./media/onboard-edit-add-contact.png)](./media/onboard-edit-add-contact.png)

    Másik megoldásként a **Javaslatok** között kiválaszthat egy vagy több kapcsolattartót.

3. A munka mentéséhez válassza a **Mentés** elemet.

Ha törölni szeretne egy névjegyet, válassza a **Törlés** gombot (a kuka szimbólumot) a névjegytől jobbra.

Ha szerkeszteni szeretne egy névjegyet, válassza a **Szerkesztés** gombot (a ceruza szimbólumot) a névjegytől jobbra.

## <a name="add-or-edit-resources"></a>Erőforrások hozzáadása és szerkesztése

Hasznos fájlokat, térképeket és hivatkozásokat adhat a felvételi útmutató **Erőforrások** szakaszához.

1. Az **Erőforrások** lapon válassza az **Új erőforrás** elemet.
2. Tegye a következők egyikét:

    - Fájl hozzáadásához válassza ki a **Fájlok** lapot, és húzza a fájlt a kívánt területre. (Másik lehetőségként kattintson a területen bárhová a számítógépen található fájlok tallózásához, vagy válassza a **OneDrive tallózása** parancsot.) Írjon be egy nevet a fájlnak, majd válassza a **Hozzáadás** elemet.
    - Hivatkozás hozzáadásához válassza a **Hivatkozás** lapot, adja meg a hivatkozás nevét és címét, majd válassza a **Hozzáadás** elemet.
    - Térkép hozzáadásához válassza a **Térkép** lapot, adja meg a térkép nevét és címét, majd válassza a **Hozzáadás** elemet. Az Onboard tartalmazni fogja a megadott cím térképét.

    ![[Erőforrás hozzáadása a felvételi útmutatóhoz vagy sablonhoz] (./media/onboard-edit-add-resource.png)](./media/onboard-edit-add-resource.png)

3. A munka mentéséhez válassza a **Mentés** elemet.

Ha törölni szeretne egy erőforrást, válassza a **Törlés** gombot (a kuka szimbólumot) az erőforrástól jobbra.

Ha szerkeszteni szeretne egy névjegyet, válassza a **Szerkesztés** gombot (a ceruza szimbólumot) az erőforrástól jobbra.

## <a name="next-steps"></a>Következő lépések

- [Osszon meg tartalmakat más közreműködőkkel](./onboard-share-template.md)
- [A feladatok és az alkalmazottak és bevezetési állapotának megtekintése](./onboard-view-status.md)
- [Toborzócsoportok létrehozása az Onboard alkalmazásban](./onboard-create-team.md)

### <a name="see-also"></a>Lásd még

- [Próbálja ki vagy vásárolja meg az Onboard alkalmazást](https://dynamics.microsoft.com/talent/onboard/)
- [Újdonságok](./whats-new.md)
- [Programverzióra vonatkozó megjegyzések](https://docs.microsoft.com/business-applications-release-notes/index)
- [Támogatás kérése](./talent-support.md)
