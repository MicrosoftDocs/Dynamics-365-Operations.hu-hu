---
title: Szolgáltatási szerződések és projektek integrálása
description: A szolgáltatási szerződések és soraik műveletei során a Projektvezetés és könyvelés területein beállított adatokat hasznosíthatja.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6bd2fb1f54a3decb77f019db6b2016cebdcaddb9
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571048"
---
# <a name="integration-for-service-agreements-and-projects"></a><span data-ttu-id="a59a5-103">Szolgáltatási szerződések és projektek integrálása</span><span class="sxs-lookup"><span data-stu-id="a59a5-103">Integration for service agreements and projects</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="a59a5-104">A szolgáltatási szerződések és soraik műveletei során a **Projektvezetés és könyvelés** következő területein beállított adatokat hasznosíthatja.</span><span class="sxs-lookup"><span data-stu-id="a59a5-104">When you work with service agreements and service agreement lines, you use data that is set up in the following areas in **Project management and accounting**.</span></span>

## <a name="project-prices"></a><span data-ttu-id="a59a5-105">Projektárak</span><span class="sxs-lookup"><span data-stu-id="a59a5-105">Project prices</span></span>

<span data-ttu-id="a59a5-106">A szolgáltatási szerződés tranzakciójának önköltségi és eladási árát a szerződéshez kapcsolódó projekt önköltségi árbeállításából lehet levezetni.</span><span class="sxs-lookup"><span data-stu-id="a59a5-106">The cost and the sales price for a service agreement transaction are derived from the cost price setup that applies to the project that is attached to the service agreement.</span></span> <span data-ttu-id="a59a5-107">Az önköltségi és eladási árak projektenként, alkalmazottanként és kategóriánként is beállíthatók.</span><span class="sxs-lookup"><span data-stu-id="a59a5-107">Cost and sales prices can be set up by project, employee, and category.</span></span> 

## <a name="project-validation"></a><span data-ttu-id="a59a5-108">Projektellenőrzés</span><span class="sxs-lookup"><span data-stu-id="a59a5-108">Project validation</span></span>

<span data-ttu-id="a59a5-109">A **Projektvezetés és könyvelés** ellenőrzési beállításaival korlátozni lehet, hogy mely projektek, alkalmazottak és kategóriák legyenek kiválaszthatók a szolgáltatási szerződés soraiban.</span><span class="sxs-lookup"><span data-stu-id="a59a5-109">The projects, employees, and categories that are available for selection on a service agreement line can be limited by the validation setup in **Project management and accounting**.</span></span> <span data-ttu-id="a59a5-110">Az ellenőrzés beállítás segítségével alkalmazottakat, projekteket és kategóriákat kombinálhat a hozzáférés vezérlése céljából.</span><span class="sxs-lookup"><span data-stu-id="a59a5-110">By using the validation setup, you can combine employees, projects, and categories for control access.</span></span> 

## <a name="project-line-properties"></a><span data-ttu-id="a59a5-111">Projekt sortulajdonságai</span><span class="sxs-lookup"><span data-stu-id="a59a5-111">Project line properties</span></span>

<span data-ttu-id="a59a5-112">A sortulajdonság egy automatikusan rögzített beállítás minden szolgáltatásiszerződés-sorban.</span><span class="sxs-lookup"><span data-stu-id="a59a5-112">A line property is entered automatically for a service agreement line.</span></span>

<span data-ttu-id="a59a5-113">A sortulajdonságok a **Sortulajdonság** képernyőn hozhatók létre a **Projektvezetés és könyvelés** modulban.</span><span class="sxs-lookup"><span data-stu-id="a59a5-113">Line properties are created in the **Line properties** form in **Project management and accounting**.</span></span> <span data-ttu-id="a59a5-114">A szolgáltatási szerződésen rögzített sortulajdonságot a rendszer csatolja a szolgáltatási szerződéshez kiválasztott projekthez, ebből következően ezt a szolgáltatásiszerződés-sor is örökli.</span><span class="sxs-lookup"><span data-stu-id="a59a5-114">The line property that is entered on a service agreement is attached to the project that is selected for the service agreement and inherited subsequently by the service agreement line.</span></span> 

## <a name="default-offset-accounts"></a><span data-ttu-id="a59a5-115">Alapértelmezett ellenszámlák</span><span class="sxs-lookup"><span data-stu-id="a59a5-115">Default offset accounts</span></span>

<span data-ttu-id="a59a5-116">Kiadási tranzakció rögzítésekor a program automatikusan kiválasztja az alapértelmezett kiadási ellenszámlát a tranzakcióhoz.</span><span class="sxs-lookup"><span data-stu-id="a59a5-116">If you enter an expense transaction, a default expense offset account is selected automatically for the transaction.</span></span> <span data-ttu-id="a59a5-117">Az alapértelmezett költségszámla az aktuális szolgáltatási szerződéshez csatolt projektben állítható be.</span><span class="sxs-lookup"><span data-stu-id="a59a5-117">The default expense account is set up for the project that is attached to the current service agreement.</span></span>

## <a name="project-categories"></a><span data-ttu-id="a59a5-118">Projektkategóriák</span><span class="sxs-lookup"><span data-stu-id="a59a5-118">Project categories</span></span>

