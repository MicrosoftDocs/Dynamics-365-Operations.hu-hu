---
title: Külső adatok használata pénzforgalmi előrejelzésekben (előzetes verzió)
description: Ez a témakör azokat a beállítási lépéseket ismerteti, amelyeket végre kell hajtania ahhoz, hogy külső adatokat lehessen bevinni vagy behozni a pénzforgalmi előrejelzésekbe.
author: rcarlson
manager: AnnBe
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-06-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 03318eaae0b3329dc758c48202f8f47ca2c4ab08
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5245568"
---
# <a name="use-external-data-in-cash-flow-forecasts-preview"></a><span data-ttu-id="a516f-103">Külső adatok használata pénzforgalmi előrejelzésekben (előzetes verzió)</span><span class="sxs-lookup"><span data-stu-id="a516f-103">Use external data in cash flow forecasts (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="a516f-104">A külső adatok bevihetők vagy importálhatók a pénzforgalmi előrejelzésekbe.</span><span class="sxs-lookup"><span data-stu-id="a516f-104">External data can be entered or imported into cash flow forecasts.</span></span> <span data-ttu-id="a516f-105">Ez a témakör azokat a beállítási lépéseket ismerteti, amelyek a külső adatok használatára vonatkoznak, és amelyek lehetővé teszik a külső adatok pénzforgalmi előrejelzésbe való beírását.</span><span class="sxs-lookup"><span data-stu-id="a516f-105">This topic describes the setup steps that are specific to the use of external data and that enable the external data to be included in a cash flow forecast.</span></span>

## <a name="external-data-setup"></a><span data-ttu-id="a516f-106">Külső adatbeállítás</span><span class="sxs-lookup"><span data-stu-id="a516f-106">External data setup</span></span>

<span data-ttu-id="a516f-107">A **Pénzforgalmi előrejelzés beállítása** lapon (**Készpénz- és bankkezelés \> Pénzforgalmi előrejelzés**) lévő **Külső forrás** oldalon adhatja meg azokat a beállításokat, amelyek támogatják a külső adatok használatát a pénzforgalmi előrejelzésekben.</span><span class="sxs-lookup"><span data-stu-id="a516f-107">Use the **External source** tab on the **Cash flow forecast setup** page (**Cash and bank management \> Cash flow forecasting**) to enter settings that support the use of external data in cash flow forecasts.</span></span>

