---
title: B2C-bérlő beállítása a Commerce-ben
description: Ez a témakör azt Azure Active Directory ismerteti, hogyan lehet beállítani a felhasználók által használt (Azure AD B2C) bérlőket a felhasználói webhely hitelesítésére Dynamics 365 Commerce.
author: BrianShook
ms.date: 05/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4b1ee8999717d70dfe36baef95921962a1b7be65
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853741"
---
# <a name="set-up-a-b2c-tenant-in-commerce"></a>B2C-bérlő beállítása a Commerce-ben

[!include [banner](includes/banner.md)]

Ez a témakör azt Azure Active Directory ismerteti, hogyan lehet beállítani a felhasználók által használt (Azure AD B2C) bérlőket a felhasználói webhely hitelesítésére Dynamics 365 Commerce.

A Dynamics 365 Commerce az Azure AD B2C protokollt használja a felhasználók hitelesítő adatainak és hitelesítési folyamatainak támogatásához. A felhasználó ezeket a folyamatokat feliratkozhat, bejelentkezhet és alaphelyzetbe állíthatja jelszavát. Az Azure AD B2C érzékeny természetű felhasználói hitelesítési adatokat, például a felhasználónevet és a jelszót tárolja. A B2C-bérlőben a felhasználói rekordja a B2C helyi fiók rekordját vagy a B2C társadalmi identitásszolgáltatói rekordját fogja tárolni. Ezek a B2C rekordoknak a vevői rekordra mutatnak vissza a Commerce környezetben.

> [!WARNING] 
> Az Azure AD B2C megszünteti a régi (örökölt) felhasználói folyamatokat 2021. augusztus 1-jéig. Ezért érdemes megterveznie a felhasználói folyamatai áttelepítését az új, ajánlott verzióba. Az új verzió funkcióparitást és új funkciókat biztosít. A Commerce 10.0.15-ös vagy újabb verziójának modulkönyvtárát az ajánlott B2C felhasználói folyamatokkal kell használni. További információért lásd: [Felhasználói folyamatok az Azure Active Directory B2C-ben](/azure/active-directory-b2c/user-flow-overview).
 
 > [!NOTE]
 > A kereskedelmi értékelési környezetek egy előre betöltött Azure AD B2C bérlővel érkeznek demonstrációs célokra. Az értékelési környezetek esetén nincs szükség saját Azure AD B2C-bérlő betöltésére az alábbi lépésekkel.

> [!TIP]
> A Azure AD azonosítóvédelemmel és a feltételes hozzáféréssel tovább védheti webhelyének felhasználóit, és növelheti a Azure AD B2C bérlőinek biztonságát. A Azure AD B2C Premium P1 és Premium P2 bérlők számára elérhető képességek áttekintéséhez lásd: [Identitásvédelem és feltételes hozzáférés a Azure AD B2C oldalon](/azure/active-directory-b2c/conditional-access-identity-protection-overview).

## <a name="dynamics-environment-prerequisites"></a>Dynamics-környezet előfeltételei

Mielőtt hozzákezd, győződjön meg arról, hogy a Dynamics 365 Commerce-környezet és az e-kereskedelmi csatorna a következő előfeltételeknek megfelelően van konfigurálva.

- Állítsa az **AllowNonymousAccess** pénztári műveletek értékét „1” értékre a Commerce központban:
    1. Ugrás a **POS-műveletekhez**.
    1. A műveleti rácsban kattintson a jobb gombbal, majd válassza a **Testreszabás** parancsot.
    1. Válassza a **Mező hozzáadása** lehetőséget.
    1. Az elérhető oszlopok listájában válassza az **AllowAnonymousAccess** oszlopot a hozzáadáshoz.
    1. Válassza ki a **Frissítés** lehetőséget.
    1. A **612** „Vevő hozzáadása” műveletnél módosítsa az **AllowAnonymousAccess** gombra az „1” lehetőséget.
    1. Futtassa az **1090 (Pénztárgépek)** feladatot.
- Állítsa a vevői számla számsorozatának **Manuális** attribútumát **Nem** értékre a Commerce központban:
    1. Lépjen a **Retail és Commerce \> Központ beállítása \> Paraméterek \> Kinnlevőségi paraméterek** menüpontra.
    1. Válassza a **Számsorozatok** elemet.
    1. A **Vevői számla** sorban kattintson duplán a **Számsorozatkód** értékre.
    1. A számsorozat **Általános** gyorslapján állítsa a **Manuális** beállítást **Nem** értékre.

A Dynamics 365 Commerce környezet telepítését követően ajánlott a [Kiindulási adatok inicializálása](enable-configure-retail-functionality.md) a környezetben.

## <a name="create-or-link-to-an-existing-azure-ad-b2c-tenant-in-the-azure-portal"></a>Meglévő B2C-bérlő Azure AD létrehozása vagy hivatkozása az Azure-portálon

Ez a szakasz a Azure AD B2C-bérlők commerceben való használatra való létrehozásának és kapcsolatának létrehozását foglalja magában. A további tudnivalókat lásd [: Azure Active Directory B2C bérlő létrehozása](/azure/active-directory-b2c/tutorial-create-tenant).

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com/).
1. Válassza az Azure Portal menü **Erőforrás létrehozása** pontját. Ügyeljen arra, hogy a Commerce környezethez kapcsolt előfizetést és könyvtárat használja.

    ![Erőforrás létrehozása az Azure-portálon.](./media/B2CImage_1.png)

