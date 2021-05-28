---
title: TDS koncessziós tanúsítvány számának rögzítése
description: Ez a témakör elmagyarázza, hogyan kell rögzíteni a forrásnál levont adó (TDS) koncessziós tanúsítvány számait, amelyeket a szállítóknak bocsátanak ki.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: f543adc8bab5ca224bdb672d6b3c282c2d8531d8
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023286"
---
# <a name="record-tds-concession-certificate-numbers"></a><span data-ttu-id="59174-103">TDS koncessziós tanúsítvány számának rögzítése</span><span class="sxs-lookup"><span data-stu-id="59174-103">Record TDS concession certificate numbers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="59174-104">Ez a témakör elmagyarázza, hogyan kell rögzíteni a forrásnál levont adó (TDS) koncessziós tanúsítvány számait, amelyeket a szállítóknak bocsátanak ki.</span><span class="sxs-lookup"><span data-stu-id="59174-104">This topic explains how to record the Tax Deducted at Source (TDS) concession certificate numbers that are issued to vendors.</span></span>

1. <span data-ttu-id="59174-105">Ugorjon az **Adó \> Közvetett adók \> Adóelőleg \> Adóelőleg-koncessziók** elemre.</span><span class="sxs-lookup"><span data-stu-id="59174-105">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax concessions**.</span></span>
2. <span data-ttu-id="59174-106">Az **Adó típusa** mezőben válassza a **TDS** lehetőséget a TDS-adótípus koncessziós tanúsítványainak rögzítéséhez.</span><span class="sxs-lookup"><span data-stu-id="59174-106">In the **Tax type** field, select **TDS** to record concession certificates for the TDS tax type.</span></span>
3. <span data-ttu-id="59174-107">Az **Áttekintés** fülön válassza az **Alt+N** lehetőséget egy sor létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="59174-107">On the **Overview** tab, select **Alt+N** to create a line.</span></span>

    <span data-ttu-id="59174-108">[![Az új sor fejléce](./media/apac-ind-TDS-34.png)](./media/apac-ind-TDS-34.png)</span><span class="sxs-lookup"><span data-stu-id="59174-108">[![Header of the new line](./media/apac-ind-TDS-34.png)](./media/apac-ind-TDS-34.png)</span></span>

4. <span data-ttu-id="59174-109">Az **Adóelőleg-kód** mezőben válassza ki azt a TDS-adókódot, amelyről az szállítói koncessziós tanúsítványokat kiállították.</span><span class="sxs-lookup"><span data-stu-id="59174-109">In the **Withholding tax code** field, select the TDS tax code that the vendor concession certificates are issued for.</span></span> <span data-ttu-id="59174-110">Az **Adóelőlegkód** mező mutatja a TDS-adókód nevét.</span><span class="sxs-lookup"><span data-stu-id="59174-110">The **Withholding tax code name** field shows the name of the TDS tax code.</span></span>
5. <span data-ttu-id="59174-111">A **Kezdő dátum** és a **Befejező dátum** mezőkben határozza meg annak a koncessziós tanúsítványnak az érvényességi idejét, amely a TDS-adókódot használja a TDS koncessziós alapon történő kiszámításához.</span><span class="sxs-lookup"><span data-stu-id="59174-111">In the **From date** and **To date** fields, define the period of validity for the concession certificate that uses the TDS tax code to calculate TDS for the vendor on a concessional basis.</span></span>
6. <span data-ttu-id="59174-112">A **Megjegyzések** mezőbe írja be a megjegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="59174-112">In the **Remarks** field, enter any remarks.</span></span>
7. <span data-ttu-id="59174-113">A **Szakasz** mezőbe írja be azt a jogi szakaszkódot, amely alatt a TDS koncessziós tanúsítványt igénybe veszi.</span><span class="sxs-lookup"><span data-stu-id="59174-113">In the **Section** field, enter the legal section code that the TDS concession certificate is availed under.</span></span>

    <span data-ttu-id="59174-114">Ha a szakaszkód 197, az „A” érték a 26Q űrlap „A levonás elmulasztásának oka/alacsonyabb levonás” oszlopában, valamint a 27Q űrlap „A levonás elmaradásának/alacsonyabb levonásának/bruttósításának oka (ha van ilyen)” oszlopban jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="59174-114">If the section code is 197, the value "A" appears in both the "Reason for non-deduction/lower deduction" column in Form 26Q and the "Reason for non-deduction/lower deduction/grossing up (if any)" column in Form 27Q.</span></span> <span data-ttu-id="59174-115">Ha a szakaszkód 197A, akkor a „B” érték mindkét helyen megjelenik.</span><span class="sxs-lookup"><span data-stu-id="59174-115">If the section code is 197A, the value "B" appears in both those places.</span></span>

8. <span data-ttu-id="59174-116">Válassza ki a **Tanúsítvány** FastTab lehetőséget a TDS koncessziós tanúsítvány számának rögzítéséhez a szállítók számára.</span><span class="sxs-lookup"><span data-stu-id="59174-116">Select the **Certificate** FastTab to record TDS concession certificate numbers for vendors.</span></span>
9. <span data-ttu-id="59174-117">A **Szállítói fiók** mezőben válassza ki azt a szállítói fiókot, amelyről a TDS koncessziós tanúsítványt kiállították.</span><span class="sxs-lookup"><span data-stu-id="59174-117">In the **Vendor account** field, select the vendor account that the TDS concession certificate is issued for.</span></span>
10. <span data-ttu-id="59174-118">Az **Kezdő dátum** és a **Befejező dátum** mezőkben határozza meg a TDS koncessziós tanúsítvány érvényességi idejét.</span><span class="sxs-lookup"><span data-stu-id="59174-118">In the **From date** and **To date** fields, define the period of validity for the TDS concession certificate.</span></span>

    <span data-ttu-id="59174-119">A TDS koncessziós alapon történő kiszámítása azon az időszakon alapul, amikor a tanúsítványt a szállító számára létrehozták.</span><span class="sxs-lookup"><span data-stu-id="59174-119">The calculation of TDS on a concessional basis is based on the period when the certificate is created for the vendor.</span></span>

11. <span data-ttu-id="59174-120">A **Tanúsítvány** mezőben adja meg a TDS koncessziós tanúsítvány számát.</span><span class="sxs-lookup"><span data-stu-id="59174-120">In the **Certificate** field, enter the TDS concession certificate number.</span></span>

    <span data-ttu-id="59174-121">[![Tanúsítvány FastTab](./media/apac-ind-TDS-33.png)](./media/apac-ind-TDS-33.png)</span><span class="sxs-lookup"><span data-stu-id="59174-121">[![Certificate FastTab](./media/apac-ind-TDS-33.png)](./media/apac-ind-TDS-33.png)</span></span>

12. <span data-ttu-id="59174-122">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="59174-122">Close the page.</span></span>
