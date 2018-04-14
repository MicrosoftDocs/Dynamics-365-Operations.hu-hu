---
title: "A kelet-európai elszámolási tranzakciók megtekintése"
description: "Ez a témakör a vevők és szállítók Elszámolási tranzakciók lapjával kapcsolatosan tartalmaz információkat."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustVendTransPostingLog_RU
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 270544
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: e2972d06346533659dfc26ac243dc57ec5e0f6fb
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---

# <a name="view-transactions-on-settlement-for-eastern-europe"></a><span data-ttu-id="adf25-103">A kelet-európai elszámolási tranzakciók megtekintése</span><span class="sxs-lookup"><span data-stu-id="adf25-103">View transactions on settlement for Eastern Europe</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="adf25-104">Ez a témakör a vevők és szállítók Elszámolási tranzakciók lapjával kapcsolatosan tartalmaz információkat.</span><span class="sxs-lookup"><span data-stu-id="adf25-104">This topic provides information about the Transactions on settlement page for customers and vendors.</span></span>

<span data-ttu-id="adf25-105">Használja az **Elszámolási tranzakciók** lapot a vevők vagy szállítók összetett kiegyenlítési tranzakcióival kapcsolatos információk megtekintésére.</span><span class="sxs-lookup"><span data-stu-id="adf25-105">Use the **Transactions on settlement** page to view information about complex settlement transactions for a customer or a vendor.</span></span> <span data-ttu-id="adf25-106">Ez a funkció csak az olyan jogi személyek esetében működik, amelyeknek Litvániában, Lettországban, Észtországban, Csehországban, Magyarországon vagy Lengyelországban van az elsődleges címe.</span><span class="sxs-lookup"><span data-stu-id="adf25-106">This feature is available only for legal entities that have their primary address in Lithuania, Latvia, Estonia, Czech Republic, Hungary, or Poland.</span></span> <span data-ttu-id="adf25-107">Az **Elszámolási tranzakciók** lapot az alábbi helyeken találja:</span><span class="sxs-lookup"><span data-stu-id="adf25-107">You can find the **Transactions on settlement** page at the following locations:</span></span>

-   <span data-ttu-id="adf25-108">**Kötelezettségek** &gt; **Szállítók** &gt; **Minden szállító**.</span><span class="sxs-lookup"><span data-stu-id="adf25-108">**Accounts payable** &gt; **Vendors** &gt; **All vendors**.</span></span> <span data-ttu-id="adf25-109">A **Szállító** lap műveletpaneljén kattintson a **Tranzakciók** &gt; **Tranzakciók** elemre.</span><span class="sxs-lookup"><span data-stu-id="adf25-109">On the Action Pane, on the **Vendor** tab, click **Transactions** &gt; **Transactions**.</span></span> <span data-ttu-id="adf25-110">A **Szállítói tranzakciók** lapon válasszon ki egy tranzakciót, és kattintson az **Elszámolási tranzakciók** elemre.</span><span class="sxs-lookup"><span data-stu-id="adf25-110">On the **Vendor transactions** page, select a transaction, and then click **Transactions on settlement**.</span></span>
-   <span data-ttu-id="adf25-111">**Kinnlevőségek** &gt; **Vevők** &gt; **Minden vevő**.</span><span class="sxs-lookup"><span data-stu-id="adf25-111">**Accounts receivable** &gt; **Customers** &gt; **All customers**.</span></span> <span data-ttu-id="adf25-112">A **Vevő** lap műveletpaneljén kattintson a **Tranzakciók** elemre.</span><span class="sxs-lookup"><span data-stu-id="adf25-112">On the Action Pane, on the **Customer** tab, click **Transactions**.</span></span> <span data-ttu-id="adf25-113">A **Vevői tranzakciók** lapon válasszon ki egy tranzakciót, és kattintson az **Elszámolási tranzakciók** elemre.</span><span class="sxs-lookup"><span data-stu-id="adf25-113">On the **Customer transactions** page, select a transaction, and then click **Transactions on settlement**.</span></span>

<span data-ttu-id="adf25-114">A rendszer rögzíti az elszámolással kapcsolatos információkat, amelyek megjeleníthetők az **Elszámolási tranzakciók** oldalon azon tranzakcióknál, amelyek a következő helyzetekben jöttek létre:</span><span class="sxs-lookup"><span data-stu-id="adf25-114">Settlement-related information is captured and can be shown on the **Transactions on settlement** page for transactions that were created in the following scenarios:</span></span>

-   <span data-ttu-id="adf25-115">**Árfolyam-korrekció** - amikor egy számla kiegyenlítése és a fizetés realizált vagy nem realizált árfolyam-különbözetet okoz.</span><span class="sxs-lookup"><span data-stu-id="adf25-115">**Exchange adjustment** – Settlement of an invoice and a payment generates a realized or unrealized exchange rate difference.</span></span>
-   <span data-ttu-id="adf25-116">**Feladási profil módosítása** – Két bejegyzés, például egy számla és egy jóváírás, amelyeknél különböző feladási profilok vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="adf25-116">**Posting profile change** – Two entries, such as an invoice and a credit memo, that have different posting profiles are settled.</span></span>
-   <span data-ttu-id="adf25-117">Az előlegfizetés fizetéssé vagy a fizetés előleggé van alakítva.</span><span class="sxs-lookup"><span data-stu-id="adf25-117">A prepayment is converted to a payment, or a payment is converted to a prepayment.</span></span>
-   <span data-ttu-id="adf25-118">**Készpénzfizetési engedmény** - egy számla olyan fizetéssel való kiegyenlítése, amelyből levontak egy engedményösszeget.</span><span class="sxs-lookup"><span data-stu-id="adf25-118">**Cash discount** – An invoice is settled with a payment that a discount amount has been deducted from.</span></span>
-   <span data-ttu-id="adf25-119">**Filléreltérés** – Egy számla kiegyenlítése olyan fizetéssel történik, amely némileg eltérő összeget a számlán szereplőhöz képest.</span><span class="sxs-lookup"><span data-stu-id="adf25-119">**Penny difference** – An invoice is settled with a payment that has a slightly different amount than the invoice.</span></span>
-   <span data-ttu-id="adf25-120">**Feltételes adófeladás** - Egy számla olyan fizetéssel való kiegyenlítése, amelyre feltételes adó vonatkozik;</span><span class="sxs-lookup"><span data-stu-id="adf25-120">**Conditional tax posting** – An invoice is settled with a payment that conditional tax has been applied to.</span></span>
-   <span data-ttu-id="adf25-121">**Több vállalatot érintő kiegyenlítés** – Vállalatközi funkció, amely segítségével egy számla egy szervezettől eredő fizetéssel egyenlíthető ki.</span><span class="sxs-lookup"><span data-stu-id="adf25-121">**Cross-company settlement** – Intercompany functionality is used to settle an invoice with a payment from an organization.</span></span>





