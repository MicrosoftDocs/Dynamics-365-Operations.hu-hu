---
title: Juttatáskezelési paraméterek konfigurálása vállalatonként
description: A Juttatáskezelés paramétereinek konfigurálása vállalatonként a Microsoft Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 87d4f1e7580b333fd17d3b779aafa47c5baed424
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805658"
---
# <a name="configure-benefits-management-parameters-per-company"></a><span data-ttu-id="fe5dc-103">Juttatáskezelési paraméterek konfigurálása vállalatonként</span><span class="sxs-lookup"><span data-stu-id="fe5dc-103">Configure Benefits management parameters per company</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="fe5dc-104">Minden olyan szervezetnek, amely juttatásokat kínál, konfigurálnia kell a beállításokat az juttatásokat visszaigazoló e-mailekhez.</span><span class="sxs-lookup"><span data-stu-id="fe5dc-104">For each organization that offers benefits, you must configure settings for benefits confirmation emails.</span></span>

## <a name="configure-confirmation-email-settings"></a><span data-ttu-id="fe5dc-105">Megerősítő e-mail-beállítások megadása</span><span class="sxs-lookup"><span data-stu-id="fe5dc-105">Configure confirmation email settings</span></span>

1. <span data-ttu-id="fe5dc-106">A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Emberi erőforrások paraméterei** elemet.</span><span class="sxs-lookup"><span data-stu-id="fe5dc-106">In the **Benefits management** workspace, under **Setup**, select **Human Resources Parameters**.</span></span>

2. <span data-ttu-id="fe5dc-107">A **Juttatások kezelése** lapon adja meg a megfelelő értékeket az alábbi mezőkben:</span><span class="sxs-lookup"><span data-stu-id="fe5dc-107">In the **Benefits management** tab, specify values for the following fields:</span></span> 

   | <span data-ttu-id="fe5dc-108">Mező</span><span class="sxs-lookup"><span data-stu-id="fe5dc-108">Field</span></span> | <span data-ttu-id="fe5dc-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="fe5dc-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="fe5dc-110">**Visszaigazoló e-mail küldése**</span><span class="sxs-lookup"><span data-stu-id="fe5dc-110">**Send confirmation email**</span></span> | <span data-ttu-id="fe5dc-111">Ha ez a funkció be van kapcsolva, a rendszer visszaigazoló e-mailt küld az alkalmazottaknak, amikor kijelentkeznek a juttatások regisztrációs szolgáltatásából a Munkavállalói önkiszolgáló rendszerben.</span><span class="sxs-lookup"><span data-stu-id="fe5dc-111">When this feature is on, a confirmation email will be sent to employees when they check out from the benefits enrollment experience in Employee self-service.</span></span> |
   | <span data-ttu-id="fe5dc-112">**Visszaigazoló e-mail-sablon**</span><span class="sxs-lookup"><span data-stu-id="fe5dc-112">**Confirmation email template**</span></span> | <span data-ttu-id="fe5dc-113">Válassza ki a regisztrációs visszaigazolás elküldésekor használandó szervezeti e-mail-sablont.</span><span class="sxs-lookup"><span data-stu-id="fe5dc-113">Select the organization email template to use when sending the enrollment confirmation.</span></span> <span data-ttu-id="fe5dc-114">Ha nem választ sablont, a rendszer a következő általános e-mailt küldi el:</span><span class="sxs-lookup"><span data-stu-id="fe5dc-114">If you don't select a template, the following generic email will be sent:</span></span><br><br><span data-ttu-id="fe5dc-115">%EmployeeFirstName%,</span><span class="sxs-lookup"><span data-stu-id="fe5dc-115">%EmployeeFirstName%,</span></span><br><br><span data-ttu-id="fe5dc-116">Gratulálunk!</span><span class="sxs-lookup"><span data-stu-id="fe5dc-116">Congratulations!</span></span> <span data-ttu-id="fe5dc-117">Sikeresen végrehajtotta a juttatási regisztrációt.</span><span class="sxs-lookup"><span data-stu-id="fe5dc-117">You’ve successfully completed benefits enrollment.</span></span><br><br><span data-ttu-id="fe5dc-118">Köszönettel:</span><span class="sxs-lookup"><span data-stu-id="fe5dc-118">Thank you,</span></span><br><span data-ttu-id="fe5dc-119"><Company/Org name> juttatások.</span><span class="sxs-lookup"><span data-stu-id="fe5dc-119"><Company/Org name> Benefits.</span></span> |
   | <span data-ttu-id="fe5dc-120">**Alapértelmezett feladói e-mail-cím**</span><span class="sxs-lookup"><span data-stu-id="fe5dc-120">**Default email sender address**</span></span> | <span data-ttu-id="fe5dc-121">A visszaigazoló e-mail küldésekor használandó e-mail cím.</span><span class="sxs-lookup"><span data-stu-id="fe5dc-121">The email address to use when sending the confirmation email.</span></span> |

3. <span data-ttu-id="fe5dc-122">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fe5dc-122">Select **Save**.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]