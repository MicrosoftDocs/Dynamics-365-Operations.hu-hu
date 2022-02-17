---
title: A kettős írás Finance and Operations alkalmazásokban és a Dataverse-ben történő konfigurálásának igazolása
description: Ez a témakör bemutatja, hogyan állapíthatja meg, hogy a kettős írás be van-e konfigurálva a Finance and Operations alkalmazásokban és a Dataverse.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 3fa16a450032464e445ae166f0699fe0dc388071
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8062800"
---
# <a name="verify-dual-write-configuration-in-finance-and-operations-apps-and-dataverse"></a>A kettős írás Finance and Operations alkalmazásokban és a Dataverse-ben történő konfigurálásának igazolása

[!include [banner](../../includes/banner.md)]





Ez a témakör hibaelhárítási információkat tartalmaz a Finance and Operations alkalmazások és a kettős írási integrációhoz Dataverse. Pontosabban elmagyarázza, hogyan állapíthatja meg, hogy a kettős írás be van-e konfigurálva a Finance and Operations alkalmazásokban és a Dataverse.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>Ellenőrizze, hogy a kettős írás be van-e állítva egy Finance and Operations alkalmazásban

Annak eldöntéséhez, hogy a sorok frissítésre való mentéskor megjelenő hibák a kettős írásból származnak-e, először ellenőrizze, hogy a kettős írás konfigurálva van-e.

+ Ha rendszergazdai jogosultságokkal rendelkezik a Finance and Operations alkalmazásban, lépjen a következő helyre: **Munkaterületek \> Adatkezelés**, és válassza ki a lehetőséget **Kettős írás** csempe. Ha megjelenik a csatolt környezetek részletei és a futó táblaleképezések listája, akkor a kettős írás konfigurálva van.

    ![A Finance and Operations alkalmazás kapcsolatának ellenőrzése, ha rendszergazdai jogosultságokkal rendelkezik.](media/verify_fin_ops_1.png)

+ Ha nincs rendszergazdai jogosultsága, a következő hibaüzenet jelenik meg: *Nem lehet adatokat írni az \<entity name\>* entitásba. A következő ábrán látható példában nem hozhat létre ügyfélsort a Finance and Operations alkalmazásban, mert a kettős írás konfigurálva van, de az ügyfélcsoport és a fizetési feltételek referenciaadatai nem léteznek a következőben:Dataverse.

    ![A Finance and Operations alkalmazás kapcsolatának ellenőrzése, ha nem rendelkezik rendszergazdai jogosultságokkal.](media/verify_fin_ops_2.png)

A Finance and Operations alkalmazásokban történő adatok létrehozása során felmerülő problémák megoldásával kapcsolatos információkért lásd: [Az élő szinkronizálással kapcsolatos problémák elhárítása](dual-write-troubleshooting-live-sync.md).

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a>Ellenőrizze, hogy a kettős írás be van-e állítva a Dataverse szolgáltatásban

Amikor adatokat hoz létre, ha a **Vállalat** oszlopot látja a Dataverse lapjain, akkor a kettős írás konfigurálva van.

![A Dataverse kapcsolatának ellenőrzése.](media/verify_cds.png)

Az Dataverse szolgáltatásban adatok létrehozásakor jelentkező problémák megoldásával kapcsolatos tudnivalókat lásd az [Élő szinkronizálási problémák elhárítása](dual-write-troubleshooting-live-sync.md) című témakörben.

Azzal kapcsolatosan, hogy hogyan tekinteti meg a hibák részleteit, amikor a Dataverse szolgáltatásban hoz létre adatokat következő témakörben talál: [A beépülő modul nyomkövetési naplójának engedélyezése és megtekintése a Dataverse szolgáltatásban a hiba részleteinek megtekintéséhez](dual-write-troubleshooting.md#enable-view-trace).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]