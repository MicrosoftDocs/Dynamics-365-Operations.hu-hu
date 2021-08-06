---
title: A Távollétkezelő szerepkör konfigurálása
description: Ez a témakör bemutatja, hogy hogyan lehet beállítani a Távollétkezelő szerepkört az alkalmazottak szabadságainak kezeléséhez.
author: hasrivas
ms.date: 07/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace, LeaveAbsenceManager
audience: Application User
ms.search.scope: Human Resources
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: hasrivas
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e8a8250b36d2774ac308637253b780592df316cd
ms.sourcegitcommit: 86d38cf57abe768e5bccde48b28280bc2224080c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/19/2021
ms.locfileid: "6639606"
---
# <a name="configure-the-absence-manager-role"></a>A Távollétkezelő szerepkör konfigurálása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [preview feature](./includes/preview-feature.md)]

Egyes szervezeteknél a vezetők nem kezelik a saját csapatuk szabadságait. Ehelyett egy távollétkezelőnek kell kezelnie ezt a folyamatot több részleg és csapat tagjaira vonatkozóan. A távollétkezelők a következő távollétkezelési képességekkel rendelkeznek:

- Távollét áttekintése és jóváhagyása egy másik hierarchia alapján.
- Csapattagok egyenlegének megtekintése.
- A távolléti naptár megtekintése.

## <a name="turn-on-the-feature"></a>A funkció bekapcsolása

1. A **Rendszerfelügyelet** munkaterületen válassza a **Funkciókezelés** lehetőséget.

2. A **Funkciókezelés lapon** engedélyezze az **(előzetes verzió) A távollétkezelő kezeli a szabadásgokat** funkciót.

## <a name="define-a-custom-hierarchy"></a>Egyéni hierarchia definiálása

A távollétkezelő funkciók egyéni hierarchiát használnak, és ezt konfigurálni kell.

1. A **Szervezet adminisztrációja** munkaterületen válassza ki a **Beosztáshierarchia-típusok** lehetőséget.

2. Hozzon létre egy **Szabadság** nevű beosztáshierarchia-típust.

3. A **Szabadság és távollét** munkaterületen a **Hivatkozások** alatt válassza a **Szabadság és távollét paraméterei** lehetőséget.

4. Az **Általános** lap **Távolléti hierarchia** legördülő listájában válassza ki a korábban létrehozott **Szabadság** hierarchiatípust. Ezt a Szabadság hierarchiatársítást minden olyan jogi személynél ki kell tölteni, amelynél használni fogja a távollétkezelői funkciókat.

A hierarchiatípus meghatározása után a beosztáshierarchia-jelentést hozzá kell rendelni a beosztáshoz.

1. A **Szervezet adminisztrációja** munkaterületen válassza ki az **Összes beosztás** lehetőséget.

2. Válassza ki a beosztást, amelyhez a Szabadság hierarchiát hozzá szeretné adni.

3. A **Kapcsolatok** lapon válassza a **Hozzáadás** lehetőséget.

4. A **Hierarchia neve** mezőben válassza ki az **Szabadság** lehetőséget.

5. A **Felettes beosztás** mezőben válasszon ki egy beosztást. A beosztás kiválasztása után a rendszer automatikusan kitölti a dolgozó nevét.

## <a name="assign-the-absence-manager-role-to-a-user"></a>A Távollétkezelő szerepkör hozzárendelése egy felhasználóhoz

A távollétkezelő szerepkört alkalmazottakhoz kell rendelni, hogy jóváhagyhassák vagy elutasíthassák a távolléti kérelmeket.

1. Válassza a **Hivatkozások** lehetőséget a **Rendszergazda** munkaterületen.

2. A **Felhasználók** szakaszban válassza ki a **Felhasználók** hivatkozást.

3. A felhasználók listájában válassza ki azt a felhasználót, akihez a Távollétkezelő szerepkört hozzárendeli.

4. A **Felhasználó szerepköre** lapon válassza a **Szerepkörök hozzárendelése** elemet.

5. A listában válassza ki a **Távollétkezelő** szerepkört. Majd kattintson az **OK** lehetőségre.

    > [!IMPORTANT]
    > Győződjön meg arról, hogy ahhoz a felhasználóhoz is hozzá van rendelve az Alkalmazott szerepkör is, akihez a Távollétkezelő szerepkört hozzárendeli. Ellenkező esetben a dolgozó nem használhatja a funkciót.

