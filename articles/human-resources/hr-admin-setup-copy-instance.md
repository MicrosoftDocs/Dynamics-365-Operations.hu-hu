---
title: Példány másolása
description: A Microsoft Dynamics Lifecycle Services (LCS) szolgáltatással átmásolhat egy Microsoft Dynamics 365 Human Resources-adatbázist egy védőfalkörnyezetbe.
author: twheeloc
ms.date: 07/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 20a2ffb44f9b99800146e3365e6f0d6df8e9a75e
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9324260"
---
# <a name="copy-an-instance"></a>Példány másolása

_**Érvényes:** Emberi erőforrások a különálló infrastruktúrán_ 

> [!NOTE]
> 2022 június elején az Emberi erőforrások környezeteket csak a pénzügyek és műveletek alkalmazás-infrastruktúráira lehet telepíteni. A további tudnivalókat lásd [az Emberi erőforrások biztosítása a pénzügyi és a műveleti infrastruktúra területén](hr-admin-setup-provision-fo.md).

> [!IMPORTANT]
> A pénzügyi és műveleti infrastruktúra nem támogatja a példánymásoló funkciót. Új környezeteket telepíthet, és az adatbázismozgások segítségével másolatokat hozhat létre. Az önkiszolgáló rendszer telepítésekkel kapcsolatos további tudnivalókat lásd [az önkiszolgáló rendszer telepítésének áttekintésében](../fin-ops-core/dev-itpro/deployment/infrastructure-stack.md). A pénzügyi és műveleti infrastruktúrával kapcsolatos adatbázismozgásokkal kapcsolatos további tudnivalókat lásd [az Adatbázismozgási műveletek kezdőlapján](../fin-ops-core/dev-itpro/database/dbmovement-operations.md).

A Microsoft Dynamics Lifecycle Services (LCS) szolgáltatással átmásolhat egy Microsoft Dynamics 365 Human Resources-adatbázist egy védőfalkörnyezetbe. Ha van másik tesztkörnyezete, akkor abból a környezetből is másolható az adatbázis a célként kiválasztott tesztkörnyezetbe.

Egy példány másolásához tartsa szem előtt a következő tanácsokat:

- A felülírni kívánt Human Resources példánynak védőfalkörnyezetnek kell lennie.

- A környezeteknek, ahonnan és ahová másolni kíván, ugyanabban a régióban kell lenniük. Nem másolhat régiók között.

- A célkörnyezetben rendszergazdának kell lennie ahhoz, hogy a példány másolása után bejelentkezhessen.

- A Human Resources adatbázisának másolása során nem másolja át a Microsoft Power Apps környezetben található elemeket (alkalmazásokat vagy adatokat). A Power Apps-környezet elemeinek másolásával kapcsolatos tudnivalókat lásd: [Környezet másolása](/power-platform/admin/copy-environment). A felülírni kívánt Power Apps -könyezetnek védőfalkörnyezetnek kell lennie. A Power Apps éles környezet védőfalkörnyezetbe történő módosításához globális bérlői rendszergazdának kell lennie. A Power Apps-környezet módosításával kapcsolatos további tudnivalókat lásd: [Példány váltása](/dynamics365/admin/switch-instance).

- Ha példányát egy tesztkörnyezetbe másolja , és szeretné integrálni a tesztkörnyezetét a Dataverse szolgáltatással, akkor újra kell alkalmaznia az egyéni mezőket a Dataverse-táblákra. Lásd: [Egyéni mezők alkalmazása a Dataverse-szolgáltatásra](hr-admin-setup-copy-instance.md?apply-custom-fields-to-common-data-service).

## <a name="effects-of-copying-a-human-resources-database"></a>A Human Resources-adatbázis másolásának hatásai

> [!Note]
> 2022. augusztus 1-ével kezdődően Microsoft Azure a Blob tárolóban található dokumentumok bekerülnek a termelési környezetek jelölőnégyzet-környezetbe való másolása során. A csatolt dokumentumok és sablonok a forráskörnyezetből a célkörnyezetbe másolhatók.

A Human Resources-adatbázis másolásakor a következő események történnek:

- A másolási folyamat törli a meglévő adatbázist a célkörnyezetből. A másolási folyamat befejezése után nem lehet visszaállítani a meglévő adatbázist.

- A célkörnyezet addig nem lesz elérhető, amíg a másolási folyamat be nem fejeződik.

- A "Rendszergazda" biztonsági szerepkörrel rendelkező felhasználók és más belső szolgáltatási felhasználói fiókok kivételével egyik felhasználó sem lesz elérhető. A rendszergazda felhasználó még azelőtt törölheti az adatokat, hogy más felhasználók visszatérhetnek a rendszerbe.

- A "Rendszergazda" biztonsági szerepkörrel rendelkező felhasználóknak el kell végezniük a szükséges konfigurációs módosításokat, például az integrációs végpontok újrakapcsolását bizonyos szolgáltatásokhoz vagy URL-címekhez.

## <a name="copy-the-human-resources-database"></a>Human Resources-adatbázis másolása

A feladat végrehajtásához először másolja a példányt, majd jelentkezzen be a Microsoft Power Platform Admin Center programba a Power Apps-környezet másolásához.

> [!WARNING]
> Példány másolásakor a program törli az adatbázist a célpéldányban. A célpéldány nem érhető el a folyamat során.

1. Jelentkezzen be az LCS-rendszerbe, majd válassza ki a másolni kívánt példányt tartalmazó LCS-projektet.

2. Az LCS-projektben válassza a **Human Resources alkalmazás kezelése** csempét.

3. Válassza ki a másolni kívánt példányt, majd válassza a **Másolás** parancsot.

