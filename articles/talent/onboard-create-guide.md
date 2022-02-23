---
title: Felvételi útmutató létrehozása és küldése a Dynamics 365 Talent – Onboard használatával
description: Ez a témakör bemutatja, hogyan használhatja a Microsoft Dynamics 365 Talent – Onboard alkalmazást arra, hogy bevezető útmutatót hozzon létre az újonnan felvettek számára. Ez a feladat fontos első lépés a humánerőforrás-kezelési szolgáltatás (HCM) nyugdíjazásig történő felvétel stratégiájában.
author: andreabichsel
manager: ''
ms.date: 05/02/2019
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
ms.search.validFrom: 2019-05-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 2371d86165390503312c2848842acf4745a8ed7a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461377"
---
# <a name="create-and-send-an-onboarding-guide"></a>Felvételi útmutató létrehozása és küldése

[!include [banner](includes/banner.md)]

Microsoft Dynamics 365 Talent: Onboard lehetővé teszi, hogy a galériában elérhető vagy az Ön által létrehozott sablonokból felvételi útmutatókat hozzon létre.

Miután létrehozta a felvételi útmutatót, elküldheti azt egy újonnan felvett munkatársnak. Azt is megteheti, hogy több újonnan felvett munkatársnak küldi el, akiket egy Microsoft Excel fájlban határoz meg, amit az Onboard alkalmazásból tölthet le.

## <a name="create-an-onboarding-guide-from-a-template-and-send-it-to-a-single-new-hire"></a>Felvételi útmutató létrehozása sablonból és küldés egyetlen újonnan felvett munkatársnak

1. A bal oldali menüben válassza a **Sablonok** lehetőséget.
2. A **Saját sablonok** területen válassza ki azt a sablont, amelyet be szeretne állítani az újonnan felvett munkatársnak a felvételi útmutatóként.
3. Igény szerint szerkessze a sablont. Ne felejtse el rendszeresen elmenteni a munkát.
4. Ha befejezte a sablon szerkesztését, válassza az **Útmutatólétrehozása** parancsot.

    [![A felvételi útmutató létrehozása egy sablonból](./media/onboard-create-guide.png)](./media/onboard-create-guide.png)

5. Az **Új sablon létrehozás ablakban** a **Kit vesz fel?** részben adja meg az új munkatárs nevét vagy e-mail-címét. Ha az újonnan felvett munkatárs még nincs a rendszerben, válassza a **Hozzáadás most** lehetőséget, majd adja meg az alkalmazott adatait.

    ![[A felvételi útmutató információinak megadása](./media/onboard-create-a-guide-window.png)](./media/onboard-create-a-guide-window.png)

6. A **Mi a kezdés dátuma?** alatt válassza ki a kezdés dátumát.
7. Ha a felvételi útmutatót automatikusan kell kiküldeni az új munkatársnak egy megadott napon, győződjön meg arról, hogy az **Automatikus küldési dátum ütemezése** beállítás be van kapcsolva, majd válassza ki az automatikus küldés dátumát. Ha azonnal el szeretné küldeni az útmutatót, kapcsolja ki a **Automatikus küldési dátum ütemezése** beállítást.
8. Válassza a **Kész** lehetőséget.
9. Ha befejezte a felvételi útmutató szerkesztését, válassza a jobb felső sarokban látható **Küldés** parancsot. Majd tegye a következők egyikét:

    - **A hivatkozásmásolása** hivatkozásra kattintva majd a **Másolás** kiválasztásával elküldheti a felvételi útmutató hivatkozását az új munkatársnak.
    - Ha azt szeretné az e-mail-címet testreszabni a felvételi útmutatóban, válassza a **Végezze el az e-mail testreszabását küldés előtt**, majd a **Tovább** lehetőséget, szabja testre az e-mail-címet, majd válassza a **Küldés** lehetőséget.
    - Ha azt szeretné, hogy az e-mail küldése a Testreszabás nélkül történjen, válassza a **Tovább**, majd a **Küldés** lehetőséget.

## <a name="create-an-onboarding-guide-from-a-template-and-send-it-to-multiple-new-hires"></a>Felvételi útmutató létrehozása sablonból és küldés több újonnan felvett munkatársnak

Az Onboard lehetővé teszi, hogy egyszerre több újonnan felvett munkatársnak küldjön felvételi útmutatót.

1. A bal oldali menüben válassza a **Sablonok** lehetőséget.
2. A **Saját sablonok** területen válassza ki azt a sablont, amelyet be szeretne állítani az újonnan felvett munkatársaknak a felvételi útmutatóként.
3. Igény szerint szerkessze a sablont. Ne felejtse el rendszeresen elmenteni a munkát.
4. Ha befejezte a sablon szerkesztését, válassza az **Útmutatólétrehozása** parancsot.
5. Az **Útmutató létrehozása** ablakban válassza ki az **Egyszerre több embert kell felvennie?** lehetőséget.

    [![A fedélzeti útmutató létrehozása több új munkatársnak](./media/onboard-send-guide-multiple-people.png)](./media/onboard-send-guide-multiple-people.png)