6. Miután létrehozta a Szabadsághierarchiát, a következő lépésekkel lehet megtekinteni azt:

    1. A **Szervezet adminisztrációja** munkaterületen válassza ki a **Beosztáshierarchia** lehetőséget.
    
    2. A **Hierarchia típusa** mezőben válassza ki a **Szabadság** lehetőséget.

## <a name="absence-manager-workspace"></a>Távollétkezelő munkaterülete

Az **Alkalmazotti önkiszolgáló** munkaterületen a **Távollétkezelő** lap a távollét hierarchiában a távollétkezelőhöz rendelt alkalmazottak távolléti adatait jeleníti meg.

A **Szabadság és távollét** lapon az egyes alkalmazottaknál a következő lehetőségek érhetők el:

- **Szabadságolás** –Aa kiválasztott alkalmazott egyenlegének, jóváhagyott távolléteinek és távolléti kérelmeinek megtekintése.
- **Szabadságegyenlegek** – a kiválasztott alkalmazott különböző távolléti terveihez megadott egyenlegeinek listájának megtekintése.

## <a name="approve-time-off-requests"></a>Szabadságkérelmek jóváhagyása

A távollétkezelők jóváhagyhatják vagy elutasíthatják az alkalmazottak szabadságkérelmeit. Szükség esetén az alkalmazottak nevében is létrehozhatnak igényléseket.

> [!IMPORTANT]
> Ahhoz, hogy a távollétkezelők jóváhagyhatják vagy elutasíthatják a szabadságkérelmeket, be kell állítani szabadságkérelem munkafolyamatát, hogy szabadságkérelmi munkaelemet lehessen hozzájuk rendelni, amelyekt áttekinthetnek.
>
> 1. Az **Emberierőforrás-munkafolyamatok** lapon válasszon ki vagy hozzon létre egy szabadságkérési munkafolyamatot.
> 2. Válassza a **Hierarchia társítása** lehetőséget, majd a **Hierarchia neve** mezőben válassza a **Szabadság** lehetőséget.
> 3. A munkafolyamat frissítése a munkafolyamat-tervezőben. A **Hozzárendelés típusa** mezőben válassza a **Hierarchia** beállítást, majd a **Hierarchia kiválasztása** lapon válassza a **Konfigurálható hierarchia** beállítást.
>
> A szabadságkérelem munkafolyamatának létrehozásával további tudnivalókért lásd: [Szabadságkérelmezési munkafolyamat létrehozása](hr-leave-and-absence-workflow.md).

1. Válassza ki az **Alkalmazotti önkiszolgáló rendszer** munkaterületen a **Távollétkezelő** lapot.

2. A **Távollétkezelő** lapon válassza ki a kívánt alkalmazottat.

3. Válassza ki a **Részletek**, majd a **Szabadság** lehetőséget.

4. Keresse meg a szabadságkérelmet kérést, és válassza a **Jóváhagyás** lehetőséget. Ezután választhat, hogy jóváhagyja vagy elutasítja-e a szabadságkérelmet.

Az **Érvénytelenítve** állapot azt jelzi, hogy a kérést elutasították. A **Befejezett** állapot azt jelzi, hogy a kérést jóváhagyták.

## <a name="view-time-off-in-the-calendar"></a>Szabadság megtekintése a naptárban

A Távollétkezelő szerepkörű felhasználók a naptárban megtekinthetik az szabadságkérelmeket. A szabadságnaptár eléréséhez kövesse az alábbi lépéseket.

> [!IMPORTANT]
> A távollétkezelő naptár nézetbeállításait a rendszergazdának kell beállítania. A **Szabadság és távollét paraméterei** lap **Naptár** lapján lehetőség van a születésnapok, a részletek nélküli távollétek, a szabadásgok és a függőben lévő távolléti kérelmek elrejtésére és megjelenítésére. Lehetőség van a naptárnézet dolgozótípus szerint való szűrésére is.

1. Válassza ki az **Alkalmazotti önkiszolgáló szolgáltatás** munkaterületén a **Távollétkezelő**, majd a **Távollétkezelő naptára** lehetőséget.

2. Adja meg a kívánt dátumokat a **Dátum** mezőben.

3. Szükség szerint frissítse a nézetbeállításokat.

A távollétkezelő naptára mutatja az összes olyan alkalmazott rekordját, aki a Távolléti hierarchiában a távollétkezelő alá tartoznak.

## <a name="see-also"></a>Lásd még

- [Szabadság és távollét áttekintése](hr-leave-and-absence-overview.md)
- [Szabadságkérelmezési munkafolyamat létrehozása](hr-leave-and-absence-workflow.md)
- [Csapat és vállalati naptárak megtekintése](hr-employee-self-service-calendar.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
