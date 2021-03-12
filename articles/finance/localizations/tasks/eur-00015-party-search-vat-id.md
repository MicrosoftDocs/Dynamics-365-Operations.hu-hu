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
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c586de249575def120a6ae04fdc409aadfa1083d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4984840"
---
# <a name="eur-00015-party-search-using-vat-id"></a><span data-ttu-id="efbfd-103">EUR-00015 Fél keresése adószám használatával</span><span class="sxs-lookup"><span data-stu-id="efbfd-103">EUR-00015 Party search using VAT ID</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="efbfd-104">Ez az eljárás bemutatja, hogyan kell elvégezni egy fél keresését a regisztrációs azonosító használatával.</span><span class="sxs-lookup"><span data-stu-id="efbfd-104">This procedure shows how to complete a party search using a registration ID.</span></span> <span data-ttu-id="efbfd-105">Mielőtt ezt a műveletet végrehajthatná, be kell állítani az áfaazonosítót, és áfaazonosítót kell megadnia a szállítókhoz, vevőkhöz vagy jogi személyekhez.</span><span class="sxs-lookup"><span data-stu-id="efbfd-105">Before you can complete this procedure, you must set up VAT IDs and enter any VAT IDs for vendors, customers, or legal entities.</span></span>

<span data-ttu-id="efbfd-106">Ez az eljárás minden európai országra/régióra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="efbfd-106">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="efbfd-107">Ezt az eljárást a németországi elsődleges címmel rendelkező DEMF bemutatócég segítségével hozták létre.</span><span class="sxs-lookup"><span data-stu-id="efbfd-107">The procedure was created using the demo data company DEMF with a primary address in Germany.</span></span> <span data-ttu-id="efbfd-108">Ez az eljárás a kötelezettségeket kezelő vezető és a kinnlevőség-kezelő számára szól.</span><span class="sxs-lookup"><span data-stu-id="efbfd-108">This procedure is intended for an accounts payable manager or accounts receivable manager.</span></span> <span data-ttu-id="efbfd-109">Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.</span><span class="sxs-lookup"><span data-stu-id="efbfd-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="efbfd-110">Ugrás a Szervezeti adminisztráció > Globális címjegyzék > Globális címjegyzék elemre.</span><span class="sxs-lookup"><span data-stu-id="efbfd-110">Go to Organization administration > Global address book > Global address book.</span></span>
2. <span data-ttu-id="efbfd-111">Kattintson a Regisztrációs azonosító keresése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="efbfd-111">Click Registration ID search.</span></span>
3. <span data-ttu-id="efbfd-112">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="efbfd-112">Click Add.</span></span>
4. <span data-ttu-id="efbfd-113">A Regisztráció típusa mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="efbfd-113">In the Registration type field, enter or select a value.</span></span>
    * <span data-ttu-id="efbfd-114">Ha például áfaazonosító típusú regisztrációs azonosítóval rendelkező feleket szeretne megkeresni, válassza az áfaazonosítót.</span><span class="sxs-lookup"><span data-stu-id="efbfd-114">For example, if you wanted to find parties with a registration ID of type VAT ID, select VAT ID.</span></span>  
5. <span data-ttu-id="efbfd-115">Az Ország/régió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="efbfd-115">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="efbfd-116">Például írja be, hogy DEU.</span><span class="sxs-lookup"><span data-stu-id="efbfd-116">For example, enter DEU.</span></span>  
6. <span data-ttu-id="efbfd-117">Írjon be egy értéket a Regisztrációs szám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="efbfd-117">In the Registration number field, type a value.</span></span>
7. <span data-ttu-id="efbfd-118">Kattintson a Keresés gombra.</span><span class="sxs-lookup"><span data-stu-id="efbfd-118">Click Find.</span></span>
    * <span data-ttu-id="efbfd-119">Minden, az adott regisztrációs azonosítóval rendelkező fél megjelenik.</span><span class="sxs-lookup"><span data-stu-id="efbfd-119">All parties with that registration ID will be displayed.</span></span>  

