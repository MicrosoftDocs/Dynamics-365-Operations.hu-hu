---
title: Szállítói számlák automatizálási eredményeinek megtekintése (előnézet)
description: Ez a témakör azt mutatja be, hogyan lehet megtekinteni az automatizált munkafolyamatba küldési folyamatban lévő szállítói számlák állapotát.
author: abruer
manager: AnnBe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 3b87af4c64f8021a1b23cca5d8f38ac21c8efbd4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5248089"
---
# <a name="view-vendor-invoice-automation-results"></a><span data-ttu-id="65f40-103">Szállítói számlák automatizálási eredményeinek megtekintése</span><span class="sxs-lookup"><span data-stu-id="65f40-103">View vendor invoice automation results</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="65f40-104">Ez a témakör azt mutatja be, hogyan lehet megtekinteni az automatizált munkafolyamatba küldési folyamatban lévő szállítói számlák állapotát.</span><span class="sxs-lookup"><span data-stu-id="65f40-104">This topic explains how to view the status of vendor invoices that are in the automated submit-to-workflow process.</span></span> <span data-ttu-id="65f40-105">A program minden importált szállítói számlához megőrzi az automatizálási előzmények adatait.</span><span class="sxs-lookup"><span data-stu-id="65f40-105">Details of the automation history are maintained for each imported vendor invoice.</span></span> <span data-ttu-id="65f40-106">Az automatizált üzleti folyamatoktól függően a **Függő szállítói számlák** oldal az **Automatizált nyugtaegyeztetés állapota** és az **Automatizált munkafolyamatba küldés állapota** értékeket jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="65f40-106">Depending on the business processes that you've automated, the **Pending vendor invoices** page shows **Automated receipt match status** and **Automated submit to workflow status** values.</span></span> <span data-ttu-id="65f40-107">Megtekintheti a részleteket, és tervet készíthet azon számlákhoz, amelyek nem tartalmaznak automatizált lépést.</span><span class="sxs-lookup"><span data-stu-id="65f40-107">You can view the details and make a plan to focus on the invoices that failed an automated step.</span></span> <span data-ttu-id="65f40-108">Ezután a hiba javítását követően újraindíthatja az importált számlára vonatkozó automatizált folyamatot.</span><span class="sxs-lookup"><span data-stu-id="65f40-108">Then, after you correct the issue, you can resume the automated process for the imported invoice.</span></span>

<span data-ttu-id="65f40-109">A már elküldött számlák szerkesztéséhez szüneteltetni kell az automatikus feldolgozást.</span><span class="sxs-lookup"><span data-stu-id="65f40-109">Before you can edit an invoice that has been submitted, you must pause the automated processing.</span></span> <span data-ttu-id="65f40-110">Ha szüneteltetni kell egy számlát az automatizált munkafolyamatba küldési folyamatban, akkor a **Szállítói számlák** oldalon állítsa **Nem** értékre az **Automatizált feldolgozás bevonása** mezőt.</span><span class="sxs-lookup"><span data-stu-id="65f40-110">If an invoice in the automated submit-to-workflow process must be paused, set the **Include in Automated processing** field to **No** on the **Vendor invoices** page.</span></span> <span data-ttu-id="65f40-111">Az automatizálás addig nem fog futni, amíg az **Automatizált feldolgozás bevonása** mezőt nem állítják át **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="65f40-111">Automation then won't run until **Include in Automated processing** is set to **Yes**.</span></span> <span data-ttu-id="65f40-112">Ha a számla nem szerepel a munkafolyamat-rendszerben és nincs az automatizált folyamatban, a számla további automatizálása szüneteltethető.</span><span class="sxs-lookup"><span data-stu-id="65f40-112">An invoice can be paused from further automation if it isn't yet in the workflow system and isn't used by the automated process.</span></span>

<span data-ttu-id="65f40-113">Ha egy importált számla a munkafolyamatba küldési folyamatban van, akkor a **Szállítói számlák** oldalon megtekintheti az **Automatizáció állapotát**.</span><span class="sxs-lookup"><span data-stu-id="65f40-113">If an imported invoice is subject to the submit-to-workflow process, you can view its **Automation status** value on the **Vendor invoices** page.</span></span> <span data-ttu-id="65f40-114">A következő állapotok követi végig a rendszer:</span><span class="sxs-lookup"><span data-stu-id="65f40-114">The following statuses are tracked:</span></span>

- <span data-ttu-id="65f40-115">**Bevonva** – Azok az automatizált folyamatok, amelyeket a **Kötelezettségek paraméterei** oldalon definiáltak, megfelelően futnak, de még nem befejeződtek be.</span><span class="sxs-lookup"><span data-stu-id="65f40-115">**Included** – The automated processes that are defined on the **Accounts payable parameters** page are running correctly but haven't yet been completed.</span></span>
- <span data-ttu-id="65f40-116">**Szüneteltetve** – A **Kötelezettségek paraméterei** oldalon definiált automatizált folyamatok, amelyek végigfutottak, de a folyamat legalább egy lépése sikertelen volt.</span><span class="sxs-lookup"><span data-stu-id="65f40-116">**Paused** – The automated processes that are defined on the **Accounts payable parameters** page have run, but at least one step in the process failed.</span></span> <span data-ttu-id="65f40-117">A **Szüneteltetett** állapotot akkor is alkalmazza a program, ha a **Bevonás az automatizált feldolgozásba** mezőt **Nem** értékre állítja.</span><span class="sxs-lookup"><span data-stu-id="65f40-117">The **Paused** status is also applied if the **Include in automated processing** field is set to **No**.</span></span> <span data-ttu-id="65f40-118">A hibákat a **Legutóbbi eredmények megtekintése** gombbal lehet megtekinteni.</span><span class="sxs-lookup"><span data-stu-id="65f40-118">You can view the failures by selecting **View most recent results**.</span></span>
- <span data-ttu-id="65f40-119">**Munkafolyamatban** – Az importált számlát a program elküldte a munkafolyamat-rendszerbe akár automatizált munkafolyamatba küldési folyamattal, akár manuálisan.</span><span class="sxs-lookup"><span data-stu-id="65f40-119">**In workflow** – The imported invoice has been submitted to the workflow system, either by the automated submit-to-workflow process or manually.</span></span>
- <span data-ttu-id="65f40-120">**Munkafolyamat befejezve** – Az importált számlához tartozó munkafolyamat befejeződött.</span><span class="sxs-lookup"><span data-stu-id="65f40-120">**Workflow complete** – The workflow process has been completed for the imported invoice.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]