---
title: A pénzügyi és adóügyi hivatkozási adatokhoz való hozzáférés
description: Ez a témakör a pénzügyi és adóügyi hivatkozási adatokhoz való hozzáféréssel kapcsolatban nyújt tájékoztatást.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: 3003eabf970bc0883ff22d930b4a111925af1eeb
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684031"
---
# <a name="access-to-finance-and-tax-reference-data"></a><span data-ttu-id="2ef7e-103">A pénzügyi és adóügyi hivatkozási adatokhoz való hozzáférés</span><span class="sxs-lookup"><span data-stu-id="2ef7e-103">Access to finance and tax reference data</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="2ef7e-104">Minden vállalkozás pénzügyi adatok egy alapvető készletével dolgozik, például üzleti év, a pénznem, amiben az vállalkozás a tranzakcióit folytatja, a számlák, amelyen a pénzforgalom zajlik, adókulcsok és utalás.</span><span class="sxs-lookup"><span data-stu-id="2ef7e-104">Every business works with a basic set of financial data, such as the fiscal calendar year, the currency that business is transacted in, the accounts that the money to run the business comes in to or goes out of, tax rates, and remittance.</span></span> <span data-ttu-id="2ef7e-105">Ezek az adatok a Finance and Operations alkalmazásokban találhatók.</span><span class="sxs-lookup"><span data-stu-id="2ef7e-105">This data resides in Finance and Operations apps.</span></span> <span data-ttu-id="2ef7e-106">Azonban ez elérhető a Dataverse számára, hogy a modellvezérelt alkalmazások a Microsoft Dynamics 365-ben egyetlen forrásból jussanak pénzügyi és adózási adatokhoz.</span><span class="sxs-lookup"><span data-stu-id="2ef7e-106">However, it's exposed to Dataverse so that model-driven apps in Microsoft Dynamics 365 can have a single source for finance and tax data.</span></span> <span data-ttu-id="2ef7e-107">Ily módon az adatok az üzleti ökoszisztémán belül egységesek.</span><span class="sxs-lookup"><span data-stu-id="2ef7e-107">In this way, data is uniform across the business ecosystem.</span></span> 

<span data-ttu-id="2ef7e-108">A pénzügyi és adózási adatok a következő hozzárendelések segítségével integrálhatók:</span><span class="sxs-lookup"><span data-stu-id="2ef7e-108">Finance and tax data is integrated by using the following mappings:</span></span>

+ [<span data-ttu-id="2ef7e-109">Integrált főkönyv</span><span class="sxs-lookup"><span data-stu-id="2ef7e-109">Integrated ledger</span></span>](ledger-mapping.md)
+ [<span data-ttu-id="2ef7e-110">Integrált adózási alapadat</span><span class="sxs-lookup"><span data-stu-id="2ef7e-110">Integrated tax master</span></span>](tax-mapping.md)