<span data-ttu-id="a59a5-119">A szolgáltatásiszerződés-sorokban elérhető kategóriák a **Projektkategóriák** képernyőn állíthatók be a **Projektvezetés és könyvelés** modulban.</span><span class="sxs-lookup"><span data-stu-id="a59a5-119">The categories that are available for service agreement lines are set up in the **Project categories** form in **Project management and accounting**.</span></span> 

> [!NOTE]
> <P><span data-ttu-id="a59a5-120">Azok a kategóriák választhatók ki, amelyek <STRONG>Aktív a naplókban</STRONG> jelölőnégyzete be van jelölve a <STRONG>Projektkategóriák</STRONG> képernyő <STRONG>Projekt</STRONG> lapján.</span><span class="sxs-lookup"><span data-stu-id="a59a5-120">Categories that have the <STRONG>Active in journals</STRONG> check box selected on the <STRONG>Project</STRONG> tab in the <STRONG>Project categories</STRONG> form are available for selection.</span></span> <span data-ttu-id="a59a5-121">Ha azonban az <STRONG>Inaktív kategóriák</STRONG> jelölőnégyzet be van jelölve a <STRONG>Naplók</STRONG> lapon, a <STRONG>Projektvezetési és könyvelési paraméterek</STRONG> képernyőn, minden kategóriát ki lehet választani</span><span class="sxs-lookup"><span data-stu-id="a59a5-121">However, if the <STRONG>Inactive categories</STRONG> check box is selected on the <STRONG>Journals</STRONG> tab in the <STRONG>Project management and accounting parameters</STRONG> form, all categories are available for selection.</span></span></P>

## <a name="project-parameters"></a><span data-ttu-id="a59a5-122">Projekt paraméterei</span><span class="sxs-lookup"><span data-stu-id="a59a5-122">Project parameters</span></span>

<span data-ttu-id="a59a5-123">Ha a **Kilépett alkalmazottak** mező be van jelölve a **Naplók** lapon, a **Projektvezetési és könyvelési paraméterek** képernyőn, akkor az aktív alkalmazottak mellett az inaktívak is kiválaszthatók a **Szolgáltatási szerződések** és a **Szervizrendelések** képernyőn.</span><span class="sxs-lookup"><span data-stu-id="a59a5-123">If the **Terminated workers** field on the **Journals** tab in the **Project management and accounting parameters** form is selected, you can select inactive employees and active employees in the **Service agreements** and **Service orders** forms.</span></span>

<span data-ttu-id="a59a5-124">Emellett a **Szervizrendelések** képernyő **Projekt** lapján engedélyezheti a **Kezdő idő** és **Záró idő** mezőket, és ezután kezdő és záró időpontokat határozhat meg a szervizrendeléssorokon.</span><span class="sxs-lookup"><span data-stu-id="a59a5-124">Also, you can enable the **Start time** and **End time** fields on the **Project** tab in the **Service orders** form to enter starting and ending times on service order lines.</span></span>

## <a name="enable-the-starting-and-ending-time-feature-for-service-orders"></a><span data-ttu-id="a59a5-125">A kezdő és záró időpont megadásának engedélyezése a szervizrendelésekhez</span><span class="sxs-lookup"><span data-stu-id="a59a5-125">Enable the starting and ending time feature for service orders</span></span>

1.  <span data-ttu-id="a59a5-126">Kattintson a **Projektvezetés és könyvelés** \> **Beállítás** \> **Projektvezetési és könyvelési paraméterek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a59a5-126">Click **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.</span></span>

2.  <span data-ttu-id="a59a5-127">Kattintson a **Naplók** lapra, majd jelölje be a **Kezdő és záró időpont megjelenítése** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="a59a5-127">Click the **Journals** tab, and then select the **Show start/end times** check box.</span></span>

3.  <span data-ttu-id="a59a5-128">Kattintson a következőkre: **Projektvezetés és könyvelés** \> **Beállítás** \> **Naplók** \> **Naplók nevei**.</span><span class="sxs-lookup"><span data-stu-id="a59a5-128">Click **Project management and accounting** \> **Setup** \> **Journals** \> **Journal names**.</span></span>

4.  <span data-ttu-id="a59a5-129">Válassza ki a szervizrendeléshez csatolt napló nevét.</span><span class="sxs-lookup"><span data-stu-id="a59a5-129">Select the journal name that is attached to the service order.</span></span>

5.  <span data-ttu-id="a59a5-130">Kattintson az **Általános** lapra, majd jelölje be a **Kezdő és záró időpont megjelenítése** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="a59a5-130">Click the **General** tab, and then select the **Show start/end times** check box.</span></span>


> [!NOTE]
> <P><span data-ttu-id="a59a5-131">Válassza ki a szervizrendelés naplójának nevét a <STRONG>Szolgáltatáskezelés paraméterei</STRONG> képernyő <STRONG>Naplók</STRONG> lapjának <STRONG>Óra</STRONG> mezőjében.</span><span class="sxs-lookup"><span data-stu-id="a59a5-131">Select the journal name for the service order in the <STRONG>Hour</STRONG> field on the <STRONG>Journals</STRONG> tab in the <STRONG>Service management parameters</STRONG> form.</span></span></P>





