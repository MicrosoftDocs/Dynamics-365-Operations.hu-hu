---
title: Regulatory Configuration Services (RCS) – Globalizációs funkció
description: Ez a témakör azt mutatja be, hogyan használható a Microsoft Regulatory Configuration Services (RCS) és a Globális tár a globalizációs funkciók létrehozásához és használatához.
author: JaneA07
ms.date: 06/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, RCSWorkspace, e-Invoicing service
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: 7faa9a3cf6a29d8ed126cfcb0e2902b2016d03ff
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6358146"
---
# <a name="regulatory-configuration-services-rcs---globalization-features"></a>Regulatory Configuration Services (RCS) – Globalizációs funkció

[!include [banner](../includes/banner.md)]

A Microsoft Regulatory Configuration Services (RCS) segítségével létrehozhat egy globalizációs szolgáltatást, amely a globalizációs szolgáltatásokban, például az elektronikus számlázásban is használható. Az RCS segítségével a következő feladatokat hajthatja végre:

- A szolgáltatáshoz kapcsolódó összetevők definiálása.
- A funkció életciklusának kezelése a funkció állapotán keresztül.
- Szolgáltatás elérhetővé tétele meghatározott környezetekben.
- Szolgáltatások megosztása más szervezetekkel.

A következő lépések leírják, hogy egy RCS-felhasználó hogyan adhatja hozzá a globalizációs szolgáltatásokat és a kapcsolódó összetevőket, frissítheti a szolgáltatás állapotát, és teheti elérhetővé a szolgáltatást, hogy a globalizációs szolgáltatásokban is használható legyen.

Az eljárások elvégzése előtt be kell fejeznie a következő feladatokhoz kapcsolódó lépéseket:

- Hozzáférés egy RCS-példányhoz.
- Konfigurációs szolgáltató létrehozása és aktiválása. További információért tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.

Hajtsa végre az alábbi lépéseket a Finance and Operations alkalmazáspéldányban.

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. Ha nincs RCS környezete a vállalathoz, kattintson a **Regulatory services – konfiguráció** lehetőségre, és kövesse a létrehozására vonatkozó instrukciókat.

> [!NOTE]
> Ha van már RCS-környezet létesítve a vállalat számára, akkor az oldal URL-címével érheti el a környezetet, a bejelentkezési beállítás kiválasztásával.

## <a name="turn-on-the-globalization-features"></a>A globalizációs szolgáltatások bekapcsolása

1. A RCS-példányban válassza ki a **Funkció kezelése** mozaikját.
2. A **Funkció kezelése** munkaterületen válassza ki a **Globalizációs funkciókat** a listán, majd válassza az **Engedélyezés most** lehetőséget.

    ![Globalizációs szolgáltatások a szolgáltatások kezelésében.](./media/RCS_GlobalF_1%20Feature%20mgmt.JPG)

## <a name="globalization-features"></a>Globalizációs funkciók

A globalizációs funkciók használatához először importálnia kell azt a globális tárházból, és létre kell hoznia saját verzióját. A globalizációs funkciókat kétféleképpen lehet hozzáadni:

- Olyan származtatott funkció hozzáadása, amely egy már közzétett vagy megosztott meglévő szolgáltatáson alapul.
- Új, a nulláról létrehozott funkció hozzáadása.

## <a name="access-globalization-features"></a>Globalizációs funkciók elérése

1. Győződjön meg róla, hogy a **globalizációs szolgáltatások** funkció be van kapcsolva a szolgáltatások kezelése modulban, az ebben a témakörben korábban ismertetett módon.
2. Nyissa meg az új **Globalizációs szolgáltatások** munkaterületet, majd a **Szolgáltatások** területen válassza az **E-számlázás** mozaikot.

    ![Globális szolgáltatások munkaterülete.](./media/RCS_GlobalF_2%20Feature%20wrkspace.JPG)

    Megnyílik az **E-számlázási szolgáltatások** lap.

    ![E-számlázási szolgáltatások lap.](./media/RCS_GlobalF_3%20Feature%20form.JPG)

## <a name="add-a-derived-globalization-feature"></a>Származtatott globalizációs funkció hozzáadása

Új globalizációs funkciókat úgy adhat hozzá, hogy egy már közzétett vagy megosztott meglévő szolgáltatásból ered.

1. Válassza az **Importálás** lehetőséget, ha meg szeretné nyitni az **Importálási funkció a globális tárházból** lapról.

    ![Szolgáltatás importálása a globális tárház lapjáról.](./media/RCS_GlobalF_4%20Feature%20import%20form%20GR.JPG)

