---
title: Dynamics 365 Commerce előnézeti környezet létesítése
description: Ez a témakör bemutatja, hogyan lehet egy Microsoft Dynamics 365 Commerce előzetes környezetet létesíteni.
author: psimolin
manager: annbe
ms.date: 01/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: cbd4c118de2e91c8849461b20a01403049a07e66
ms.sourcegitcommit: 4ed1d8ad8a0206a4172dbb41cc43f7d95073059c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024636"
---
# <a name="provision-a-dynamics-365-commerce-preview-environment"></a>Dynamics 365 Commerce előnézeti környezet létesítése


[!include [banner](includes/banner.md)]

Ez a témakör bemutatja, hogyan lehet egy Dynamics 365 Commerce előzetes környezetet létesíteni.

A művelet elkezdése előtt ajánljuk, hogy a jelen témakörben keressen egy rövid áttekintést, hogy megtudja, mire van szüksége a folyamatnak.

> [!NOTE]
> Ha még nem kapott hozzáférést a Dynamics 365 Commerce előzeteséhez, a [Dynamics 365 Commerce webhelyről](https://aka.ms/Dynamics365CommerceWebsite) kérhet előzetes hozzáférést.

## <a name="overview"></a>Áttekintés

A Kereskedelem előzetes környezetének sikeres létrehozásához létre kell hoznia egy projektet, amely egy adott terméknévvel és típussal rendelkezik. A környezet és a Commerce Scale Unit (CSU) szintén rendelkezik bizonyos paraméterekkel, amelyeket későbbiekben, az e-kereskedelem előzetesekor használnia kell. Az ebben a témakörben szereplő útmutatás leírja a létesítéshez szükséges összes lépést és a használandó paramétereket.

A Kereskedelem előzetes környezetének sikeres létesítését követően meg kell tennie néhány létesítést követő lépést a felkészítéséhez. Bizonyos lépések nem kötelezők, az értékelni kívánt rendszer bizonyos szempontjaitól függően. A választható lépéseket a későbbiekben bármikor befejezheti.

A Kereskedelem előzetes környezetének létesítés utáni konfigurálásáról további információt a következő témakörben talál: [Kereskedelem előzetes környezetének konfigurálása](cpe-post-provisioning.md). A Kereskedelem előzetes környezete nem kötelező funkcióinak konfigurálásáról további információt a következő témakörben talál: [Kereskedelem előzetes környezete nem kötelező funkcióinak konfigurálása](cpe-optional-features.md).

Ha kérdései vannak a létesítés lépéseivel kapcsolatban, vagy bármilyen probléma merülne fel, akkor tudassa a Microsofttal a [Microsoft Dynamics 365 Commerce előzetes Yammer-csoportjában](https://aka.ms/Dynamics365CommercePreviewYammer).

## <a name="prerequisites"></a>Előfeltételek

A következő előfeltételeknek kell érvényben lenniük a Kereskedelem előnézet környezetének létesítése előtt:

- Elérhetővé teszi a Microsoft Dynamics Lifecycle Services (LCS) portál elérését.
- Ön meglévő Microsoft Dynamics 365 partner vagy vevő, és létre tud hozni egy Dynamics 365 Commerce projektet.
- Ön felvételt nyert a Dynamics 365 Commerce előzetes programba.
- Rendelkezik a szükséges jogosultságokkal az **Áttelepítés, megoldások létrehozása és tanulás** projekt létrehozására.
- Ön tagja a **Környezetkezelő** vagy **Projekttulajdonos** szerepkörnek abban a projektben, amelyben a környezet létesítése történik.
- Rendszergazdai hozzáféréssel rendelkezik a Microsoft Azure-előfizetéshez, vagy felveheti a kapcsolatot egy előfizetési adminisztrátorral, aki elvégezheti a két lépést, amelyek az Ön nevében rendszergazdai jogosultságot igényelnek.
- Rendelkezésére áll az Azure Active Directory (Azure AD) bérlői azonosító.
- Létrehozott egy Azure AD biztonsági csoportot, amelyet az e-kereskedelmi rendszeradminisztrátori csoportként használhat, és a rendelkezésére áll annak azonosítója.
- Létrehozott egy Azure AD biztonsági csoportot, amelyet minősítési vagy értékelési moderátori csoportként használhat, és a rendelkezésére áll annak azonosítója. (Ez a biztonsági csoport lehet ugyanaz, mint az e-kereskedelmi rendszeradminisztrátori csoport.)

## <a name="provision-your-commerce-preview-environment"></a>Commerce előzetes környezet kiépítése

Ezek az eljárások ismertetik a Commerce előzetes környezet kiépítését. A sikeres befejezést követően a Commerce előzetes környezete készen áll a konfigurációra. Az itt ismertetett tevékenységek az LCS portálon történnek.

> [!IMPORTANT]
> Az előzetes hozzáférés LCS-fiókhoz és szervezethez kötődik, amelyet a Commerce előzetes alkalmazásban megadott. Ugyanazt a fiókot kell használnia a Commerce előzetes környezet létesítése érdekében. Ha a Commerce előzetes környezethez más LCS-fiókot vagy bérlőt kell használnia, ezeket az adatokat meg kell adnia a Microsoftnak. A kapcsolattartói adatokért tekintse meg a [Commerce előzetes környezet támogatása](#commerce-preview-environment-support) szakaszt a témakör későbbi részében.

### <a name="confirm-that-preview-features-are-available-and-turned-on-in-lcs"></a>Ellenőrizze, hogy az előzetes funkciók elérhetők-e és be vannak-e kapcsolva az LCS rendszerben

Annak ellenőrzésére, hogy elérhetők-e az előzetes funkciók és be vannak-e kapcsolva az LCS rendszerben, kövesse ezeket a lépéseket.

1. Jelentkezzen be az [LCS-portálra](https://lcs.dynamics.com) az előzeteshez való hozzáférés kérésére használt LCS-fiók használatával.
1. A LCS kezdőoldalán görgessen teljesen jobbra, majd válassza az **Előzetes funkció kezelése** csempét.

    ![Előzetes funkció kezelése csempe](./media/preview1.png)

1. Görgessen le a **Privát előzetes funkciók** elemre, és erősítse meg, hogy a következő szolgáltatások elérhetők és be vannak kapcsolva:

    - Elektronikus kereskedelem értékelése
    - Kereskedelem előnézeti környezetei

    ![Privát előzetes funkciók](./media/preview2.png)

1. Ha ezek a funkciók nem jelennek meg a listában, forduljon a Microsofthoz, és adja meg munkahelyi e-mail-címét, LCS-fiókját és bérlőadatait. A kapcsolattartói adatokért tekintse meg a [Commerce előzetes környezet támogatása](#commerce-preview-environment-support) szakaszt.

### <a name="create-a-new-project"></a>Új projekt létrehozása

Új LCS projekt létrehozásához kövesse az alábbi lépéseket.

1. Az LCS-kezdőlapon válassza a pluszjelet (**+**) a projekt létrehozásához.
1. A jobb oldali panelen kövesse az alábbi lépések egyikét:

    - Ha Ön partner, válassza az **Áttelepítés, megoldások létrehozása és tanulás** lehetőséget.
    - Ha Ön ügyfél, válassza ki **Lehetséges előértékesítések** lehetőséget.

1. Adja meg a nevet, leírást és iparágat.
1. A **Terméknév** mezőben válassza a **Dynamics 365 Retail** elemet.
1. A **Termék verziója** mezőben válassza a **Dynamics 365 Retail** elemet.
1. A **Módszertan** mezőben válassza a **Dynamics Retail-implementáció módszertana** lehetőséget.
1. Nem kötelező: Szerepköröket és felhasználókat létező projektből is importálhat.
1. Válassza a **Létrehozása** lehetőséget. Megjelenik a projektnézet.

### <a name="add-the-azure-connector"></a>Azure-összekötő hozzáadása

Az Azure-összekötő LCS-projekthez való hozzáadásához kövesse az alábbi lépéseket.

1. Tegye a következők egyikét:

    - Ha Ön partner, válassza a **Projektbeállítások** csempét a jobb szélen.
    - Ha Ön ügyfél, válassza a felső menü **Projekt beállításai** elemét.

1. Válassza ki az **Azure-összekötőket**.
1. Válassza a **+ hozzáadás** elemet az Azure-összekötő hozzáadásához.
1. Adjon meg egy nevet.
1. Adja meg Azure-előfizetésének azonosítóját.
1. Kapcsolja be a **Konfigurálás az Azure Resource Manager (ARM) használatához** lehetőséget.
1. Ellenőrizze, hogy az **Azure-előfizetés AAD-bérlőjének tartománya (vagy azonosítója)** értéke helyes. Szükség esetén forduljon a Azure előfizetés adminisztrátorához.
1. Válassza ki **Következő** lehetőséget.
1. Kövesse az oldalon megjelenő utasításokat, és adjon hozzáférést a szükséges alkalmazásoknak az előfizetéshez. Szükség esetén forduljon a Azure előfizetés adminisztrátorához.

    1. Jelentkezzen be az [Azure portálra](https://portal.azure.com/).
    1. Győződjön meg arról, hogy a megfelelő könyvtár van kijelölve, majd a bal oldali menüben válassza az **előfizetése** menüpontot.
    1. Keresse meg a megfelelő előfizetést a listában, majd válassza ki azt. Szükség szerint használja a keresési funkciót.
    1. A menüben válassza az **Elérés szabályozása (IAM)** elemet.
    1. A jobb oldalon található **Szerepkör-hozzárendelés** hozzáadása területen kattintson a **Hozzáadás** gombra. Megjelenik **Szerepkör hozzárendelése** panel.
    1. A **Szerepkör** mezőben válassza a **Közreműködő** lehetőséget.
    1. A **Hozzáférés hozzárendelése** mezőben hagyja az alapértelmezett értéket **Azure AD-felhasználó, csoport vagy szolgáltatásnév** beállításon.
    1. A **Kijelölés** alatt adja meg a **b96b7e94-b82e-4e71-99a0-cf7fb188acea** értéket.
    1. Válassza ki a **Dynamics telepítési szolgáltatások \[wsfed-enabled\]** elemet a listáról.
    1. Válassza a **Mentés** lehetőséget.

1. Válassza ki **Következő** lehetőséget.
1. Kövesse az oldalon megjelenő utasításokat, és adjon hozzáférést a szükséges alkalmazásoknak az előfizetéshez. Szükség esetén forduljon a Azure előfizetés adminisztrátorához.
1. Válassza ki **Következő** lehetőséget.
1. A **Azure régió** mezőben válassza az **Egyesült Államok keleti része**, **Egyesült Államok kelti része 2**, **Egyesült Államok nyugati része** vagy **Egyesült Államok nyugati része 2** lehetőséget.
1. Válassza a **Kapcsolódás** parancsot. Az Azure-összekötőnek meg kell jelennie a listában.

### <a name="import-the-commerce-preview-demo-base-extension"></a>A Commerce előzetes bemutató alapbővítményének importálása

A Commerce előzetes emutató alapbővítményének projektbe importálásához kövesse az alábbi lépéseket.

1. Nyissa meg a projekt kezdőlapját a tetején lévő projektnév kiválasztásával.
1. Tegye a következők egyikét:

    - Ha Ön partner, válassza az **Eszköztár** csempét a jobb szélen.
    - Ha Ön ügyfél, válassza a felső menü **Eszköztár** elemét.

1. Válassza a **Telepíthető szoftvercsomag** elemet a bal oldali listából.
1. Válassza az **Importálás** lehetőséget.
1. A **Közös eszköztár** részben válassza ki a **Commerce előzetes bemutató alapbővítmény** lehetőséget az eszközök listájából.
1. Válassza a **Kitárolás** elemet. A program visszairányítja az Eszköztárba, és a listában megjelenik a bővítmény.

A kötkező ábrán az LCS **Eszköztár** oldalán végrehajtandó műveleteket mutatja.

![A Commerce előzetes bemutató alapbővítményének importálása](./media/import.png)

### <a name="deploy-the-environment"></a>Környezet telepítése

Tegye a következőket a környezet telepítéséhez.

> [!NOTE]
> Előfordulhat, hogy nem kell a 6., 7. és/vagy 8. lépést végrehajtania, mert az egyetlen lehetőséggel rendekező oldalakat a rendszer átugorja. Amikor a **Környezeti paraméterek** nézetben van, erősítse meg, hogy a **Dynamics 365 Commerce – bemutató (10.0.* x* a Platform update *xx* frissítéssel)** szöveg közvetlenül a **Környezet neve** mező felett jelenik meg. További részletekért lásd a 8. lépés után megjelenő ábrát.

1. Válassza a felső menü **Felhőalapú környezetek**pontját.
1. Környezet hozzáadásához kattintson a **+ hozzáadás** gombra.
1. Válassza ki az **Alkalmazás verziószáma** mezőben a legfrissebb verziót. Ha a legfrissebb verziótól különböző verziót kell kijelölni, akkor ne válasszon **10.0.8** előtti verziót.
1. A **Platform verziószáma** mezőben használja a kiválasztott alkalmazás verziójának automatikusan kiválasztott platform verzióját. 

    ![Válassza ki az alkalmazás- és a platformverziókat](./media/project1.png)

1. Válassza ki **Következő** lehetőséget.
1. **Demó** kiválasztása környezeti topológiaként.

    ![1. környezeti topológia kiválasztása](./media/project2.png)

1. Válassza ki a **Dynamics 365 Commerce – bemutatót** környezeti topológiaként. Ha korábban egyetlen Azure-csatlakozót állított be, akkor ez lesz a környezethez használva. Ha több Azure-összekötőt konfigurált, kiválaszthatja a használandó összekötőt: **Egyesült Államok keleti része**, **Egyesült Államok keleti része 2**, **Egyesült Államok nyugati része** vagy **Egyesült Államok nyugati része 2**. (A legjobb végpontok közötti teljesítmény esetén ajánlott az **Egyesült Államok nyugati része 2**kiválasztása.)

    ![2. környezeti topológia kiválasztása](./media/project3.png)

1. A **Környezet telepítése** oldalán adja meg a környezet nevét. A Speciális beállításokat ne módosítsa.

    ![Környezet telepítése oldal](./media/project4.png)

1. Szükség szerint állítsa be a virtuális gép méretét. (A következő virtuálisgép-raktározási egységet javasoljuk: \[SKU\] **D13 v2**.)
1. Tekintse át az árképzési és licencelési feltételeket, majd jelölje be a jelölőnégyzetet annak jelzésére, hogy elfogadja azokat.
1. Válassza ki **Következő** lehetőséget.
1. A telepítési visszaigazolás oldalán győződjön meg róla, hogy az adatok helyesek, majd kattintson a **Telepítés** gombra. Vissza fog térni a **Felhőalapú környezetek** nézethez, és a környezetnek meg kell jelennie a listán.

    A kért környezet várólistán jelenik meg, majd telepíthető. A környezeti munkafolyamatok némi időt fognak igénybe venni. Ezért nézzen vissza körülbelül 6–9 óra múlva.

1. A folytatás előtt győződjön meg arról, hogy a környezet állapota **Telepített**.

### <a name="initialize-the-commerce-scale-unit-csu"></a>A Commerce Scale Unit (CSU) inicializálása

Egy CSU-cím inicializálásához kövesse az alábbi lépéseket.

1. A **felhőalapú környezetek** nézetben válassza ki a saját környezetét a listából.
1. Kattintson a jobb oldalon található környezeti nézet **Minden részlet** elemére. Megjelenik a környezeti részletek nézet.
1. A **Környezeti funkciók**területen kattintson a**Kezelés** elemre.
1. A **Commerce** lapon válassza az **Inicializálás** parancsot. Megjelenik a CSU inicializálási paraméterei nézet.
1. A **Régió** mezőben válassza az **Egyesült Államok keleti része**, **Egyesült Államok keleti része 2**, **Egyesült Államok nyugati része** vagy **Egyesült Államok nyugati része 2** lehetőséget.
1. A **Verzió** mezőben válassza a **Verzió megadása** lehetőséget a listából, majd a megjelenő mezőben adja meg: **9.18.20014.4**. Ügyeljen arra, hogy pontosan adja meg az itt jelzett verziószámot. Ellenkező esetben később frissítenie kell a RCSU programot a megfelelő verzióra.
1. Kapcsolja be a **bővítmény alkalmazása** beállítást.
1. A bővítmények listájából válassza a **Commerce előzetes demó alapbővítmény** lehetőséget.
1. Válassza az **Inicializálás** elemet.
1. A telepítési visszaigazolás oldalán győződjön meg róla, hogy az adatok helyesek, majd kattintson az **Igen** gombra. Újra megjelenik a **Commerce Management** nézet, amelyen a **Commerce** lap ki van választva. A CSU várólistára került a létesítéshez.
1. A folytatás előtt győződjön meg arról, hogy az CSU állapota **Sikeres**. Az inicializálás körülbelül két-öt órát vesz igénybe.

### <a name="initialize-e-commerce"></a>Az elektronikus kereskedelem inicializálása

Az e-kereskedelem inicializálásához kövesse az alábbi lépéseket.

1. Az **e-kereskedelem** lapon tekintse át az előzetes jóváhagyását, majd válassza a **Beállítás** lehetőséget.
1. Az **E-kereskedelmi bérlő neve** mezőben adjon meg egy nevet. Azonban fontos megjegyezni, hogy ez a név az e-kereskedelem példányra mutató néhány URL-címen látható lesz.
1. A **Commerce Cloud Scale Unit neve** mezőben válassza ki az CSU-t a listából. (A listában csak egy opciónak kell lennie.)

    Az **E-kereskedelmi földrajz** mező beállítása automatikus, az érték pedig nem módosítható.

1. A folytatáshoz kattintson a **Tovább** gombra.
1. A **Támogatott állomásnevek** mezőbe írjon be egy tetszőleges érvényes tartományt, például `www.fabrikam.com`.
1.  Az **AAD biztonsági csoport rendszergazdának** mezőben adja meg a használni kívánt biztonsági csoport első néhány betűjét. A keresési eredmények megjelenítéséhez válassza a nagyítóosztály ikonját. Válasszon ki egy megfelelő biztonsági csoportot a listából.
2.  Az **AAD biztonsági csoport minősítési és értékelési moderátornak** mezőben adja meg a használni kívánt biztonsági csoport első néhány betűjét. A keresési eredmények megjelenítéséhez válassza a nagyítóosztály ikonját. Válasszon ki egy megfelelő biztonsági csoportot a listából.
1. Az **Értékelések és vélemények szolgáltatás engedélyezése** értékét hagyja bekapcsolva.
1. Válassza az **Inicializálás** elemet. Újra megjelenik a **Commerce Management** nézet, amelyen a **e-kereskedelem** lap ki van választva. Az e-kereskedelem inicializálása elindult.
1. A folytatás előtt várja meg, amíg az e-kereskedelem inicializálási állapota **Az inicializálás sikerült**állapotra nem vált.
1. A jobb alsó sarokban található **Hivatkozások** részben jegyezze fel a következő hivatkozások URL-címeit:

    * **e-kereskedelmi webhely** -Az e-kereskedelmi webhely gyökerére mutató hivatkozás.
    * **e-kereskedelmi webhelykezelési eszköz** - A webhelykezelési eszközre mutató eszköz.

## <a name="commerce-preview-environment-support"></a>Commerce előzetes verziós környezet támogatása

Ha problémák merülnek fel a létesítés lépéseinek végrehajtása közben, akkor kérjen segítséget [a Microsoft Dynamics 365 Commerce előzetes Yammer-csoportjában](https://aka.ms/Dynamics365CommercePreviewYammer).

Ha problémákat tapasztal, amikor megpróbál hozzáférni a Yammer-csoporthoz, akkor lépjen kapcsolatba a Microsofttal e-mailben a <Dynamics365Commerce@microsoft.com> címen. Ez az e-mail-cím nincs aktív felügyelet alatt. Ezért késedelemre számíthat a válaszadásban.

## <a name="next-steps"></a>Következő lépések

A Kereskedelem előzetes környezetének létesítési és konfigurálási folyamatának folytatásához lásd: [Kereskedelem előzetes környezetének konfigurálása](cpe-post-provisioning.md).

## <a name="additional-resources"></a>További erőforrások

[Dynamics 365 Commerce előzetes verziós környezet áttekintése](cpe-overview.md)

[Dynamics 365 Commerce előzetes verziós környezet konfigurálása](cpe-post-provisioning.md)

[A Dynamics 365 Commerce előzetes verziós környezet választható funkcióinak konfigurálása](cpe-optional-features.md)

[Dynamics 365 Commerce előzetes verziós környezet GYIK](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Microsoft Azure-portál](https://azure.microsoft.com/features/azure-portal)

[Dynamics 365 Commerce-webhely](https://aka.ms/Dynamics365CommerceWebsite)

