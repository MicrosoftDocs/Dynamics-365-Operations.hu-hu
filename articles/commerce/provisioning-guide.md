---
title: E-commerce értékelési környezet konfigurálása
description: Ez az útmutató lépésről lépésre bemutatja a Microsoft Dynamics 365 Commerce előzetes környezet létesítését és konfigurálását.
author: v-chgri
manager: annbe
ms.date: 10/15/2019
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b0dce2796e69cd8dee87cba176a521c26c81eb1a
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771680"
---
# <a name="configure-an-e-commerce-evaluation-environment"></a>E-commerce értékelési környezet konfigurálása

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez az útmutató lépésről lépésre bemutatja a Microsoft Dynamics 365 Commerce előzetes környezet létesítését és konfigurálását. A Kezdés előtt ajánljuk, hogy a dokumentációt legalább fussa át, hogy áttekintést kapjon arról, hogy mire tér ki a folyamat, illetve, hogy mit tartalmaz az útmutató.

*Megjegyzés: Ha még nem kapott hozzáférést a Microsoft Dynamics 365 Commerce előzeteséhez, a [Commerce webhelyről](https://aka.ms/Dynamics365CommerceWebsite) kérhet előzetes hozzáférést.*

## <a name="summary"></a>Összegzés
A környezet sikeres kiépítése érdekében a projektet egy konkrét terméknévvel és típussal kell létrehozni. A környezet és a Retail Cloud Scale Unit szintén rendelkezik bizonyos paraméterekkel, amelyek később szükségesek az e-kereskedelem kiépítéséhez- Az útmutatóban szereplő utasítások tartalmazzák a szükséges lépéseket és a használandó paramétereket.

A sikeres kiépítés után néhány, az előzetes környezet előkészítéséhez a kiépítést követő lépést meg kell tennie. Bizonyos lépések nem kötelezők, attól függően, hogy milyen szempontokból szeretné értékelni a rendszert. Ha később meggondolja magát, bármikor futtathatja a választható lépéseket később is.

Ha kérdései vannak a létesítés lépéseivel kapcsolatban, vagy bármilyen probléma merülne fel, akkor tudassa velünk [a Microsoft Dynamics 365 Commerce előzetes Yammer csoportjában.](https://aka.ms/Dynamics365CommercePreviewYammer) 

## <a name="prerequisites"></a>Előfeltételek
A következő előfeltételek szükségesek a Dynamics 365 előzetes környezet létesítéséhez:
* Elérhetővé teszi az **Lifecycle Services portál (LCS)** elérését
* Ön **felvételt nyert a Dynamics 365 Commerce előzetes programba**
* Rendelkezik a szükséges jogosultságokkal projekt létrehozásához a **Lehetséges előértékesítések**vagy a **Áttelepítés, megoldások létrehozása és tanulás** funkciókhoz
* Ön tagja a **Környezetkezelő** vagy **Projekttulajdonos** szerepkörének abban a projektben, amelyben a környezet létesítése történik.
* Rendszergazdai hozzáféréssel rendelkezik a Azure-előfizetéshez, vagy felveheti a kapcsolatot egy előfizetési adminisztrátorral, aki elvégezheti a két lépést, amelyek az Ön nevében rendszergazdaui jogosultságot igényelnek.
* Rendelkezésére áll **AAD bérlői azonosító**
* Létrehozott egy **AAD biztonsági csoportot**, amelyet az **e-kereskedelmi rendszeradminisztrátori csoportként** használhat, és a rendelkezésére áll annak azonosítója
* Létrehozott egy **AAD biztonsági csoportot**, amely **Minősítési és értékelési moderátori csoportként** használatos, és rendelkezésére áll az azonosítója (a fenti rendszeradminisztrátori csoporttal megegyezhet biztonsági csoportja).
## <a name="provisioning-preview-environment"></a>Létesítési előnézeti környezet
Ezek az útmutatások a Microsoft Dynamics 365 Commerce előzetes környezetének létesítésére vonatkoznak. Miután sikeresen elvégezte ezeket a lépéseket, egy olyan előnézeti környezettel rendelkezik majd, amely készen áll a konfigurálásra. Az itt ismertetett tevékenységek az LCS portálon történnek.

*Ne feledje, hogy az előzetes hozzáférés az előzetesre történ jelentkezésben megadott LCS-fiókhoz és szervezethez van kötve. Ugyanezt a fiókot kell használni a létesítéshez. Ha az előnézeti környezethez különböző LCS-fiókot vagy bérlőt kell használnia, meg kell adnia nekünk a részleteket. A kapcsolattartási adatokkal kapcsolatos további tudnivalókat lásd: „További erőforrások”.*
### <a name="before-starting"></a>Kezdés előtt
##### <a name="grant-access-to-e-commerce-applications"></a>Hozzáférés megadása az e-kereskedelmi alkalmazásokhoz

*Megjegyzés: **A bejelentkező személynek AAD bérlői adminisztrátornak kell lennie**. Ha nem sikerült végrehajtani ezt a lépést, akkor létesítés további lépései meghiúsulnak.*

1. Ehhez a lépéshez szüksége van az **AAD bérlőiazonosítójára**. Engedélyeznie kell az e-kereskedelmi alkalmazásokat a Azure-előfizetéséhez való hozzáféréshez. A legegyszerűbb módszer ennek eléréséhez egy ilyen URL-cím összeállítása:

https://login.windows.net/{AAD_TENANT_ID}/oauth2/authorize?client_id=fbcbf727-cd18-4422-a723-f8274075331a&response_type=code&redirect_uri=https://sb.manage.commerce.dynamics.com/_commerce/Consent&response_mode=query&prompt=admin_consent&state=12345

2. **Ne kattintson közvetlenül az URL-címre**, inkább másolja át, majd illessze be a böngészőbe vagy a szövegszerkesztőbe, majd cserélje le az **\{AAD_TENANT_ID\}** elemet az ÖN **AAD bérlői azonosítójára**, mielőtt megnyitná az URL-címet.
3. Megjelenik a Microsoft AAD bejelentkezési párbeszédpanele, amelyen megerősítheti, hogy az előfizetéshez „Dynamics 365 Commerce (Előzetes)” hozzáférést kíván adni.
4. A rendszer egy olyan oldalra fogja küldeni, amely megerősíti, hogy a művelet sikeres volt-e.

##### <a name="log-in-to-the-lcs"></a>Bejelentkezés az LCS-be
1. Bejelentkezés az LCS-portálra: https://lcs.dynamics.com
1. Győződjön meg róla, hogy ugyanazon a LCS-fiókkal van bejelentkezve, amellyel az előzeteshez hozzáférést igényelt.
##### <a name="confirm-that-preview-features-are-available-and-enabled"></a>Ellenőrizze, hogy elérhetők-e az előnézeti szolgáltatások és engedélyezve vannak-e.
1. A LCS főoldalán görgessen teljesen jobbra, majd kattintson az **Előzetes funkció kezelése** csempére.
1. Görgessen le a „SAJÁT ELŐNÉZETI SZOLGÁLTATÁSOK" elemre, és győződjön meg arról, hogy a következő szolgáltatások elérhetők és engedélyezettek:
    1. **Elektronikus kereskedelem értékelése**
    1. **Kereskedelem előnézeti környezetei**
1. Ha nem látja ezeket a szolgáltatásokat a listán, forduljon hozzánk a munkahelyi e-mail-címével, a LCS-fiókjával és bérlői adataival. További tájékoztatásért a kapcsolatfelvétellel kapcsolatosan tekintse meg lejjebb a **További források** részt:

![Előzetes funkció kezelése csempe](./media/preview1.png)

![Előzetes funkciók](./media/preview2.png)
### <a name="create-project"></a>Projekt létrehozása
##### <a name="creating-new-project"></a>Új projekt létrehozása
1. Új projekt létrehozásához kattintson a **+** gombra.
1. Ha Ön partner, válassza az **Áttelepítés, megoldások létrehozása és tanulás** lehetőséget.
1. Ha Ön vevő, válassza ki **Lehetséges előértékesítések** lehetőséget.
1. Adjon meg egy nevet, leírást és iparágat, ahogy az megfelelő.
1. A **Terméknév** helyen válassza a **Dynamics 365 Retail** elemet.
1. A **Termékverzió** helyen válassza a **Dynamics 365 Retail** elemet.
1. A **Módszertan**esetében válassza a **Dynamics Retail-implementáció módszertana** lehetőséget.
1. Ha szükséges, akkor egy meglévő projektből is importálhat szerepköröket és felhasználókat.
1. Kattintson az **Új** > lehetőségre.
1. A rendszer elküldi a projekt nézetbe.
##### <a name="add-azure-connector"></a>Azure-összekötő hozzáadása
1. Ha Ön partner, kattintson az eszközök csempéken a **Projekt beállításai** pontra a jobb szélen.
1. Ha Ön vevő, válassza a felső menü **Projekt beállításai** elemét.
1. Válassza ki az **Azure-összekötőket**.
1. Kattintson a **+ hozzáadás** elemre Azure-csatlakozó hozzáadásához.
1. Adjon meg egy nevet.
1. Adja meg **Azure-előfizetésének azonosítóját**.
1. Engedélyezze a **Konfigurálás Azure Resource Manager (ARM) használatához** lehetőséget.
1. Ellenőrizze, hogy az **Azure-előfizetés AAD-bérlőjének tartománya (vagy azonosítója)** helyes. Szükség esetén forduljon a Azure előfizetés adminisztrátorához.
1. Kattintson a **Tovább** gombra.
1. Kövesse a képernyőn megjelenő utasításokat, és adjon hozzáférést a szükséges alkalmazásnak/alkalmazásoknak az előfizetéshez. Szükség esetén forduljon a Azure előfizetés adminisztrátorához:
    1. Bejelentkezés az Azure-portálra: https://portal.azure.com/
    1. Győződjön meg arról, hogy a megfelelő könyvtár ki van választva.
    1. Kattintson a bal oldali menü **Előfizetések** pontjára.
    1. Keresse meg a megfelelő előfizetést a listában, majd válassza ki azt. Szükség esetén használja a keresést.
    1. Válassza az **Elérés szabályozása (IAM)** elemet a menüből.
    1. A jobb oldalon található **Szerepkör-hozzárendelés** hozzáadása területen kattintson a **Hozzáadás** gombra. Megjelenik **Szerepkör hozzárendelése** ablaktábla.
    1. A **Szerepkör**területen válassza a **Közreműködő**elemet.
    1. A **Hozzáférés hozzárendelése** elemnél hagyja meg az **Azure AD felhasználó, csoport vagy szolgáltatásnév** értéket.
    1. A **Kijelölés** alatt adja meg a **b96b7e94-b82e-4e71-99a0-cf7fb188acea** értéket.
    1. Válassza ki a **Dynamics telepítési szolgáltatások [wsfed-enabled]** elemet a listáról.
    1. Kattintson a **Mentés** gombra.
1. Kattintson a **Tovább** gombra.
1. Kövesse a képernyőn megjelenő utasításokat, és adjon hozzáférést a szükséges alkalmazásnak/alkalmazásoknak az előfizetéshez. Szükség esetén forduljon a Azure előfizetés adminisztrátorához.
1. Kattintson a **Tovább** gombra.
1. A **Azure régió** helyen válassza az **Egyesült Államok keleti része**, **Egyesült Államok kelti része 2**, **Egyesült Államok nyugati része** vagy **Egyesült Államok nyugati része 2** lehetőséget.
1. Kattintson a **Kapcsolódás** lehetőségre.
1. Az Azure-összekötőnek meg kell jelennie a listában.
### <a name="import-extension"></a>Bővítmény importálása
1. A képernyő felső részén levő projekt nevére kattintva térjen vissza a projekt főoldalára.
1. Ha Ön partner, kattintson az eszközök csempéken az **Eszközkönyvtár** pontra a jobb szélen.
1. Ha Ön vevő, válassza a felső menü **Eszközkönyvtár** elemét.
1. Válassza a **Telepíthető szoftvercsomag** elemet a bal oldali listából.
1. A Művelet panelen kattintson az **IMPORTÁLÁS** gombra.
1. Válassza ki a **Commerce előzetes demó alapbővítmény** lehetőséget az eszközök listájából **KÖZÖS ESZKÖZÖK KÖNYVTÁRÁBAN**.
1. Kattintson a **Kitárolás** elemre.
1. A program visszairányítja az Eszközök könyvtárába, és a listában megjelenik a bővítmény.

![Projekt létrehozása – verziók](./media/import.png)
### <a name="deploy-environment"></a>Környezet telepítése

*Megjegyzés: Elképzelhető, hogy a 6, 7 és/vagy 8 lépés nem jelenik meg, mivel az egyetlen beállítást kínáló képernyők kimaradnak. A **Környezet paraméterei** nézetnél erősítse meg, hogy a „Dynamics 365 Commerce (Preview)- Demo (10.0.6 30-as platformfrissítéssel)” szöveg van közvetlenül a **Környezet neve** mező felett. Lásd a lenti képernyőképet.*

1. Válassza a felső menü **Felhőalapú környezetek**pontját.
1. Környezet hozzáadásához kattintson a **+ hozzáadás** gombra.
1. **Alkalmazásverziónak** válassza a **10.0.6** értéket.
1. A **Platformverzióhoz** válassza a **30-as platformfrissítés** lehetőséget.
1. Kattintson a **Tovább** gombra.
1. A környezeti topológiánál válassza a **DEMO** lehetőséget.
1. A környezeti topológia esetében válassza a **Dynamics 365 Commerce (előzetes) - demo** lehetőséget.
1. Ha korábban egyetlen Azure-csatlakozót állított be, akkor ez lesz a környezethez használva. Ha több Azure-csatlakozót állított be, akkor lehetősége van kiválasztani, hogy melyik csatlakozót szeretné használni: **Egyesült Államok keleti része**, **Egyesült Államok keleti része 2**, **Egyesült Államok nyugati része** vagy **Egyesült Államok nyugati része 2**.
1. Adjon meg **Környezetnevet**.
1. Állítsa be a VM-méretet úgy, ahogyan az megfelelő. (A VM SKU **D13 v2** értéket javasoljuk.)
1. A **Speciális beállításokat** ne módosítsa.
1. A képernyőn megjelenő árazási és licencelési feltételek áttekintését követően jelölje be a jelölőnégyzetet, ha meg szeretné jeleníteni a megállapodást.
1. Kattintson a **Tovább** gombra.
1. A telepítési visszaigazolás képernyőjén, miután meggyőződött róla, hogy az adatok helyesek, kattintsona **Telepítés** gombra.
1. Vissza fog térni a **Felhőalapú környezetek** nézethez, és a környezetnek meg kell jelennie a listán.
1. A kért környezet várólistán jelenik meg, majd telepíthető. A munkafolyamatok befejezése egy kis időt vesz igénybe, ezért térjen vissza néhány óra múlva (kb. 6–9 óra).
1. A folytatás előtt győződjön meg arról, hogy a környezet állapota **Telepített**.

![Projekt létrehozása – verziók](./media/project1.png)

![Projekt létrehozása – 1 topológia](./media/project2.png)

![Projekt létrehozása – 2 topológia](./media/project3.png)

![Projekt létrehozása – környezeti paraméterek](./media/project4.png)
### <a name="initialize-rcsu"></a>RCSU inicializálása
1. A **felhőalapú környezetek** nézetben válassza ki a saját környezetét a listából.
1. A képernyő jobb oldalán található környezeti nézetből kattintson az **Összes részlet**lehetőségre. Megjelenik a környezeti részletek nézet.
1. A **KÖRNYEZETI SZOLGÁLTATÁSOK**területen kattintson a**Kezelés** elemre.
1. Kattintson a **Kiskereskedelem** lap **Inicializálás** elemére . Megjelenik a RCSU inicializálási paraméterei nézet.
1. A **RÉGIÓ** helyen válassza az **Egyesült Államok keleti része**, **Egyesült Államok kelti része 2**, **Egyesült Államok nyugati része** vagy **Egyesült Államok nyugati része 2** lehetőséget.
1. A **VERZIÓ**esetében először válassza ki a legördülő listából a **Verzió meghatározása**, majd adja meg a **9.16.19262.5** értéket az alatta megjelenő szövegmezőben. *Megjegyzés: Ügyeljen arra, hogy az itt feltüntetett **pontos verziót határozza meg**, hogy ne kelljen később az RCSU-t a megfelelő verzióra frissíteni.*
1. Engedélyezze a **Bővítmény alkalmazása** lehetőséget.
1. A bővítmények listájából válassza a **Commerce előzetes demó alapbővítmény** lehetőséget.
1. Kattintson az **Inicializálás** lehetőségre.
1. A telepítési visszaigazolás képernyőjén, miután meggyőződött róla, hogy az adatok helyesek, kattintson az **Igen** gombra.
1. A program visszaküldi a **Kiskereskedelem kezelése** nézetbe. úgy, hogy a **Kiskereskedelem** lap van aktiválva. A RCSU várólistára került a létesítéshez.
1. A továbblépés előtt várja meg, amíg az RSCU állapota **SIKERES** nem lesz, mielőtt folytatná (ez körülbelül 2–5 órát vesz igénybe).
### <a name="initialize-e-commerce"></a>Az elektronikus kereskedelem inicializálása
1. Váltsoon az **E-kereskedelem (Előnézet)** lapra.
1. Az előnézeti beleegyezés megtekintése után kattintson a **Beállítás**gombra.
1. Az **E-kereskedelmi bérlőnek** adjon meg egy nevet. Azonban fontos megjegyezni, hogy ez az e-kereskedelem példányra mutató néhány URL-címen látható lesz.
1. A **Retail Cloud Scale Unit neve** esetében válassza ki az RCSU-t a listáról (a lista csak egy lehetőséget kell tartalmazzon).
1. Az **Elektronikus kereskedelem földrajzi adatai** automatikusan kitöltődnek, és nem módosítható.
1. A folytatáshoz kattintson a **Tovább** gombra.
1. A **Támogatott állomásnevek**esetében adjon meg egy érvényes tartományt (például www.fabrikam.com).
1. Az **AAD biztonsági csoport a rendszer adminisztrátorának** helyen adja meg az AAD SG azonosítót, amelyet az e-kereskedelmi rendszer adminisztrátori csoportjához szeretne használni.
1. Az **AAD biztonsági csoport minősítésekhez és felülvizsgálathoz moderátor**számára adja meg az AAD SG azonosítót, amelyet minősítési vagy értékelési moderátori csoportként szeretne használni.
1. Hagyja üresen a **B2C** értékeket (7 mező, amelyek B2C-rel kezdődnek).
1. Hagyja az **Értékelési és minősítési szolgáltatás** elemet bekapcsolva.
1. Kattintson az **Inicializálás** lehetőségre.
1. A program visszaküldi a **Kiskereskedelem kezelése** nézetbe, úgy, hogy az **E-kereskedelem (előzetes)** lap van aktiválva. Az e-kereskedelem inicializálása elindult.
1. A folytatás előtt várja meg, amíg az e-kereskedelem inicializálási állapota **SIKERES INICIALIZÁLÁSRA**nem vált.
1. A jobb alsó sarokban látható **HIVATKOZÁSOK** területen.
    * Jegyezze fel az **e- kereskedelmi webhely** hivatkozását. Ez a C2-oldal gyökeréhez vezető hivatkozás.
    * Jegyezze fel az **e- kereskedelmi webhely felügyeleti eszköze** hivatkozását. Ez az oldalkezelő eszközre mutató hivatkozás (C1- authoring eszköz).
## <a name="post-provisioning-steps"></a>Létesítés utáni lépések
Ebben a stádiumban a környezet végponttól végpontig ki van építve, de még mindig vannak olyan konfigurációs lépések, amelyeket a környezet kipróbálásának elkezdése előtt el kell végezni.
### <a name="before-starting"></a>Kezdés előtt
1. Válassza a felső menü **Felhőalapú környezetek**pontját.
1. A listából válassza ki a környezetét.
1. Kattintson a jobb oldalon található környezeti információk **Minden részlet** elemére.
1. Kattintson a **Bejelentkezés** gombra a menü megnyitásához , majd válassza a **Bejelentkezés a környezetbe** parancsot.

Győződjön meg róla , hogy az **USRT** jogi személy van kiválasztva (jobb felső sarok).

### <a name="configure-pos"></a>POS beállítása
##### <a name="associate-worker-with-your-identity"></a>Dolgozó társítása az Ön identitásához
1. A bal oldalon található menü használatával nyissa meg a **Modulok > Kereskedelem > Alkalmazottak > Dolgozók** lehetőséget.
1. Keresse meg és jelölje ki a következő rekordot a listán: **000713 - Andrew Collette**.
1. A Művelet panelen kattintson a **Kiskereskedelem** elemre.
1. Kattintson a **Létező identitás társítása** lehetőségre.
1. Írja be az e-mail címét az **E-mail** mezőbe (a **Keresés e-mailt használatával** lehetőségtől jobbra).
1. Kattintson a **Keresés** gombra.
1. Válassza ki a rekordot a saját nevével.
1. Kattintson az **OK** gombra.
1. Kattintson a **Mentés** gombra.
##### <a name="activate-cloud-pos"></a>Felhőalapú pénztár aktiválása
1. Jelentkezzen be az LCS-portálra.
1. Navigáljon a projektjéhez.
1. Válassza a felső menü **Felhőalapú környezetek**pontját.
1. A listából válassza ki a környezetét.
1. Kattintson a jobb oldalon található környezeti információk **Minden részlet** elemére.
1. Kattintson a **Bejelentkezés** lehetőségre a menü megnyitásához, válassza a **Bejelentkezés a pénztári felhőbe** lehetőségre, ekkor a pénzár betöltődik.
1. Kattintson a **Tovább** gombra.
1. Jelentkezzen be AAD-fiókjával.
1. Az **Üzlet neve** területen válassza a **SanFrancisco** lehetőséget.
1. Kattintson a **Tovább** gombra.
1. A **Pénztár és eszköz** területen válassza a **SANFRAN-1** lehetőséget.
1. Kattintson az **Aktiválás** gombra.
1. Ekkor a rendszer ki kell jelentkeztesse, és a pénztár bejelentkezési képernyőjére kerül.
1. Most bejelentkezhet a Felhő pénztár élménybe, a **000713** kezelői azonosítóval és az **123** jelszóval.
### <a name="site-setup"></a>Hely beállítása
1. Jelentkezzen be a **helykezelő eszközbe** a korábban feljegyzett URL-cím használatával.
1. A hely beállítási párbeszédpanelének megnyitásához kattintson a **Gyár** helyre.
1. A tartományhoz válassza ki azt a tartományt, amelyet korábban megadott az e-kereskedelem inicializálásához.
1. Az alapértelmezett csatornához válassza ki a **Fabrikam bővített online áruház** lehetőséget. *Megjegyzés: Győződjön meg arról, hogy a **kiterjesztett** online áruházat választja*
1. Alapértelmezett nyelvnek válassza az **en-us**elemet.
1. Az **Elérési út** lehetőséget hagyja változatlanul.
1. Kattintson az **OK** gombra.
1. Ekkor el lesz küldve Önnek a webhely lapjainak listája.
### <a name="enable-jobs"></a>Munkák engedélyezése
1. Jelentkezzen be a környezetbe (HQ).
1. A bal oldali menü használatával nyissa meg a **Kereskedelem > Lekérdezések és jelentések > Kötegelt feladatok** lehetőséget.
1. Végezze el az alábbi lépéseket az egyes munkákhoz az alábbi listában:
    * **Kiskereskedelmi rendelés e-mail értesítésének feldolgozása**.
    * **Termék elérhetősége**.
    * **P-0001**.
    * **Rendelésfeladatok szinkronizálása**.
1. A Gyorsszűrő használatával kereshet a feladatra annak neve használatával (fent felsorolva).
1. Ha a feladat állapota **Visszatartás**, hajtsa végre a következő lépéseket:
    1. Válassza ki a rekordot.
    1. Nyissa meg a műveleti ablaktáblában a **Kötegelt feladat** menüszalagot,majd kattintson az **Állapot módosítása** hivatkozásra .
    1. Válassza a **Várakozás** lehetőséget, majd kattintson az **OK** gombra.
### <a name="run-full-data-sync"></a>Teljes adatszinkronizálás futtatása
1. A bal oldali menü használatával nyissa meg a **Modulok > Kereskedelem > Központ beállítása > Kiskereskedelmi ütemezés > Csatornaadatbázis**.
1. Az **Alapértelmezett** csatorna a bal oldali listából van kiválasztva. *Válassza ki a másik elérhető csatornát (az **scXXXXXXXXX** nevűt)*.
1. Kattintson **a műveleti ablak** teljes adatszinkronizálás elemére.
1. Adja meg **9999** értéket az elosztási ütemezéshez.
1. Kattintson az **OK** gombra.
1. Kattintson az **OK** gombra.
### <a name="after-these-steps-you-are-ready-to-start-evaluating-your-preview-environment"></a>Ezeket a lépéseket követően elindíthatja az előzetes környezet értékelését.
Az **e- kereskedelmi webhely felügyeleti eszköze** URL-címének használatával navigáljon a C1-es szerkesztői élményhez és az **e-kereskedelmi webhely** URL-címére a C2 webhelyélményhez.

## <a name="additional-resources"></a>További erőforrások
### <a name="how-to-find-your-aad-tenant-id"></a>Az AAD bérlői azonostíó megkeresése
Az AAD bérlő azonosítója egy GUID, és ehhez a péládához hasonlóan néz ki: **72f988bf-86f1-41af-91ab-2d7cd011db47**
##### <a name="from-azure-portal"></a>Az Azure-portálról
1. Bejelentkezés az Azure-portálra: https://portal.azure.com/
1. Győződjön meg arról, hogy a megfelelő könyvtár ki van választva.
1. Kattintson a bal oldali menü **Azure Active Directory** pontjára.
1. Válassza ki a **Tulajdonságok** elemet a **Kezelés** lehetőség alatt.
1. Az AAD bérlő azonosítója a **Könyvtárazonosító** alatt látható.
##### <a name="from-openid-connect-metadata"></a>Az OpenID Connect metaadatokból
Hozza létre az **OpenID URL-t** ehhez cserélje a **\{YOUR_DOMAIN\}** elemet az Ön tartományára, pl. microsoft.com: https://login.microsoftonline.com/{YOUR_DOMAIN}/.well-known/openid-configuration helyett https://login.microsoftonline.com/microsoft.com/.well-known/openid-configuration lesz

1. Keresse meg az **OpenID URL-címet**, ami tralmazza az Ön tartományát.
1. Az AAD bérlő azonosítója több tulajdonságértékben is látható.
1. Keresse meg az **authorization_endpoint** elemet, és másolja ki a GUID-azonosítót közvetlenül a **login.microsoftonline.com/** elem után.
### <a name="how-to-find-the-id-of-your-aad-security-group"></a>Az AAD biztonsági csoport azonosítójának megkeresése
Az AAD biztosági csoport azonosítója egy GUID, és ehhez a példához hasonlóan néz ki: **436ea7f5-ee6c-40c1-9f08-825c5811066a**

Ez a lépés feltételezi, hogy a felhasználó tagja annak a csoportnak, amelybennek megpróbálja megkeresni az azonosítóját.
1. Navigáljon a Graph-vizsgálóhoz: https://developer.microsoft.com/en-us/graph/graph-explorer#
1. Kattintson a **Bejelentkezés Microsoft-fiókkal** lehetőségre, és jelentkezzen be a hitelesítő adataival.
1. A bejelentkezés után kattintson a bal oldalon látható **több minta megjelenítése** lehetőségre.
1. Engedélyezze a **Csoportokat** a jobb oldali panelen.
1. Válassza ki a jobb oldali ablaktáblát.
1. Kattintson az **összes csoport, amelynek tagja vagyok** lehetőégre.
1. Keresse meg a csoportot a **Válasz előnézete** szövegmezőből.
1. A biztonsági csoport azonosítója a tulajdonság **azonosítója**területen jelenik meg.
### <a name="test-credit-card-information-to-perform-test-purchases"></a>A hitelkártyaadatok tesztelése tesztvásárlások végrehajtásához
Teszttranzakciók végrehajtásához a weboldalon használhatja ezeket a teszt hitelkártyaadatokat:

Kártya száma: 4111-1111-1111-1111, Lejárat: 10/20, CVV: 737

*Megjegyzés: Semmilyen körülmények között ne használjon tényleges hitelkártya-adatokat a teszt oldalon.*
### <a name="useful-links"></a>Hasznos hivetkozások
* [LCS (Lifecycle services)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)
* [RCSU (Retail Cloud Scale Unit)](https://docs.microsoft.com/en-us/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)
* [Microsoft Azure-portál](https://azure.microsoft.com/en-us/features/azure-portal)
* [Dynamics 365 Commerce-webhely](https://aka.ms/Dynamics365CommerceWebsite)
* [Súgóerőforrások: Dynamics 365 Retail](../retail/index.md)
### <a name="microsoft-dynamics-365-commerce-preview-support"></a>Microsoft Dynamics 365 Commerce előzetes támogatása
Ha problémák merülnek fel a létesítés lépéseinek végrehajtása közben, akkor kérjen segítséget [a Microsoft Dynamics 365 Commerce előzetes Yammer-csoportjában](https://aka.ms/Dynamics365CommercePreviewYammer). 

Ha problémák lépnek fel a Yammer-csoport elérésével kapcsolatosan, akkor e-mailben is felveheti velünk a kapcsolatot **Dynamics365Commerce@microsoft.com** címen. Ez az e-mail cím nincs aktívan figyelve, ezért eltarthat egy ideig, amíg választ kap.
***
## <a name="prerequisites-for-optional-features"></a>Az opcionális szolgáltatások előfeltételei
Ha ki szeretné próbálni tranzakciós e-mail funkciókat, akkor az alábbi előfeltételeknek kell teljesülniük:
* Rendelkezik egy e-mail kiszolgálóval (SMTP-kiszolgáló), amelyet az Azure előfizetésből lehet használni, létesíti ez előzetes környezetet.
* A kiszolgáló FQDN/IP, SMTP-portszáma és a hitelesítési adatok rendelkezésre állnak.

Ha ki szeretné próbálni a Digitális eszközkezelés funkcióit, különösen az új többcsatornás képek betöltését, akkor a következő előfeltételeknek kell teljesülniük:
* A **CMS-bérlő nevének** is rendelkezésre kell állnia. A név megtalálásához szükséges utasítások alább találhatók.
### <a name="configure-image-backend-optional"></a>Képháttér konfigurálása (nem kötelező)
##### <a name="finding-your-media-base-url"></a>A média alap URL-címének megkeresése
*Megjegyzés: Ezt a lépést csak akkor tudja végrehajtani, ha befejezte az **Oldalbeállítást**.*
1. Jelentkezzen be a helykezelő eszközbe a korábban feljegyzett URL-cím használatával.
1. Nyissa meg a **Gyár** webhelyet.
1. Válassz a bal oldali menü **Eszközök** pontját.
1. Válasszon ki egyetlen képeszközt.
1. Keresse meg a **Nyilvános URL-címet** a jobb oldali tulajdonságviszgálóból. Található benne egy URL-cím.
    * Példa URL-cím: https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC
1. A következő karakterlánccal cserélje le az URL-címben szereplő utolsó azonosítót (a fenti példa URL-ben MA1nQC) a következő karakterlánccal: **search?fileName=**
    * Példa az URL-címre a helyettesítés után: https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=
    * Ez a **Media-alapú URL-címe** – jegyezze fel.
##### <a name="updating-the-media-base-url"></a>A média alap URL-cím frissítése
1. Jelentkezzen be a környezetbe (HQ).
1. A bal oldali menü használatával nyissa meg a **Modulok > Kereskedelem > Csatorna beállítása > Csatornaprofilok** lehetőséget.
1. Kattintson a **Szerkesztés** lehetőségre.
1. A **Profil tulajdonságainál** cserélje le a **Médiakiszolgáláó alap URL-címe** értéket a korábban létrehozott **Média alap URL-címre**.
1. Válassza ki a másik csatornát a bal oldali listából az **Alapértelmezett** csatornánál.
1. A **Profil tulajdonságai** területen kattintson a **+hozzáadás** gombra.
1. A hozzáadott tulajdonsághoz válassza ki a **Média-kiszolgáló alap URL-címe** lehetőséget tulajdonságkulcsként vagy tulajdonságértékként adja meg a korábban létrehozott **Média alap URL-címet**.
1. Kattintson a **Mentés** gombra.

### <a name="configure-email-server-optional"></a>E-mail-kiszolgáló konfigurálása (nem kötelező)
Ne feledje, hogy az itt megadott SMTP-kiszolgálónak vagy e-mail szolgáltatásnak elérhetőnek kell lennie a környezethez használt Azure-előfizetésből.
1. Jelentkezzen be a környezetbe (HQ).
1. A bal oldali menü használatával nyissa meg a **Modulok > Kereskedelem > Központ beállítása > Paraméterek > E-mail-paraméterek**.
1. Kattintson az **SMTP-beállítások** lapra.
1. Írja be az SMTP-kiszolgáló vagy az e-mail szolgáltatás FQDN vagy IP-címét a **Kimenő levelek kiszolgálója** mezőbe.
1. Az **SMTP-portszáma** mezőbe írja be a portszámot (az alapértelmezett érték 25, ha nem használ SSL protokollt).
1. A **Felhasználónév** mezőbe írjon be egy értéket (ha hitelesítés szükséges).
1. A **Jelszó** mezőbe írjon be egy értéket (ha hitelesítés szükséges).
1. Kattintson a **Mentés** gombra.
1. Kattintson a **Frissítés** gombra.
1. Kattintson a **Teszt-e-mail** lapra.
1. Az e-mail szolgáltató mezőben válassza az **SMTP** lehetőséget.
1. A **Címzett** mezőbe írja be azt az e-mail címet, amelyre a teszt e-mailt kézbesíteni kívánja.
1. Kattintson a **Teszt-e-mail küldése** lehetőségre.
### <a name="configure-email-templates-optional"></a>E-mail-sablonok konfigurálása (nem kötelező)
Az e-mail sablont minden olyan tranzakciós eseményhez, amelyre e-maileket szeretne küldeni, frissíteni kell egy érvényes feladói e-mail címmel.
1. A bal oldali menü használatával nyissa meg a **Modulok > Szervezet felügyelete > Beállítás > Szervezeti e-mail-sablonok** elemet.
1. Kattintson a **Lista megjelenítése** elemre.
1. A lista egyes sablonjaihoz:
    1. Írja be az e-mail sablon feladói e-mail címét a **Feladó e-mail címe** mezőjébe.
    1. (Választható) A **Feladó neve** mezőbe írja be azt a nevet, amelyet a rendszer feladóként fog használni ehhez az e-mail sablonhoz.
1. Kattintson a **Mentés** gombra.
### <a name="customizing-email-templates-optional"></a>E-mail-sablonok testreszabása (nem kötelező)
Előfordulhat, hogy testre szeretné szabni az e-mail sablonokat, mert más képeket szeretne használni, vagy frissítnei szeretné a hivatkozásokat a sablonba, hogy azok visszamutassanak az Előnézeti környezetre. A következő lépések leírják, hogyan lehet letölteni az alapértelmezett sablonokat, illetve hogyan szabhatja testre és frissítheti a sablonokat a rendszerben.
1. A böngésző használatával letöltheti [a Microsoft Dynamics 365 Commerce Preview default email templates .zip fájlt](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip), amely a következő HTML-dokumentumokat tartalmazza a számíytógépére.
    1. Rendelés megerősítési sablon
    1. Ajándékutalvány-sablon kiadása
    1. Új rendeléssablon
    1. Csomagrendelési sablon
    1. Kitárolás rendelési sablon
1. A sablonokat a szöveg- vagy HTML-szerkesztő segítségével szabhatja testre. Aláb találja a támogatott tokenek listáját.
1. Jelentkezzen be a környezetbe (HQ).
1. A bal oldali menü használatával nyissa meg a **Modulok > Kereskedelem > Központ beállítása > Paraméterek > Szervezeti e-mail-sablonok**.
1. A bal oldali lista kibontásával megjelenítheti az összes sablont.
1. Hajtsa végre a következő lépéseket a testreszabni kívánt sablonok mindegyikéhez:
    1. Válassza ki a sablont a listából.
    1. Az **E-mail-üzenet tartalma**területen válassza ki a megfelelő nyelvi verziót a listából (az alapértelmezett az **en-us**).
    1. Az **E-mail üzenet tartalma**területen kattintson a **Szerkesztés** lehetőségre, ekkor megnyílik az **E-mail-sablon feltöltése** panel.
    1. Kattintson a **Tallózás** gombra, és keresse meg a testreszabott tartalmat tartalmazó HTML-fájlt.
    1. Kattintson a **Feltöltés** hivatkozásra, a sablon fel lesz töltve a rendszerbe, és megjelenik egy előnézet.
    1. Kattintson az **OK** gombra.
    1. (Opcionális) A sablon **Tárgy** tulajdonságának testreszabása.
    1. Kattintson a **Mentés** gombra.

#### <a name="supported-tokens-in-the-email-template"></a>Az e-mail-sablonban támogatott tokenek
Ezeket a tokeneket az e-mail renderelése során a program lecseréli a a vevőkre és a rendelésre vonatkozó tényleges értékekre.

**Értékesítési rendelés** -a következő tokenek érvényesek a teljes értékesítési rendelésre.

|A token neve|Jogkivonat|
|---|---|
|Rendelés száma|%salesid%|
|Vevő neve|%customername%|
|Szállítási cím|%deliveryaddress%|
|Számlázási cím|%customeraddress%|
|Megrendelési dátum|%shipdate%|
|Kézbesítés módja|%modeofdelivery%|
|Engedmény|%discount%|
|Áfa|%tax%|
|Rendelés végösszege|%total%|

**Értékesítési sor** – A program a következő tokeneket tölti fel a rendelés egyes termékeihez.

*Megjegyzés: a **Terméklista – kezdés** és a **Terméklista – befejezés** tokeneket a minden terméknél ismétlődő HTML-tömb elejére vagy végére helyezze el.*

|A token neve|Jogkivonat|
|---|---|
|Terméklista – kezdés|\<!--%tablebegin.salesline% -->|
|Terméklista – befejezés|\<!--%tableend.salesline%-->|
|Termék neve|%lineproductname%|
|Leírás|%lineproductdescription%|
|Mennyiség|%linequantity%|
|Sor egységára|%lineprice% (verify)|
|sortétel összege|%linenetamount%|
|sorkedvezmény|%linediscount%|
|Szállítási dátum|%lineshipdate%|
|Beszerzési mód|%linedeliverymode%|
|szállítási cím|%linedeliveryaddress%|
|A sor értékesítési egysége|%lineunit%|

