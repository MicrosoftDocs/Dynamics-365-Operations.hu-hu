---
title: "Külső katalógus használata engedélyezése a PunchOut e-beszerzés számára"
description: "Ez a témakör bemutatja, hogyan tud külső katalógusok segítségével igényléseket létrehozni és elküldeni."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchVendorPortalRequests
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 035c5d15e5508c78dd66a349defd534bfecc96bb
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="use-external-catalogs-for-punchout-eprocurement"></a><span data-ttu-id="c925b-103">Külső katalógus használata engedélyezése a PunchOut e-beszerzés számára</span><span class="sxs-lookup"><span data-stu-id="c925b-103">Use external catalogs for PunchOut eProcurement</span></span>
<span data-ttu-id="c925b-104">Ha külső katalógusokat használ a PunchOut e-beszerzéssel, nem kell megőriznie a szállítók termékeivel kapcsolatos információkat a saját alapadataiban.</span><span class="sxs-lookup"><span data-stu-id="c925b-104">By using external catalogs for PunchOut e-procurement, you don't have to maintain information about your vendors' products in your own master data.</span></span> <span data-ttu-id="c925b-105">Ehelyett a rendszer a szállító webhelyén levő bevásárlókocsit alakítja át az igénylési sorokká, amelyek a megfelelő termékinformációkkal rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="c925b-105">Instead, the shopping cart on a vendor's website is converted to requisition lines that have the correct product information.</span></span> 

<span data-ttu-id="c925b-106">Kerülje a szállító termékei leírásainak és árainak saját termék alapadataiban történő karbantartását.</span><span class="sxs-lookup"><span data-stu-id="c925b-106">You should avoid maintaining the descriptions and prices of your vendors’ products in your own product master data.</span></span> <span data-ttu-id="c925b-107">Ehelyett használjon külső katalógusokat a PunchOut e-beszerzéssel.</span><span class="sxs-lookup"><span data-stu-id="c925b-107">Instead, use external catalogs for PunchOut e-procurement.</span></span> <span data-ttu-id="c925b-108">Ezután amikor az alkalmazottak igénylésekethoznak létre, „blokkolhatják” ezeket a szállító külső katalógusának helyéhez (vagyis elhagyják a rendszerét és a szállítói webhelyre lépnek).</span><span class="sxs-lookup"><span data-stu-id="c925b-108">Then, when employees create requisitions, they can “punch out” to a vendor’s external catalog site (in other words, they leave your system and go to the vendor’s site).</span></span> <span data-ttu-id="c925b-109">A bevásárlókocsihoz a szállító webhelyén hozzáadott termékek ezután igénylési sorokká konvertálhatók.</span><span class="sxs-lookup"><span data-stu-id="c925b-109">The products that are added to the shopping cart on the vendor’s website can then be converted to requisition lines.</span></span> <span data-ttu-id="c925b-110">Ennek megfelelően helyes termékinformációkat kap a termékazonosító, a név, az ár stb. tekintetében.</span><span class="sxs-lookup"><span data-stu-id="c925b-110">Therefore, you get the correct product information: product ID, name, price, and so on.</span></span>

<span data-ttu-id="c925b-111">Külső katalógusok használatához egy alkalmazottnak létre kell hoznia egy igénylést a **Saját beszerzési igénylések** lapon.</span><span class="sxs-lookup"><span data-stu-id="c925b-111">To use external catalogs, an employee must create a requisition on the **My purchase requisitions** page.</span></span>

<span data-ttu-id="c925b-112">Az igénylést létrehozó alkalmazottat az igénylés készítőjének nevezik.</span><span class="sxs-lookup"><span data-stu-id="c925b-112">The employee who creates a requisition is referred to as the preparer of the requisition.</span></span> <span data-ttu-id="c925b-113">Készítőként a következő műveleteket végezheti el:</span><span class="sxs-lookup"><span data-stu-id="c925b-113">As a preparer, you can complete the following tasks.</span></span>

<span data-ttu-id="c925b-114">A **Külső katalógusok** sorművelet segítsésével nyisson meg egy olyan lapot, amely tartalmazza a megadott kérelmező, vevő jogi személy és fogadó üzemi egység rendelkezésére álló összes külső katalógust.</span><span class="sxs-lookup"><span data-stu-id="c925b-114">Use the **External catalogs** line action to open a page that includes all external catalogs that are available for the specified requester, buying legal entity, and receiving operating unit.</span></span>