<span data-ttu-id="a516f-108">Az számlálók beállításával kapcsolatos további információkat lásd: [Pénzforgalmi előrejelzés](https://docs.microsoft.com/dynamics365/finance/cash-bank-management/cash-flow-forecasting).</span><span class="sxs-lookup"><span data-stu-id="a516f-108">For more information about the setup, see [Cash flow forecasting](https://docs.microsoft.com/dynamics365/finance/cash-bank-management/cash-flow-forecasting).</span></span>

<span data-ttu-id="a516f-109">A pénzforgalmi előrejelzések külső adatainak megadásához használja az Open in Excel felhasználói felületet külső adatok beviteléhez és módosításához.</span><span class="sxs-lookup"><span data-stu-id="a516f-109">To enter external data for cash flow forecasts, you can use the Open in Excel experience for entering and modifying external data.</span></span> <span data-ttu-id="a516f-110">Válassza ki a **Külső adatok** gombot, majd válassza a **Külső adatok hozzáadása** vagy a **Meglévő külső adatok szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a516f-110">Select the **External data** button, and then select either **Add External Data** or **Edit existing external data**.</span></span> <span data-ttu-id="a516f-111">A Microsoft Excel-fájl megnyitásakor a következő mezőkben adhatja meg a kívánt adatokat:</span><span class="sxs-lookup"><span data-stu-id="a516f-111">When the Microsoft Excel file is opened, you can enter information in the following fields:</span></span>

- <span data-ttu-id="a516f-112">**Bejegyzésazonosító**</span><span class="sxs-lookup"><span data-stu-id="a516f-112">**Entry ID**</span></span>
- <span data-ttu-id="a516f-113">**Leírás** (nem kötelező)</span><span class="sxs-lookup"><span data-stu-id="a516f-113">**Description** (optional)</span></span>
- <span data-ttu-id="a516f-114">**Külső forrás neve** – A pénzügyi betekintések beállításakor megadott lista egyik értékének kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="a516f-114">**External Source name** – Select one of the values in the list that you defined when you set up Finance Insights.</span></span>
- <span data-ttu-id="a516f-115">**Jogi személy**</span><span class="sxs-lookup"><span data-stu-id="a516f-115">**Legal Entity**</span></span>
- <span data-ttu-id="a516f-116">**Dátum**</span><span class="sxs-lookup"><span data-stu-id="a516f-116">**Date**</span></span>
- <span data-ttu-id="a516f-117">**Összeg a tranzakció pénznemében.**</span><span class="sxs-lookup"><span data-stu-id="a516f-117">**Amount in transaction currency**</span></span>
- <span data-ttu-id="a516f-118">**Pénznemkód**</span><span class="sxs-lookup"><span data-stu-id="a516f-118">**Currency Code**</span></span>
- <span data-ttu-id="a516f-119">**Alapértelmezett dimenzió** (nem kötelező)</span><span class="sxs-lookup"><span data-stu-id="a516f-119">**Default Dimension** (optional)</span></span>
- <span data-ttu-id="a516f-120">**Dokumentum száma** (nem kötelező)</span><span class="sxs-lookup"><span data-stu-id="a516f-120">**Document number** (optional)</span></span>
- <span data-ttu-id="a516f-121">**Számla száma** (nem kötelező)</span><span class="sxs-lookup"><span data-stu-id="a516f-121">**Account number** (optional)</span></span>
- <span data-ttu-id="a516f-122">**Számla neve** (nem kötelező)</span><span class="sxs-lookup"><span data-stu-id="a516f-122">**Account name** (optional)</span></span>

## <a name="importing-external-data-by-using-the-data-management-framework"></a><span data-ttu-id="a516f-123">Külső adatok importálása az Adatkezelési keretrendszer használatával</span><span class="sxs-lookup"><span data-stu-id="a516f-123">Importing external data by using the Data Management framework</span></span>

<span data-ttu-id="a516f-124">A külső adatokat a pénzforgalmi előrejelzésekhez az **Adatkezelés** munkaterületen és a **Pénzforgalmi előrejelzés külső forrás bejegyzésével** ellátott entitáson keresztül importálhatók.</span><span class="sxs-lookup"><span data-stu-id="a516f-124">You can import external data for cash flow forecasts by using the **Data Management** workspace and the entity that is named **Cash flow forecast external source entry**.</span></span>

<span data-ttu-id="a516f-125">Ezenkívül ha a beállítási adatokat át kell vinni egyik környezetből a másikba, a következő entitások érhetők el a szükséges beállítási táblákban:</span><span class="sxs-lookup"><span data-stu-id="a516f-125">Additionally, if you must move setup data from one environment to another, the following entities area available for the setup tables that are required:</span></span>

- <span data-ttu-id="a516f-126">Pénzforgalmi előrejelzés külső forrásának beállítása</span><span class="sxs-lookup"><span data-stu-id="a516f-126">Cash flow forecast external source setup</span></span>
- <span data-ttu-id="a516f-127">Pénzforgalmi előrejelzés külső forrásaként megadott jogi személy beállítása</span><span class="sxs-lookup"><span data-stu-id="a516f-127">Cash flow forecast external source legal entity setup</span></span>

#### <a name="privacy-notice"></a><span data-ttu-id="a516f-128">Adatvédelmi nyilatkozat</span><span class="sxs-lookup"><span data-stu-id="a516f-128">Privacy notice</span></span>
<span data-ttu-id="a516f-129">Az előzetes verziók (1) kevesebb adatvédelmi és biztonsági intézkedést alkalmazhatnak, mint a Dynamics 365 Finance and Operations szolgáltatás (2) és nem vonatkozik a szolgáltatásiszint-szerződés (SLA) ehhez a szolgáltatáshoz, (3) nem használhatók olyan személyes adatok vagy más adatok feldolgozásához, melyekhez törvényi vagy jogszabályi megfelelési követelmények tartoznak, és (4) korlátozott támogatás tartozik hozzá.</span><span class="sxs-lookup"><span data-stu-id="a516f-129">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]