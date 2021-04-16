---
title: Példány másolása
description: A Microsoft Dynamics Lifecycle Services (LCS) szolgáltatással átmásolhat egy Microsoft Dynamics 365 Human Resources-adatbázist egy védőfalkörnyezetbe.
author: andreabichsel
ms.date: 07/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6cb8050980b9b54480d09a59379430cd229ff141
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801095"
---
# <a name="copy-an-instance"></a>Példány másolása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

A Microsoft Dynamics Lifecycle Services (LCS) szolgáltatással átmásolhat egy Microsoft Dynamics 365 Human Resources-adatbázist egy védőfalkörnyezetbe. Ha van másik tesztkörnyezete, akkor abból a környezetből is másolható az adatbázis a célként kiválasztott tesztkörnyezetbe.

Egy példány másolásához tartsa szem előtt a következő tanácsokat:

- A felülírni kívánt Human Resources példánynak védőfalkörnyezetnek kell lennie.

- A környezeteknek, ahonnan és ahová másolni kíván, ugyanabban a régióban kell lenniük. Nem másolhat régiók között.

- A célkörnyezetben rendszergazdának kell lennie ahhoz, hogy a példány másolása után bejelentkezhessen.

- A Human Resources adatbázisának másolása során nem másolja át a Microsoft Power Apps környezetben található elemeket (alkalmazásokat vagy adatokat). A Power Apps-környezet elemeinek másolásával kapcsolatos tudnivalókat lásd: [Környezet másolása](https://docs.microsoft.com/power-platform/admin/copy-environment). A felülírni kívánt Power Apps -könyezetnek védőfalkörnyezetnek kell lennie. A Power Apps éles környezet védőfalkörnyezetbe történő módosításához globális bérlői rendszergazdának kell lennie. A Power Apps-környezet módosításával kapcsolatos további tudnivalókat lásd: [Példány váltása](https://docs.microsoft.com/dynamics365/admin/switch-instance).

- Ha példányát egy tesztkörnyezetbe másolja , és szeretné integrálni a tesztkörnyezetét a Dataverse szolgáltatással, akkor újra kell alkalmaznia az egyéni mezőket a Dataverse-táblákra. Lásd: [Egyéni mezők alkalmazása a Dataverse-szolgáltatásra](hr-admin-setup-copy-instance.md?apply-custom-fields-to-common-data-service).

## <a name="effects-of-copying-a-human-resources-database"></a>A Human Resources-adatbázis másolásának hatásai

A Human Resources-adatbázis másolásakor a következő események történnek:

- A másolási folyamat törli a meglévő adatbázist a célkörnyezetből. A másolási folyamat befejezése után nem lehet visszaállítani a meglévő adatbázist.

- A célkörnyezet addig nem lesz elérhető, amíg a másolási folyamat be nem fejeződik.

- A Microsoft Azure Blob-tárolóban lévő dokumentumok nem kerülnek át egyik környezetből a másikba. Ennek megfelelően a rendszer nem másolja a csatolt dokumentumokat és sablonokat, és a forráskörnyezetben maradnak.

- Az összes felhasználó elérhetetlen lesz a rendszergazdai felhasználó és az egyéb belső szolgáltatási felhasználói fiókok kivételével. A Rendszergazda felhasználó törölheti vagy álcázhatja az adatokat, mielőtt a többi felhasználó visszakerül a rendszerbe.

- A Rendszergazda felhasználónak végre kell hajtania a szükséges konfigurációs változtatásokat, például az integrációs végpontok újracsatlakoztatását meghatározott szolgáltatásokhoz vagy URL-címekhez.

## <a name="copy-the-human-resources-database"></a>Human Resources-adatbázis másolása

A feladat végrehajtásához először másolja a példányt, majd jelentkezzen be a Microsoft Power Platform Admin Center programba a Power Apps-környezet másolásához.

> [!WARNING]
> Példány másolásakor a program törli az adatbázist a célpéldányban. A célpéldány nem érhető el a folyamat során.

1. Jelentkezzen be az LCS-rendszerbe, majd válassza ki a másolni kívánt példányt tartalmazó LCS-projektet.

2. Az LCS-projektben válassza a **Human Resources alkalmazás kezelése** csempét.

3. Válassza ki a másolni kívánt példányt, majd válassza a **Másolás** parancsot.

4. A **Példány másolása** munkaablakban válassza ki azt a példányt, amelyet felül szeretne írni, majd válassza a **Másolás** parancsot. Várjon, amíg a **Másolás állapota** mező értéke **Kész** értékre módosul.

   ![[Felülírandó példány kiválasztása](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. Válassza ki a **Power Platform** lehetőséget, majd jelentkezzen be a Microsoft Power Platform Admin Centerbe.

   ![[Válassza a Power Platform lehetőséget](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. Válassza ki a másolni kívánt Power Apps-környezetet, majd válassza a **Másolás** parancsot.

7. A másolási folyamat befejezése után jelentkezzen be a célpéldányba, és engedélyezze a Dataverse-integrációt. További tudnivalókért és utasításokért lásd: [A Dataverse-integráció konfigurálása](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).

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

- A rendszergazda kivételével minden felhasználó **Letiltva** állapotban van.

- Minden kötegelt feladat – kivéve néhány rendszerfeladatot – **Visszatartás** értékre van állítva.

## <a name="environment-admin"></a>Környezeti adminisztrátor

A cél védőfalkörnyezetében található összes felhasználót, többek között a rendszergazdákat is, felváltották a forráskörnyezet felhasználói. Egy példány másolása előtt győződjön meg arról, hogy Ön a forráskörnyezet rendszergazdája. Ha nem, akkor nem tud bejelentkezni a cél védőfalkörnyezetébe a másolás befejezése után.

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

További információkért az egyéni mezőkről lásd: [Egyéni mezők létrehozása és felhasználása](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/user-defined-fields).

## <a name="see-also"></a>Lásd még

[Emberi erőforrások létesítése](hr-admin-setup-provision.md)</br>
[Példány eltávolítása](hr-admin-setup-remove-instance.md)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]