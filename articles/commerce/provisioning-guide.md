---
title: Dynamics 365 Commerce értékelési környezet kiépítése
description: Ez a témakör bemutatja, hogyan lehet egy Microsoft Dynamics 365 Commerce értékelési környezetet létesíteni.
author: psimolin
ms.date: 12/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8b288a0d6b7516faf635486fbaad885344d2cc6f
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6352084"
---
# <a name="provision-a-dynamics-365-commerce-evaluation-environment"></a>Dynamics 365 Commerce értékelési környezet kiépítése

[!include [banner](includes/banner.md)]

Ez a témakör bemutatja, hogyan lehet egy Microsoft Dynamics 365 Commerce értékelési környezetet létesíteni.

A művelet elkezdése előtt ajánljuk, hogy a jelen témakörben keressen egy rövid áttekintést, hogy megtudja, mire van szüksége a folyamatnak.

> [!NOTE]
> A Commerce értékelési környezetek általában nem állnak rendelkezésre, és a partnerek és a vevők számára a kérelem alapján biztosítják. További információért lépjen kapcsolatba Microsoft-partnerének kapcsolattartójával.

A Commerce értékelési környezetének sikeres létrehozásához létre kell hoznia egy projektet, amely egy adott terméknévvel és típussal rendelkezik. A környezet és a Commerce Scale Unit (CSU) szintén rendelkezik bizonyos paraméterekkel, amelyeket későbbiekben, az e-kereskedelem létesítésekor használnia kell. Az ebben a témakörben szereplő útmutatás leírja a létesítéshez szükséges összes lépést és a használandó paramétereket.

A Kereskedelem értékelési környezetének sikeres létesítését követően meg kell tennie néhány létesítést követő lépést a felkészítéséhez. Bizonyos lépések nem kötelezők, az értékelni kívánt rendszer bizonyos szempontjaitól függően. A választható lépéseket a későbbiekben bármikor befejezheti.

A Kereskedelem értékelési környezetének létesítés utáni konfigurálásáról további információt a következő témakörben talál: [Kereskedelem értékelési környezetének konfigurálása](cpe-post-provisioning.md). A Kereskedelem értékelési környezete nem kötelező funkcióinak konfigurálásáról további információt a következő témakörben talál: [Kereskedelem értékelési környezete nem kötelező funkcióinak konfigurálása](cpe-optional-features.md).

## <a name="prerequisites"></a>Előfeltételek

A következő előfeltételeknek kell érvényben lenniük a Kereskedelem értékelési környezetének létesítése előtt:

- Önt már beléptették az értékelési programba, és kapacitást biztosítottak egy értékelési környezethez.
- Elérhetővé teszi a Microsoft Dynamics Lifecycle Services (LCS) portál elérését.
- Ön meglévő Microsoft Dynamics 365 partner vagy vevő, és létre tud hozni egy Dynamics 365 Commerce projektet.
- Rendszergazdai jogosultsággal rendelkezik a Microsoft Azure-előfizetéshez, vagy kapcsolatba lép egy előfizetési adminisztrátorral, aki a szükség esetén segítséget nyújthat.
- Rendelkezésére áll az Azure Active Directory (Azure AD) bérlői azonosító.
- Létrehozott egy Azure AD biztonsági csoportot, amelyet az e-kereskedelmi rendszeradminisztrátori csoportként használhat, és a rendelkezésére áll annak azonosítója.
- Létrehozott egy Azure AD biztonsági csoportot, amelyet minősítési vagy értékelési moderátori csoportként használhat, és a rendelkezésére áll annak azonosítója. (Ez a biztonsági csoport lehet ugyanaz, mint az e-kereskedelmi rendszeradminisztrátori csoport.)

Ne felejtse el, hogy ez a lista nem teljes. Ha bármilyen problémába ütközik forduljon a Microsoft-partnere kapcsolattartójához.

## <a name="provision-your-commerce-evaluation-environment"></a>Commerce értékelési környezet kiépítése

Ezek az eljárások ismertetik a Commerce értékelési környezet kiépítését. A sikeres befejezést követően a Commerce értékelési környezete készen áll a konfigurációra. Az itt ismertetett tevékenységek az LCS portálon történnek.

### <a name="create-a-new-project"></a>Új projekt létrehozása

Új LCS projekt létrehozásához kövesse az alábbi lépéseket.

1. Az LCS-kezdőlapon válassza a pluszjelet (**+**) a projekt létrehozásához.
1. A jobb oldali panelen kövesse az alábbi lépések egyikét:

    - Ha Ön partner, válassza az **Áttelepítés, megoldások létrehozása és tanulás** lehetőséget.
    - Ha Ön ügyfél, válassza ki **Lehetséges előértékesítések** lehetőséget.

