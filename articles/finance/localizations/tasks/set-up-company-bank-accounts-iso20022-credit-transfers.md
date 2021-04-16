---
title: Vállalati bankszámlák beállítása ISO20022 típusú átutalásokhoz
description: Ez az eljárás bemutatja a cégspecifikus bankszámlaadatok beállítását, amelyek fizetési fájl létrehozásához szükségesek.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankAccountTable, OMLegalEntity, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a3ddcae4a53fffa07bd386174811c12150f2f162
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819480"
---
# <a name="set-up-company-bank-accounts-for-iso20022-credit-transfers"></a><span data-ttu-id="68b9d-103">Vállalati bankszámlák beállítása ISO20022 típusú átutalásokhoz</span><span class="sxs-lookup"><span data-stu-id="68b9d-103">Set up company bank accounts for ISO20022 credit transfers</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="68b9d-104">Ez az eljárás bemutatja a cégspecifikus bankszámlaadatok beállítását, amelyek fizetési fájl létrehozásához szükségesek.</span><span class="sxs-lookup"><span data-stu-id="68b9d-104">This procedure shows how to set up company-specific bank account information that is required for payment file generation.</span></span> <span data-ttu-id="68b9d-105">Az adatok megadása az ISO 20022 átutalási formátum létrehozásának igényei alapján történik, de formátumtól függően lehet, hogy más adatokat, például a vállalat azonosítója vagy a rendezési kódot is meg kell adni.</span><span class="sxs-lookup"><span data-stu-id="68b9d-105">You set up information required to generate ISO 20022 credit transfer format but depending on the format there might be other information required, such as the Company ID or the Sort code.</span></span> 

<span data-ttu-id="68b9d-106">Ez az eljárás az DEMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="68b9d-106">The demo data company used to create this procedure is DEMF.</span></span>

<span data-ttu-id="68b9d-107">Ez a második azon öt eljárás közül, amelyek elektronikus jelentési beállítások használatával mutatják be a szállítói kifizetési folyamatot.</span><span class="sxs-lookup"><span data-stu-id="68b9d-107">This is the second procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="68b9d-108">Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.</span><span class="sxs-lookup"><span data-stu-id="68b9d-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-iban-and-swift-code"></a><span data-ttu-id="68b9d-109">IBAN- és SWIFT-kód beállítása</span><span class="sxs-lookup"><span data-stu-id="68b9d-109">Set up IBAN and SWIFT code</span></span>
1. <span data-ttu-id="68b9d-110">Ugorjon a Készpénz- és bankkezelés > Bankszámlák pontra.</span><span class="sxs-lookup"><span data-stu-id="68b9d-110">Go to Cash and bank management > Bank accounts.</span></span>
2. <span data-ttu-id="68b9d-111">A gyorsszűrő használatával szűrjön rá a Bankszámla mezőre a „DEMF OPER” értékkel.</span><span class="sxs-lookup"><span data-stu-id="68b9d-111">Use the Quick Filter to filter on the Bank account field with a value of 'DEMF OPER'.</span></span>
3. <span data-ttu-id="68b9d-112">Kattintson a DEMF OPER lehetőségre a bankszámla adatainak megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="68b9d-112">Click DEMF OPER to open bank account details.</span></span>
4. <span data-ttu-id="68b9d-113">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="68b9d-113">Click Edit.</span></span>
5. <span data-ttu-id="68b9d-114">Bontsa ki a További azonosítás szakaszt.</span><span class="sxs-lookup"><span data-stu-id="68b9d-114">Expand the Additional identification section.</span></span>
6. <span data-ttu-id="68b9d-115">Az IBAN mezőbe írja be a „DE89370400440532013000” értéket.</span><span class="sxs-lookup"><span data-stu-id="68b9d-115">In the IBAN field, type 'DE89370400440532013000'.</span></span>
7. <span data-ttu-id="68b9d-116">A SWIFT kód mezőbe írja be a „DEUTDEFF” értéket.</span><span class="sxs-lookup"><span data-stu-id="68b9d-116">In the SWIFT code field, type 'DEUTDEFF'.</span></span>
    * <span data-ttu-id="68b9d-117">Ne feledje, hogy sok fizetési formátumhoz a SWIFT\BIC nem szükséges, ajánlott viszont rögzíteni a bankszámlához.</span><span class="sxs-lookup"><span data-stu-id="68b9d-117">Note that SWIFT\BIC is not required for many payment formats, however it is recommended to have it registered for a bank account.</span></span>  
8. <span data-ttu-id="68b9d-118">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="68b9d-118">Click Save.</span></span>

## <a name="set-up-bank-account-for-the-legal-entity"></a><span data-ttu-id="68b9d-119">Bankszámla beállítása jogi személynek</span><span class="sxs-lookup"><span data-stu-id="68b9d-119">Set up bank account for the legal entity</span></span>
1. <span data-ttu-id="68b9d-120">Ugorjon a Szervezeti adminisztráció > Szervezetek > Jogi személyek pontra.</span><span class="sxs-lookup"><span data-stu-id="68b9d-120">Go to Organization administration > Organizations > Legal entities.</span></span>
2. <span data-ttu-id="68b9d-121">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="68b9d-121">Click Edit.</span></span>
3. <span data-ttu-id="68b9d-122">Bontsa ki a Bankszámlaadatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="68b9d-122">Expand the Bank account information section.</span></span>
4. <span data-ttu-id="68b9d-123">A Bankszámlák mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="68b9d-123">In the Bank account field, enter or select a value.</span></span>
5. <span data-ttu-id="68b9d-124">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="68b9d-124">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]