4. A **Példány másolása** munkaablakban válassza ki azt a példányt, amelyet felül szeretne írni, majd válassza a **Másolás** parancsot. Várja meg, amíg **a Másolás állapotmező** befejezve **lesz**.

   ![[Válassza ki a felülírni kívánt példányt.](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. Válassza ki a **Power Platform** lehetőséget, majd jelentkezzen be a Microsoft Power Platform Admin Centerbe.

   ![[Válassza ki Power Platform.](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. Válassza ki a másolni kívánt Power Apps-környezetet, majd válassza a **Másolás** parancsot.

A környezetek másolási lehetőségével kapcsolatos további Power Apps tudnivalókat lásd [A környezet másolása tudnivalókat tartalmaz](/power-platform/admin/copy-environment#copy-an-environment-1).

7. A másolási folyamat befejezése után jelentkezzen be a célpéldányba, és engedélyezze a Dataverse-integrációt. További tudnivalókért és utasításokért lásd: [A Dataverse-integráció konfigurálása](./hr-admin-integration-common-data-service.md).

## <a name="data-elements-and-statuses"></a>Adatelemek és állapotok

A rendszer nem másolja át a következő adatelemeket a Human Resources példányának másolásakor:

- E-mail-címek a **LogisticsElectronicAddress** táblában

- A kötegelt feladat előzményei a **BatchJobHistory**, a **BatchHistory** és a **BatchConstraintHistory** táblákban

- A Simple Mail Transfer Protocol (SMTP)-jelszó a **SysEmailSMTPPassword** táblában

- Az SMTP-közvetítőkiszolgáló a **SysEmailParameters** táblában

- A **PrintMgmtSettings** és a **PrintMgmtDocInstance** táblákban lévő nyomtatáskezelési beállítások

- Környezetspecifikus rekordok a **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig** és **BatchServerGroup** táblákban

- Dokumentumok mellékletei a DocuValue táblában. Ezek a mellékletek a Microsoft Office forráskörnyezetben felülírt sablonokat tartalmazzák

- Kapcsolati karakterlánc a **PersonnelIntegrationConfiguration** táblában

Néhány elemet nem másolt át a program, mert környezetspecifikusak. Ilyenek például a **BatchServerConfig** és a **SysCorpNetPrinters** rekordok. A rendszer más elemeket nem másol a támogatási jegyek mennyisége miatt. Példa:

- Ismétlődő e-mailek küldése történhet, mert az SMTP továbbra is engedélyezve van a felhasználói elfogadás (teszt) környezetében.

- A program érvénytelen integrációs üzeneteket küld, mert a kötegelt feladatok továbbra is engedélyezve vannak.

- A felhasználók engedélyezhetők, mielőtt a rendszergazdák elvégezhetnék a frissítés utáni karbantartási műveleteket.

Ezenkívül a következő állapotok módosulnak egy példány másolásakor:

- A "Rendszergazda" biztonsági szerepkörrel rendelkező felhasználók kivételével minden felhasználó **Letiltott** állapotra van beállítva.

- Minden kötegelt feladat – kivéve néhány rendszerfeladatot – **Visszatartás** értékre van állítva.

## <a name="environment-admin"></a>Környezeti adminisztrátor

A cél védőfalkörnyezetében található összes felhasználót, többek között a rendszergazdákat is, felváltották a forráskörnyezet felhasználói. Egy példány másolása előtt győződjön meg arról, hogy Ön a forráskörnyezet rendszergazdája. Ha nem, akkor nem tud bejelentkezni a cél ezredmásodógép-környezetbe, miután a másolás befejeződött.

A cél-védőfalkörnyezet minden nem rendszergazdai felhasználója le van tiltva, megakadályozva a nem kívánt bejelentkezéseket a védőfalkörnyezetben. Ha szükséges, a rendszergazdák újra engedélyezhetik a felhasználókat.

## <a name="apply-custom-fields-to-dataverse"></a>Egyéni mezők alkalmazása a Dataverse-szolgáltatásra

Ha példányát egy tesztkörnyezetbe másolja , és szeretné integrálni a tesztkörnyezetét a Dataverse szolgáltatással, akkor újra kell alkalmaznia az egyéni mezőket a Dataverse-táblákra.

A Dataverse-táblákon közzétett egyéni mezők esetében hajtsa végre a következő lépéseket:

1. Nyissa meg az egyéni mezőt, és válassza a **Szerkesztés** elemet.

2. Törölje az **Engedélyezve** jelölőnégyzet jelölését minden olyan cdm_* entitás esetében, amelynél engedélyezve van az egyéni mező.

3. Válassza a **Módosítások alkalmazása** lehetőséget.

4. Válassza ismét a **Szerkesztés** lehetőséget.

5. Jelölj be az **Engedélyezve** jelölőnégyzetet minden olyan cdm_* entitás esetében, amelynél engedélyezve van az egyéni mező.

6. Válassza ismét a **Módosítások alkalmazása** lehetőséget.

A kijelölés törlése, változtatások alkalmazása, kijelölés újra, és változtatások ismételt alkalmazása arra utasítja a sémát, hogy frissítsen a Dataverse-szolgáltatásban, hogy tartalmazza az egyéni mezőket.

További információkért az egyéni mezőkről lásd: [Egyéni mezők létrehozása és felhasználása](../fin-ops-core/fin-ops/get-started/user-defined-fields.md).

## <a name="see-also"></a>Lásd még

[Emberi erőforrások létesítése](hr-admin-setup-provision.md)</br>
[Példány eltávolítása](hr-admin-setup-remove-instance.md)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