1. Nyissa meg az **Identitás \> Azure Active Directory B2C** elemet.
1. A **AAD B2C-bérlő létrehozása vagy hivatkozás egy meglévő bérlőre az Azure Portal webhelyen** lapon, használja vállalat igényeinek leginkább megfelelő alábbi lehetőséget:

    - **Új B2C bérlő létrehozása Azure AD: Ezzel a** Azure AD beállítással új B2C-bérlőt hozhat létre.
        1. Válassza az **Új Azure AD B2C-bérlő létrehozása** lehetőséget.
        1. A **Szervezet neve** területen írja be a szervezet nevét.
        1. A **Kezdeti tartománynév** mezőbe írja be a kezdeti tartománynevet.
        1. Az **Ország vagy régió** helyen válassza ki az országot vagy régiót.
        1. Válassza a **Létrehozás** lehetőséget a bérlő létrehozásához.

     ![Új Azure AD-bérlő létrehozása.](./media/B2CImage_2.png)

     - **Meglévő Azure AD B2C-bérlő csatolása a saját Azure előfizetésemhez**: Akkor használja ezt a lehetőséget, ha már van egy Azure AD B2C bérlője, amelyhez csatolni kívánja.
        1. Válassza ki a **Meglévő Azure AD B2C bérlő csatolása saját Azure előfizetéshez** lehetőséget.
        1. Az **Azure AD B2C bérlő** esetében válassza ki a megfelelő B2C-bérlőt. Ha a kiválasztási mezőben a „Nem jogosult B2C-bérlők találhatók” üzenet jelenik meg, akkor nem rendelkezik jogosult B2C Bérlővel, és újat kell létrehoznia.
        1. Az **Erőforráscsoport** helyen válassza az **Új létrehozása** lehetőséget. Írja be annak a csoportnak a **Nevét**, amely a bérlőt fogja tartalmazni, válassza ki az **Erőforráscsoport helyét** ,majd válassza a **Létrehozás** parancsot.

    ![Válassza ki a Meglévő Azure AD B2C bérlő csatolása saját Azure előfizetéshez lehetőséget.](./media/B2CImage_3.png)

1. Miután létrehozta az új Azure AD B2C könyvtárat (ez néhány percet is igénybe vehet), az új könyvtárra mutató hivatkozás megjelenik az irányítópulton. Ez a link közvetlenül az „Üdvözli az Azure Active Directory B2C” oldalra mutat.

    ![Csatolás az új könyvtárhoz Azure AD](./media/B2CImage_4.png)

> [!NOTE]
> Ha több előfizetése van a Azure-fiókján belül, vagy a B2C-bérlőt egy aktív előfizetés csatolása nélkül állította be, akkor egy **Hibaelhárítási** banner fogja arra kérni hogy a bérlőt egy előfizetéshez kapcsolja. Válassza ki a hibaelhárítási üzenetet, majd kövesse az utasításokat az előfizetési probléma megoldásához.

A következő kép egy Azure AD B2C **Hibaelhárítási** bannert mutat be.

![Figyelmeztetés, amely azt mutatja, hogy könyvtárának nincs aktív előfizetése.](./media/B2CImage_5.png)

## <a name="create-the-b2c-application"></a>A B2C-alkalmazás létrehozása

Miután a B2C bérlő létrejött, egy B2C alkalmazást fog létrehozni az új Azure AD B2C bérlőn belül, hogy a Commerce műveletekkel együttműködjön.

A B2C alkalmazás létrehozásához kövesse az alábbi lépéseket.

