---
title: "Kiterjesztett bejelentkezés funkció beállítása Pénztár felhőhöz és MPOS-hoz"
description: "A témakör magába foglalja a felhőalapú pénztár és Kiskereskedelmi Modern pénztár (MPOS) kiterjesztett bejelentkezés beállításainak lehetőségeit."
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 92353
ms.assetid: 7473e237-fbc8-41d5-8ba0-920242747488
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 8075abccdcdde21df967dcc9948a738895f35cef
ms.openlocfilehash: d369b760047a18c82dd89f3452d94b9c62ba8841
ms.contentlocale: hu-hu
ms.lasthandoff: 01/25/2018

---

# <a name="set-up-extended-logon-functionality-for-cloud-pos-and-mpos"></a><span data-ttu-id="ad880-103">Kiterjesztett bejelentkezés funkció beállítása Pénztár felhőhöz és MPOS-hoz</span><span class="sxs-lookup"><span data-stu-id="ad880-103">Set up extended logon functionality for Cloud POS and MPOS</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="ad880-104">A témakör magába foglalja a felhőalapú pénztár és Kiskereskedelmi Modern pénztár (MPOS) kiterjesztett bejelentkezés beállításainak lehetőségeit.</span><span class="sxs-lookup"><span data-stu-id="ad880-104">This topic covers your options for setting up extended logon for Cloud POS and Retail Modern POS (MPOS).</span></span>

## <a name="setting-up-extended-logon"></a><span data-ttu-id="ad880-105">Kiterjesztett bejelentkezés beállítása</span><span class="sxs-lookup"><span data-stu-id="ad880-105">Setting up extended logon</span></span>

<span data-ttu-id="ad880-106">A vonalkódmaszkok beállítását megtalálja a következő helyen: **Kiskereskedelem** &gt; **Csatornabeállítás** &gt; **Pénztárbeállítás** &gt; **Pénztárprofilok** &gt; **Funkcióprofilok**.</span><span class="sxs-lookup"><span data-stu-id="ad880-106">You can find the setup for bar code masks at **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS profiles** &gt; **Functionality profiles**.</span></span> <span data-ttu-id="ad880-107">A **Funkciók** gyorslap a következő kiterjesztett belépéshez tartozó beállításokat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="ad880-107">The **Functions** FastTab includes the following options that are related to extended logon.</span></span>

### <a name="staff-bar-code-logon"></a><span data-ttu-id="ad880-108">Munkatárs - vonalkódos bejelentkezés</span><span class="sxs-lookup"><span data-stu-id="ad880-108">Staff bar code logon</span></span>

<span data-ttu-id="ad880-109">Amikor a **Személyzeti vonalkódos bejelentkezés** beállítás engedélyezve van, a pénztárhoz tartozó kiterjesztett bejelentkezéssel rendelkező dolgozók be tudnak lépni vonalkód használatával.</span><span class="sxs-lookup"><span data-stu-id="ad880-109">When the **Staff bar code logon** option is enabled, workers who have an extended logon assigned to their point of sale (POS) credentials can log on by using a bar code.</span></span>

### <a name="staff-bar-code-logon-requires-password"></a><span data-ttu-id="ad880-110">A személyzeti vonalkódos bejelentkezéshez jelszó szükséges</span><span class="sxs-lookup"><span data-stu-id="ad880-110">Staff bar code logon requires password</span></span>

<span data-ttu-id="ad880-111">Ha a **A személyzeti vonalkódos bejelentkezéshez jelszó szükséges** beállítás engedélyezve van, a személyzeti vonalkódos bejelentkezés csak azt a dolgozót engedi belépni, akinek van jogosultsága az aktuális kiterjesztett belépéshez.</span><span class="sxs-lookup"><span data-stu-id="ad880-111">When the **Staff bar code logon requires password** option is enabled, the staff bar code logon selects only the worker who is assigned to the extended logon that is presented.</span></span> <span data-ttu-id="ad880-112">A dolgozóknak be kell írniuk jelszavukat akkor is, ha ez a beállítás van engedélyezve.</span><span class="sxs-lookup"><span data-stu-id="ad880-112">Workers must still enter their password when this option is enabled.</span></span>

### <a name="staff-card-logon"></a><span data-ttu-id="ad880-113">Munkatárs - kártyás bejelentkezés</span><span class="sxs-lookup"><span data-stu-id="ad880-113">Staff card logon</span></span>

<span data-ttu-id="ad880-114">Amikor a **Személyzeti kártyás bejelentkezés** beállítás van engedélyezve, a pénztárhoz tartozó kiterjesztett bejelentkezéssel rendelkező dolgozók be tudnak lépni mágnescsík használatával.</span><span class="sxs-lookup"><span data-stu-id="ad880-114">When the **Staff card logon** option is enabled, workers who have an extended logon assigned to their POS credentials can log on by using a magnetic stripe.</span></span>

### <a name="staff-card-logon-requires-password"></a><span data-ttu-id="ad880-115">A személyzeti kártyás bejelentkezéshez jelszó szükséges</span><span class="sxs-lookup"><span data-stu-id="ad880-115">Staff card logon requires password</span></span>

<span data-ttu-id="ad880-116">Ha a **A személyzeti kártyás bejelentkezéshez jelszó szükséges** beállítás engedélyezve van, a személyzeti kártyás bejelentkezés csak azt a dolgozót engedi belépni, akinek van jogosultsága az aktuális kiterjesztett belépéshez.</span><span class="sxs-lookup"><span data-stu-id="ad880-116">When the **Staff card logon requires password** option is enabled, the staff card logon selects only the worker who is assigned to the extended logon that is presented.</span></span> <span data-ttu-id="ad880-117">A dolgozóknak be kell írniuk jelszavukat akkor is, ha ez a beállítás van engedélyezve.</span><span class="sxs-lookup"><span data-stu-id="ad880-117">Workers must still enter their password when this option is enabled.</span></span>

