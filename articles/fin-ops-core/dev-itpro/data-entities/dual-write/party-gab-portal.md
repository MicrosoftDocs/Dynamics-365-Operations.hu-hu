---
title: A Power Portal használata a Fél adatmodelljével
description: Ez a témakör a Power Portal webszerepkörök változásait írja le a fél adatmodell megjelenése miatt a kettős írásban.
author: RamaKrishnamoorthy
ms.date: 03/22/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-22
ms.openlocfilehash: a2ea914344341ee26138e853727c551bdd5d733e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833090"
---
# <a name="using-power-portal-with-the-party-data-model"></a><span data-ttu-id="1aa12-103">A Power Portal használata a Fél adatmodelljével</span><span class="sxs-lookup"><span data-stu-id="1aa12-103">Using Power Portal with the Party data model</span></span>

[!INCLUDE[banner](../../includes/banner.md)]

[!INCLUDE[rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="1aa12-104">A kettős írású alkalmazás vezérlési megoldása 2.0.999.0 és későbbi verziója tartalmazza a partner- és globális címjegyzék adatmodell-módosításait a Számla és Kapcsolattartó táblákban.</span><span class="sxs-lookup"><span data-stu-id="1aa12-104">The Dual-write application orchestration solution version 2.0.999.0 and later includes data model changes to party and global address book for the Account and Contact tables.</span></span> <span data-ttu-id="1aa12-105">A módosítások több a többhöz kapcsolatot is lehetővé tesznek, amelyek speciális üzleti helyzeteket támogatnak.</span><span class="sxs-lookup"><span data-stu-id="1aa12-105">The changes allow many-to-many relationships that support advanced business scenarios.</span></span> <span data-ttu-id="1aa12-106">Ezeket a módosításokat nem támogatják a portál webes szerepkörei, köztük a vevői portál, amelyek a gyári telepítés része, vagy amelyek a környezetben léteztek a kettős írás telepítése előtt.</span><span class="sxs-lookup"><span data-stu-id="1aa12-106">These changes are not supported by portal web roles, including the customer portal, that are shipped out-of-the-box or that existed in your environment before you installed dual-write.</span></span> <span data-ttu-id="1aa12-107">Ahhoz, hogy a webes szerepkörök a várt módon működjenek, új webes szerepköröket kell létrehozni az új adatmodell segítségével.</span><span class="sxs-lookup"><span data-stu-id="1aa12-107">For the web roles to work as expected, you need to create new web roles using the new data model.</span></span> 

<span data-ttu-id="1aa12-108">Összegzésképpen: a táblák kommunikációja megváltozott, de a vevői portál táblaengedélyei nem módosultak.</span><span class="sxs-lookup"><span data-stu-id="1aa12-108">In summary, the way the tables interact has changed, but the table permissions in the customer portal haven't changed.</span></span> <span data-ttu-id="1aa12-109">Ez a témakör bemutatja az új speciális adatmodellel működő új webes szerepkörök létrehozásához szükséges feladatokat.</span><span class="sxs-lookup"><span data-stu-id="1aa12-109">This topic explains how to create new web roles that work with the new advanced data model.</span></span>

<span data-ttu-id="1aa12-110">Ez az ábra a fél és a globális címjegyzék adatmodell **nélkül** ábrázolja a táblakapcsolatokat:</span><span class="sxs-lookup"><span data-stu-id="1aa12-110">This diagram shows the table relationship **without** the party and global address book data model:</span></span>

   ![Fél modell nélkül](media/without-party-model.PNG)

<span data-ttu-id="1aa12-112">Ez az ábra a fél és a globális címjegyzék adatmodell **esetén** ábrázolja a táblakapcsolatokat:</span><span class="sxs-lookup"><span data-stu-id="1aa12-112">This diagram shows the table relationship **with** the party and global address book data model:</span></span>

   ![fél modellel](media/with-party-model.png)

## <a name="create-a-new-table-permission"></a><span data-ttu-id="1aa12-114">Új táblaengedély létrehozása</span><span class="sxs-lookup"><span data-stu-id="1aa12-114">Create a new table permission</span></span>

<span data-ttu-id="1aa12-115">Az alábbi lépések szerint hozhatja létre az új táblaengedélyeket:</span><span class="sxs-lookup"><span data-stu-id="1aa12-115">To create these new table permissions, follow these steps:</span></span>

1. <span data-ttu-id="1aa12-116">Jelentkezzen be a [Power Apps](https://make.powerapps.com) alkalmazásokba, és lépjen be az alkalmazásokba.</span><span class="sxs-lookup"><span data-stu-id="1aa12-116">Sign in to [Power Apps](https://make.powerapps.com), and go to your apps.</span></span>
2. <span data-ttu-id="1aa12-117">Válassza ki a Portálkezelést alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="1aa12-117">Select your Portal Management app.</span></span>
3. <span data-ttu-id="1aa12-118">Válassza az oldalsávon a **Biztonság > Táblaengedélyek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1aa12-118">In the side bar, select **Security > Table permissions**.</span></span>

    <span data-ttu-id="1aa12-119">Három új engedélyt kell létrehoznia:</span><span class="sxs-lookup"><span data-stu-id="1aa12-119">You must create three new permissions:</span></span>

    + <span data-ttu-id="1aa12-120">Kapcsolattartó a félhez kapcsolat</span><span class="sxs-lookup"><span data-stu-id="1aa12-120">Contact to Party connection</span></span>
    + <span data-ttu-id="1aa12-121">Fél a kapcsolattartóhoz kapcsolat</span><span class="sxs-lookup"><span data-stu-id="1aa12-121">Party to Account connection</span></span>
    + <span data-ttu-id="1aa12-122">Fél a rendeléshez kapcsolat</span><span class="sxs-lookup"><span data-stu-id="1aa12-122">Account to Order connection</span></span>

4. <span data-ttu-id="1aa12-123">Új engedély létrehozása és mentése a Kapcsolattartó a Félhez kapcsolathoz a következő paraméterek beállításával:</span><span class="sxs-lookup"><span data-stu-id="1aa12-123">Create and save a new permission for the Contact to Party connection, setting these parameters:</span></span>

    + <span data-ttu-id="1aa12-124">**Név**: Fél-Partner kapcsolat (vagy az Ön választása)</span><span class="sxs-lookup"><span data-stu-id="1aa12-124">**Name**: Party to Account Connection (or your choice)</span></span>
    + <span data-ttu-id="1aa12-125">**Tábla neve**: msdyn_contactforparty</span><span class="sxs-lookup"><span data-stu-id="1aa12-125">**Table Name**: msdyn_contactforparty</span></span>
    + <span data-ttu-id="1aa12-126">**Weboldal**: Ügyfélportál</span><span class="sxs-lookup"><span data-stu-id="1aa12-126">**Website**: Customer Portal</span></span>
    + <span data-ttu-id="1aa12-127">**Hatókör**: Kapcsolattartó</span><span class="sxs-lookup"><span data-stu-id="1aa12-127">**Scope**: Contact</span></span>
    + <span data-ttu-id="1aa12-128">**Jogosultságok**: Az összes kijelölése</span><span class="sxs-lookup"><span data-stu-id="1aa12-128">**Privileges**: Select all</span></span>
    + <span data-ttu-id="1aa12-129">**Webes szerepkörök**: Hitelesített felhasználók, ügyfél-képviselő (vagy az Ön választása)</span><span class="sxs-lookup"><span data-stu-id="1aa12-129">**Web roles**: Authenticated Users, Customer Representative (or your choice)</span></span>

5. <span data-ttu-id="1aa12-130">Új engedély létrehozása és mentése a Fél a Partnerhez kapcsolathoz a következő paraméterek beállításával:</span><span class="sxs-lookup"><span data-stu-id="1aa12-130">Create and save a new permission for the Party to Account connection, setting these parameters:</span></span>

    + <span data-ttu-id="1aa12-131">**Név**: Fél-Partner kapcsolat (vagy az Ön választása)</span><span class="sxs-lookup"><span data-stu-id="1aa12-131">**Name**: Party to Account Connection (or your choice)</span></span>
    + <span data-ttu-id="1aa12-132">**Tábla neve**: partner</span><span class="sxs-lookup"><span data-stu-id="1aa12-132">**Table Name**: account</span></span>
    + <span data-ttu-id="1aa12-133">**Weboldal**: Ügyfélportál</span><span class="sxs-lookup"><span data-stu-id="1aa12-133">**Website**: Customer Portal</span></span>
    + <span data-ttu-id="1aa12-134">**Hatókör:** Szülő</span><span class="sxs-lookup"><span data-stu-id="1aa12-134">**Scope**: Parent</span></span>
    + <span data-ttu-id="1aa12-135">**Jogosultságok**: Az összes kijelölése</span><span class="sxs-lookup"><span data-stu-id="1aa12-135">**Privileges**: Select all</span></span>
    + <span data-ttu-id="1aa12-136">**Szülőtábla engedélye**: Kapcsolattartó a Félhez kapcsolat</span><span class="sxs-lookup"><span data-stu-id="1aa12-136">**Parent Table Permission**: Contact to Party Connection</span></span>

6. <span data-ttu-id="1aa12-137">Új engedély létrehozása és mentése a Partner a Rendeléshez kapcsolathoz a következő paraméterek beállításával:</span><span class="sxs-lookup"><span data-stu-id="1aa12-137">Create and save a new permission for the Account to Order connection, setting these parameters:</span></span>

    + <span data-ttu-id="1aa12-138">**Név**: Fél a Partnerhez kapcsolat (vagy az Ön választása)</span><span class="sxs-lookup"><span data-stu-id="1aa12-138">**Name**: Account to Order Connection (or your choice)</span></span>
    + <span data-ttu-id="1aa12-139">**Tábla neve**: értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="1aa12-139">**Table Name**: salesorder</span></span>
    + <span data-ttu-id="1aa12-140">**Weboldal**: Ügyfélportál</span><span class="sxs-lookup"><span data-stu-id="1aa12-140">**Website**: Customer Portal</span></span>
    + <span data-ttu-id="1aa12-141">**Hatókör:** Szülő</span><span class="sxs-lookup"><span data-stu-id="1aa12-141">**Scope**: Parent</span></span>
    + <span data-ttu-id="1aa12-142">**Jogosultságok**: Az összes kijelölése</span><span class="sxs-lookup"><span data-stu-id="1aa12-142">**Privileges**: Select all</span></span>
    + <span data-ttu-id="1aa12-143">**Szülőtábla engedélye**: Fél a Partnerhez kapcsolat</span><span class="sxs-lookup"><span data-stu-id="1aa12-143">**Parent Table Permission**: Party to Account Connection</span></span>

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
