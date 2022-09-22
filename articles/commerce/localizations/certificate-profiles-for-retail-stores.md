---
title: A kiskereskedelmi üzletek felhasználó által megadott tanúsítványprofiljai
description: Ez a cikk áttekintést nyújt a tanúsítványprofilokról, amelyek elérhetők a következőben:Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 09/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: v-chgriffin
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.search.industry: Retail
ms.search.form: RetailFormLayout, RetailParameters
ms.openlocfilehash: 5baf043a43210d819b605546089e981c86922ca9
ms.sourcegitcommit: 4f28f262cfb8f047cb5c0070261aa0748835e74b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2022
ms.locfileid: "9558437"
---
# <a name="user-defined-certificate-profiles-for-retail-stores"></a>A kiskereskedelmi üzletek felhasználó által megadott tanúsítványprofiljai

[!include [banner](../includes/banner.md)]

Ez a cikk áttekintést nyújt a tanúsítványprofilokról, amelyek elérhetők a következőben:Microsoft Dynamics 365 Commerce. Ez a funkció helyi tanúsítványok támogatásának hozzáadásával terjeszti ki a [Retail csatornák titkos kódjainak kezelése](../dev-itpro/manage-secrets.md) funkciót.

Amíg a pénztár offline módban fut, Microsoft Azure nem férhet hozzá a Kulcs kulcsként tárolt tanúsítványokhoz. Helyette a helyi tanúsítványt kell használni. A következő lehetőségeket támogatja a rendszer:

- Helyi tanúsítványok használata a kulcssúúsítványos tartalékok esetében
- Helyi tanúsítványok használata Key Key nélkül (például létesítményben való telepítés esetén)
- A tanúsítványok fokozatos frissítése, amelynél egyes áruházak és terminálok a tanúsítvány új verzióját használják, míg más áruházak és terminálok továbbra is a korábbi verziót használják

A tanúsítványprofilok lehetővé teszik egy alapértelmezett tanúsítvány megadását, és beállíthatja az azonos tanúsítványprofilban lévő tanúsítványok keresési sorrendjét. A funkció a helyi tanúsítványokhoz és a Key Vault tanúsítványokhoz hasonló beállítási lehetőséget kínál. A tanúsítványokhoz a vállalatra jellemző beállításokat adhat hozzá; az egyes tanúsítványok egyedi, vállalatközi azonosítója viszont a Commerce csatornákon használható.

### <a name="scenarios"></a>Forgatókönyvek

A tanúsítványprofilok a következő helyzeteket támogatják a Commerce csatornákon:

- Használjon helyi tanúsítványt a kulcssúúsítvány tartalékok esetén. Az alábbiakban néhány példa látható az ilyen kieséses esetekre:

    - A kulcstartó tárterülete nem érhető el.
    - Nem található a tanúsítvány a kulcstartóban.
    - A POS offline módban működik.

- Használjon helyi tanúsítványokat, de ne tárolja őket a Key Key KeyBen (például egy létesítményben).
- Tanúsítványok fokozatos frissítésének végzése, és a tanúsítvány új verziójának csak az üzletekben vagy olyan terminálokon való használata, ahol az új verzió már elérhető.
- Ugyanazon tanúsítvány több vállalatnál való használata.

## <a name="set-up-certificate-profiles"></a>Tanúsítványprofilok beállítása

A következő eljárás a tanúsítványprofilok beállítását mutatja be.

### <a name="set-up-key-vault"></a>Kulcs- és kulcskulcsok beállítása

A kulcstárolókban tárolt digitális tanúsítványok használata előtt a következő lépéseket kell végrehajtani.

1. KulcsHely tárolási fiók létrehozása Javasoljuk, hogy a tárolási fiókot a Commerce Scale Unit mértékegységével azonos földrajzi területen telepítse.
1. A digitális tanúsítvány feltöltése a KulcsHely tárolási fiókba
1. Az Application Object Server -alkalmazás (AOS-) alkalmazás olvasási jogosultsága a KulcsKereső tárolási fiókból.

A Kulcskulcs- és kulcskulcsok használatával kapcsolatos további tudnivalókat lásd [Az Azure kulcs– Kulcssúva (Im) használatának első lépésekben](/azure/key-vault/key-vault-get-started).

### <a name="set-up-system-parameters"></a>Rendszerparaméterek beállítása

Ahhoz, hogy tanúsítványprofilokat konfiguráljon a Commerce csatornában, engedélyeznie kell a Commerce rendszernek, hogy mind a kulcs- és tanúsítványprofilban tárolt tanúsítványt használja.

A Commerce Headquarters rendszerben a következő lépések szerint állíthatja be a rendszerparamétereket.

