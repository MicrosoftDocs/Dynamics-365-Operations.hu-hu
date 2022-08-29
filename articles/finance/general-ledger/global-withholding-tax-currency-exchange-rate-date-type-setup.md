---
title: A globális adóelőleg pénznemárfolyam-típusának és dátumtípus-beállításának engedélyezése
description: Ez a cikk bemutatja az adóelőleg pénzneme árfolyamtípusának és dátumtípusának globális beállítását.
author: kailiang
ms.date: 08/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 41f12a33651c14439f3a59c5c2f2d34019dada2d
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2022
ms.locfileid: "9229979"
---
# <a name="enable-the-global-withholding-tax-currency-exchange-rate-type-and-date-type-setup"></a>A globális adóelőleg pénznemárfolyam-típusának és dátumtípus-beállításának engedélyezése

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

Ez a cikk bemutatja az adóelőleg pénzneme árfolyamtípusának és dátumtípusának globális beállítását. Most ki lehet választani egy külön árfolyamtípust és árfolyam-számítási dátumtípust az adóelőleg pénznemére. Ezek a beállítások határozzák meg az adóelőleg összegének kiszámításához használt átváltási árfolyamot az adóelőleg pénznemében, a kifizetési tranzakciókban.

Ez a funkció a Microsoft Dynamics 365 Pénzügy 10.0.29-es és újabb verzióiban érhető el.

1. Ugrás az **Adóbeállítás** \> **paramétereihez** \> **:** \> **Főkönyvi paraméterek**
2. Az Adóelőleg **lapon** állítsa **A** speciális adóelőleg pénznemének engedélyezése lehetőséget Igen **beállításra**.
3. Az Árfolyam **típusa mezőben** válassza ki az adóelőleg pénznemének árfolyamtípusát.
4. A Számítás **dátuma típusa mezőben** válassza ki azt a számítási dátumtípust, amely meghatározza az adóelőleg pénznemének árfolyamát:

    - **Kifizetési dátum** – az árfolyam meghatározása a kifizetési napló feladási dátuma alapján.
    - **Számla dátuma** – az árfolyam meghatározása a számlanapló számladátumán alapul. Ha a bizonylat számladátumának üres a dátuma, a számla feladási dátumát használja a vevő. 
    - **Bizonylat dátuma** – az árfolyam meghatározása a kifizetési napló bizonylatdátumán alapul. Ha a bizonylat bizonylatdátumának üres a dátuma, a rendszer a kifizetési dátumot használja.

5. Válassza a **Mentés** lehetőséget.

Ha a tranzakció pénzneme eltér az adóelőlegkódban meghatározott adóelőleg pénznemtől, akkor a program a tranzakció pénznemében kiszámítja az adóelőleg pénznemében megadott összeget a tranzakció pénzneme alapján, az előző beállítások alapján, és rögzíti a feladott adóelőleg-tranzakciókban.
