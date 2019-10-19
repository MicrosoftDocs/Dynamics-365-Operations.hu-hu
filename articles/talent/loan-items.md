---
title: Dolgozóknak kölcsönzött cikkek kezelése
description: A kölcsöncikkek olyan rekordok, amelyek segítik a menedzsert a cég által a munkavállalók számára kölcsönadott tényleges cikkkek követésében.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmLoanItem, HcmLoanType, HcmPersonLoan
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 3581
ms.assetid: b14bdddb-f10e-4619-9f91-8c88439da862
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: 73ffe05d8c869418f7601025e8ce19e1b05c952f
ms.sourcegitcommit: 0dd8d0510214f92936a9dd214b404c5c8103587b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/01/2019
ms.locfileid: "2419246"
---
# <a name="manage-items-that-are-lent-to-workers"></a><span data-ttu-id="f6276-103">Dolgozóknak kölcsönzött cikkek kezelése</span><span class="sxs-lookup"><span data-stu-id="f6276-103">Manage items that are lent to workers</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f6276-104">A kölcsöncikkek olyan rekordok, amelyek segítik a menedzsert a cég által a munkavállalók számára kölcsönadott tényleges cikkkek követésében.</span><span class="sxs-lookup"><span data-stu-id="f6276-104">Loan items are records that help managers track the physical items that your company lends to its workers.</span></span> 

<span data-ttu-id="f6276-105">A következő szempontok olyan elemek példáit sorolja fel, amelyeket a vállalat kölcsönözhet a munkavállalóknak:</span><span class="sxs-lookup"><span data-stu-id="f6276-105">The following points list examples of items that a company might lend to workers:</span></span>
-   <span data-ttu-id="f6276-106">Mobiltelefonok</span><span class="sxs-lookup"><span data-stu-id="f6276-106">Mobile telephones</span></span>
-   <span data-ttu-id="f6276-107">Gépjárművek</span><span class="sxs-lookup"><span data-stu-id="f6276-107">Automobiles</span></span>
-   <span data-ttu-id="f6276-108">Számítógépes eszközök</span><span class="sxs-lookup"><span data-stu-id="f6276-108">Computer equipment</span></span>

<span data-ttu-id="f6276-109">Minden fizikai cikknek rendelkeznie kell egy megfelelő kölcsöncikkel.</span><span class="sxs-lookup"><span data-stu-id="f6276-109">Each physical item must have a corresponding loan item.</span></span> <span data-ttu-id="f6276-110">Minden kölcsöntétel rekordnak le kell írni a kölcsönzött tételt, meg kell adni a kölcsönzésért felelős személyt, és a tétel kölcsönzési idejét.</span><span class="sxs-lookup"><span data-stu-id="f6276-110">Each loan item record should describe what is being loaned, who is responsible for the loan, and the number of days the item can loaned to a worker.</span></span> <span data-ttu-id="f6276-111">Ezzel egy időben több kölcsöncikkek hozhatók létre cikkekhez, mint például kulcsokhoz, belépőkártyákhoz vagy egyenruhákhoz.</span><span class="sxs-lookup"><span data-stu-id="f6276-111">You can create multiple loan items, for items such as keys, access cards or uniforms, at the same time.</span></span> 

<span data-ttu-id="f6276-112">Tétel kölcsönzése esetén jegyezze fel a tétel kölcsönzésének az időpontját és a visszaadás tervezett időpontját.</span><span class="sxs-lookup"><span data-stu-id="f6276-112">When loaning an item, enter the date that the item was loaned, and the planned return date.</span></span> <span data-ttu-id="f6276-113">Ha a cikk visszaérkezett, adja meg a tényleges visszaadási időpontot is.</span><span class="sxs-lookup"><span data-stu-id="f6276-113">When the item is returned, enter the actual return date.</span></span>

<span data-ttu-id="f6276-114">Az alkalmazottak az Alkalmazott önkiszolgáló munkaterület segítségével tekinthetik meg a kölcsönadott cikkek rekordjait.</span><span class="sxs-lookup"><span data-stu-id="f6276-114">Employees can view the records of the items that have been loaned to them using the Employee self-service workspace.</span></span> <span data-ttu-id="f6276-115">Szerkeszthetik is a meglévő rekordokat vagy megadhatnak új kölcsöncikkeket, ha már kaptak további tényleges cikkeket.</span><span class="sxs-lookup"><span data-stu-id="f6276-115">They can also edit the existing records or enter new loan items, if they've received additional physical items.</span></span>  <span data-ttu-id="f6276-116">A munkafolyamatot be lehet állítani úgy, hogy a változtatásokat irányítsa új vagy már meglévő kölcsöncikkekhez egy jóváhagyási folyamaton keresztül.</span><span class="sxs-lookup"><span data-stu-id="f6276-116">Workflow can be set up to route changes to new or existing loan items through an approval process.</span></span> 

<span data-ttu-id="f6276-117">A vezetők megtekinthetik a közvetlen jelentések közvetlen cikkeit.</span><span class="sxs-lookup"><span data-stu-id="f6276-117">Managers can view loaned items for their direct reports.</span></span> <span data-ttu-id="f6276-118">Megkaphatják az engedélyt új kölcsön cikkek hozzáadására az alkalmazottaik nevében.</span><span class="sxs-lookup"><span data-stu-id="f6276-118">They can also be granted permission to add new loan items on behalf of their employees.</span></span>

 <a name="account-for-lost-or-misplaced-loan-items"></a><span data-ttu-id="f6276-119"> Elveszett vagy rossz helyre tett kölcsöncikkek számlája</span><span class="sxs-lookup"><span data-stu-id="f6276-119">Account for lost or misplaced loan items</span></span>
-----------------------------------------

<span data-ttu-id="f6276-120">Ha egy tétel megsérül vagy rossz helyre kerül, adjon meg egy fiktív visszaadási rekordot.</span><span class="sxs-lookup"><span data-stu-id="f6276-120">If an item becomes damaged or misplaced, enter a fictitious return record.</span></span> <span data-ttu-id="f6276-121">Ezután vagy törölje a cikket, vagy tartsa meg az áttekintésben, de a leírásában jelezze, hogy nem áll rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="f6276-121">Then either delete the item or keep it in the overview and change the description to indicate that the item is not available.</span></span>


<a name="additional-resources"></a><span data-ttu-id="f6276-122">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="f6276-122">Additional resources</span></span>
--------

[<span data-ttu-id="f6276-123">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="f6276-123">Human resources</span></span>](index.yml)