1. Adja meg a nevet, leírást és iparágat.
1. A **Terméknév** mezőben válassza a **Dynamics 365 Commerce** elemet.
1. A **Termék verziója** mezőben válassza a **Dynamics 365 Commerce** elemet.
1. A **Módszertan** mezőben válassza a **Dynamics Retail-implementáció módszertana** lehetőséget.
1. Nem kötelező: Szerepköröket és felhasználókat létező projektből is importálhat.
1. Válassza a **Létrehozása** lehetőséget. Megjelenik a projektnézet.

### <a name="add-the-azure-connector"></a>Azure-összekötő hozzáadása

Az Azure összekötőnek az LCS-projekthez történő hozzáadásához kövesse az [Azure Resource Manager felvételi folyamat teljesítése](../fin-ops-core/dev-itpro/deployment/arm-onboarding.md) lépéseit.

### <a name="deploy-the-environment"></a>Környezet telepítése

Tegye a következőket a környezet telepítéséhez.

> [!NOTE]
> Előfordulhat, hogy nem kell a 6., 7. és/vagy 8. lépést végrehajtania, mert az egyetlen lehetőséggel rendekező oldalakat a rendszer átugorja. Amikor a **Környezeti paraméterek** nézetben van, erősítse meg, hogy a **Dynamics 365 Commerce – bemutató (10.0.* x* a Platform update *xx* frissítéssel)** szöveg közvetlenül a **Környezet neve** mező felett jelenik meg. További részletekért lásd a 8. lépés után megjelenő ábrát.

1. Válassza a felső menü **Felhőalapú környezetek** pontját.
1. Környezet hozzáadásához kattintson a **+ hozzáadás** gombra.
1. Válassza ki az **Alkalmazás verziószáma** mezőben a legfrissebb verziót. Ha a legfrissebb verziótól különböző verziót kell kijelölni, akkor ne válasszon **10.0.14** előtti verziót.
1. A **Platform verziószáma** mezőben használja a kiválasztott alkalmazás verziójának automatikusan kiválasztott platform verzióját. 

    ![Válassza ki az alkalmazás- és a platformverziókat.](./media/project1.png)

1. Válassza ki **Következő** lehetőséget.
1. **Demó** kiválasztása környezeti topológiaként.

    ![1. környezeti topológia kiválasztása.](./media/project2.png)

1. A **Környezet telepítése** oldalán adja meg a környezet nevét. A Speciális beállításokat ne módosítsa.

    ![Környezet telepítése oldal.](./media/project4.png)

1. Szükség szerint állítsa be a virtuális gép méretét. (A következő virtuálisgép-raktározási egységet javasoljuk: \[SKU\] **D13 v2**.)
1. Tekintse át az árképzési és licencelési feltételeket, majd jelölje be a jelölőnégyzetet annak jelzésére, hogy elfogadja azokat.
1. Válassza ki **Következő** lehetőséget.
1. A telepítési visszaigazolás oldalán győződjön meg róla, hogy az adatok helyesek, majd kattintson a **Telepítés** gombra. Vissza fog térni a **Felhőalapú környezetek** nézethez, és a környezetnek meg kell jelennie a listán.

    A kért környezet várólistán jelenik meg, majd telepíthető. A környezeti munkafolyamatok némi időt fognak igénybe venni. Ezért nézzen vissza körülbelül 6–9 óra múlva.

1. A folytatás előtt győződjön meg arról, hogy a környezet állapota **Telepített**.

### <a name="initialize-the-commerce-scale-unit-cloud"></a>A Commerce Scale Unit (felhő) inicializálása

A CSU-cím inicializálásához kövesse az alábbi lépéseket.

1. A **felhőalapú környezetek** nézetben válassza ki a saját környezetét a listából.
1. Kattintson a jobb oldalon található környezeti nézet **Minden részlet** elemére. Megjelenik a környezeti részletek nézet.
1. A **Környezeti funkciók** területen kattintson a **Kezelés** elemre.
1. A **Commerce** lapon válassza az **Inicializálás** parancsot. Megjelenik a CSU inicializálási paraméterei nézet.
1. A **Régió** mezőben válassza ki azt a régiót, amely ugyanazon vagy azon a területen vagy annak közelében van, amelybe a környezetet telepítették.
1. Hagyja a **Verzió** mező értékét változatlanul.
1. Válassza az **Inicializálás** elemet.
1. A telepítési visszaigazolás oldalán győződjön meg róla, hogy az adatok helyesek, majd kattintson az **Igen** gombra. Újra megjelenik a **Commerce Management** nézet, amelyen a **Commerce** lap ki van választva. A CSU várólistára került a létesítéshez.
1. A folytatás előtt győződjön meg arról, hogy az CSU állapota **Sikeres**. Az inicializálás körülbelül két-öt órát vesz igénybe.

Ha nem találja a **Kezelés** hivatkozást a környezet részletei nézetben, kérjen segítséget a Microsoft kapcsolattartótól.

