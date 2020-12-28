---
title: EUR-00015 Fél keresése adószám használatával
description: Ez az eljárás bemutatja, hogyan kell elvégezni egy fél keresését a regisztrációs azonosító használatával.
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DirPartyTable, DirPartTaxRegistrationSearch
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 401971b6f146f1df028291ba0f691ccac5f1966d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408016"
---
# <a name="eur-00015-party-search-using-vat-id"></a><span data-ttu-id="2a28c-103">EUR-00015 Fél keresése adószám használatával</span><span class="sxs-lookup"><span data-stu-id="2a28c-103">EUR-00015 Party search using VAT ID</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2a28c-104">Ez az eljárás bemutatja, hogyan kell elvégezni egy fél keresését a regisztrációs azonosító használatával.</span><span class="sxs-lookup"><span data-stu-id="2a28c-104">This procedure shows how to complete a party search using a registration ID.</span></span> <span data-ttu-id="2a28c-105">Mielőtt ezt a műveletet végrehajthatná, be kell állítani az áfaazonosítót, és áfaazonosítót kell megadnia a szállítókhoz, vevőkhöz vagy jogi személyekhez.</span><span class="sxs-lookup"><span data-stu-id="2a28c-105">Before you can complete this procedure, you must set up VAT IDs and enter any VAT IDs for vendors, customers, or legal entities.</span></span>

<span data-ttu-id="2a28c-106">Ez az eljárás minden európai országra/régióra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="2a28c-106">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="2a28c-107">Ezt az eljárást a németországi elsődleges címmel rendelkező DEMF bemutatócég segítségével hozták létre.</span><span class="sxs-lookup"><span data-stu-id="2a28c-107">The procedure was created using the demo data company DEMF with a primary address in Germany.</span></span> <span data-ttu-id="2a28c-108">Ez az eljárás a kötelezettségeket kezelő vezető és a kinnlevőség-kezelő számára szól.</span><span class="sxs-lookup"><span data-stu-id="2a28c-108">This procedure is intended for an accounts payable manager or accounts receivable manager.</span></span> <span data-ttu-id="2a28c-109">Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.</span><span class="sxs-lookup"><span data-stu-id="2a28c-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="2a28c-110">Ugrás a Szervezeti adminisztráció > Globális címjegyzék > Globális címjegyzék elemre.</span><span class="sxs-lookup"><span data-stu-id="2a28c-110">Go to Organization administration > Global address book > Global address book.</span></span>
2. <span data-ttu-id="2a28c-111">Kattintson a Regisztrációs azonosító keresése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2a28c-111">Click Registration ID search.</span></span>
3. <span data-ttu-id="2a28c-112">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="2a28c-112">Click Add.</span></span>
4. <span data-ttu-id="2a28c-113">A Regisztráció típusa mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2a28c-113">In the Registration type field, enter or select a value.</span></span>
    * <span data-ttu-id="2a28c-114">Ha például áfaazonosító típusú regisztrációs azonosítóval rendelkező feleket szeretne megkeresni, válassza az áfaazonosítót.</span><span class="sxs-lookup"><span data-stu-id="2a28c-114">For example, if you wanted to find parties with a registration ID of type VAT ID, select VAT ID.</span></span>  
5. <span data-ttu-id="2a28c-115">Az Ország/régió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2a28c-115">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="2a28c-116">Például írja be, hogy DEU.</span><span class="sxs-lookup"><span data-stu-id="2a28c-116">For example, enter DEU.</span></span>  
6. <span data-ttu-id="2a28c-117">Írjon be egy értéket a Regisztrációs szám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="2a28c-117">In the Registration number field, type a value.</span></span>
7. <span data-ttu-id="2a28c-118">Kattintson a Keresés gombra.</span><span class="sxs-lookup"><span data-stu-id="2a28c-118">Click Find.</span></span>
    * <span data-ttu-id="2a28c-119">Minden, az adott regisztrációs azonosítóval rendelkező fél megjelenik.</span><span class="sxs-lookup"><span data-stu-id="2a28c-119">All parties with that registration ID will be displayed.</span></span>  