6. Válassza az **új felvételi sablon** lehetőséget.
7. Az. xlsx fájl letöltését követően válassza a **Megnyitás** parancsot, adja meg az alkalmazottak adatait az Excel-munkafüzetben, majd mentse a munkafüzetet.

    [![Az Excel-sablon letöltése a fedélzeti útmutató több új munkatársnak történő küldéséhez](./media/onboard-send-guide-download-spreadsheet.png)](./media/onboard-send-guide-download-spreadsheet.png)

    > [!NOTE]
    > A munkafüzet szerkesztéséhez ki kell választania a **Szerkesztés engedélyezése** lehetőséget az Excelben.
    > 
    > [![Szerkesztés engedélyezése](./media/onboard-send-guide-enable-editing.png)](./media/onboard-send-guide-enable-editing.png)

8. Húzza az Excel-munkafüzetet a **Több útmutatólétrehozása** ablak kijelölt területére, vagy kattintson a területen bárhova, és keresse meg a fájlt a számítógépen.

    [![A szerkesztett munkafüzet húzása](./media/onboard-send-guide-drag-spreadsheet.png)](./media/onboard-send-guide-drag-spreadsheet.png)

9. Ha befejezte a felvételi útmutató szerkesztését, válassza a jobb felső sarokban látható **Küldés** parancsot. Majd tegye a következők egyikét:

    - **A hivatkozás másolása** hivatkozásra kattintva majd a **Másolás** kiválasztásával elküldheti a felvételi útmutató hivatkozását az új munkatársaknak.
    - Ha azt szeretné az e-mail-címet testreszabni a felvételi útmutatóban, válassza a **Végezze el az e-mail testreszabását küldés előtt**, majd a **Tovább** lehetőséget, szabja testre az e-mail-címet, majd válassza a **Küldés** lehetőséget.
    - Ha azt szeretné, hogy az e-mail küldése a Testreszabás nélkül történjen, válassza a **Tovább**, majd a **Küldés** lehetőséget.

## <a name="create-a-guide-without-using-a-template"></a>Útmutató létrehozása sablon használata nélkül

Nem feltétlenül kell sablonból létrehoznia egy útmutatót. Ha szeretné, létrehozhat az elejéről is egy útmutatót.

1. A bal oldali menüben válassza ki az **Útmutatók**, majd válassza a **Hozzáadás** gombot (a pluszjelet \[**+**\]).
2. Az **Új sablon létrehozás ablakban** a **Kit vesz fel?** részben adja meg az új munkatárs nevét vagy e-mail-címét. Ha az újonnan felvett munkatárs még nincs a rendszerben, válassza a **Hozzáadás most** lehetőséget, majd adja meg az alkalmazott adatait.

    ![[A felvételi útmutató információinak megadása](./media/onboard-create-a-guide-window.png)](./media/onboard-create-a-guide-window.png)

3. A **Mi a kezdés dátuma?** alatt válassza ki a kezdés dátumát.
4. Ha a felvételi útmutatót automatikusan kell kiküldeni az új munkatársnak egy megadott napon, győződjön meg arról, hogy az **Automatikus küldési dátum ütemezése** beállítás be van kapcsolva, majd válassza ki az automatikus küldés dátumát. Ha azonnal el szeretné küldeni az útmutatót, kapcsolja ki a **Automatikus küldési dátum ütemezése** beállítást.
5. Válassza a **Kész** lehetőséget.

## <a name="save-a-guide-as-a-template"></a>Az útmutató mentése sablonként

A felvételi útmutató sablonként is menthető. Ily módon időt takaríthat meg, amikor később további felvételi útmutatókat kell létrehoznia.

1. A bal oldali menüben válassza a **Guides** lehetőséget.
2. Válassza ki a **Továbbiak** gombot (három pont \[**…**\]) azon útmutatóhoz, amelyből sablont szeretne létrehozni, majd válassza a **Mentés sablonként** parancsot.

    ![[A felvételi útmutató mentése sablonként](./media/onboard-save-guide-as-template.png)](./media/onboard-save-guide-as-template.png)

3. Írja be az új sablon nevét a **Mentés új sablonként** ablakba, majd válassza a **Mentés** parancsot.

## <a name="next-steps"></a>Következő lépések

- [Bevezetési útmutatók és sablonok szerkesztése](./onboard-edit-guides-templates.md)
- [Osszon meg tartalmakat más közreműködőkkel](./onboard-share-template.md)
- [A feladatok és az alkalmazottak és bevezetési állapotának megtekintése](./onboard-view-status.md)
- [Toborzócsoportok létrehozása az Onboard alkalmazásban](./onboard-create-team.md)

### <a name="see-also"></a>Lásd még

- [Próbálja ki vagy vásárolja meg az Onboard alkalmazást](https://dynamics.microsoft.com/talent/onboard/)
- [Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban](./whats-new.md)
- [Kiadási tervek](https://docs.microsoft.com/business-applications-release-notes/index)
- [Támogatás kérése a Microsoft Dynamics 365 Talent alkalmazáshoz](./talent-support.md)
