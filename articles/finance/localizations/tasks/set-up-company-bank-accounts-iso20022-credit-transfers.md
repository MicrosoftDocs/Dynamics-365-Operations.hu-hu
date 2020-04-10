---
title: Vállalati bankszámlák beállítása ISO20022 típusú átutalásokhoz
description: Ez az eljárás bemutatja a cégspecifikus bankszámlaadatok beállítását, amelyek fizetési fájl létrehozásához szükségesek.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankAccountTable, OMLegalEntity, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5e121ce7d87ee50a4e6b367a170eea4375d64fb3
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144874"
---
# <a name="set-up-company-bank-accounts-for-iso20022-credit-transfers"></a><span data-ttu-id="c1602-103">Vállalati bankszámlák beállítása ISO20022 típusú átutalásokhoz</span><span class="sxs-lookup"><span data-stu-id="c1602-103">Set up company bank accounts for ISO20022 credit transfers</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c1602-104">Ez az eljárás bemutatja a cégspecifikus bankszámlaadatok beállítását, amelyek fizetési fájl létrehozásához szükségesek.</span><span class="sxs-lookup"><span data-stu-id="c1602-104">This procedure shows how to set up company-specific bank account information that is required for payment file generation.</span></span> <span data-ttu-id="c1602-105">Az adatok megadása az ISO 20022 átutalási formátum létrehozásának igényei alapján történik, de formátumtól függően lehet, hogy más adatokat, például a vállalat azonosítója vagy a rendezési kódot is meg kell adni.</span><span class="sxs-lookup"><span data-stu-id="c1602-105">You set up information required to generate ISO 20022 credit transfer format but depending on the format there might be other information required, such as the Company ID or the Sort code.</span></span> 

<span data-ttu-id="c1602-106">Ez az eljárás az DEMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="c1602-106">The demo data company used to create this procedure is DEMF.</span></span>

<span data-ttu-id="c1602-107">Ez a második azon öt eljárás közül, amelyek elektronikus jelentési beállítások használatával mutatják be a szállítói kifizetési folyamatot.</span><span class="sxs-lookup"><span data-stu-id="c1602-107">This is the second procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="c1602-108">Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.</span><span class="sxs-lookup"><span data-stu-id="c1602-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-iban-and-swift-code"></a><span data-ttu-id="c1602-109">IBAN- és SWIFT-kód beállítása</span><span class="sxs-lookup"><span data-stu-id="c1602-109">Set up IBAN and SWIFT code</span></span>
1. <span data-ttu-id="c1602-110">Ugorjon a Készpénz- és bankkezelés > Bankszámlák pontra.</span><span class="sxs-lookup"><span data-stu-id="c1602-110">Go to Cash and bank management > Bank accounts.</span></span>
2. <span data-ttu-id="c1602-111">A gyorsszűrő használatával szűrjön rá a Bankszámla mezőre a „DEMF OPER” értékkel.</span><span class="sxs-lookup"><span data-stu-id="c1602-111">Use the Quick Filter to filter on the Bank account field with a value of 'DEMF OPER'.</span></span>
3. <span data-ttu-id="c1602-112">Kattintson a DEMF OPER lehetőségre a bankszámla adatainak megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="c1602-112">Click DEMF OPER to open bank account details.</span></span>
4. <span data-ttu-id="c1602-113">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c1602-113">Click Edit.</span></span>
5. <span data-ttu-id="c1602-114">Bontsa ki a További azonosítás szakaszt.</span><span class="sxs-lookup"><span data-stu-id="c1602-114">Expand the Additional identification section.</span></span>
6. <span data-ttu-id="c1602-115">Az IBAN mezőbe írja be a „DE89370400440532013000” értéket.</span><span class="sxs-lookup"><span data-stu-id="c1602-115">In the IBAN field, type 'DE89370400440532013000'.</span></span>
7. <span data-ttu-id="c1602-116">A SWIFT kód mezőbe írja be a „DEUTDEFF” értéket.</span><span class="sxs-lookup"><span data-stu-id="c1602-116">In the SWIFT code field, type 'DEUTDEFF'.</span></span>
    * <span data-ttu-id="c1602-117">Ne feledje, hogy sok fizetési formátumhoz a SWIFT\BIC nem szükséges, ajánlott viszont rögzíteni a bankszámlához.</span><span class="sxs-lookup"><span data-stu-id="c1602-117">Note that SWIFT\BIC is not required for many payment formats, however it is recommended to have it registered for a bank account.</span></span>  
8. <span data-ttu-id="c1602-118">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="c1602-118">Click Save.</span></span>

## <a name="set-up-bank-account-for-the-legal-entity"></a><span data-ttu-id="c1602-119">Bankszámla beállítása jogi személynek</span><span class="sxs-lookup"><span data-stu-id="c1602-119">Set up bank account for the legal entity</span></span>
1. <span data-ttu-id="c1602-120">Ugorjon a Szervezeti adminisztráció > Szervezetek > Jogi személyek pontra.</span><span class="sxs-lookup"><span data-stu-id="c1602-120">Go to Organization administration > Organizations > Legal entities.</span></span>
2. <span data-ttu-id="c1602-121">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c1602-121">Click Edit.</span></span>
3. <span data-ttu-id="c1602-122">Bontsa ki a Bankszámlaadatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="c1602-122">Expand the Bank account information section.</span></span>
4. <span data-ttu-id="c1602-123">A Bankszámlák mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c1602-123">In the Bank account field, enter or select a value.</span></span>
5. <span data-ttu-id="c1602-124">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="c1602-124">Click Save.</span></span>