A következő hibaüzenet jelenhet meg a rendszerbe állítási folyamat során:

> A kiértékelési (demó-/teszt-) környezetekben regisztrálni kell a skálázásiegység-csatlakoztató alkalmazást \<application ID\> a központi felületen.

Ha a CSU inicializálása sikertelen, és megjelenik ez a hibaüzenet, jegyezze fel az alkalmazásazonosítót, amely globálisan egyedi azonosító (GUID), majd hajtsa végre a következő szakaszban található lépéseket a CSU telepítési alkalmazásnak a Commerce központi felületén való regisztrálásához.

### <a name="register-the-csu-deployment-application-in-commerce-headquarters-if-required"></a>Regisztrálja a CSU telepítési alkalmazást a Commerce központi felületén (ha szükséges)

A CSU telepítési alkalmazás Commerce központi felületén történő regisztrációjához kövesse az alábbi lépéseket.

1. A Commerce központi felületén lépjen a **Rendszerfelügyelet \> Beállítás \> Azure Active Directory-alkalmazások** lehetőségre.
1. Az **Ügyfélazonosító** oszlopban adja meg a CSU inicializálásakor kapott hibaüzenet alkalmazásazonosítóját.
1. A **Név** oszlopban adjon meg egy leíró szöveget (például **CSU Eval**).
1. A **Felhasználói azonosító** oszlopba írja be a **RetailServiceAccount** szöveget.
1. Próbálja meg újra a CSU inicializálását és telepítését az LCS-ről.

### <a name="initialize-e-commerce"></a>Az elektronikus kereskedelem inicializálása

Az e-kereskedelem inicializálásához kövesse az alábbi lépéseket.

1. Az **e-kereskedelem** lapon tekintse át az értékelési verzió jóváhagyását, majd válassza a **Beállítás** lehetőséget.
1. Az **E-kereskedelmi környezet neve** mezőben adjon meg egy nevet. Fontos megjegyezni, hogy ez a név az e-kereskedelem példányra mutató néhány URL-címen látható lesz.
1. A **Commerce Scale Unit neve** mezőben válassza ki az CSU-t a listából. (A listában csak egy opciónak kell lennie.)

    Az **e-commerce földrajz** mező automatikusan be van állítva.

1. A folytatáshoz kattintson a **Tovább** gombra.
1. A **Támogatott állomásnevek** mezőbe írjon be egy tetszőleges érvényes tartományt, például `www.fabrikam.com`.
1. Írja be a használni kívánt biztonsági csoport nevének első néhány betűjét az **AAD biztonsági csoportja rendszergazdának** mezőbe, majd válassza ki a nagyító szimbólumot a keresési eredmények megtekintéséhez. Válassza ki a megfelelő biztonsági csoportot a listából.
1.  Írja be a használni kívánt biztonsági csoport nevének első néhány betűjét az **AAD biztonsági csoport minősítési és értékelési moderátornak** mezőbe, majd válassza ki a nagyító szimbólumot a keresési eredmények megtekintéséhez. Válassza ki a megfelelő biztonsági csoportot a listából.
1. Hagyja az **Értékelések és vélemények szolgáltatás engedélyezése** beállítást **Igen** értéken.
1. Válassza az **Inicializálás** elemet. Újra megjelenik a **Commerce Management** nézet, amelyen a **e-kereskedelem** lap ki van választva. Az e-kereskedelem inicializálása elindult.
1. A folytatás előtt várja meg, amíg az e-kereskedelem inicializálási állapota **Az inicializálás sikerült** állapotra nem vált.
1. A jobb alsó sarokban található **Hivatkozások** részben jegyezze fel a következő hivatkozások URL-címeit:

    * **e-kereskedelmi webhely** -Az e-kereskedelmi webhely gyökerére mutató hivatkozás.
    * **e-kereskedelmi webhelykészítő** - A webhelykezelési eszközre mutató eszköz.

## <a name="next-steps"></a>További lépések

A Kereskedelem értékelési környezetének létesítési és konfigurálási folyamatának folytatásához lásd: [Kereskedelem értékelési környezetének konfigurálása](cpe-post-provisioning.md).

## <a name="additional-resources"></a>További erőforrások

[Dynamics 365 Commerce értékelési környezet áttekintése](cpe-overview.md)

[Dynamics 365 Commerce értékelési környezet konfigurálása](cpe-post-provisioning.md)

[BOPIS konfigurálása Dynamics 365 Commerce értékelési környezetben](cpe-bopis.md)

[Dynamics 365 Commerce értékelési környezet választható funkcióinak konfigurálása](cpe-optional-features.md)

[Dynamics 365 Commerce értékelési környezet GYIK](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Commerce Scale Unit (felhő)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Microsoft Azure-portál](https://azure.microsoft.com/features/azure-portal)

[Dynamics 365 Commerce-webhely](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]