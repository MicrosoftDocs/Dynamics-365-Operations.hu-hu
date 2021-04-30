---
title: Külső adatok használata pénzforgalmi előrejelzésekben (előzetes verzió)
description: Ez a témakör azokat a beállítási lépéseket ismerteti, amelyeket végre kell hajtania ahhoz, hogy külső adatokat lehessen bevinni vagy behozni a pénzforgalmi előrejelzésekbe.
author: rcarlson
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: ddfc0670a5fca24d996e9ab605e267f9f3f26f19
ms.sourcegitcommit: 7d0cfb359a4abc7392ddb3f0b3e9539c40b7204d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/14/2021
ms.locfileid: "5897888"
---
# <a name="use-external-data-in-cash-flow-forecasts-preview"></a><span data-ttu-id="58200-103">Külső adatok használata pénzforgalmi előrejelzésekben (előzetes verzió)</span><span class="sxs-lookup"><span data-stu-id="58200-103">Use external data in cash flow forecasts (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="58200-104">A külső adatok bevihetők vagy importálhatók a pénzforgalmi előrejelzésekbe.</span><span class="sxs-lookup"><span data-stu-id="58200-104">External data can be entered or imported into cash flow forecasts.</span></span> <span data-ttu-id="58200-105">Ez a témakör azokat a beállítási lépéseket ismerteti, amelyek a külső adatok használatára vonatkoznak, és amelyek lehetővé teszik a külső adatok pénzforgalmi előrejelzésbe való beírását.</span><span class="sxs-lookup"><span data-stu-id="58200-105">This topic describes the setup steps that are specific to the use of external data and that enable the external data to be included in a cash flow forecast.</span></span>

## <a name="external-data-setup"></a><span data-ttu-id="58200-106">Külső adatbeállítás</span><span class="sxs-lookup"><span data-stu-id="58200-106">External data setup</span></span>

<span data-ttu-id="58200-107">A **Pénzforgalmi előrejelzés beállítása** lapon (**Készpénz- és bankkezelés \> Pénzforgalmi előrejelzés**) lévő **Külső forrás** oldalon adhatja meg azokat a beállításokat, amelyek támogatják a külső adatok használatát a pénzforgalmi előrejelzésekben.</span><span class="sxs-lookup"><span data-stu-id="58200-107">Use the **External source** tab on the **Cash flow forecast setup** page (**Cash and bank management \> Cash flow forecasting**) to enter settings that support the use of external data in cash flow forecasts.</span></span>

<span data-ttu-id="58200-108">Az számlálók beállításával kapcsolatos további információkat lásd: [Pénzforgalmi előrejelzés](../cash-bank-management/cash-flow-forecasting.md).</span><span class="sxs-lookup"><span data-stu-id="58200-108">For more information about the setup, see [Cash flow forecasting](../cash-bank-management/cash-flow-forecasting.md).</span></span>

<span data-ttu-id="58200-109">A pénzforgalmi előrejelzések külső adatainak megadásához használja az Open in Excel felhasználói felületet külső adatok beviteléhez és módosításához.</span><span class="sxs-lookup"><span data-stu-id="58200-109">To enter external data for cash flow forecasts, you can use the Open in Excel experience for entering and modifying external data.</span></span> <span data-ttu-id="58200-110">Válassza ki a **Külső adatok** gombot, majd válassza a **Külső adatok hozzáadása** vagy a **Meglévő külső adatok szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="58200-110">Select the **External data** button, and then select either **Add External Data** or **Edit existing external data**.</span></span> <span data-ttu-id="58200-111">A Microsoft Excel-fájl megnyitásakor a következő mezőkben adhatja meg a kívánt adatokat:</span><span class="sxs-lookup"><span data-stu-id="58200-111">When the Microsoft Excel file is opened, you can enter information in the following fields:</span></span>