2. A legújabb szolgáltatások beszerzéséhez válassza a **Szinkronizálás** elemet.

    A szinkronizált lista olyan funkciókat tartalmaz, amelyek elérhetők az Ön számára, akár azért, mert a Microsoft közzétette, akár azért, mert egy másik konfigurációs szolgáltató megosztotta Önnel.

    ![A szolgáltatások szinkronizált listája.](./media/RCS_GlobalF_5%20Feature%20GR%20sync.JPG)

3. Válassza ki az importálni kívánt funkciókat a listán, majd válassza az **Importálás** elemet. A kiválasztott szolgáltatások sikeres importálásakor egy üzenet jelenik meg.

    ![Sikeres importálás üzenet.](./media/RCS_GlobalF_6%20Feature%20GR%20import%20success.JPG)

4. Válassza a **Hozzáadás** lehetőséget, majd a legördülő párbeszédpanelen válassza ki a **Meglévő verzió alapján** beállítást.
5. Írja be a funkció nevét és a leírását.
6. A választható szolgáltatások listáján válassza ki a funkció alapverzióját, majd válassza a **Funkció létrehozása** elemet.

    ![Származtatott funkció hozzáadása.](./media/RCS_GlobalF_7%20Feature%20create%20derived.JPG)

    A hozzáadott funkció létrejön, és **Vázlat** lesz az állapota.

    ![Vázlat állapotú származtatott funkció.](./media/RCS_GlobalF_8%20Feature%20draft%20create.JPG)

7. Tekintse át a szolgáltatások összetevőit annak a megállapításához, hogy szükségesek-e frissítések:

    - Tekintse át a konfigurációkat, ha testre szeretné szabni az elektronikus jelentések (ER) formátumát, valamint a szolgáltatás verziójának formátum-hozzárendelésével történő kötését.
    - Ellenőrizze a beállítást, ha testre szeretné szabni a funkció verziójának **Műveletek** lapját, **Alkalmazhatósági szabályok** lapját és **Változók** lapját.

8. A **Változatok** lapon válassza ki az **Érvényesség kezdő** dátumát, és adjon meg egy leírást, ha a **Leírás** mező üres.
9. A funkció befejezéséhez válassza az **Állapot módosítása** parancsot. A teljesített funkciókat egy adott környezet számára elérhetővé teheti, hogy a globalizációs szolgáltatásokban használható legyen, vagy közzétehető legyen a globális tárházban.

> [!NOTE]
> A funkciók, amelyeknél a **Szolgáltatási verzió állapota** értéke **Közzétett**, megoszthatók külső szervezetekkel.

## <a name="add-a-new-globalization-feature"></a>Új globalizációs funkció hozzáadása

Új globalizációs funkciót úgy is hozzáadhat, hogy a semmiből hozza létre.

1. Az **Szolgáltatás importálása a globális tárházból** lapon válassza ki a **Hozzáadás** elemet, majd a legördülő listából válassza az **Új szolgáltatás** lehetőséget.
2. Írja be a funkció nevét és a leírását.
3. Válassza a **Létrehozás lehetőséget**.

    ![Új funkció hozzáadása.](./media/RCS_GlobalF_9%20Feature%20create%20new.JPG)

4. A **Változatok** lapon válasszon egy **Érvényesség kezdő** dátumát, majd a funkció befejezéséhez válassza az **Állapot módosítása** lehetőséget. A teljesített funkciókat egy adott környezet számára elérhetővé teheti, hogy a globalizációs szolgáltatásokban használható legyen, vagy közzétehető legyen a globális tárházban.

> [!NOTE]
> A funkciók, amelyeknél a **Szolgáltatási verzió állapota** értéke **Közzétett**, megoszthatók külső szervezetekkel.

## <a name="feature-component-overview"></a>Funkcióösszetevő áttekintése

A globalizációs szolgáltatások számos összetevővel rendelkeznek:

- **Verzió** – Ez az összetevő támogatja a szolgáltatások életciklusának kezelését, és lehetővé teszi a felhasználók számára a funkció különböző verzióihoz tartozó állapot kezelését.
- **Konfigurációk** – Ez az összetevő lehetővé teszi a felhasználók számára a kapcsolódó ER-formátumok és formátum-hozzárendelések kezelését, megtekintését és szerkesztését.
- **Beállítások** – Ez az összetevő lehetővé teszi a globalizációs szolgáltatások – például az e-számlázási szolgáltatások – felhasználóinak a kapcsolódó szolgáltatás verziójának beállításának kezelését. Ezért támogatja a kommunikációs és a válaszadási szabályok rugalmas felépítését.
- **Környezet** – Ez az összetevő lehetővé teszi a globalizációs szolgáltatások – például az e-számlázási szolgáltatások – felhasználóinak annak a környezetnek a kezelését, ahol a szolgáltatásverzió beállítását használják, és engedélyt adni azoknak a felhasználóknak, akik hozzáférhetnek a rendszerhez.
- **Szervezetek** – Ez az összetevő lehetővé teszi a felhasználók számára a funkció külső szervezetekkel való megosztását.

