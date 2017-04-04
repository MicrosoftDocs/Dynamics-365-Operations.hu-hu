---
title: "Szállítói portál felhasználói biztonság"
description: "Ez a cikk ismerteti a szállítói portált használó külső szállítók biztonságának beállítását. Ezt az információt csak azokra a február 2016 &amp;Dynamics AX verziói május 2016."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysUserManagement
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 30231
ms.assetid: 3574db17-81c7-4c5a-999b-0098aa0b9cda
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 3a5c6a256f8330ba238ea3c0c25f14b10a9a58e6
ms.lasthandoff: 03/31/2017


---

# <a name="vendor-portal-user-security"></a>Szállítói portál felhasználói biztonság

Ez a cikk ismerteti a szállítói portált használó külső szállítók biztonságának beállítását. Ezt az információt csak azokra a február 2016 &amp;Dynamics AX verziói május 2016.

A Szállítói portál funkciók kiterjesztett szállító csoportmunka 365 Dynamics műveletek verzió 1611 váltotta ki. Szállító együttműködési biztonsági beállításával kapcsolatos további tudnivalókért lásd: [Set up és karbantartása a szállítói együttműködési](set-up-maintain-vendor-collaboration.md). A szállítói portálon korlátozott mennyiségű információ érhető el a beszerzési rendelésekkel (PO) kapcsolatban külső szállítók számára. A Microsoft Dynamics AX szállítói portáljánál fontos a felhasználói jogosultságok helyes beállítása, hogy a szállítók ne férhessenek hozzá véletlenül további információkhoz a Dynamics AX szolgáltatásban. **Fontos:** más felhasználókkal ellentétben a külső szállítóknak nem szabad **rendszerfelhasználó** szerepkörrel rendelkezniük. A **rendszerfelhasználó** szerepkör olyan jogosultságokhoz ad hozzáférést, amelyek nem megfelelők külső felhasználók számára.

## <a name="setting-up-a-vendor-portal-user"></a>A szállítói portál felhasználóinak beállítása
Mielőtt létrehozna egy felhasználói fiókot valaki számára, aki a szállítói portált fogja használni, be kell állítania a szállítót, hogy lehetővé váljon a szállítói együttműködés. Használja a **Beszerzési rendelési együttműködési** mezőt az **Általános** lapon, a **Szállítók** oldalon. A szállítói portált használó külső szállítók esetében a következő beállítást kell használni:

-   Regisztrálni kell egy Microsoft Azure Active Directory (AAD) felhasználói fiókot a szállító számára a **Felhasználók** oldalon a Dynamics AX rendszerben.
-   A szállítónak a **Szállító (külső)** biztonsági szerepkörrel kell rendelkeznie, nem pedig a **Rendszerfelhasználó **szerepkörrel. **Megjegyzés:** a **Rendszerfelhasználó** szerepkört automatikusan megadja a rendszer egy új felhasználói fiók létrehozásakor a Dynamics AX rendszerben. Ezért ezt a szerepkört el kell távolítani, és nyugtázni kell megjelenő figyelmeztetőüzenetet.
-   A szállítói felhasználó nem rendelkezhet olyan jogosultsággal, amellyel további mezőket adhat a PO-táblázatokból a saját PO-nézetéhez. A **Személyre szabás** lapon, a **Felhasználók** lapon állítsa be az **Explicit személyre szabás engedélyezve** lehetőségnél a **Nem** értéket.
-   A felhasználói fiókot egy regisztrált kapcsolattartó személyhez kell társítani. A **Felhasználók** oldalon, válasszon ki egy kapcsolattartót a **Név** mezőben. A kiválasztott személynek **Kapcsolattartó** szerepkörrel kell rendelkeznie az érintett szállítónál.

Ha egy adott személynek több szállítói fiókkal kell hozzáférnie a szállítói portálhoz (például mert külön jogi személyekről van szó), akkor ezen személy felhasználói fiókjaihoz ugyanazt a regisztrált kapcsolattartó személyt kell társírani. A **Szállító (külső)** szerepkör tartalmaz minden alapvető képességet, amelyek a szállítói portálon elérhető funkciók használatához szükségesek. Ezen beállítás segítségével garantálható, hogy a külső felhasználó által látható felhasználói felület csak a tervszerinti forgatókönyvre koncentrál.

<a name="see-also"></a>Lásd még
--------

[Vendor collaboration](collaborate-vendors-vendor-portal.md)


