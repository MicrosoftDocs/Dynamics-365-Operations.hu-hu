---
title: A kiskereskedelmi üzletek felhasználó által megadott tanúsítványprofiljai
description: Ez a cikk áttekintést nyújt arról, hogyan használják a tanúsítványokat a kiskereskedelmi üzletekben.
author: josaw1
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.search.industry: Retail
ms.search.form: RetailFormLayout, RetailParameters
ms.openlocfilehash: c9840ecba7752c06b46c1a5b050055bd471027f8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276163"
---
# <a name="user-defined-certificate-profiles-for-retail-stores"></a>A kiskereskedelmi üzletek felhasználó által megadott tanúsítványprofiljai

[!include [banner](../includes/banner.md)]


## <a name="overview"></a>Áttekintés

Ez a cikk áttekintést nyújt a tanúsítványprofilokról, amelyek elérhetők a következőben: Microsoft Dynamics 365 Commerce. Ez a funkció helyi tanúsítványok támogatásának hozzáadásával terjeszti ki a [Retail csatornák titkos kódjainak kezelése](../dev-itpro/manage-secrets.md) funkciót.

Ha a pénztár (POS) offline módban üzemel, nem tud hozzáférni a kulcstartóban tárolt tanúsítványokhoz. Helyette a helyi tanúsítványt kell használni. A következő lehetőségeket támogatja a rendszer:

- Helyi tanúsítványok használata a kulcstartó kiesése esetén
- Kulcstartó nélküli helyi tanúsítványok használata (például helyszíni telepítéssel)
- A tanúsítványok fokozatos frissítése, amelynél egyes áruházak és terminálok a tanúsítvány új verzióját használják, míg más áruházak és terminálok továbbra is a korábbi verziót használják

A tanúsítványprofilok lehetővé teszik egy alapértelmezett tanúsítvány megadását, és beállíthatja az azonos tanúsítványprofilban lévő tanúsítványok keresési sorrendjét. A funkció a helyi tanúsítványokhoz és a Key Vault tanúsítványokhoz hasonló beállítási lehetőséget kínál. A tanúsítványokhoz a vállalatra jellemző beállításokat adhat hozzá; az egyes tanúsítványok egyedi, vállalatközi azonosítója viszont a Commerce csatornákon használható.

### <a name="scenarios"></a>Forgatókönyvek

A tanúsítványprofilok a következő helyzeteket támogatják a Commerce csatornákon:

- Helyi tanúsítvány használata a kulcstartó kiesése esetén. Az alábbiakban néhány példa látható az ilyen kieséses esetekre:

    - A kulcstartó tárterülete nem érhető el.
    - Nem található a tanúsítvány a kulcstartóban.
    - A POS offline módban működik.

- Helyi tanúsítványok használata (például helyszíni telepítéssel), azok kulcstartóban való tárolása nélkül.
- Tanúsítványok fokozatos frissítésének végzése, és a tanúsítvány új verziójának csak az üzletekben vagy olyan terminálokon való használata, ahol az új verzió már elérhető.
- Ugyanazon tanúsítvány több vállalatnál való használata.

## <a name="set-up-certificate-profiles"></a>Tanúsítványprofilok beállítása

A következő eljárás a tanúsítványprofilok beállítását mutatja be. Mielőtt tanúsítványprofilokat használna a Commerce csatornákon, kövesse az alábbi lépéseket a beállítások konfigurálásához.

1. A **Funkciókezelés** munkaterületen kapcsolja be a **Felhasználó által definiált tanúsítványprofilok kiskereskedelmi üzleteket számára** funkciót.
2. Lépjen a **Rendszerfelügyelet \> Beállítás \> Tanúsítványprofilok** elemre.
3. Hozzon létre egy rekordot, és töltse ki a **Tanúsítványprofil**, **Név** és **Leírás** mezőt.

    > [!NOTE]
    > A tanúsítványprofil a tanúsítvány egyedi azonosítója az összes vállalatnál és Commerce egységnél.

3. A **Jogi személyek** lapon adjon hozzá egy sort, és válassza ki azt a jogi személyt (vállalatot), amelyhez az aktuális tanúsítványprofilt használni kívánja. Ha a tanúsítványprofilt több jogi személyhez is szeretné használni, ismételje meg ezt a lépést, és minden egyes további jogi személy esetében adjon hozzá egy új sort.
4. A **Beállítások** lehetőség választásával nyissa meg a **Tanúsítványprofil beállításai** lapot, és végezze el a tanúsítványprofil beállítását az egyes vállalatokra.

### <a name="certificate-profile-settings"></a>Tanúsítványprofil beállításai

Amikor a tanúsítványprofil-sorokhoz a **Beállítások** elemet kiválasztja, megjelenik a **Tanúsítványprofil beállításai** lap. Ezen az oldalon megadhatja, hogy mely tanúsítványok használhatók az aktuális tanúsítványprofil Commerce csatornákon való behívásakor. Megadhatja azt a rendelést is, amelyben a tanúsítványokat keresni kell.

> [!NOTE]
> A **Prioritás** mező beállítása automatikus. Az **1** érték jelenti a legmagasabb prioritást. Amikor új sort ad hozzá a **Tanúsítványprofilok beállításai** lapon, prioritásként egy olyan számot kap, amely eggyel nagyobb, mint az előző sor prioritása. Egy adott sor prioritásának módosításához jelölje ki a sort, és a prioritás növeléséhez válassza a **Mozgatás felfelé**, csökkentéséhez a **Mozgatás felfelé** lehetőséget.

