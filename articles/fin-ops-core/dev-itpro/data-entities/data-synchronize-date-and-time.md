---
title: Dátum és idő szinkronizálása az importálási feladatokban
description: Az importálási feladatokban használja az UTC időzónákat, hogy elkerülje az időzóna-átalakításokkal kapcsolatos problémákat.
author: Sunil-Garg
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 41c0ec805a20a525989e0133e5dffb29ce3fed39
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748669"
---
# <a name="synchronize-date-and-time-in-import-jobs"></a><span data-ttu-id="8d3ac-103">Dátum és idő szinkronizálása az importálási feladatokban</span><span class="sxs-lookup"><span data-stu-id="8d3ac-103">Synchronize date and time in import jobs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8d3ac-104">Fontos, hogy az importált feladat időzónáját UTC-formátumra (koordinált világidő) állítsa be.</span><span class="sxs-lookup"><span data-stu-id="8d3ac-104">It's important to set the time zone for your import job to Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="8d3ac-105">Az importált adatokban nem várt dátumok és időpontok is előfordulhatnak, ha más beállítást használ.</span><span class="sxs-lookup"><span data-stu-id="8d3ac-105">You might see unexpected dates and times in your imported data if you use a different setting.</span></span> <span data-ttu-id="8d3ac-106">A helyes beállítás nélkül az importálási folyamat az UTC-dátumot helyi formátumra alakítja, majd a rendszerbeállítások újra konvertálják.</span><span class="sxs-lookup"><span data-stu-id="8d3ac-106">Without the correct setting, the import process converts the UTC date to the local format, and then system settings converts it again.</span></span>

<span data-ttu-id="8d3ac-107">A két konverzió hatására megváltoznak a dátumok az alkalmazások között.</span><span class="sxs-lookup"><span data-stu-id="8d3ac-107">This dual conversion causes dates to change between applications.</span></span> <span data-ttu-id="8d3ac-108">A kettős átalakítás például azzal jár, hogy egy alkalmazott kezdő dátuma eltérő lesz a helyi időzónákban lévő különbségek miatt a Dynamics 365 Human Resources és a Dynamics 365 Finance megoldásban.</span><span class="sxs-lookup"><span data-stu-id="8d3ac-108">For example, the dual conversion could cause an employee's start date to be different between Dynamics 365 Human Resources and Dynamics 365 Finance due to differences in local time zones.</span></span> <span data-ttu-id="8d3ac-109">Az importálási feladat UTC-formátumra való beállításával ez a probléma megoldódik.</span><span class="sxs-lookup"><span data-stu-id="8d3ac-109">Setting the import job to UTC resolves this problem.</span></span>

1. <span data-ttu-id="8d3ac-110">Válassza a Dynamics 365 Finance and Operations megoldásban az **Adatkezelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8d3ac-110">In Dynamics 365 Finance and Operations, select **Data management**.</span></span>

2. <span data-ttu-id="8d3ac-111">Válassza a **Projektek importálása** lehetőséget, majd a projektet.</span><span class="sxs-lookup"><span data-stu-id="8d3ac-111">Select **Import projects**, and then select the project.</span></span>

3. <span data-ttu-id="8d3ac-112">A **Forrásdátum formátumban** válassza a **CSV-Unicode** kódot.</span><span class="sxs-lookup"><span data-stu-id="8d3ac-112">Under **Source date format**, select **CSV-Unicode**.</span></span>

   <span data-ttu-id="8d3ac-113">[![Forrásdátum formátumának módosítása UTC-formátumra](./media/data-source-date-format.png)](./media/data-source-date-format.png)</span><span class="sxs-lookup"><span data-stu-id="8d3ac-113">[![Change source date format to UTC](./media/data-source-date-format.png)](./media/data-source-date-format.png)</span></span>

4. <span data-ttu-id="8d3ac-114">Az **Időzónaidőzóna** beállítását módosítsa az **Egyezményes világidő** lehetőségre, és a **Nyelv** legyen **En-US**.</span><span class="sxs-lookup"><span data-stu-id="8d3ac-114">Change **Timezone** to **Coordinated Universal Timezone**, and change **Language** to **En-US**.</span></span>




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]