1. Az Azure portálon válassza az **Alkalmazásregisztrációk** elemet, majd az **Új regisztráció** lehetőséget.
1. A **Név** mezőbe írja be a Azure AD B2C-alkalmazásnak adni kívánt nevet.
1. A **Támogatott fióktípusok** csoportban válassza a **Fiókok bármely identitásszolgáltatóban vagy szervezeti címtárban (felhasználók hitelesítéséhet a felhasználói folyamatokkal)**.
1. Az **Átirányítási URI** szolgáltatáshoz írja be a dedikált válasz URL-eket **Web** típusúként. A válasz URL-címekkel és a formázásukkal kapcsolatos információkért lásd: [Válasz URL-címek](#reply-urls) részt alább. Meg kell adni egy átirányítási URI-címet/válasz URL-címet Azure AD, amely lehetővé teszi a B2C rendszerből a webhelyre való átirányítást, amikor egy felhasználó hitelesíti magát. A válasz URL-címe hozzáadható a regisztrációs folyamat során, **illetve később is, ha a B2C** **alkalmazás Áttekintés szakaszában az "Átirányítás URI** **hozzáadása**" hivatkozásra kattint.
1. Az **Engedélyek** esetében válassza a **Rendszergazdai hozzájárulás biztosítása az OpenID-hoz és az offline hozzáférési engedélyezkhez** lehetőséget.
1. Válassza a **Regisztrálás** lehetőséget.
1. Válassza ki az újonnan létrehozott alkalmazást, és nyissa meg a Hitelesítés **menüt**. 
1. Ha meg van adva egy válasz URL-címe, **az Implicit támogatás és az áramlási** **folyamat mezőben válassza a Hozzáférési tokenek** **és az azonosítótokenek** lehetőséget az alkalmazás engedélyezéséhez, **majd válassza a Mentés lehetőséget**. Ha a regisztráció során nem lett megadva válasz URL-címe, **akkor ezen a lapon a Platform hozzáadása, a** **Webes** lehetőség kiválasztásával, majd az alkalmazás átirányítási URI-jének beírásával is hozzáadható. Ezt követően **a Implicit támogatás és áramlási** **folyamat szakasz elérhetővé válik a Hozzáférési tokenek és az azonosítótokenek** **beállításának kiválasztásához**.
1. Lépjen az Azure Portal **Áttekintés** menüjébe, és másolja be az **Alkalmazás (ügyfél) azonosítóját**. Jegyezze fel ezt az azonosítót a későbbi beállítási lépésekhez (később **Ügyfél GUID azonosítóként** hivatkoznak rá).

Az Azure AD B2C alkalmazásregisztrációiról további információt az [Azure Active Directory B2C új alkalmazásregisztrációs élménye](/azure/active-directory-b2c/app-registrations-training-guide) részben talál

### <a name="reply-urls"></a>Válasz URL-címek

A válasz URL-címek fontosak, mivel egy engedélyezési listát biztosítanak a visszajövő tartományokhoz, amikor a webhelye meghívja az Azure AD B2C-t a felhasználó hitelesítéséhez. Ez engedélyezi a hitelesített felhasználó visszaküldését abba a tartományba, ahonnan bejelentkeznek (a webhelye tartományába). 

A **Válasz URL** mezőben az **Azure AD B2c – Alkalmazások \> Új alkalmazás** képernyőjén a válasz URL-cím mezőben külön sorokat kell megadni a webhely-tartományához (ha a környezet létesítése megtörtént) és a Commerce által generált URL-címhez. Ezeknek az URL-címnek mindig érvényes URL-formátumot kell használniuk, és csak alap URL-címek lehetnek (nem lehetnek záró perjelek vagy elérési utak). Ezt követően az ``/_msdyn365/authresp`` karakterláncot a következő példáknak megfelelően kell hozzáfűzni az alap URL-címekhez.

- ``https://www.fabrikam.com/_msdyn365/authresp`` (A tartománynak teljesen meg kell egyeznie az e-kereskedelmi tartománnyal. Ha több tartománya van, akkor mindegyik tartományhoz hozzá kell adnia ezt az URL-címet.)
- ``https://fabrikam-prod.commerce.dynamics.com/_msdyn365/authresp``

## <a name="create-user-flow-policies"></a>Felhasználóifolyamat-irányelvek létrehozása

A felhasználói folyamatok a házirendek, amelyeket az Azure AD B2C használ a biztonságos bejelentkezéshez, a profil szerkesztéséhez és elfelejtett jelszó funkcióhoz. A Dynamics 365 Commerce ezeket a folyamatokat a házirendműveletek elvégzéséhez használja az interakcióhoz az Azure AD B2C-bérlővel. Amikor egy felhasználó a fenti házirendekkel interakcióba lép akkor a program átirányítja őket az Azure AD B2C-bérlőre, hogy végrehajtsa a műveleteket.

Az Azure AD B2C három alapvető felhasználói folyamatot kínál:
- Feliratkozás és bejelentkezés
- Profil szerkesztése
- Új jelszó létrehozása

Választhat, hogy a Azure AD B2C által biztosított alapértelmezett felhasználói folyamatokat használja-e, amelyek a Azure AD B2C által tárolt lapot jelenítik meg. Másik megoldásként HTML-lapot is létrehozhat, amellyel szabályozhatja a felhasználói folyamatok megjelenését és érzetét. 

A felhasználói irányelvek oldalainak Dynamics 365 Commerce alkalmazásban létrehozott oldalakkal való testreszabásáról lásd: [Felhasználói bejelentkezéshez használt egyéni lapok beállítása](custom-pages-user-logins.md). További tájékoztatás: [A felhasználói élmények kezelőfelületének testreszabása az Azure Active Directory B2C-ben](/azure/active-directory-b2c/tutorial-customize-ui).

### <a name="create-a-sign-up-and-sign-in-user-flow-policy"></a>Felhasználói folyamatra vonatkozó bejelentkezési irányelv létrehozása

A következő lépések szerint hozzon létre egy bejelentkezési és bejelentkezési felhasználói folyamatra vonatkozó házirendet.

1. Az Azure Portal modul bal oldali navigációs ablakában válassza ki a **Felhasználói folyamatok (házirendek)** elemet.
1. Az **Azure AD B2C – Felhasználói folyamatok (házirendek)** lapon válassza az **Új felhasználói folyamat** elemet.
1. Válassza ki a **Regisztráció és bejelentkezés** irányelvet, majd válassza az **Ajánlott** verziót.
1. A **Név** mezőbe írja be a házirend nevét. Ez a név azután jelenik meg, hogy a portál hozzárendel egy előtagot (például „B2C_1_”).
1. Válassza **az E-mailben** való regisztrációt az **Identitásszolgáltató területen a Helyi** számlák **szakaszban**. A Commerce rendszer leggyakrabban az e-mail hitelesítést használja. Ha a társadalombiztosítási szolgáltató hitelesítését is használja, akkor ezeket is ki lehet választani most.
1. A **Többlépcsős hitelesítés** területen válassza ki a vállalat számára a megfelelő lehetőséget. 
1. A **Felhasználói attribútumok és igények** területen válassza ki az attribútumok gyűjtését vagy igénylések visszaküldését szükség szerint. Válassza a **Több megjelenítése...** lehetőséget az attribútumok és a jogcímbeállítások teljes listájának bemutatja. A Commerce a következő alapértelmezett beállításokat igényli:

    | **Attribútum összegyűjtése** | **Igény visszaküldése** |
    | ---------------------- | ----------------- |
    | E-mail cím          | E-mail-címek   |
    | Utónév             | Utónév        |
    |                        | Identitásszolgáltató |
    | Vezetéknév                | Vezetéknév           |
    |                        | Felhasználó objektumazonosítója  |

1. Válassza a **Létrehozása** lehetőséget.

A következő kép egy példa Azure AD a B2C regisztrációra és a bejelentkezési felhasználói folyamatra.

![A Regisztráció és bejelentkezés irányelv konfigurálása.](./media/B2CImage_11.png)

   
### <a name="create-a-profile-editing-user-flow-policy"></a>Profilszerkesztési felhasználóifolyamat-irányelv létrehozása

Profilszerkesztési felhasználóifolyamat-házirend konfigurálásához kövesse az alábbi lépéseket.

1. Az Azure Portal modul bal oldali navigációs ablakában válassza ki a **Felhasználói folyamatok (házirendek)** elemet.
1. Az **Azure AD B2C – Felhasználói folyamatok (házirendek)** lapon válassza az **Új felhasználói folyamat** elemet.
1. Válassza a **Profilszerkesztés** lehetőséget, majd az **Ajánlott** verziót.
1. A **Név** mezőbe adja meg a profilszerkesztési felhasználói folyamatot. Ez a név azután jelenik meg, hogy a portál hozzárendel egy előtagot (például „B2C_1_”).
1. Az **Identitásszolgáltató** területen a Helyi **számlák** területen válassza az **E-mail bejelentkezési azonosítót**.
1. A **Felhasználói attribútumok** alatt jelölje be az alábbi jelölőnégyzeteket:
    
    | **Attribútum összegyűjtése** | **Igény visszaküldése** |
    | ---------------------- | ----------------- |
    |                        | E-mail-címek   |
    | Utónév             | Utónév        |
    |                        | Identitásszolgáltató |
    | Vezetéknév                | Vezetéknév           |
    |                        | Felhasználó objektumazonosítója  |
    
1. Válassza a **Létrehozása** lehetőséget.

A következő kép egy példát mutat be a Azure AD B2C profilszerkesztő felhasználói folyamatára.

![Példa a Azure AD B2C profil szerkesztésére - felhasználói folyamat](./media/B2CImage_12.png)

### <a name="create-a-password-reset-user-flow-policy"></a>Egy jelszóvisszaállítás felhasználóifolyamat létrehozása

Jelszóvisszaállítás felhasználóifolyamat-házirend konfigurálásához kövesse az alábbi lépéseket.

1. Az Azure Portal modul bal oldali navigációs ablakában válassza ki a **Felhasználói folyamatok (házirendek)** elemet.
1. Az **Azure AD B2C – Felhasználói folyamatok (házirendek)** lapon válassza az **Új felhasználói folyamat** elemet.
1. Válassza az **Új jelszó kérése** lehetőséget, majd az **Ajánlott** verziót.
1. A **Név** mezőben adjon meg egy nevet a jelszóvisszaállítási felhasználói folyamat számára.
1. Az **Identitásszolgáltatók** alatt válassza az **Új jelszó beállítása e-mail-cím használatával** lehetőséget.
1. Válassza a **Létrehozása** lehetőséget.
1. A **Jelentkezési igények** alatt jelölje be az alábbi jelölőnégyzeteket:
    - **E-mail címek**
    - **Utónév**
    - **Vezetéknév**
    - **Felhasználó objektumazonosítója**
1. Válassza a **Létrehozása** lehetőséget.

A következő kép azt jelzi, hogy hol kell beállítani az **Új jelszó beállítása e-mail-cím használatával** funkciót az Azure AD B2C felhasználói folyamatában.

![A „Új jelszó beállítása e-mail-cím használatával” beállítása a Jelszóvisszaállítási-házirendben](./media/B2CImage_13.png)

## <a name="add-social-identity-providers-optional"></a>Közösségi identitásszolgáltatók hozzáadása (nem kötelező)

A közösségi identitásszolgáltatók lehetővé teszik a felhasználók számára a saját közösségi fiókjaik hitelesítéshez történő használatát. A Dynamics 365 Commerce alkalmazásban a közösségi identitásszolgáltató hozzáadása opcionális. 

Ha nincs hozzáadva közösségi identitásszolgáltatón keresztüli hitelesítés, akkor az Azure AD B2C profilok lesznek a felhasználói bázis fő profiljai. A felhasználók kiválasztják a saját felhasználónevüket (az előnyben részesített e-mail címüket), és beállíthatnak egy jelszót. Az Azure AD B2C a felhasználókat közvetlenül hitelesíti. 

Ha a közösségi identitásszolgáltatói hitelesítés hozzá van adva, és a felhasználó a felajánlott közösségi identitásszolgáltatók egyikét választja, akkor is létrejön egy entitás az Azure AD B2C-bérlőn. Az Azure AD B2C ezt követően hitelesíteni fogja a felhasználó hitelesítő adatait a közösségi identitásszolgáltatóval.

> [!NOTE]
> Az identitásszolgáltató egy rekordot hoz létre a B2C-bérlőben, de a helyi fiókoktól eltérő formában, mivel egy külső identitásszolgáltató hivatkozását hívja meg a hitelesítéséhez. A felhasználó ugyanazt az e-mail címet használhatja több közösségi identitásszolgáltató esetében is ami azt jelenti, hogy a hitelesítéshez használt e-mail-felhasználónév nem biztos, hogy egyedi a bérlő számára. Az Azure AD B2C csak azt kényszeríti, hogy a B2C helyi fiókokban rendelkezzenek egyedi e-mail-címmel rendelkeznek.

A közösségi identitásszolgáltató hitelesítéshez történő hozzáadásához el kell látogatnia az identitásportálra és egy identitásszolgáltatói alkalmazást kell beállítania az Azure AD B2C dokumentációja utasításai alapján. A dokumentációra mutató hivatkozások listáját alább találja.

- [Amazon](/azure/active-directory-b2c/active-directory-b2c-setup-amzn-app)
- [Azure AD (egy bérlő)](/azure/active-directory-b2c/active-directory-b2c-setup-oidc-azure-active-directory)
- [Microsoft-fiók](/azure/active-directory-b2c/active-directory-b2c-setup-msa-app)
- [Facebook](/azure/active-directory-b2c/active-directory-b2c-setup-fb-app)
- [GitHub](/azure/active-directory-b2c/active-directory-b2c-setup-github-app)
- [Google](/azure/active-directory-b2c/active-directory-b2c-setup-goog-app)
- [LinkedIn](/azure/active-directory-b2c/active-directory-b2c-setup-li-app)
- [OpenID Connect](/azure/active-directory-b2c/active-directory-b2c-setup-oidc-idp)
- [Twitter](/azure/active-directory-b2c/active-directory-b2c-setup-twitter-app)

### <a name="add-and-set-up-a-social-identity-provider"></a>Közösségi identitásszolgáltató hozzáadása és beállítása

Egy közösségi identitásszolgáltató hozzáadásához és beállításához hajtsa végre az alábbi lépéseket.  

1. Az Azure portálon menjen az **Identitásszolgáltató** részre.
1. Válassza a **Hozzáadás** lehetőséget. Megjelenik az **Identitásszolgáltató** hozzáadása képernyő.
1. A **Név** csoportban adja meg a bejelentkezési képernyőn a felhasználók számára megjelenítendő nevet.
1. Az **Identitásszolgáltatótípusa** területen válasszon ki egy identitásszolgáltatót a listából.
1. Válassza ki az **OK** lehetőséget.
1. Válassza az **Identitásszolgáltató beállítása** lehetőséget, hogy elérje a **Közösségi identitásszolgáltató beállítása** képernyőt.
1. Az **Ügyfélazonosító** területen írja be az ügyfél azonosítóját, amelyet az identitásszolgáltató alkalmazás-beállításaiban kapott.
1. A **Titkos ügyfélkód** területen írja be aza titkos ügyfélkódot, amelyet az identitásszolgáltató alkalmazás-beállításaiban kapott.
1. Felhasználói folyamat csatolása a bejelentkezési/bejelentkezési irányelvekhez:
1. Nyissa meg az **Azure AD B2C – Felhasználói folyamatok (házirendek) \> {az Ön regisztrációs házirendje} \> Identitásszolgáltatók** lehetőséget.
1. A bejelentkezési/bejelentkezési felhasználói folyamat irányelvének csatolásához válassza ki a fiókhoz beállított összes identitásszolgáltatót. Ezek teszteléséhez válassza ki a **Felhasználói folyamat futtatása** lehetőséget az egyes identitásszolgáltatókhoz. Egy új lap a bejelentkezési lapot jeleníti meg, amely az új identitásszolgáltató kiválasztási dobozát jeleníti meg.

A következő képen példákat talál az **Identitásszolgáltató hozzáadása** és az **Identitiásszolgáltató beállítása** képernyőkre az Azure AD B2C-ben.

![Közösségi identitásszolgáltató hozzáadása az alkalmazásához.](./media/B2CImage_14.png)

A következő képen egy példa látható arra, hogyan lehet kiválasztani az identitásszolgáltatót az Azure AD B2C **Identitásszolgáltatók** lapján.

![Válassza ki az egyes közösségi identitásszolgáltatókat, hogy engedélyezze azokat házirendjéhez.](./media/B2CImage_16.png)

A következő kép egy példát mutat be egy alapértelmezett bejelentkezési képernyőre, amely a közösségi identitásszolgáltató bejelentkezési gombját jeleníti meg.

> [!NOTE]
> Ha a Commerce alkalmazásban létrehozott egyéni oldalakat szeretné használni a felhasználói folyamatokhoz, a közösségi identitásszolgáltatók gombjait a Commerce modultár bővíthetőségi funkcióival kell hozzáadni. Továbbá, amikor az alkalmazásokat egy adott közösségi identitásszolgáltatónál állítja be, bizonyos esetekben az URL- vagy konfigurációs sztringekben megkülönböztethetik a kis- és nagybetűket. További információt a közösségi identitásszolgáltató csatlakozási utasításaiban talál.
 
![Példa az alapértelmezett bejelentkezési képernyőre, melyen látható a közösségi identitásszolgáltató bejelentkezési gombja.](./media/B2CImage_17.png)

## <a name="update-commerce-headquarters-with-the-new-azure-ad-b2c-information"></a>A Commerce központ frissítése az új Azure AD B2C adatokkal

Miután az Azure AD B2C létesítési lépések befejeződtek, az Azure AD B2C alkalmazást regisztrálni kell a Dynamics 365 Commerce környezetében.

Az új Azure AD B2C információval rendelkező központ frissítéséhez hajtsa végre az alábbi lépéseket.

1. A Commerce menüben nyissa meg a **Commerce megosztott paraméterei elemet**, és válassza ki a bal oldali menüben az **Identitásszolgáltatók** elemet.
1. Az **identitás-szolgáltatók** területen hajtsa végre a következő műveleteket:
    1. A Kibocsátó **mezőben** adja meg az azonosító szolgáltató kibocsátójának karakterláncát. A kibocsátó karakterlánc megkereshető az alábbi [, a központ beállításához szükséges kibocsátó karakterlánc bejedve](#obtain-issuer-string-for-headquarters-setup).
    1. A **Név** mezőbe írja be a kiállító rekordjának nevét.
    1. A **Típus** mezőbe írja be a **Azure AD B2C (id_token)** értéket.
1. A **Függő felek** területen, a fenti B2C identitásszolgáltató kiválasztása után tegye a következőket:
    1. Az **Ügyfélazonosító** mezőbe írja be a B2C alkalmazás azonosítóját. Ezt a B2C alkalmazás tulajdonságlapján található **Alkalmazásazonosító** mezőben találja.
    1. A **Típus** mezőbe írja be a **Nyilvános** kifejezést.
    1. A **Felhasználó típusa** mezőbe írja be az **Ügyfél** kifejezést.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A Commerce keresőmezőjében keressen rá az **Elosztási ütemezés** elemre
1. Az **Elosztási ütemezések** lap bal oldali navigációs menüjében válassza a **1110 globális konfiguráció** feladatot.
1. A műveleti ablaktáblán kattintson a **Futtatás most** elemre.

### <a name="obtain-issuer-string-for-headquarters-setup"></a>Kibocsátó karakterlánc beszerzése a központ beállításához

Az azonosító szolgáltató kibocsátójának karakterlánca az alábbi lépések szerint szerezhető be.

1. Az Azure Portal Azure AD B2C lapján keresse meg a **Regisztráció és bejelentkezés** felhasználói folyamatot.
1. Válassza a bal oldali navigációs menü **Oldalelrendezések** elemét, az **Elrendezés neve** alatt válassza az **Egyesített regisztrációs vagy bejelentkezési oldal** lehetőséget, majd a **Felhasználói folyamat futtatása** elemet.
1. Győződjön meg róla Azure AD, hogy az alkalmazás az fent létrehozott, a kívánt B2C-alkalmazásra van beállítva, majd válassza ki azt a felhasználói folyamathivatkozást, **·**``.../.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>`` amely a Felhasználói folyamat fejlécének futtatása alatt látható. (Ne jelölje be **Felhasználói folyamat futtatása**.) Megjelenik egy új lap, amely megjeleníti a kibocsátó karakterlánc beszedése irányelv metaadatait.
1. A böngészőben megjelenített metaadatlapon másolja át az azonosító szolgáltató kibocsátójának karakterláncát (**a** kibocsátónak a "https://" karaktersel kezdődő, "/v2.0/" végződésűre) értékét, amely a következő példához hasonlónak látszik.
   - ``https://login.fabrikam.com/011115c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.
 
**VAGY**: Ha ugyanazt a metaadat-URL-címet manuálisan szeretné megépíteni, tegye meg a következő lépéseket.

1. Hozzon létre egy metaadat cím-URL-t a következő formátumban a B2C bérlő és irányelv használatával: ``https://<B2CTENANTNAME>.b2clogin.com/<B2CTENANTNAME>.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``
    - Példa: ``https://d365plc.b2clogin.com/d365plc.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=B2C_1_signinup``
1. Adja meg a metaadatcím URL-jét a böngésző címsorába.
1. A metaadatokban másolja az identitásszolgáltató kiállítójának URL-címét (az **„issuer”** értékét).
    - Példa: ``https://login.fabrikam.com/011115c3-0113-4f43-b5e2-df01266e24ae/v2.0/``

## <a name="configure-your-b2c-tenant-in-commerce-site-builder"></a>A B2C-bérlő konfigurálása a Commerce webhelyszerkesztőben

A Azure AD B2C-bérlő beállításainak megadása után konfigurálni kell a B2C-bérlőt a Commerce webhelyszerkesztőben. A konfigurálás lépései közül az egyik a B2C alkalmazás adatainak összegyűjtése az Azure portálról, a B2C alkalmazás adatainak megadása webhelykészítőben, majd a B2C alkalmazás társítása a webhelyéhez és a csatornájához.

### <a name="collect-the-required-application-information"></a>A szükséges alkalmazásadatok összegyűjtése

A szükséges alkalmazásadatok összegyűjtéséhez kövesse az alábbi lépéseket.

1. Az Azure-portálon menjen a **\>Azure AD B2C – alkalmazásregisztrációk webhelyre**.
1. Válassza ki az alkalmazást, majd a bal oldali navigációs ablakban válassza **az Áttekintés** lehetőséget az alkalmazás részletes adataihoz.
1. Az alkalmazásazonosító-hivatkozásból **gyűjtse** össze a B2C-bérlőben létrehozott B2C-alkalmazás azonosítóját. Ezt a későbbiekben a webhelykészítőben **Ügyfél GUID-ként** lesz megadva.
1. Válassza az **Átirányítási URL-címeket**, és gyűjtse össze a webhelyéhez látható válasz URL-címet (a válasz URL-címét a beállításkor adja meg).
1. Ugrás a **B2C \>Azure AD kezdőlaphoz – felhasználói folyamatok**, majd az egyes felhasználói folyamati irányelvek teljes nevének összegyűjtése.

Az alábbi kép egy példát **Azure AD mutat be a B2C – alkalmazásregisztrációk áttekintő** lapra.

![Azure AD B2C - Az alkalmazásregisztrációk áttekintő lapja a kijelölt alkalmazásazonosítóval (ügyfél)](./media/ClientGUID_Application_AzurePortal.png)

A következő kép egy példát mutat be a felhasználói folyamatokra az **Azure AD B2C – felhasználói folyamatok (házirendek)** oldalon.

![A B2C házirendfolyamatok neveinek összegyűjtése.](./media/B2CImage_22.png)

### <a name="enter-your-azure-ad-b2c-tenant-application-information-into-commerce"></a>Adja meg a Azure AD B2C bérlő alkalmazásával kapcsolatos adatokat a Commerce rendszerből.

Meg kell adnia a Azure AD B2C bérlő adatait a Commerce oldalkészítő számára, mielőtt a B2C bérlőt a webhelyéhez/webhelyeihez társítja.

A B2C Azure AD bérlőalkalmazási információinak a Commerce alkalmazásba való felvételéhez kövesse ezeket a lépéseket.

1. Jelentkezzen be rendszergazdaként a saját környezetéhez tartozó Commerce oldalkészítőbe.
1. A bal oldali navigációs panelen válassza a **Bérlőbeállítások** elemet a kibontáshoz.
1. A Bérlő **beállításai csoportban** válassza a Webhely hitelesítésének **beállításait**. 
1. Válassza a Kezelés lehetőséget a Webhely **hitelesítési** profiljai melletti fő **ablakban**. (Ha a bérlő megjelenik a webhely hitelesítési profiljainak listáján, azt már egy rendszergazda hozzáadta. Győződjön meg róla, hogy az alábbi 6. lépésben lévő cikkek megegyeznek a B2C beállításokban tervezett cikkekkel. Új profilt a Azure AD B2C hasonló bérlők vagy pályázatok segítségével is létre lehet hozni, hogy kisebb különbségeket is figyelembe tudjanak venni, például eltérő felhasználói irányelv-azonosítókat.
1. Válassza a **Webhely hitelesítési profiljának hozzáadása lehetőséget**.
1. A megjelenő képernyőn adja meg a következő szükséges elemeket a B2C bérlő és az alkalmazás értékeit használva. A nem kötelező mezők (a csillag nélküliek) üresen maradhatnak.

    - **Alkalmazás neve**: A B2C alkalmazás neve (például „Fabrikam B2C”).
    - **Bérlő neve**: A B2C bérlője neve (például használja a „fabrikam” beállítást, ha a B2C-bérlőnek a tartomány „fabrikam.onmicrosoft.com” néven jelenik meg). 
    - **Felejtse el a jelszót házirend azonosító**: A felejtse el a jelszót felhasználóifolyamat házirend azonosítója „B2C_1_PasswordReset”.
    - **Bejelentkezési irányelv azonosítója**: A regisztráció és a bejelentkezés felhasználói folyamatának irányelvazonosítója, például "B2C_1_signup_signin".
    - **Ügyfél GUID**: A B2C alkalmazás azonosítója: (például „22290eb2-c52e-42e9-8b35-a2b0a3bcb9e6” B2C).
    - **Profilirányelv azonosítója**: A profilszerkesztő felhasználói folyamatazonosító, például „B2C_1A_ProfileEdit”.

1. Válassza ki az **OK** lehetőséget. Ekkor megjelenik a B2C alkalmazásának neve a listán.
1. A változtatások mentéséhez válassza a **Mentés** elemet.

A Bejelentkezési **név egyéni tartomány választható mezőjét** csak akkor kell használni, ha egyéni tartományt ad meg a Azure AD B2C bérlő számára. Az egyéni tartománynév bejelentkezési **mezőjének**[használatáról az alábbi További B2C-információk tartalmaznak további részleteket és](#additional-b2c-information) szempontokat.

### <a name="associate-the-b2c-application-to-your-site-and-channel"></a>A B2C alkalmazás társítása a webhelyéhez és a csatornához

> [!WARNING]
> - Ha webhelye már B2C alkalmazáshoz van társítva, a másik B2C alkalmazásra történő módosítás eltávolítja a korábban a környezetben már feliratkozott felhasználók számára létrehozott aktuális hivatkozásokat. Módosítás eseténe az aktuálisan hozzárendelt B2C alkalmazáshoz társított hitelesítő adatok nem lesznek elérhetők a felhasználók számára. 
> - Csak akkor frissítse a B2C alkalmazást, ha első alkalommal szeretné bejelenni a csatorna B2C-alkalmazását, vagy ha szeretné, hogy a felhasználók újra regisztrálják az új B2C-alkalmazást erre a csatornára. A csatornáknak a B2C alkalmazásokkal történő társítása során legyen körültekintő, valamint az alkalmazásoknevét egyértelműen adja meg. Ha egy csatorna nincs egy B2C alkalmazáshoz van társítva az alábbi lépésekben, akkor a program a webhelyébe bejelentkező felhasználókat belépteti az **alapértelmezett** B2C alkalmazásba a **Bérlői beállítások \> B2C beállítások** helyen található B2C alkalmazások listáján.

A B2C alkalmazás társításához a webhelyéhez és a csatornához kövesse az alábbi lépéseket.

1. Nyissa meg a webhelyét a Commerce webhelykészítőben.
1. A bal oldali navigációs panelen válassza a **Webhelybeállítások** elemet a kibontáshoz.
1. A **Webhely beállításai** alatt válassza ki a **Csatornák** elemet.
1. Válassza ki a **Csatorna** elem alatti fő ablakban válassza ki a csatornáját.
1. A jobb oldali csatornatulajdonságok ablaktáblán válassza ki a B2C-alkalmazás nevét a **B2C-alkalmazás** kiválasztása legördülő menüből.
1. Válassza a **Bezárás** parancsot, majd válassza a **Mentés és közzététel** parancsot.

## <a name="additional-b2c-information"></a>További B2C információk

### <a name="customer-migration"></a>Ügyfelek áttelepítése

Ha egy korábbi identitásszolgáltatói platformról szeretné áttelepíteni a vevői rekordokat, forduljon a Dynamics 365 Commerce csapathoz a vevői áttelepítéssel kapcsolatosa igényei áttelepítéséhez.

A vevői áttelepítéssel kapcsolatos további Azure AD B2C dokumentációkat lásd: [Felhasználók áttelepítése az Azure Active Directory B2C megoldásba](/azure/active-directory-b2c/active-directory-b2c-user-migration).

### <a name="custom-policies"></a>Egyéni házirendek

További tájékoztatás az Azure AD B2C által kínált interakciók és irányelvfolyamatok testreszabásával a B2C szabványos házirendjein túl, lásd: [Egyéni házirendek az Azure Active Directory B2C megoldásban](/azure/active-directory-b2c/active-directory-b2c-overview-custom). 

### <a name="secondary-admin"></a>Másodlagos adminisztrátor

Egy opcionális, másodlagos adminisztrátori fiók is hozzáadható a B2C bérlő **Felhasználók** szakaszához. Ez lehet egy közvetlen fiók vagy egy általános fiók. Ha egy csoport erőforrásai között egy fiókot meg kell osztania, akkor egy közös fiókot is létre lehet hozni. Az Azure AD B2C-ben tárolt adatok érzékenysége miatt egy közös fiókot a vállalat biztonsági eljárásai szerint gondosan nyomon kell követni.

### <a name="set-up-a-custom-sign-in-domain"></a>Egyéni bejelentkezési tartomány beállítása

Azure AD A B2C lehetővé teszi a B2C bérlő Azure AD egyéni bejelentkezési tartományának beállítását. Az útmutatásért lásd [egyéni tartományok engedélyezése a Azure Active Directory B2C számára](/azure/active-directory-b2c/custom-domain). 

Egyéni bejelentkezési tartomány használata esetén a tartományt meg kell adni a Commerce Webhelyszerkesztőben.

A webhelyszerkesztőben egyéni bejelentkezési tartományt a következő lépések szerint lehet megadni.

1. A Webhelyszerkesztő jobb felső sarkában válassza ki a hely kapcsolóját, majd válassza **a Helyek kezelése lehetőséget**.
1. A bal oldali navigációs ablakban válassza a Bérlő **beállításai \> webhely hitelesítésének beállítását**.
1. Válassza a **Kezelés lehetőséget a Webhely hitelesítési** profiljai **szakaszban**.
1. A jobboldali menüben **válassza** a Szerkesztés gombot (szimbólumot) annak a hely hitelesítési profilnak a mellett, amelybe egyéni tartományt szeretne megadni.
1. A Webhely hitelesítési **profiljának** szerkesztése **párbeszédpanel** Egyéni tartomány bejelentkezése területen adja meg az egyéni bejelentkezési tartományt (például " login.fabrikam.com").

> [!WARNING]
> Amikor a B2C bérlő egyéni tartományát frissíti, a módosítás hatással van a Azure AD bérlő által létrehozott token kibocsátójának adataira. A kibocsátó adatai ezután az egyéni tartományt tartalmazzák, nem pedig a B2C által biztosított Azure AD alapértelmezett tartományt. **A** Commerce Headquarters más kibocsátó konfigurációja (**Retail and Commerce \> Headquarters \>\>\>** beállítása – Megosztott kereskedelmi paraméterek – Azonosító szolgáltatók) módosítja a rendszer és a webhely felhasználói közötti kommunikációt, potenciálisan új vevőrekordot hoz létre, ha egy felhasználó az új kibocsátóval szemben hitelesítést kap. Az egyéni tartományváltozásokat Azure AD alaposan tesztelni kell, mielőtt élő B2C környezetben átváltanának az egyéni tartományra.

## <a name="additional-resources"></a>További erőforrások

[Tartománynév konfigurálása](configure-your-domain-name.md)

[Új e-kereskedelmi bérlő telepítése](deploy-ecommerce-site.md)

[E-kereskedelmi webhely létrehozása](create-ecommerce-site.md)

[Dynamics 365 Commerce webhely társítása online csatornával](associate-site-online-store.md)

[robots.txt fájlok kezelése](manage-robots-txt-files.md)

[URL-átirányítások tömeges feltöltése](upload-bulk-redirects.md)

[Felhasználói bejelentkezéshez használt egyéni lapok beállítása](custom-pages-user-logins.md)

[Több B2C-bérlő konfigurálása egy Commerce környezetben](configure-multi-B2C-tenants.md)

[Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása](add-cdn-support.md)

[Helyalapú áruházészlelés engedélyezése](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
