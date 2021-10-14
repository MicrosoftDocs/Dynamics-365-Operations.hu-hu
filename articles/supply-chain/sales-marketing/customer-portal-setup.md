---
title: Az ügyfélportál telepítése, beállítása és frissítése
description: Ez a témakör tartalmazza az Ügyfélportál licencelési adatait és telepítési útmutatását.
author: Henrikan
ms.date: 06/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 3b415252ef93987765d8970cde6b45f397136afd
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572649"
---
# <a name="install-set-up-and-update-the-customer-portal"></a>Az ügyfélportál telepítése, beállítása és frissítése

[!include [banner](../includes/banner.md)]
[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="licensing-requirements"></a>Licencelési követelmények

A Ügyfélportál kiépítése érdekében a következő licencekkel kell rendelkeznie:

- **Power Apps-portálok** – Ez a licenc szükséges a Ügyfélportál hosztolásához. A portálok a használat alapján vannak licencelve. A további tudnivalókat lásd a [Power Apps-portálok licencelési követelményei](/power-platform/admin/powerapps-flow-licensing-faq#portals) részben.
- **Kettős írás** – Rendelkeznie kell a szükséges licencekkel, hogy a Supply Chain Management táblák számára lehetővé tegye a kettős írást. További tudnivalókért lásd a [kettős írás rendszerkövetelményeit](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).

## <a name="dependencies-on-dual-write-and-power-apps-portals"></a>A kettős írással és Power Apps-portálokkal kapcsolatos függőségek

Az Ügyfélportál a Power Apps-portálokon és a kettős íráson alapul, ahogy az a következő ábrán látható.

![Ügyfélportál függőségei.](media/customer-portal-elements.png "Ügyfélportál függőségei")

A Supply Chain Management egyéb szolgáltatásaitól eltérően a Customer Portal-sablon a Power Apps-portálokra épül. Ezért az Ügyfélportált korlátozzák a Power Apps portálok és a kettős írás tábláinak funkcionalitása és képességei.

## <a name="required-setup-to-enable-the-customer-portal"></a><a name="required-setup"></a>A Ügyfélportál engedélyezéséhez szükséges beállítás

Miután elvégezte a szükséges licencek megadását, a [kettős írás kezdeti szinkronizálási útmutatóban](/dynamics365/supply-chain/sales-marketing/enable-entity-map) leírtaknak megfelelően beállíthatja a kettős írást.

Ügyeljen arra, hogy a következő tábla-hozzárendeléseket engedélyezze a kettős írásban:

- Értékesítési rendelés fejléce
- Értékesítési rendelés részletei
- Számlák
- Névjegyek
- Termékek

A beállítás befejezése után telepítheti az Ügyfélportál sablonját.

## <a name="provision-the-customer-portal"></a>Az Ügyfélportál telepítése

A Kezdés előtt győződjön meg arról, hogy már végrehajtotta a [szükséges beállításokat](#required-setup). Ezt követően végezze el a következő lépéseket a Ügyfélportál létesítéséhez.

1. Ugorjon a [make.powerapps.com](https://make.powerapps.com/) oldalra.
2. Győződjön meg arról, hogy a környezetben, amit használ a kettős írás engedélyezve van.
3. A **Létrehozás** lapon görgessen a **Kezdés sablonból** szakaszhoz, és válassza ki azt a sablont, amelynek neve az **Ügyfélportál**.
4. Kövesse a képernyőn megjelenő utasításokat.

A létesítés befejezése után a **Kezdőlap** a **Saját alkalmazások** területén érheti el az Ügyfélportált.

> [!NOTE]
> Ha a kettős írás megoldás nincs telepítve a környezetben, amelyen dolgozik, hibaüzenet jelenik meg, és a Ügyfélportál nem lesz kiépítve.

## <a name="update-the-customer-portal"></a>Az Ügyfélportál frissítése

Később több funkció is hozzáadható a Ügyfélportálhoz. A Microsoft által az mögöttes megoldás-összetevőkre vonatkozóan végrehajtott módosítások automatikusan megjelennek az Ön környezetében. A környezetben létesített webhely azonban nem fogja automatikusan tükrözni a konfigurációs adatokon elvégzett változtatásokat. Ezeket a változtatásokat manuálisan kell alkalmazni a kód új sablonból történő beolvasásával, és a kiépített webhellyel történő egyesítésével.

## <a name="additional-resources"></a>További erőforrások

A Ügyfélportál beállításával és testreszabásával kapcsolatos tudnivalók elsajátítását a következő dokumentációk áttekintésével kezdheti meg:

- [Power Apps portálok dokumentációja](/powerapps/maker/portals/overview)
- [Kettős írás dokumentációja](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)

A portálok hatékony kezeléséhez ismernie kell a Power Apps-portálokat és a Microsoft Dataverse-életciklust. További információért tekintse át az alábbi forrásokat:

- [A portál életciklusáról](/powerapps/maker/portals/admin/portal-lifecycle)
- [Portál frissítése](/powerapps/maker/portals/admin/upgrade-portal)
- [Portál konfigurációjának áttelepítése](/powerapps/maker/portals/admin/migrate-portal-configuration)
- [Megoldás életciklus-kezelése: Dynamics 365 for Customer Engagement alkalmazásokhoz](https://www.microsoft.com/download/details.aspx?id=57777)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]