1. A Rendszerparaméterek **lapon** állítsa **a** Speciális tanúsítványtár használata beállítást Igen **beállításra**.
1. A **Funkciókezelés** munkaterületen kapcsolja be a **Felhasználó által definiált tanúsítványprofilok kiskereskedelmi üzleteket számára** funkciót.

### <a name="set-up-key-vault-parameters"></a>Fő paraméterek paramétereinek beállítása

A Kulcs **– Paraméterek** lapon a Következő paramétereket kell megadnia a Kulcs – Tárolás kulcs eléréséhez:

- **Név** és **leírás** – a Kulcs– Tárolószámla neve és leírása.
- **Kulcs Url-címe** – a KulcsTároló tárolási fiók URL-címe.
- **Kulcs Ügyfél –** a Azure Active Directory Kulcs– ügyfél interaktív ügyfélazonosítója annak a (Azure AD) alkalmazásnak, amely hitelesítési célból a Kulcs – Raktár tárolási fiókhoz van társítva. Ennek az ügyfélnek hozzáférést kell tudnia olvasni a tárolási fiókból.
- **Kulcs, Titkos kulcs** – titkos Azure AD kulcs, amely az alkalmazáshoz van társítva, és amely hitelesítésre használatos a Kulcs – Mindig tárolási fiókban.
- **Név**, **leírás** és titkos **hivatkozás** – a tanúsítvány neve, leírása és titkos hivatkozása.

A további tudnivalókat lásd [Az Azure-kulcs ügyfél beállítása.](../../finance/localizations/setting-up-azure-key-vault-client.md)

### <a name="configure-a-certificate-profile"></a>Tanúsítványprofil konfigurálása

A Commerce Headquartersban a következő lépésekkel konfigurálhatja a tanúsítványprofilokat.

1. Lépjen a **Rendszerfelügyelet \> Beállítás \> Tanúsítványprofilok** elemre.
1. Jelölje be a műveleti ablakban az **Új** lehetőséget a rekord létrehozásához.
1. Adja meg az értékeket a **Tanúsítványprofil**, **Név** és **Leírás mezőkben**.

    > [!NOTE]
    > A tanúsítványprofil a tanúsítvány egyedi azonosítója az összes vállalatnál és Commerce egységnél.

1. A Jogi **személyek gyorsgombra vonatkozó** sor hozzáadásához válassza a Hozzáadás **lehetőséget**.
1. A **Jogi személy mezőben** válassza ki azt a jogi személyt (vállalatot), amelynél az aktuális tanúsítványprofilt használni kell.

    Ha a tanúsítványprofilt több jogi személyhez is használni kell, ismételje meg a 4–5. lépést, hogy minden további jogi személyhez egy sort adjon hozzá.