Ha új sort ad hozzá a **Tanúsítványprofil beállításai** laphoz, következő mezőket kell megadnia:

- **Hely típusa** – Válassza ki azt a helyet, ahol a tanúsítványt tárolni kívánja. A mező két lehetséges értéket kaphat: **Helyi tanúsítvány** és **Key Vault**.
- **Key Vault tanúsítvány** – A mezőt akkor kell megadni, ha a **Hely típusa** mezőt a **Key Vault** értékre állítja. Segítségével megadhatja a Key Vault tanúsítvány titkos kódját.

    > [!NOTE]
    > Mielőtt Key Vault tanúsítványt használna tanúsítványprofilokban, feltétlenül töltsön fel egy tanúsítványt a kulcstartó tárolójába, és kövesse az [Azure Key Vault ügyfél beállítása](../../finance/localizations/setting-up-azure-key-vault-client.md) utasításait.

- **Üzlet neve** – Ez a mező nem kötelező, és csak akkor érhető el, ha a **Hely típusa** mező értéke **Helyi tanúsítvány**. Itt megadhat egy alapértelmezett üzletnevet, amelyet a helyi tanúsítványok keresésénél használni kell.
- **Üzlet helye** – Ez a mező nem kötelező, és csak akkor érhető el, ha a **Hely típusa** mező értéke **Helyi tanúsítvány**. Itt megadhat egy alapértelmezett üzlethelyet, amelyet a helyi tanúsítványok keresésénél lehet használni.

    > [!NOTE]
    > Az alapértelmezett üzletnév és üzlethely hozzáadása azért történik, hogy egyszerűbbé váljon a helyi tanúsítványok keresése a Commerce Runtime során. Az X509StoreProvider a mappák listáját tartalmazza, ahol a tanúsítványokat tárolják. Ha az alapértelmezett üzletnév és az alapértelmezett üzlethely nincs megadva, az X509StoreProvider a tanúsítványt a listán található többi mappában próbálja megtalálni.

- **Ujjlenyomat** – Ez a mező nem kötelező, és csak akkor érhető el, ha a **Hely típusa** mező értéke **Helyi tanúsítvány**. Segítségével megadhatja a tanúsítvány ujjlenyomatát.
- **Megjegyzések** – Ez a mező nem kötelező; megjegyzések bevitelét teszi lehetővé a felhasználók számára.

### <a name="workflow-searching-certificates-in-the-commerce-runtime"></a>Munkafolyamat: tanúsítványok keresése a Commerce Runtime-ban

Itt található az az alapvető munkafolyamat, amely tanúsítvány keresésére szolgál, amikor tanúsítványprofilt hívnak meg a Commerce runtime-ban.

1. A rendszer ellenőrzi, hogy a tanúsítványprofil rendelkezik-e vállalatspecifikus beállításokkal az aktuális jogi személy számára.
1. A rendszer megpróbálja megkeresni a tanúsítványt a **Tanúsítványprofil beállításai** lap azon sorában, ahol a **Prioritás** mező értéke **1**.

    - Ha a **Hely típusa** mező értéke **Key Vault**, a **Key Vault tanúsítvány titkos kódja** mező értékét használja a rendszer a tanúsítvány kereséséhez a **Key vault paraméterek** oldalon. Ezt követően a tanúsítvány keresése a kulcstartóban folytatódik.
    - Ha a **Hely típusa** mező a **Helyi tanúsítvány** értékre van állítva, akkor az X509StoreProvider először az alapértelmezett üzletnévvel és az üzlethellyel keresi a tanúsítványt, ha ezek a paraméterek meg vannak adva. Ezt követően a keresés a mappalista összes többi mappájában folytatódik.

1. Ha a tanúsítvány nem található, akkor a rendszer megismétli a folyamatot annál a sornál, ahol a **Prioritás** mező értéke **2**, és így tovább.

> [!NOTE]
> Ha a tanúsítványprofilnál nincs beállítva az aktuális jogi személy, vagy ha a tanúsítvány keresése nem járt sikerrel a **Tanúsítványprofil beállításai** lap egyik sorában sem, akkor a tanúsítvány nem található.

#### <a name="caching-the-results-of-certificate-searches"></a>A tanúsítványkeresés eredményének gyorsítótárazása

A tanúsítványkeresés eredménye a gyorsítótárba kerül. A gyorsítótár alapértelmezett lejárati ideje egy óra. Ez az idő azonban testre szabható, és maximum 24 órás értékre állítható.

### <a name="gradual-update"></a>Fokozatos frissítés

Ha a tanúsítvány új verziója kerül bevezetésre, de azt nem lehet minden üzletben egyszerre frissíteni, a tanúsítványprofilok működése lehetővé teszi a fokozatos tanúsítványfrissítést.

1. Keresse meg a tanúsítványprofilt és a frissítendő sort, majd válassza a **Beállítások** elemet.
1. Adjon hozzá egy sort, és adja meg a tanúsítvány legújabb verziójához kapcsolódó beállításokat.
1. Növelje meg az új sornál a **Prioritás** értékét. A **Mozgatás felfelé** gomb a sort úgy mozgatja, hogy az ugyanazon tanúsítvány előző verziójához tartozó sor felett legyen.

> [!NOTE]
> A Commerce Runtime-ban először a tanúsítvány új verzióját hívja meg a rendszer. Ha a tanúsítvány még nincs frissítve egy adott üzletben vagy egy konkrét terminálon, akkor a rendszer a korábbi verziót fogja behívni.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
