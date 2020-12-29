---
title: Felhasználói biztonság a szállítói portálon
description: Ez a cikk ismerteti a szállítói portált használó külső szállítók biztonságának beállítását. Az itt olvasható információk csak a Dynamics AX 2016. februári és 2016. májusi verzióira vonatkoznak.
author: mkirknel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 30231
ms.assetid: 3574db17-81c7-4c5a-999b-0098aa0b9cda
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 72f353448f3b5d1f816bb240a230e26529c9cec3
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429803"
---
# <a name="vendor-portal-user-security"></a>Szállítói portál felhasználói biztonsága

[!include [banner](../includes/banner.md)]

Ez a cikk ismerteti a szállítói portált használó külső szállítók biztonságának beállítását. Az itt olvasható információk csak a Dynamics AX 2016. februári és 2016. májusi verzióira vonatkoznak.

A Szállítói portál funkciót a Dynamics 365 for Operations rendszer 1611-es verziójának Kiterjesztett szállítói együttműködés funkciója váltotta le. A biztonságnak a szállítói együttműködésben való beállítására vonatkozó további tudnivalókat lásd: [Szállítói együttműködés beállítása és karbantartása](set-up-maintain-vendor-collaboration.md). A szállítói portálon korlátozott mennyiségű információ érhető el a beszerzési rendelésekkel (PO) kapcsolatban külső szállítók számára. A Microsoft Dynamics AX szállítói portáljánál fontos a felhasználói jogosultságok helyes beállítása, hogy a szállítók ne férhessenek hozzá véletlenül további információkhoz a Dynamics AX szolgáltatásban. **Fontos:** más felhasználókkal ellentétben a külső szállítóknak nem szabad **rendszerfelhasználó** szerepkörrel rendelkezniük. A **rendszerfelhasználó** szerepkör olyan jogosultságokhoz ad hozzáférést, amelyek nem megfelelők külső felhasználók számára.

## <a name="setting-up-a-vendor-portal-user"></a>A szállítói portál felhasználóinak beállítása
Mielőtt létrehozna egy felhasználói fiókot valaki számára, aki a szállítói portált fogja használni, be kell állítania a szállítót, hogy lehetővé váljon a szállítói együttműködés. Használja a **Beszerzési rendelési együttműködési** mezőt az **Általános** lapon, a **Szállítók** oldalon. A szállítói portált használó külső szállítók esetében a következő beállítást kell használni:

-   Regisztrálni kell egy Microsoft Azure Active Directory (AAD) felhasználói fiókot a szállító számára a **Felhasználók** oldalon a Dynamics AX rendszerben.
-   A szállítónak a **Szállító (külső)** biztonsági szerepkörrel kell rendelkeznie, nem pedig a **Rendszerfelhasználó** szerepkörrel. **Megjegyzés**: a **Rendszerfelhasználó** szerepkört automatikusan megadja a rendszer egy új felhasználói fiók létrehozásakor a Dynamics AX rendszerben. Ezért ezt a szerepkört el kell távolítani, és nyugtázni kell megjelenő figyelmeztetőüzenetet.
-   A szállítói felhasználó nem rendelkezhet olyan jogosultsággal, amellyel további mezőket adhat a PO-táblázatokból a saját PO-nézetéhez. A **Személyre szabás** lapon, a **Felhasználók** lapon állítsa be az **Explicit személyre szabás engedélyezve** lehetőségnél a **Nem** értéket.
-   A felhasználói fiókot egy regisztrált kapcsolattartó személyhez kell társítani. A **Felhasználók** oldalon, válasszon ki egy kapcsolattartót a **Név** mezőben. A kiválasztott személynek **Kapcsolattartó** szerepkörrel kell rendelkeznie az érintett szállítónál.

Ha egy adott személynek több szállítói fiókkal kell hozzáférnie a szállítói portálhoz (például mert külön jogi személyekről van szó), akkor ezen személy felhasználói fiókjaihoz ugyanazt a regisztrált kapcsolattartó személyt kell társírani. A **Szállító (külső)** szerepkör tartalmaz minden alapvető képességet, amelyek a szállítói portálon elérhető funkciók használatához szükségesek. Ezen beállítás segítségével garantálható, hogy a külső felhasználó által látható felhasználói felület csak a tervszerinti forgatókönyvre koncentrál.

<a name="additional-resources"></a>További erőforrások
--------

[Együttműködés a szállítókkal a Szállítói portálon keresztül](collaborate-vendors-vendor-portal.md)