## <a name="configuring-feature-components"></a>Szolgáltatásösszetevők konfigurálása

### <a name="version-and-status"></a>Állapot és verzió

A verzió a globalizációs szolgáltatások életciklusának kezelésére szolgál.

Az állapot módosítható az **Állapot** mezőjében a **Verzió** lapnak. A következő állapotok érhetők el:

- **Vázlat** – a funkció csak akkor szerkeszthető, ha ebben az állapotban van.
- **Kész** – a funkció és az összes kapcsolódó összetevő véglegesítésre került (kész), és nem szerkeszthető.
- **Közzétéve** – a funkció és az összes kapcsolódó összetevő közzé lett téve a globális tárházban.
- **Megosztott** – a funkció és a kapcsolódó összetevők megosztása megtörtént a külső szervezetekkel.
- **Engedélyezve** – a funkció és az összes kapcsolódó összetevő engedélyezve van egy globalizációs szolgáltatásban való használatra, mint például az e-számlázási szolgáltatás.

> [!NOTE]
> A szolgáltatásoknak egymás után kell mozogni az egyes állapotok között. Ennélfogva nem minden állapot érhető el minden életciklus-szakaszban.

### <a name="configurations"></a>Konfigurációk

A konfigurációkhoz az alábbi műveletek érhetők el:

