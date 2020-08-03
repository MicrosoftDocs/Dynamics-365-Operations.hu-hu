---
title: Példány másolása
description: A Microsoft Dynamics Lifecycle Services (LCS) szolgáltatással átmásolhat egy Microsoft Dynamics 365 Human Resources-adatbázist egy védőfalkörnyezetbe.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
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
ms.openlocfilehash: b14baf49517f5d606038af20366944788b22eba2
ms.sourcegitcommit: 1ec931f8fe86bde27f6def36ea214a2a05fb22f6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/13/2020
ms.locfileid: "3554325"
---
# <a name="copy-an-instance"></a>Példány másolása

A Microsoft Dynamics Lifecycle Services (LCS) szolgáltatással átmásolhat egy Microsoft Dynamics 365 Human Resources-adatbázist egy védőfalkörnyezetbe. Ha van másik tesztkörnyezete, akkor abból a környezetből is másolható az adatbázis a célként kiválasztott tesztkörnyezetbe.

Egy példány másolásához a következőket kell biztosítania:

- A felülírni kívánt Human Resources példánynak védőfalkörnyezetnek kell lennie.

- A környezeteknek, ahonnan és ahová másolni kíván, ugyanabban a régióban kell lenniük. Nem másolhat régiók között.

- A célkörnyezetben rendszergazdának kell lennie ahhoz, hogy a példány másolása után bejelentkezhessen.

- A Human Resources adatbázisának másolása során nem másolja át a Microsoft PowerApps környezetben található elemeket (alkalmazásokat vagy adatokat). A PowerApps-környezet elemeinek másolásával kapcsolatos tudnivalókat lásd: [Környezet másolása](https://docs.microsoft.com/power-platform/admin/copy-environment). A felülírni kívánt PowerApps -könyezetnek védőfalkörnyezetnek kell lennie. A PowerApps éles környezet védőfalkörnyezetbe történő módosításához globális bérlői rendszergazdának kell lennie. A PowerApps-környezet módosításával kapcsolatos további tudnivalókat lásd: [Példány váltása](https://docs.microsoft.com/dynamics365/admin/switch-instance).

## <a name="effects-of-copying-a-human-resources-database"></a>A Human Resources-adatbázis másolásának hatásai

A Human Resources-adatbázis másolásakor a következő események történnek:

- A másolási folyamat törli a meglévő adatbázist a célkörnyezetből. A másolási folyamat befejezése után nem lehet visszaállítani a meglévő adatbázist.

- A célkörnyezet addig nem lesz elérhető, amíg a másolási folyamat be nem fejeződik.

- A Microsoft Azure Blob-tárolóban lévő dokumentumok nem kerülnek át egyik környezetből a másikba. Emiatt a rendszer nem másolja a csatolt dokumentumokat és sablonokat, és a forráskörnyezetben maradnak.

- Az összes felhasználó elérhetetlen lesz a rendszergazdai felhasználó és az egyéb belső szolgáltatási felhasználói fiókok kivételével. Emiatt a Rendszergazda felhasználó törölheti vagy álcázhatja az adatokat, mielőtt a többi felhasználó visszakerül a rendszerbe.

- A Rendszergazda felhasználónak végre kell hajtania a szükséges konfigurációs változtatásokat, például az integrációs végpontok újracsatlakoztatását meghatározott szolgáltatásokhoz vagy URL-címekhez.

## <a name="copy-the-human-resources-database"></a>Human Resources-adatbázis másolása

A feladat végrehajtásához először másolja a példányt, majd jelentkezzen be a Microsoft Power Platform Admin Center programba a PowerApps-környezet másolásához.

> [!WARNING]
> Példány másolásakor a program törli az adatbázist a célpéldányban. A célpéldány nem érhető el a folyamat során.

1. Jelentkezzen be az LCS-rendszerbe, majd válassza ki a másolni kívánt példányt tartalmazó LCS-projektet.

2. Az LCS-projektben válassza a **Human Resources alkalmazás kezelése** csempét.

3. Válassza ki a másolni kívánt példányt, majd válassza a **Másolás** parancsot.

4. A **Példány másolása** munkaablakban válassza ki azt a példányt, amelyet felül szeretne írni, majd válassza a **Másolás** parancsot. Várjon, amíg a **Másolás állapota** mező értéke **Kész** értékre módosul.

   ![[Felülírandó példány kiválasztása](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. Válassza ki a **Power Platform** lehetőséget, majd jelentkezzen be a Microsoft Power Platform Admin Centerbe.

   ![[Válassza a Power Platform lehetőséget](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. Válassza ki a másolni kívánt PowerApps-környezetet, majd válassza a **Másolás** parancsot.

7. A másolási folyamat befejezése után jelentkezzen be a célpéldányba, és engedélyezze a Common Data Service-integrációt. További tudnivalókért és utasításokért lásd: [A Common Data Service-integráció konfigurálása](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).

## <a name="data-elements-and-statuses"></a>Adatelemek és állapotok

A rendszer nem másolja át a következő adatelemeket a Human Resources példányának másolásakor:

- E-mail-címek a **LogisticsElectronicAddress** táblában

- A kötegelt feladat előzményei a **BatchJobHistory**, a **BatchHistory**és a **BatchConstraintHistory** táblákban

- A Simple Mail Transfer Protocol (SMTP)-jelszó a **SysEmailSMTPPassword** táblában

- Az SMTP-közvetítőkiszolgáló a **SysEmailParameters** táblában

- A **PrintMgmtSettings** és a **PrintMgmtDocInstance** táblákban lévő nyomtatáskezelési beállítások

- Környezetspecifikus rekordok a **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig** és **BatchServerGroup** táblákban

- Dokumentumok mellékletei a DocuValue táblában. Ezek a mellékletek a Microsoft Office forráskörnyezetben felülírt sablonokat tartalmazzák

- Kapcsolati karakterlánc a **PersonnelIntegrationConfiguration** táblában

Néhány elemet nem másolt át a program, mert környezetspecifikusak. Ilyenek például a **BatchServerConfig** és a **SysCorpNetPrinters** rekordok. A rendszer más elemeket nem másol a támogatási jegyek mennyisége miatt. Előfordulhat például, hogy a rendszer ismétlődő e-maileket küld el, mivel az SMTP továbbra is engedélyezve van a felhasználó jóváhagyásának tesztelésére szolgáló (védőfal-) környezetben, a rendszer érvénytelen integrációs üzeneteket küld, mert a kötegelt feladatok továbbra is engedélyezve vannak, és a felhasználók engedélyezésére csak a rendszergazdák által végrehajtott frissítés utáni törlési műveletek elvégzése után kerül sor.

Ezenkívül a következő állapotok módosulnak egy példány másolásakor:

- A rendszergazda kivételével minden felhasználó **Letiltva** állapotban van.

- Minden kötegelt feladat – kivéve néhány rendszerfeladatot – **Visszatartás** értékre van állítva.

## <a name="environment-admin"></a>Környezeti adminisztrátor

A cél védőfalkörnyezetében található összes felhasználót, többek között a rendszergazdákat is, felváltották a forráskörnyezet felhasználói. Egy példány másolása előtt győződjön meg arról, hogy Ön a forráskörnyezet rendszergazdája. Ha nem, akkor nem tud bejelentkezni a cél védőfalkörnyezetébe a másolás befejezése után.

A cél-védőfalkörnyezet minden nem rendszergazdai felhasználója le van tiltva, megakadályozva a nem kívánt bejelentkezéseket a védőfalkörnyezetben. Ha szükséges, a rendszergazdák újra engedélyezhetik a felhasználókat.
