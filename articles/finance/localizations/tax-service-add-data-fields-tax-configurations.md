---
title: Adatmezők hozzáadása adókonfigurációkhoz
description: Ez a cikk bemutatja, hogyan lehet adatmezők hozzáadásával testreszabni az adókonfigurációkat.
author: Kai-Cloud
ms.date: 10/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 894c42f444d27b807288b84c7b9c620ad0121fa9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872326"
---
# <a name="add-data-fields-in-tax-configurations"></a>Adatmezők hozzáadása adókonfigurációkhoz

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogyan [lehet testreszabni az adókonfigurációkat az adóintegrációban hozzáadott adatmezők segítségével](tax-service-add-data-fields-tax-integration-by-extension.md).

## <a name="customize-the-tax-data-model"></a>Az adóadatmodell konfigurációjának testreszabása

1. A Microsoft Dynamics 365 Pénzügyben menjen az Elektronikus jelentési **adó** > **konfigurációihoz**.
2. A konfigurációs fán válassza az **Adószámítás adat-modell** lehetőséget. Majd a Műveleti ablaktáblán kattintson a **Konfiguráció létrehozása** elemre. 

  > [!NOTE] 
  > Ha nincs elérhető konfigurációs szolgáltató, hozzon létre egyet, és tegye aktívvá az adókonfigurációban. További információért tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.
  
3. A legördülő párbeszédpanelen jelölje ki az **Adóköteles dokumentummodell származtatva névből: Számítási adatmodell - Microsoft** lehetőséget, írja be az új adóadatmodell nevét, majd válassza a **Konfiguráció létrehozása** lehetőséget.
4. Jelölje ki az éppen létrehozott adóadatmodellt, majd a Műveleti panelen válassza a **Tervező** lehetőséget.
5. Bontsa ki az adatmodellfát, válassza a **Sorok** lehetőséget, majd válassza az **Új** lehetőséget.
6. A **Csomópont létrehozása** párbeszédpanelen adjon meg egy nevet, adja meg az elemtípust, majd válassza a **Hozzáadás** lehetőséget.
7. Adja hozzá a szükséges oszlopokat.
8. Válassza a Művelet panel **Mentés** elemét, majd válassza az **Befejezés** elemet.
9. Zárja be a lapot, és tekintse meg az adóadat-modell befejezett verzióját.

## <a name="customize-the-tax-configuration"></a>Az adókonfiguráció testreszabása

1. A Finance alkalmazásban nyissa meg az **Elektronikus jelentéskészítés** > **Konfigurációk** lehetőséget.
2. A konfigurációs fán válassza az **Adószámítás konfiguráció** lehetőséget. Majd a Műveleti ablaktáblán kattintson a **Konfiguráció létrehozása** elemre.
3. A legördülő párbeszédpanelen jelölje ki az **Adószolgáltatás-konfiguráció származtatva névből: Adószámítás konfiguráció - Microsoft** lehetőséget, írja be az új adókonfiguráció nevét, majd válassza a **Konfiguráció létrehozása** lehetőséget.
4. Jelölje ki az éppen létrehozott adókonfigurációt, majd a Műveleti panelen válassza a **Tervező** lehetőséget.
5. A **Tulajdonságok** szakaszban az **Adatmodell** mezőben válassza ki a korábban létrehozott testreszabott adó-adatmodellt.
6. Az **Adatmodell verzió** mezőben válassza ki az adóadat-modell kész verzióját.
7. Válassza a **Hozzáadás** lehetőséget, és adja hozzá a szükséges adóintézkedéseket.
8. Válassza a Művelet panel **Mentés** elemét, majd válassza az **Befejezés** elemet.
9. Zárja be a lapot, és tekintse meg az adóadatkonfiguráció befejezett verzióját.

## <a name="implement-tax-features-in-the-customized-tax-configuration"></a>Adófunkciók implementása a testreszabott adókonfigurációban

1. A Regulatory Configuration Service (RCS) szolgáltatásban nyissa meg a **Globalizációs funkciók** > **Adó** lehetőséget.
2. Válassza a **Hozzáadás** lehetőséget, írja be az új funkció adatait, majd válassza a **Funkció létrehozása** lehetőséget.
3. A **Verziók** lapon válassza ki a funkciót, majd kattintson a **Szerkesztés** gombra.
4. Az **Általános** lap **Konfigurációs verzió** mezőjében jelölje ki a testreszabott adókonfigurációt és -verziót.
5. Az **Oszlopok kezelése** párbeszédpanelen jelölje ki a testreszabott adómértékbe felvenni kívánt fejléc- és soroszlopokat, majd a megfelelő nyílgombot válassza a **Kijelölt oszlopok** listájához való hozzáadásához.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
