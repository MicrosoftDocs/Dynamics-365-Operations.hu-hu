---
title: Dataverse-integráció konfigurálása
description: Ez a téma a Microsoft Dataverse és a Dynamics 365 Human Resources közötti integrációt írja le.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c4e68142045b72b139bdda8be707a73e21e568fd
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8065451"
---
# <a name="configure-dataverse-integration"></a>Dataverse-integráció konfigurálása


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A Microsoft Dataverse és a Dynamics 365 Human Resources között be- és kikacsolhatja az integrációt. Ezenkívül megtekintheti a szinkronizálási adatokat, törölheti a nyomonkövetési adatokat, valamint újraszinkronizálhat egy táblát a két környezet közötti adatproblémák elhárítása érdekében.

> [!NOTE]
> A Dataverse (a korábbi Common Data Service) rendszer kapcsolatos további tudnivalókat és a terminológiai frissítéseket lásd: [Mi a Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)

Ha kikapcsolja az integrációt, a felhasználók módosíthatják az emberi erőforrásokat vagy a Dataverse megoldást, de ezek a módosítások nem szinkronizálhatók a két környezet között.

Az adatintegráció Human Resources és a Dataverse között alapértelmezetten ki van kapcsolva.

Előfordulhat, hogy a következő helyzetekben ki szeretné kapcsolni az integrációt:

- Az adatokat az adatkezelési keretrendszeren keresztül tölti ki, és az adatokat többször kell importálni, hogy a megfelelő állapotba kerüljenek.

- Probléma adódott az adatokkal a Human Resources vagy a Dataverse programok valamelyikében. Ha kikapcsolta az integrációt, akkor úgy törölhet egy rekordot az egyik környezetből, hogy az a másikban megmarad. Amikor újra bekapcsolja az integrációt, az a rekord, amelynek környezetében nem történt törlés, szinkronizálva lesz abba a környezetbe, ahonnan törölte azt. A szinkronizálás azután kezdődik, hogy a **Dataverse-integráció nem fogadott kérelemszinkronizálási** kötegelt feladatot futtatja.

> [!WARNING]
> Az adatintegráció kikapcsolásakor ügyeljen arra, hogy ne szerkessze mindkét környezetben ugyanazt a rekordot. Az integráció visszakapcsolásakor az utoljára szerkesztett rekordot szinkronizálja a rendszer. Ezért ha nem ugyanazokat a változtatásokat hajtotta végre a rekordon mindkét környezetben, adatvesztés léphet fel.

## <a name="access-the-dataverse-integration-page"></a>A Dataverse-integráció oldal elérése