- **Nézet** – a frissítést nem igénylő alapfunkció-konfigurációk megtekintése.
- **Szerkesztés** – a kiválasztott konfiguráció vázlat verziójának létrehozása, amellyel szerkeszthető a formátum vagy a formátum-hozzárendelés a formátumtervezőben.
- **Törlés** – a funkcióból kiválasztott konfiguráció törlése.
- **Új alap** – a funkció új alapra helyezése. További információt a témakör későbbi részében található [Származtatott globalizációs funkciók új alapra helyezése](#rebase) című szakaszban talál.

### <a name="setups"></a>Beállítások

A funkcióbeállításhoz az alábbi műveletek érhetők el:

- **Hozzáadás** – új funkcióbeállítás létrehozása. Ez a funkcióbeállítás származtatható egy létező funkcióbeállításból, vagy a nulláról létrehozva.
- **Törlés** – a kiválasztott funkcióbeállítás törlése.
- **Nézet** – egy alap funkcióbeállítás megtekintése, amelyekhez nem szükséges változtatás.
- **Szerkesztés** – a funkcióbeállítás három fő összetevőjéhez tartozó attribútumok létrehozása, törlése vagy módosítása:

    - Műveletek és paramétereik
    - Alkalmazhatósági szabályok
    - Változók

![Szolgáltatásverzió beállítási lapja.](./media/RCS_GlobalF_10%20Feature%20set%20up.JPG)

### <a name="environments"></a>Környezetek

A környezetekhez az alábbi műveletek érhetők el:

- **Engedélyezés** – a kiválasztott szolgáltatási verzió esetében válasszon ki egy közzétett környezetet, és válassza ki a **tényleges kezdő** dátumot, amikor elérhetővé kell tenni. További információt a témakör későbbi részében találhat: [Környezet konfigurálása engedélyezéshez](#configureenvironment) című szakaszban talál.
- **Mégse** – környezet eltávolítása a funkció beállításához.

### <a name="organizations"></a>Szervezetek

Kövesse az alábbi lépéseket egy globalizációs funkció külső szervezettel történő megosztásához.

1. Az **E-számlázási szolgáltatások** lapon válassza ki a megosztani kívánt funkciót és a funkció-verziószámot.
2. Válassza a **Szervezetek** lapon a **Megosztás a következővel** elemet, majd a legördülő párbeszédpanelen írja be a szervezet tartománynevét.
3. Válassza ki a **Megosztás** elemet.

    ![Szolgáltatás megosztása egy szervezettel.](./media/RCS_GlobalF_20%20Feature%20orgn_share%20with.JPG)

A funkció megosztásra kerül a kiválasztott szervezettel, és a szervezet számára elérhető a globális tárban. Innen a funkció a szervezet RCS- vagy Dynamics 365 Finance-példányába importálható, hogy használható legyen.

## <a name="rebase-derived-globalization-features"></a><a name="rebase"></a>Származtatott globalizációs funkciók új alapra helyezése

A származtatott globalizáció funkció az új vagy a frissített alapszolgáltatási verzióra vezethető át új alapra helyezéssel. Ily módon az alapverzióban történt módosítások automatikusan frissíthetők. A frissített alapverziót a származó konfigurációs szolgáltató hozza létre, és ezt követően közzéteszi vagy megosztja.

![Frissített alapfunkció-verzió.](./media/RCS_GlobalF_12%20Feature%20new%20version.JPG)

Ha például a létrehozott funkció származtatott verzióját szeretné új alapra helyezni, először a szolgáltatás legújabb verzióját kell beolvasnia a globális tárházból.

1. Az **E-számlázási szolgáltatások** lapon válassza az **Importálás** elemet.
2. A legújabb szolgáltatások beszerzéséhez válassza a **Szinkronizálás** elemet.
3. Válassza ki az importálni kívánt funkciókat a funkciólistán, majd válassza az **Importálás** elemet.

    ![A szolgáltatás legújabb verziójának importálása.](./media/RCS_GlobalF_13%20Feature%20new%20version%20import.JPG)

4. A szolgáltatások listájában válassza ki az új alapra helyezendő funkciót.
5. A **Verzió** lapon válassza az **Új** parancsot a vázlat verzió létrehozásához.

    ![Új vázlat verzió létrehozva.](./media/RCS_GlobalF_14%20Feature%20new%20base%20version.JPG)

6. Válassza az **Új alap** lehetőséget.
7. Az **Új alap** párbeszédpanelen válassza ki annak a funkciónak a legfrissebb verzióját, amelybe át szeretné alapozni.

    ![Új alap párbeszédpanel.](./media/RCS_GlobalF_15%20Feature%20rebase%20version.JPG)

8. Válassza ki az **OK** lehetőséget.
9. Tekintse át a funkció összetevőit, és végezze el a szükséges módosításokat.
10. Az új alapra helyezett funkció befejezéséhez válassza az **Állapot módosítása** parancsot. Az új alapra helyezetés befejezése után további műveleteket is végre lehet hajtani. Közzéteheti például a funkciót, és elérhetővé teheti a globalizációs szolgáltatásokban való használatra.

    ![A funkció állapota készre módosult.](./media/RCS_GlobalF_16%20Feature%20rebase%20version%20complete.JPG)

## <a name="configure-environments-for-globalization-features"></a><a name="configureenvironment"></a>A globalizációs szolgáltatások környezetének konfigurálása

A globalizációs szolgáltatásokat használó felhasználók kezelhetik a környezetet a globalizációs funkció beállításához, és engedélyt adhatnak más felhasználóknak, akik hozzáférhetnek a rendszerhez.

1. Nyissa meg a **Globalizációs szolgáltatások** munkaterületet, majd a **Környezetek** területen válassza az **E-számlázás** mozaikot.

    ![Globalizációs szolgáltatások munkaterülete.](./media/RCS_GlobalF_17%20Feature%20environment.JPG)

2. Válassza ki a **Kulcstároló paramétereit**, majd az **Új** parancsot választva hozzon létre egy Azure Key Vault-titkot.
3. Írjon be egy nevet és egy leírást a kulcstárolóhoz, majd a **Kulcstároló-URI** mezőbe írja be azt az URL-címet, amely azonosítja a kulcstároló erőforrást az Azure megoldásban.
4. A **Tanúsítványok** gyorslapon válassza a **Hozzáadás** lehetőséget a tanúsítvány hozzáadásához, majd adja meg az egyes tanúsítványok nevét és leírását.

    ![Tanúsítvány hozzáadva.](./media/RCS_GlobalF_18%20Feature%20envn%20key%20vault%20parameter.JPG)

5. Válassza ki az **Új** lehetőséget egy új környezet létrehozásához.
6. Írjon be egy nevet, egy leírást, valamint a tároláshoz szükséges megosztott hozzáférési aláírás token titkát.
7. A **Felhasználók** gyorslapon válassza az **Új** lehetőséget, ha a környezethez hozzáférési jogosultsággal rendelkező felhasználó szeretne hozzáadni.
8. Adja meg a felhasználó felhasználói azonosítóját és e-mail-címét.
9. További felhasználók hozzáadásához ismételje meg a 7. és 8. lépést.
10. A környezet közzétételéhez válassza a **Közzététel** lehetőséget.

    ![Közzétett környezet.](./media/RCS_GlobalF_19%20Feature%20envn%20publishing.JPG)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]