<span data-ttu-id="c925b-115">Az engedélyektől függően módosítsa a kérelmezőt, a vevő jogi személyt vagy a fogadó üzemi egységet.</span><span class="sxs-lookup"><span data-stu-id="c925b-115">Depending on your permissions, change the requester, buying legal entity, and receiving operating unit.</span></span> <span data-ttu-id="c925b-116">Az ilyen értékek módosítása megváltoztathatja a kérelmező számára elérhető külső katalógusok listáját.</span><span class="sxs-lookup"><span data-stu-id="c925b-116">A change in those values might change the list of external catalogs that are available to a requester.</span></span> <span data-ttu-id="c925b-117">A rendelkezésre álló külső katalógusok a vevő jogi személy vagy a bevételező üzemi egység aktuális aktív beszerzési irányelveitől függnek.</span><span class="sxs-lookup"><span data-stu-id="c925b-117">The external catalogs that are available depend on the current active purchasing policies for the buying legal entity or the receiving operating unit.</span></span> <span data-ttu-id="c925b-118">Ezek az irányelvek engedélyezhetik vagy megakadályozhatják a konkrét beszerzési kategóriákhoz való hozzáférést.</span><span class="sxs-lookup"><span data-stu-id="c925b-118">These policies can allow or prevent access to specific procurement categories.</span></span> <span data-ttu-id="c925b-119">Ezért ez befolyással lehet az ilyen beszerzési kategóriákhoz leképezett külső katalógusok listájára.</span><span class="sxs-lookup"><span data-stu-id="c925b-119">Therefore, the list of external catalogs that are mapped to these procurement categories can be affected.</span></span>

<span data-ttu-id="c925b-120">Az irényelvekkel kapcsolatos további információ: [Beszerzési irányelvek](../procurement/purchase-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c925b-120">For more information about policies, see [Purchasing policies](../procurement/purchase-policies.md).</span></span>

- <span data-ttu-id="c925b-121">Az egyes beszerzési kategóriákhoz tartozó külső katalógusok kereséséhez írjon be szöveget a katalóguskeresési mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c925b-121">To find external catalogs for specific procurement categories, enter text in the catalog search field.</span></span>
- <span data-ttu-id="c925b-122">A szállító weboldalán található termékek külső szállítói katalógusából történő hozzáadásához kattintson a külső katalógusra.</span><span class="sxs-lookup"><span data-stu-id="c925b-122">To add products from a vendor’s external catalog on the vendor’s website, click the external catalog.</span></span> <span data-ttu-id="c925b-123">Ezután adjon termékeket a bevásárlókocsihoz, majd fizessen. A bevásárlókocsi sorai átkerülnek a Microsoft Dynamics 365 rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="c925b-123">Then add products to the shopping cart, and check out. The shopping cart lines will be transferred to Microsoft Dynamics 365.</span></span>

<span data-ttu-id="c925b-124">Ha a beszerzési kategóriákhoz több lehetőség is van, válassza ki a megfelelő beszerzési kategóriát, mielőtt hozzáadná a sorokat az igényléshez.</span><span class="sxs-lookup"><span data-stu-id="c925b-124">If there are multiple options for procurement categories, select the correct procurement category before you add the lines to the requisition.</span></span>
<span data-ttu-id="c925b-125">Miután sorokat adtak hozzá egy igénybevételhez, további sorokat is hozzáadhat külső katalógusok használata nélkül.</span><span class="sxs-lookup"><span data-stu-id="c925b-125">After lines have been added to a requisition, you can add more lines without using external catalogs.</span></span> <span data-ttu-id="c925b-126">Alternatívaként továbbra is használhat külső katalógusokat sorok hozzáadására.</span><span class="sxs-lookup"><span data-stu-id="c925b-126">Alternatively, you can continue to use external catalogs to add lines.</span></span>

<span data-ttu-id="c925b-127">Amikor az igénylés készen áll, használja a **Munkafolyamat** > **Küldés** műveletet a jóváhagyásra küldéshez.</span><span class="sxs-lookup"><span data-stu-id="c925b-127">When the requisition is ready, use the **Workflow** > **Submit** action to submit it for approval.</span></span>