1. Abban a Human Resources példányban, ahol megtekinteni vagy konfigurálni szeretné a Dataverse rendszerrel való integrációs beállításokat, válassza ki a **Rendszerfelügyelet** csempét.

    [![Rendszerfelügyelet csempe.](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)

2. Válassza ki a **Hivatkozások** lapot.

    [![Hivatkozások lap.](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)

3. Az **Integrációk** menüpontban válassza a **Dataverse konfigurációja** elemet.

    [![Dataverse-konfigurációs hivatkozás.](./media/hr-admin-integration-dataverse-select.png)](./media/hr-admin-integration-dataverse-select.png)

## <a name="turn-data-integration-between-human-resources-and-dataverse-on-or-off"></a>Adatintegráció be- vagy kikapcsolása a Human Resources és a Dataverse között

- Ha be szeretné kapcsolni az integrációt, állítsa be, hogy **Microsoft Dataverse-integráció** oldalon a **Dataverse-integráció engedélyezése** értéke **Igen** legyen.

    > [!NOTE]
    > Amikor bekapcsolja az integrációt, az adatok szinkronizálása az után történik meg, hogy a **Dataverse-integráció nem fogadott kérelemszinkronizálási** kötegelt feladatot futtatja. Minden adatnak elérhetőnek kell lennie a kötegelt feladat befejezése után.

- Ha ki szeretné kapcsolni az integrációt, állítsa át a beállítást **Nem** értékre.

[![Dataverse-integráció be- és kikapcsolása.](./media/hr-admin-integration-dataverse-enable-disable.png)](./media/hr-admin-integration-dataverse-enable-disable.png)

> [!WARNING]
> Az adatáttelepítési feladatok végrehajtása közben erősen ajánlott kikapcsolni a Dataverse integrációt. A nagyméretű adatfeltöltések jelentősen befolyásolhatják a teljesítményt. Például 2000 dolgozó feltöltése több óráig is eltarthat, ha engedélyezve van az integráció, viszont kevesebb mint egy óráig tart, ha le van letiltva. A jelen példában megadott számok csak bemutató célt szolgálnak. A rekordok importálásához szükséges idő pontos mértékét számos tényező befolyásolhatja.

## <a name="view-data-integration-details"></a>Az adatintegráció részleteinek áttekintése

Az **Adminisztráció** gyorslapon, amely a **Microsoft Dataverse-integráció** oldalon található, megtekintheti a sorok összekapcsolásának módját a Human Resources és a Dataverse között.

- A tábla sorainak megtekintéséhez válassza ki táblát a **Dataverse-tábla** mezőben. A rács a kiválasztott táblához kapcsolódó összes sort megjeleníti.

> [!NOTE]
> Jelenleg nem minden Dataverse-tábla szerepel a listán. Csak olyan táblák jelennek meg, amelyek támogatják az egyéni mezők használatát a rácsban. Az új táblák a Human Resources folyamatos termékkiadásai révén válnak elérhetővé.

A rács a következő mezőket tartalmazza:

- **Dataverse-tábla** – a Dataverse-tábla neve.
- **Dataverse-tábla referenciája** – a Dataverse által rekord azonosítására használt azonosító. Ez az érték egyenértékű a Human Resources rendszerben található **RecId**-értékkel. Az azonosítót akkor találja meg, ha megnyitja a Dataverse-táblát a Microsoft Excel programban.
- **Human Resources-entitás neve** – az a Human Resources-entitás, amely utoljára szinkronizált adatokat a Dataverse rendszerbe. Az entitás Dataverse előtaggal vagy egy másik előtaggal rendelkezik.
- **Human Resources-referencia** – az a **RecId**-érték, amely a Human Resources alkalmazásban található rekordhoz van társítva.
- **Törölve a Dataverse-ből** – az az érték, amely azt jelzi, hogy a sort törölték-e a Dataverse rendszerből.

> [!NOTE]
> A Human Resources rekordjai a Dataverse rendszerben lévő soroknak felelnek meg.

## <a name="remove-the-association-of-a-human-resources-record-from-a-dataverse-row"></a>Human Resources-rekordtársítás eltávolítása egy Dataverse-sorból

Ha problémák merülnének fel a Human Resources és a Dataverse közötti adatszinkronizálás során, a nyomon követés törlésével és a nyomonkövetési tábla újraszinkronizálásával feloldhatja őket. Ha eltávolítja a társítást, majd módosítja vagy törli a sort a Dataverse rendszerben, a rendszer a módosításokat nem szinkronizálja a Human Resources alkalmazással. Ha módosításokat hajt végre a Human Resources alkalmazásban, létrejön egy új nyomonkövetési rekord, majd a sor frissül a Dataverse rendszerben.

- Ha el szeretne távolítani egy rekordtársítást a Human Resources és a Dataverse-sor között, válassza ki az entitást a **Dataverse-tábla** mezőben, majd válassza a **Nyomonkövetési adatok törlése** elemet.

[![Nyomonkövetési adatok törlése.](./media/hr-admin-integration-dataverse-clear-tracking.png)](./media/hr-admin-integration-dataverse-clear-tracking.png)

Ha szeretné, hogy a nyomon követés törlése után teljes szinkronizálás fusson a táblán, tekintse meg a következő eljárást.

## <a name="sync-a-table-between-human-resources-and-dataverse"></a>Tábla szinkronizálása a Human Resources és a Dataverse között

Ez a művelet akkor használható, ha:

- A Dataverse változásai túl lassan jelennek meg a Human Resources alkalmazásban.

- A nyomon követés törlése után frissítenie kell a nyomon követési táblát.

Teljes szinkronizálás futtatása egy táblához a Human Resources és Dataverse között:

1. A **Dataverse-tábla** mezőben válassza ki a táblát.

2. Válassza a **Szinkronizálás most** lehetőséget.

[![Teljes szinkronizálás futtatása.](./media/hr-admin-integration-dataverse-sync-now.png)](./media/hr-admin-integration-dataverse-sync-now.png)

## <a name="see-also"></a>Lásd még

[Dataverse-táblák](hr-developer-entities.md)<br>
[Dataverse virtuális táblák konfigurálása](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Human Resources – virtuális táblák – GYIK](hr-admin-virtual-entity-faq.md)<br>
[Mi az a Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Terminológia frissítései](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
