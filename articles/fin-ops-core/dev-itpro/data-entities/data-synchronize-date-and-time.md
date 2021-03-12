---
title: Dátum és idő szinkronizálása az importálási feladatokban
description: Az importálási feladatokban használja az UTC időzónákat, hogy elkerülje az időzóna-átalakításokkal kapcsolatos problémákat.
author: Sunil-Garg
manager: tfehr
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ae04b09a68e64d6d70c0329e689ab08c3903fca0
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798719"
---
# <a name="synchronize-date-and-time-in-import-jobs"></a><span data-ttu-id="ee963-103">Dátum és idő szinkronizálása az importálási feladatokban</span><span class="sxs-lookup"><span data-stu-id="ee963-103">Synchronize date and time in import jobs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ee963-104">Fontos, hogy az importált feladat időzónáját UTC-formátumra (koordinált világidő) állítsa be.</span><span class="sxs-lookup"><span data-stu-id="ee963-104">It's important to set the time zone for your import job to Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="ee963-105">Az importált adatokban nem várt dátumok és időpontok is előfordulhatnak, ha más beállítást használ.</span><span class="sxs-lookup"><span data-stu-id="ee963-105">You might see unexpected dates and times in your imported data if you use a different setting.</span></span> <span data-ttu-id="ee963-106">A helyes beállítás nélkül az importálási folyamat az UTC-dátumot helyi formátumra alakítja, majd a rendszerbeállítások újra konvertálják.</span><span class="sxs-lookup"><span data-stu-id="ee963-106">Without the correct setting, the import process converts the UTC date to the local format, and then system settings converts it again.</span></span>

<span data-ttu-id="ee963-107">A két konverzió hatására megváltoznak a dátumok az alkalmazások között.</span><span class="sxs-lookup"><span data-stu-id="ee963-107">This dual conversion causes dates to change between applications.</span></span> <span data-ttu-id="ee963-108">A kettős átalakítás például azzal jár, hogy egy alkalmazott kezdő dátuma eltérő lesz a helyi időzónákban lévő különbségek miatt a Dynamics 365 Human Resources és a Dynamics 365 Finance megoldásban.</span><span class="sxs-lookup"><span data-stu-id="ee963-108">For example, the dual conversion could cause an employee's start date to be different between Dynamics 365 Human Resources and Dynamics 365 Finance due to differences in local time zones.</span></span> <span data-ttu-id="ee963-109">Az importálási feladat UTC-formátumra való beállításával ez a probléma megoldódik.</span><span class="sxs-lookup"><span data-stu-id="ee963-109">Setting the import job to UTC resolves this problem.</span></span>

1. <span data-ttu-id="ee963-110">Válassza a Dynamics 365 Finance and Operations megoldásban az **Adatkezelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ee963-110">In Dynamics 365 Finance and Operations, select **Data management**.</span></span>

2. <span data-ttu-id="ee963-111">Válassza a **Projektek importálása** lehetőséget, majd a projektet.</span><span class="sxs-lookup"><span data-stu-id="ee963-111">Select **Import projects**, and then select the project.</span></span>

3. <span data-ttu-id="ee963-112">A **Forrásdátum formátumban** válassza a **CSV-Unicode** kódot.</span><span class="sxs-lookup"><span data-stu-id="ee963-112">Under **Source date format**, select **CSV-Unicode**.</span></span>

   <span data-ttu-id="ee963-113">[![Forrásdátum formátumának módosítása UTC-formátumra](./media/data-source-date-format.png)](./media/data-source-date-format.png)</span><span class="sxs-lookup"><span data-stu-id="ee963-113">[![Change source date format to UTC](./media/data-source-date-format.png)](./media/data-source-date-format.png)</span></span>

4. <span data-ttu-id="ee963-114">Az **Időzónaidőzóna** beállítását módosítsa az **Egyezményes világidő** lehetőségre, és a **Nyelv** legyen **En-US**.</span><span class="sxs-lookup"><span data-stu-id="ee963-114">Change **Timezone** to **Coordinated Universal Timezone**, and change **Language** to **En-US**.</span></span>


