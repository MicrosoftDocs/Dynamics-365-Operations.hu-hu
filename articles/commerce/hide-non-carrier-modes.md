---
title: A Pénztár nem szállítói kiszállítási módjainak elrejtése
description: Ez a témakör egy olyan konfigurációs beállítást tartalmaz, amellyel megakadályozhatja, hogy a nem szállítmányozói szállítási módok megjelenjenek a kiválasztásra ha a szállítási rendelések létrehozása a pénztár (POS) alkalmazásban történik.
author: hhainesms
manager: annbe
ms.date: 10/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 38d57ed5f8d2b8725cd11156f0135988bb76e047
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982989"
---
# <a name="hide-non-carrier-delivery-modes-from-the-shipping-options-in-pos"></a><span data-ttu-id="e5bd9-103">A Pénztár nem szállítói kiszállítási módjainak elrejtése</span><span class="sxs-lookup"><span data-stu-id="e5bd9-103">Hide non-carrier delivery modes from the shipping options in POS</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="e5bd9-104">Ez a témakör egy olyan konfigurációs beállítást tartalmaz, amely elérhető a pénztár (POS) alkalmazás számára.</span><span class="sxs-lookup"><span data-stu-id="e5bd9-104">This topic describes a configuration option that is available for the point of sale (POS) application.</span></span> <span data-ttu-id="e5bd9-105">Ez a beállítási lehetőség megváltoztatja a szállítási mód kiválasztásának működését, ha a kiszállítási rendeléseket a pénztárban hozzák létre.</span><span class="sxs-lookup"><span data-stu-id="e5bd9-105">This configuration option changes the behavior for the selection of a mode of delivery when shipment orders are created in POS.</span></span>

<span data-ttu-id="e5bd9-106">Amikor a felhasználók vevői szállítási rendeléseket hoznak létre a pénztárban, ki tudják választani a szállítmány szállítási módját.</span><span class="sxs-lookup"><span data-stu-id="e5bd9-106">When users create customer shipment orders in POS, they can select a mode of delivery for the shipment.</span></span> <span data-ttu-id="e5bd9-107">Ez a funkció elérhető attól függetlenül, hogy a teljes rendelést leszállítják, vagy csak a kiválasztott sorokat.</span><span class="sxs-lookup"><span data-stu-id="e5bd9-107">This functionality is available regardless of whether the whole order is being shipped or only selected lines.</span></span>

<span data-ttu-id="e5bd9-108">Alapértelmezés szerint az a párbeszédpanel, amelyen a szállítási mód be kiválasztható, az összes érvényes szállítási módot megmutatja egy csatorna, egy tétel és egy szállítási cím kombinációja számára.</span><span class="sxs-lookup"><span data-stu-id="e5bd9-108">By default, the dialog box where a mode of delivery is selected shows all the valid modes of delivery for the combination of a channel, an item, and a delivery address.</span></span> <span data-ttu-id="e5bd9-109">Ezeket a szállítási módokat a **Szállítási módok** oldalon a Központban ( **Értékesítési és marketing \> Beállítás \> Elosztás \> Kiszállítási módok** ) határozzák meg.</span><span class="sxs-lookup"><span data-stu-id="e5bd9-109">These modes of delivery are defined on the **Modes of delivery** page in Headquarters ( **Sales and marketing \> Setup \> Distribution \> Modes of delivery** ).</span></span> <span data-ttu-id="e5bd9-110">A „nem szállítmányozó” szállítási módok (például **Carryout** vagy **Felvétel** ) is megjelenhetnek a párbeszédpanelem kiválasztásra.</span><span class="sxs-lookup"><span data-stu-id="e5bd9-110">"Non-carrier" modes of delivery, such as **Carryout** or **Pickup** , might also appear for selection in the dialog box.</span></span>

<span data-ttu-id="e5bd9-111">Egy olyan funkció lett azonban hozzáadva, amely lehetővé teszi a nem szállítmányozói szállítási módok elrejtését a párbeszédpanelen.</span><span class="sxs-lookup"><span data-stu-id="e5bd9-111">However, a feature has been added that lets you hide non-carrier modes of delivery in the dialog box.</span></span> <span data-ttu-id="e5bd9-112">Ha be kívánja kapcsolni ezt a funkciót, akkor a **Commerce paraméterek** oldalon a **Vevői rendelések** lapon állítsa be, hogy a **Csak szállítmányozói módbeállítások megjelenítése kiszállítási rendelésekhez** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="e5bd9-112">To turn on this feature, on the **Commerce parameters** page, on the **Customer orders** tab, set the **Show only carrier mode options for ship orders** option to **Yes** .</span></span> <span data-ttu-id="e5bd9-113">Miután bekapcsolta ezt a funkciót, és futtatja a megfelelő elosztási feladatokat a csatorna-adatbázisba történő szinkronizáláshoz, nem fognak megjelenni a nem szállítmányozó szállítási módok a kiválasztáshoz a pénztári szállítmányok létrehozási folyamata során.</span><span class="sxs-lookup"><span data-stu-id="e5bd9-113">After you turn on this feature and run the appropriate distribution jobs to sync the information to the channel database, non-carrier modes of delivery won't appear for selection during the process of creating shipment orders in POS.</span></span>