- <span data-ttu-id="58200-112">**Bejegyzésazonosító**</span><span class="sxs-lookup"><span data-stu-id="58200-112">**Entry ID**</span></span>
- <span data-ttu-id="58200-113">**Leírás** (nem kötelező)</span><span class="sxs-lookup"><span data-stu-id="58200-113">**Description** (optional)</span></span>
- <span data-ttu-id="58200-114">**Külső forrás neve** – A pénzügyi betekintések beállításakor megadott lista egyik értékének kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="58200-114">**External Source name** – Select one of the values in the list that you defined when you set up Finance Insights.</span></span>
- <span data-ttu-id="58200-115">**Jogi személy**</span><span class="sxs-lookup"><span data-stu-id="58200-115">**Legal Entity**</span></span>
- <span data-ttu-id="58200-116">**Dátum**</span><span class="sxs-lookup"><span data-stu-id="58200-116">**Date**</span></span>
- <span data-ttu-id="58200-117">**Összeg a tranzakció pénznemében.**</span><span class="sxs-lookup"><span data-stu-id="58200-117">**Amount in transaction currency**</span></span>
- <span data-ttu-id="58200-118">**Pénznemkód**</span><span class="sxs-lookup"><span data-stu-id="58200-118">**Currency Code**</span></span>
- <span data-ttu-id="58200-119">**Alapértelmezett dimenzió** (nem kötelező)</span><span class="sxs-lookup"><span data-stu-id="58200-119">**Default Dimension** (optional)</span></span>
- <span data-ttu-id="58200-120">**Dokumentum száma** (nem kötelező)</span><span class="sxs-lookup"><span data-stu-id="58200-120">**Document number** (optional)</span></span>
- <span data-ttu-id="58200-121">**Számla száma** (nem kötelező)</span><span class="sxs-lookup"><span data-stu-id="58200-121">**Account number** (optional)</span></span>
- <span data-ttu-id="58200-122">**Számla neve** (nem kötelező)</span><span class="sxs-lookup"><span data-stu-id="58200-122">**Account name** (optional)</span></span>

## <a name="importing-external-data-by-using-the-data-management-framework"></a><span data-ttu-id="58200-123">Külső adatok importálása az Adatkezelési keretrendszer használatával</span><span class="sxs-lookup"><span data-stu-id="58200-123">Importing external data by using the Data Management framework</span></span>

<span data-ttu-id="58200-124">A külső adatokat a pénzforgalmi előrejelzésekhez az **Adatkezelés** munkaterületen és a **Pénzforgalmi előrejelzés külső forrás bejegyzésével** ellátott entitáson keresztül importálhatók.</span><span class="sxs-lookup"><span data-stu-id="58200-124">You can import external data for cash flow forecasts by using the **Data Management** workspace and the entity that is named **Cash flow forecast external source entry**.</span></span>

<span data-ttu-id="58200-125">Ezenkívül ha a beállítási adatokat át kell vinni egyik környezetből a másikba, a következő entitások érhetők el a szükséges beállítási táblákban:</span><span class="sxs-lookup"><span data-stu-id="58200-125">Additionally, if you must move setup data from one environment to another, the following entities area available for the setup tables that are required:</span></span>

- <span data-ttu-id="58200-126">Pénzforgalmi előrejelzés külső forrásának beállítása</span><span class="sxs-lookup"><span data-stu-id="58200-126">Cash flow forecast external source setup</span></span>
- <span data-ttu-id="58200-127">Pénzforgalmi előrejelzés külső forrásaként megadott jogi személy beállítása</span><span class="sxs-lookup"><span data-stu-id="58200-127">Cash flow forecast external source legal entity setup</span></span>

#### <a name="privacy-notice"></a><span data-ttu-id="58200-128">Adatvédelmi nyilatkozat</span><span class="sxs-lookup"><span data-stu-id="58200-128">Privacy notice</span></span>
<span data-ttu-id="58200-129">Az előzetes verziók (1) kevesebb adatvédelmi és biztonsági intézkedést alkalmazhatnak, mint a Dynamics 365 Finance and Operations szolgáltatás (2) és nem vonatkozik a szolgáltatásiszint-szerződés (SLA) ehhez a szolgáltatáshoz, (3) nem használhatók olyan személyes adatok vagy más adatok feldolgozásához, melyekhez törvényi vagy jogszabályi megfelelési követelmények tartoznak, és (4) korlátozott támogatás tartozik hozzá.</span><span class="sxs-lookup"><span data-stu-id="58200-129">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]