## <a name="assigning-an-extended-logon"></a><span data-ttu-id="ad880-118">Hozzárendelés kiterjesztett bejelentkezéshez</span><span class="sxs-lookup"><span data-stu-id="ad880-118">Assigning an extended logon</span></span>

<span data-ttu-id="ad880-119">Alapesetben csak a menedzser tud kiterjesztett bejelentkezést hozzárendelni a dolgozókhoz.</span><span class="sxs-lookup"><span data-stu-id="ad880-119">By default, only managers can assign extended logon to workers.</span></span> <span data-ttu-id="ad880-120">Kiterjesztett bejelentkezés hozzárendeléséhez, kattintson a **Kiterjesztett bejelentkezés** opcióra a pénztárban.</span><span class="sxs-lookup"><span data-stu-id="ad880-120">To assign extended logon, go to **Extended log on** in POS.</span></span> <span data-ttu-id="ad880-121">Ezután keressen rá a dolgozóra úgy, hogy begépeli annak dolgozói azonosítóját a keresőmezőbe.</span><span class="sxs-lookup"><span data-stu-id="ad880-121">Then search for a worker by entering his or her operator ID in the search field.</span></span> <span data-ttu-id="ad880-122">Válassza ki a dolgozót, majd kattintson az **Hozzáadás** gombra.</span><span class="sxs-lookup"><span data-stu-id="ad880-122">Select the worker, and then click **Assign**.</span></span> <span data-ttu-id="ad880-123">A következő oldalon húzza le vagy olvassa be a kiterjesztett belépést, hogy hozzárendelhesse azt a dolgozóhoz.</span><span class="sxs-lookup"><span data-stu-id="ad880-123">On the next page, swipe or scan the extended logon to assign to the worker.</span></span> <span data-ttu-id="ad880-124">Ha a lehúzás vagy a beolvasás sikeresen megtörtént, az **OK** gomb elérhetővé válik.</span><span class="sxs-lookup"><span data-stu-id="ad880-124">If the swipe or scan is successfully read, the **OK** button becomes available.</span></span> <span data-ttu-id="ad880-125">Kattintson a **OK** gombra, hogy elmentse az adott dolgozóhoz kapcsolódó kiterjesztett bejelentkezést.</span><span class="sxs-lookup"><span data-stu-id="ad880-125">Click **OK** to save the extended logon for that worker.</span></span>

## <a name="deleting-an-extended-logon"></a><span data-ttu-id="ad880-126">Kiterjesztett bejelentkezés törlése</span><span class="sxs-lookup"><span data-stu-id="ad880-126">Deleting an extended logon</span></span>

<span data-ttu-id="ad880-127">A dolgozó kiterjesztett bejelentkezésének törléséhez keresse meg a dolgozót a **Kiterjesztett bejelentkezés** művelet használatával.</span><span class="sxs-lookup"><span data-stu-id="ad880-127">To delete the extended logon that is assigned to a worker, search for the worker by using the **Extended log on** operation.</span></span> <span data-ttu-id="ad880-128">Válassza ki a dolgozót, majd kattintson az **Törlés** gombra.</span><span class="sxs-lookup"><span data-stu-id="ad880-128">Select the worker, and then click **Unassign**.</span></span> <span data-ttu-id="ad880-129">Minden (az adott dolgozóhoz tartozó) kiterjesztett bejelentkezési hitelesítő adat törlődik.</span><span class="sxs-lookup"><span data-stu-id="ad880-129">All extended logon credentials that are associated with that worker are removed.</span></span>

## <a name="extending-extended-logon"></a><span data-ttu-id="ad880-130">Kiterjesztett bejelentkezés kiterjesztése</span><span class="sxs-lookup"><span data-stu-id="ad880-130">Extending extended logon</span></span>

<span data-ttu-id="ad880-131">A bejelentkezés szolgáltatás kibővíthető, így pedig további beléptető szerkezetek is használhatóvá válnak (például: tenyér beolvasó).</span><span class="sxs-lookup"><span data-stu-id="ad880-131">The logon service can be extended to support additional extended logon devices, such as palm scanners.</span></span> <span data-ttu-id="ad880-132">További részletek a Pénztár kiterjesztés dokumentációban találhatók.</span><span class="sxs-lookup"><span data-stu-id="ad880-132">For more information, see the POS extensibility documentation.</span></span>

## <a name="using-extended-logon"></a><span data-ttu-id="ad880-133">Kiterjesztett bejelentkezés használata</span><span class="sxs-lookup"><span data-stu-id="ad880-133">Using extended logon</span></span>

<span data-ttu-id="ad880-134">Amennyiben a kiterjesztett bejelentkezés konfigurációja megtörtént és a dolgozóhoz hozzá lett rendelve jelszó vagy mágnescsík, a dolgozónak csupán le kell húznia vagy beolvastatnia a kártyáját, míg a pénztár belépő oldala meg van jelenítve.</span><span class="sxs-lookup"><span data-stu-id="ad880-134">When extended logon is configured, and a worker has been assigned a bar code or magnetic stripe, the worker just has to swipe or scan his or her card while the POS logon page is displayed.</span></span> <span data-ttu-id="ad880-135">Ha a jelszó is szükséges a bejelentkezéshez, a dolgozónak azt is szükséges beütnie..</span><span class="sxs-lookup"><span data-stu-id="ad880-135">If a password is also required before logon can proceed, the worker is prompted to enter his or her password.</span></span>