1. A **Beállítások** lehetőség választásával nyissa meg a **Tanúsítványprofil beállításai** lapot, és végezze el a tanúsítványprofil beállítását az egyes vállalatokra. Adja meg, hogy mely tanúsítványok használhatók az aktuális tanúsítványprofil Commerce-csatornákon való hívatakor. Adjon hozzá annyi tanúsítványt, amennyit csak szeretne, és állítsa be a bizonyítványok prioritását. Ha nem áll rendelkezésre magasabb prioritású tanúsítvány, a rendszer a következő tanúsítványt használja a prioritás alapján. A további tudnivalókat lásd [a Munkafolyamat: Tanúsítványok keresése a Commerce futásidejű szakaszban](#workflow-searching-certificates-in-the-commerce-runtime).

    > [!NOTE]
    > A **Prioritás** mező beállítása automatikus. Az **1** érték jelenti a legmagasabb prioritást. Amikor új sort ad hozzá a **Tanúsítványprofilok beállításai** lapon, prioritásként egy olyan számot kap, amely eggyel nagyobb, mint az előző sor prioritása. Egy adott sor prioritásának módosításához jelölje ki a sort, és a prioritás növeléséhez válassza a **Mozgatás felfelé**, csökkentéséhez a **Mozgatás felfelé** lehetőséget.

1. Amikor új sort ad hozzá a Tanúsítványprofil **beállításai** lapon, a következő mezőket kell beállítania:

    - **Hely típusa** – Válassza ki azt a helyet, ahol a tanúsítványt tárolni kívánja. A mező két lehetséges értéket kaphat: **Helyi tanúsítvány** és **Key Vault**.
    - **Key Vault tanúsítvány** – A mezőt akkor kell megadni, ha a **Hely típusa** mezőt a **Key Vault** értékre állítja. Segítségével megadhatja a Key Vault tanúsítvány titkos kódját.
    - **Üzlet neve** – Ez a mező nem kötelező, és csak akkor érhető el, ha a **Hely típusa** mező értéke **Helyi tanúsítvány**. Itt megadhat egy alapértelmezett üzletnevet, amelyet a helyi tanúsítványok keresésénél használni kell.
    - **Üzlet helye** – Ez a mező nem kötelező, és csak akkor érhető el, ha a **Hely típusa** mező értéke **Helyi tanúsítvány**. Itt megadhat egy alapértelmezett üzlethelyet, amelyet a helyi tanúsítványok keresésénél lehet használni.

        > [!NOTE]
        > Az alapértelmezett üzletnév és üzlethely hozzáadása azért történik, hogy egyszerűbbé váljon a helyi tanúsítványok keresése a Commerce Runtime során. Az X509StoreProvider a mappák listáját tartalmazza, ahol a tanúsítványokat tárolják. Ha nincs megadva az alapértelmezett üzletnév és az alapértelmezett üzlethely, az X509StoreProvider tanúsítványt próbál meg találni a lista többi mappájában. Az üzletnév és az üzlet helyének elérhető értékeivel kapcsolatos további tudnivalókat lásd [: StoreName Enum](/dotnet/api/system.security.cryptography.x509certificates.storename)[és StoreLocation Enum](//dotnet/api/system.security.cryptography.x509certificates.storelocation).

    - **Ujjlenyomat** – ez a mező kötelező, és csak akkor érhető el, **ha a Helytípus** mezőben a Helyi **tanúsítvány van beállítva**. Segítségével megadhatja a tanúsítvány ujjlenyomatát.

        > [!IMPORTANT]
        > Gondoskodnia kell arról, hogy a helyi tanúsítványt használó alkalmazást futtató felhasználónak (például a Modern POS offline módban) legalább olvasási jogosultsága legyen a tanúsítvány titkos kulcsához.

    - **Megjegyzések** – Ez a mező nem kötelező; megjegyzések bevitelét teszi lehetővé a felhasználók számára.

## <a name="workflow-searching-certificates-in-the-commerce-runtime"></a>Munkafolyamat: tanúsítványok keresése a Commerce Runtime-ban

Itt található az az alapvető munkafolyamat, amely tanúsítvány keresésére szolgál, amikor tanúsítványprofilt hívnak meg a Commerce runtime-ban.

1. A rendszer ellenőrzi, hogy a tanúsítványprofil rendelkezik-e vállalatspecifikus beállításokkal az aktuális jogi személy számára.
1. A rendszer megpróbálja megkeresni a tanúsítványt a **Tanúsítványprofil beállításai** lap azon sorában, ahol a **Prioritás** mező értéke **1**.

    - Ha a **Hely típusa** mező értéke **Key Vault**, a **Key Vault tanúsítvány titkos kódja** mező értékét használja a rendszer a tanúsítvány kereséséhez a **Key vault paraméterek** oldalon. Ezt követően a tanúsítvány keresése a kulcstartóban folytatódik.
    - Ha a **Hely típusa** mező a **Helyi tanúsítvány** értékre van állítva, akkor az X509StoreProvider először az alapértelmezett üzletnévvel és az üzlethellyel keresi a tanúsítványt, ha ezek a paraméterek meg vannak adva. Ezt követően a keresés a mappalista összes többi mappájában folytatódik.

1. Ha a tanúsítvány nem található, akkor a rendszer megismétli a folyamatot annál a sornál, ahol a **Prioritás** mező értéke **2**, és így tovább.

> [!NOTE]
> Ha a tanúsítványprofilnál nincs beállítva az aktuális jogi személy, vagy ha a tanúsítvány keresése nem járt sikerrel a **Tanúsítványprofil beállításai** lap egyik sorában sem, akkor a tanúsítvány nem található.

### <a name="caching-the-results-of-certificate-searches"></a>A tanúsítványkeresés eredményének gyorsítótárazása

A tanúsítványkeresés eredménye a gyorsítótárba kerül. A gyorsítótár alapértelmezett lejárati ideje egy óra. Ez az idő azonban testre szabható, és maximum 24 órás értékre állítható.

## <a name="gradual-update"></a>Fokozatos frissítés

Ha a tanúsítvány új verziója kerül bevezetésre, de azt nem lehet minden üzletben egyszerre frissíteni, a tanúsítványprofilok működése lehetővé teszi a fokozatos tanúsítványfrissítést.

1. Keresse meg a tanúsítványprofilt és a frissítendő sort, majd válassza a **Beállítások** elemet.
1. Adjon hozzá egy sort, és adja meg a tanúsítvány legújabb verziójához kapcsolódó beállításokat.
1. Növelje meg az új sornál a **Prioritás** értékét. A **Mozgatás felfelé** gomb a sort úgy mozgatja, hogy az ugyanazon tanúsítvány előző verziójához tartozó sor felett legyen.
> [!NOTE]
> A Commerce Runtime-ban először a tanúsítvány új verzióját hívja meg a rendszer. Ha a tanúsítvány még nincs frissítve egy adott üzletben vagy egy konkrét terminálon, akkor a rendszer a korábbi verziót fogja behívni.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
