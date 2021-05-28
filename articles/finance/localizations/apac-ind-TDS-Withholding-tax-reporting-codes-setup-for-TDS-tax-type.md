---
title: Adóelőleg jelentéskódok beállítása a TDS adótípusokhoz
description: Az adóelőleg jelentés kódok a Forrásnál levont adóról (TDS) szóló 26Q és 27Q űrlapkimutatások előállítására szolgálnak. Ez a témakör elmagyarázza, hogyan állíthatja be az adóelőleg jelentéskódokat, hogy beállíthassa a TDS-jelentéskódokat.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 1f9325d182f89b98e8b943ae047c55e7e1aeb02f
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023308"
---
# <a name="set-up-withholding-tax-reporting-codes-for-the-tds-tax-type"></a>Adóelőleg jelentéskódok beállítása a TDS adótípusokhoz

[!include [banner](../includes/banner.md)]

Az adóelőleg jelentés kódok a Forrásnál levont adóról (TDS) szóló 26Q és 27Q űrlapkimutatások előállítására szolgálnak. Ez a témakör elmagyarázza, hogyan állíthatja be az adóelőleg jelentéskódokat, hogy beállíthassa a TDS-jelentéskódokat.

1. Ugorjon az **Adó \> Beállítások \> Adóelőleg \> Adóelőleg jelentéskódok elemre**.

    [![Adóelőleg jelentéskódok oldal](./media/apac-ind-TDS-16.png)](./media/apac-ind-TDS-16.png)

2. Az **Adótípus** mezőben válassza ki a **TDS** lehetőséget a TDS adótípus adóelőleg jelentéskódok definiálásához.
3. Az **Adóelőleg-összetevő** mezőben válassza ki azt a TDS-összetevőt, amelyhez az adóelőleg jelentéskódot definiálja. Az **Adóelőleg-összetevő csoport** mezője a definiált TDS-összetevőre definiált TDS-összetevőcsoportot mutatja.

    Az **Általános** gyorslap **Szakaszkód** mezője a TDS-összetevőcsoporthoz csatolt szakaszkódot mutatja.

4. Az **Általános** gyorslap **Jelentéskód** mezőjében válasszon ki egy TDS jelentési kódot:

    - TDS
    - TCS
    - Pótdíj
    - PE\_Cess
    - SHE\_Cess

5. Zárja be a lapot.
