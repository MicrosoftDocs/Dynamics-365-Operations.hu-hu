---
title: Súgórendszer
description: Ez a témakör a Finance and Operations alkalmazások súgórendszeréről nyújt áttekintést.
author: edupont04
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: tfehr
ms.custom: 16381
ms.assetid: 018c148c-9cbd-41e0-8186-d75dbf66288f
ms.search.region: Global
ms.author: edupont
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 46168dd9001921471114c219c57856b7bedf6465
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749828"
---
# <a name="help-system"></a>Súgórendszer

[!include [banner](../includes/banner.md)]

A következő alkalmazások felhasználói hozzáférhetnek a környezetfüggő súgóhoz és más, ugyanazon a súgórendszeren alapuló tartalomhoz:

- Microsoft Dynamics 365 Commerce
- Dynamics 365 Finance
- Dynamics 365 Human Resources
- Dynamics 365 Supply Chain Management

Minden ilyen alkalmazásban hozzáférhet a termékspecifikus súgóhoz a **Súgó** panelről.

![Súgó ablak](./media/help-pane-ops-help.png)

## <a name="help-on-docsmicrosoftcom"></a>Súgó a docs.microsoft.com-on

A docs.microsoft.com webhely ([docs.microsoft.com/dynamics365/](https://docs.microsoft.com/dynamics365/)) a termékdokumentáció alapértelmezett forrása az imént felsorolt alkalmazásokhoz. Ez a webhely a következő funkciókat ajánlja:

- **Hozzáférés a legfrissebb tartalmakhoz** – A webhely lehetőséget ad a Microsoftnak a termékdokumentációk gyorsabb, rugalmasabb létrehozására, szállítására és frissítésére. Így egyszerűen hozzáférhet a legfrissebb technikai információkhoz jut hozzá.
- **Szakértők által írt tartalmak** – A webhely tartalma nyitott a Microsofton belül és kívül egyaránt a közösség tagjainak hozzájárulására.

A docs.microsoft.com tartalmait bármilyen keresőmotor segítségével meg lehet találni. A legjobb eredmények elérése érdekében azt javasoljuk, hogy webhelyre korlátozott keresést végezzen, mint például: **site:docs.microsoft.com dynamics 365 „keresőkifejezés”**

## <a name="get-notified-about-changes-through-an-rss-feed"></a>Értesítés a változásokról RSS-hírcsatornán keresztül

Ha fel szeretne iratkozni egy RSS (Really Simple Syndication) hírcsatornára a docs.microsoft.com tartalmára vonatkozó összes frissítésről, használja a következő hivatkozást:

[RSS-hírcsatorna](https://docs.microsoft.com/api/search/rss?locale=en-us&$filter=scopes%2Fany(t%3A%20t%20eq%20%27Unified%20Operations%27))

### <a name="leave-us-feedback"></a>Visszajelzés küldése

Ha visszajelzése vagy kérdése van egy témakörrel kapcsolatban, hagyjon megjegyzést az oldal alján.

1. Válassza a **Visszajelzés** lehetőséget, hogy eljusson a lap alján lévő megjegyzésekhez. Ezt követően válassza ki **Termékvisszajelzés** vagy a **Bejelentkezés dokumentációval kapcsolatos visszajelzéshez** lehetőséget.

2. Írja be megjegyzését, majd válassza a **Visszajelzés beküldése** lehetőséget.

    ![Megjegyzés elküldése](./media/feedback.png)

> [!NOTE]
> Ha dokumentációs visszajelzést szeretne küldeni, akkor GitHub-fiókkal kell bejelentkeznie. További információ: [GitHub-profil beállítása és kezelése](https://help.github.com/github/setting-up-and-managing-your-github-profile).

## <a name="contribute-to-the-documentation"></a>Közreműködés a dokumentációban

A dokumentációban közreműködhet, és módosításokat hajthat végre. Első lépésként kattintson a **Szerkesztés** gombra (ceruza szimbólum) egy témakörön. A következő videó bemutatja, hogyan lehet közreműködni a dokumentációban.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE36liB]

A [Hozzájárulás a Microsoft Dynamics 365 dokumentációhoz](https://youtu.be/m5djioozRbg) videó (lásd fentebb) része a Microsoft Dynamics 365 csatornának a YouTube oldalán.

A további tudnivalókat lásd a [Docs közreműködői útmutatóban](https://docs.microsoft.com/contribute), amelyet a docs.microsoft.com webhelyét összeállító csoport publikál.

> [!NOTE]
> Jelenleg csak az angol nyelvű tartalomhoz fogadunk el közreműködést.

## <a name="task-guides"></a>Feladat-útmutatók

A feladatrögzítés egy kontorollált, irányított, interaktív tapasztalat, amely végigvezeti a feladat vagy az üzleti folyamat lépésein. A **Súgó** ablakban megnyithatja (lejátszatja) a feladat útmutatót. Amikor először kattint a feladat-útmutatóra a **Súgó** ablakban láthatja lépésenként a feladathoz tartozó utasításokat. A honosított feladat-útmutatók elérhetőek.

A Microsoft feladat-útmutatók könyvtárát adta ki a termék verzióihoz a Dynamics 365 for Finance and Operations 2017. decemberi kiadásával. A témakör [Feladat-útmutatók elérése a Súgó ablakból](#accessing-task-guides-from-the-help-pane) szakasza azt mutatja be, hogyan találhatja meg a termékének megfelelő feladat-útmutatókat.

![Feladat-útmutató olvasási nézete](./media/task-guide-ops.png)

Az irányított, interaktív tapasztalat kezdéséhez kattintson a **Feladat útmutató indítása** lehetőségre a **Súgó** ablak alján. Egy fekete mutató megmutatja, hová kell menni először. Kövesse a felhasználói felületen (UI) megjelenő utasításokat, és adja meg az adatokat az utasításoknak megfelelően.

![Feladat-útmutató lépésre vonatkozó utasítása](./media/task-guide-step-1-ops.png)

> [!IMPORTANT]
> A feladat-útmutató lejátszásakor megadott adatok valósak. Ha gyártási területen van, az adatok a használt vállalathoz kerülnek bejegyzésre.

A Feladatrögzítő segítségével létrehozhatja saját egyéni feladat-útmutatóit. További tudnivalókért lásd: [Dokumentáció vagy képzés létrehozása a Feladatrögzítővel](../../dev-itpro/user-interface/task-recorder-training-docs.md).

## <a name="in-product-help"></a>Termékbe épített Súgó

Egyes mezők mezőleírással rendelkeznek, amely segítséget jelenthet a felhasználóknak abban az esetben, ha bizonytalanok például a mezőben található adatokkal kapcsolatban. Ezenkívül a termék **Súgó** ablaktáblája környezetfüggő hozzáférést biztosít a felhasználóknak az elinduláshoz, a zárolás feloldásához és a további tudnivalókhoz.

A súgótartalom eléréséhez válassza a **Súgó** gombot (**?**), majd válassza a **Súgó** lehetőséget. Vagy pedig nyomja meg a **Ctrl+Shift+?** billentyűkombinációt. Mindkét esetben a **Súgó** ablak jelenik meg. A **Súgó** ablaktáblában hozzáférhet a jelenleg a termék területére vonatkozó koncepcionális témaköröket és feladat-útmutatókat.

![Súgó ablak](./media/help-pane-ops-help.png)

### <a name="accessing-help-topics-from-the-help-pane"></a>Súgótémakörök elérése a Súgó ablakból

A **Súgó** ablakból hozzáférhet a kliensre vonatkozó témakörökhöz. Amikor először nyitja meg a **Súgó** ablakot, a **Súgó** lapon az aktuális oldalhoz kapcsolódó témakörök jelennek meg. Amennyiben nem találhatók témakörök, kulcsszavak beírásával módosíthatja a keresést. Amikor kiválaszt egy témát a **Súgó** ablaktáblán, a böngészőprogram egy új lapján nyílik meg.

> [!IMPORTANT]
> Ez a szakasz nem vonatkozik a Dynamics 365 Human Resources alkalmazásra. A Human Resources súgórendszere automatikusan kapcsolódik a termék feladat-útmutatóihoz. Ezenfelül a Human Resources rendszerben nem hozhat létre egyéni feladat-útmutatókat.

### <a name="accessing-task-guides-from-the-help-pane"></a>Feladat útmutatók elérése a Súgó ablakból

Mielőtt feladat-útmutatókat nyit meg a **Súgó** ablakban, a rendszergazdának a Finance, a Supply Chain Management vagy a Commerce **Rendszerparaméterek** lapján be kell állítania néhány paramétert. A további tudnivalókat lásd: [Feladat-útmutatók hozzáadása](help-connect.md#adding-task-guides).

<!-- > [!NOTE]
> - In order to configure Help, you must be signed in with an account in the same tenant as the tenant in which the app is deployed.
> - It is not possible to connect to an LCS library from an instance of the app running in a local virtual hard drive (VHD).

![System Parameters form with Help settings](./media/system-parameters_ops-1024x437.png)

On the **System parameters** page, follow these steps:

1. **Important:** The first time that you open the Help tab, you must connect to Lifecycle Services. Be sure to select the link in the middle of the form, wait for the connection, close the dialog box, and then select **OK** to get to the parameters form.

    ![Connect to LCS](./media/connect-to-lcs-crop-1024x365.png)

2. Select the Lifecycle Services project to connect to.
3. Select BPM libraries (within the selected project) to retrieve task recordings from.
4. Set the display order of the BPM libraries. This setting determines the order in which task recordings from the libraries will appear in the Help pane.-->

Miután egy Rendszergazda végrehajtotta ezeket a lépéseket, nyissa meg a **Súgó** ablakot, és válassza a **Feladat-útmutatók** lapot. Ekkor megjelennek az aktuális oldalhoz kapcsolódó feladat-útmutatók. Amennyiben nem találhatók feladat-útmutatók, kulcsszavak beírásával módosíthatja a keresést. Miután kiválaszt egy feladat-útmutatót a **Súgó** ablakában, a **Súgó** ablak lépésekre lebontva megjeleníti az utasításokat, továbbá lehetősége van a feladat-útmutató lejátszására is.

![Feladat-útmutató olvasási nézete](./media/task-guide-ops.png)

### <a name="where-are-the-translated-task-guides-for-microsoft-libraries"></a>Hol vannak a Microsoft tárakhoz tartozó lefordított feladat-útmutatók?

A Feladat-útmutatók a címükben az „Minden nyelv” fordulatot viselő könyvtárakban érhetők el. Ha szeretné a honosított feladat-útmutató súgót látni, győződjön meg arról, hogy csatlakozva van a megfelelő könyvtárhoz. Minden felhasználó a **Beállítások** &gt; **Beállítások** menüben található nyelvi beállítások alatt módosíthatja a feladat-útmutató megjelenítési nyelvét.

- Ha egy feladat-útmutató le van fordítva, akkor a kiválasztott nyelven fog megjelenni a feladat-útmutató teljes szövege.
- Ha egy feladat-útmutató még nincs lefordítva, akkor a megnyitásakor a kiválasztott nyelven csak a vezérlők szövegei fognak megjelenni.

## <a name="creating-custom-help"></a>Egyéni súgó létrehozása

Egyéni feladat-útmutatók létrehozásával létrehozhat egy súgót a felhasználóinak, vagy csatlakoztathatja saját webhelyét a **Súgó** panelhez. További információért tekintse át az alábbi témaköröket:

- [Feladatrögzítő erőforrásai](../../dev-itpro/user-interface/task-recorder.md)
- [Egyéni Súgó – áttekintés](../../dev-itpro/help/custom-help-overview.md)

## <a name="additional-resources"></a>További erőforrások

A következő táblázat felsorolja a weboldalainkat. A név mellett közvetlenül csillaggal (\*) jelölt webhelyeken a szolgáltatástervvel társított felhasználói fiókkal lehet belépni.

| Hely | Leírás |
|------|-------------|
| [Docs.microsoft.com](/dynamics365/) | Ezen a webhelyen található vagy kerül hivatkozásra az összes termékdokumentációhoz a Dynamics 365 rendszerben. |
| [Microsoft Learn](https://docs.microsoft.com/learn/) | Ez a webhely a Microsoft ingyenes e-learning webhelye. |
| [Microsoft DynamicsLifecycle Services (LCS)](https://lcs.dynamics.com/)\* | Ez a webhely felhőalapú együttműködési munkaterület biztosít, amelyet a vevők és a partnerek a projektek kezelésére használhatnak az értékesítés előtti műveletektől a megvalósításig és az üzemeltetésig. Az implementáció minden fázisában hasznos. |
| [Támogatási blog](https://aka.ms/AXSupportBlog) | Ez a webhely tippeket és trükköket tartalmaz, amelyeket a Támogatás csapata adott fel. |
| [Docs.microsoft.com/korábbi verziók](/previous-versions/dynamics/) | Ezen a webhelyen található a korábbi kiadások tartama. |
| [Dynamics közösség](https://community.dynamics.com/) | A webhelyen blogok, fórumok és videók találhatók. |
| [Microsoft.com/dynamics365](https://www.microsoft.com/dynamics365/home) | A webhelyen értékelések és eladási információk érhetők el. |
| [CustomerSource](https://docs.microsoft.com/dynamics/s-e/)\* | A webhely néhány oktatóanyagot tárol, letölthető jelentéseket és tanulmányokat, és ez az elsődleges támogatási webhely a szolgáltatási terv jogosultak számára. Szükség lehet egy szolgáltatási előfizetésre az egyes erőforrások eléréséhez a webhelyen. |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]