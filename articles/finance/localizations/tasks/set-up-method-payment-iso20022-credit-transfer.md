---
title: Fizetési mód beállítása ISO20022-jóváírás átutalásához
description: Ez az eljárás bemutatja, hogyan állítható be a szállító fizetési módja ISO20022 átutalásra vagy egyéb fizetési típusra fájl létrehozásához vezető elektronikus jelentéskészítés használatával.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPaymMode
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 92bc314e69628f2a287ba7c9a7c2d3d73a0bfd33
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988102"
---
# <a name="set-up-method-of-payment-for-iso20022-credit-transfer"></a><span data-ttu-id="3ce94-103">Fizetési mód beállítása ISO20022-jóváírás átutalásához</span><span class="sxs-lookup"><span data-stu-id="3ce94-103">Set up method of payment for ISO20022 credit transfer</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3ce94-104">Ez az eljárás bemutatja, hogyan állítható be a szállító fizetési módja ISO20022 átutalásra vagy egyéb fizetési típusra fájl létrehozásához vezető elektronikus jelentéskészítés használatával.</span><span class="sxs-lookup"><span data-stu-id="3ce94-104">This procedure shows how to set up the vendor method of payment for ISO20022 credit transfer or any other payment type using electronic reporting to generate a file.</span></span> 

<span data-ttu-id="3ce94-105">A feladat elvégzése előtt exportálnia kell a formátumkonfigurációkat és be kell állítania a fizetési számlákat.</span><span class="sxs-lookup"><span data-stu-id="3ce94-105">Before you complete this task, you must export format configurations and set up payment accounts.</span></span>

<span data-ttu-id="3ce94-106">Ez a feladat a DEMF bemutatócég segítségével lett létrehozva.</span><span class="sxs-lookup"><span data-stu-id="3ce94-106">This task was created using the DEMF demo data company.</span></span>

<span data-ttu-id="3ce94-107">Ez a harmadik azon öt eljárás közül, amelyek elektronikus jelentési beállítások használatával mutatják be a szállítói kifizetési folyamatot.</span><span class="sxs-lookup"><span data-stu-id="3ce94-107">This is the third procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="3ce94-108">Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.</span><span class="sxs-lookup"><span data-stu-id="3ce94-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="3ce94-109">Ugorjon a Kötelezettségek > Kifizetés beállítása > Fizetési módok pontra.</span><span class="sxs-lookup"><span data-stu-id="3ce94-109">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
2. <span data-ttu-id="3ce94-110">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="3ce94-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="3ce94-111">Például szűkítsen a „Fizetési mód” mezővel a „SEPA CT” értéket beírva.</span><span class="sxs-lookup"><span data-stu-id="3ce94-111">For example, filter on the Method of payment field with a value of 'SEPA CT'.</span></span>
3. <span data-ttu-id="3ce94-112">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3ce94-112">Click Edit.</span></span>
4. <span data-ttu-id="3ce94-113">Az Időszak mezőben válassza ki a „Teljes” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3ce94-113">In the Period field, select 'Total'.</span></span>
5. <span data-ttu-id="3ce94-114">A Fizetés típusa mezőben válassza ki az „Elektronikus fizetés” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3ce94-114">In the Payment type field, select 'Electronic payment'.</span></span>
6. <span data-ttu-id="3ce94-115">Bontsa ki a Fájlformátumok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="3ce94-115">Expand the File formats section.</span></span>
7. <span data-ttu-id="3ce94-116">Válassza az Igen beállítást az Általános elektronikus jelentéskészítés mezőben.</span><span class="sxs-lookup"><span data-stu-id="3ce94-116">Select Yes in the Generic electronic reporting field.</span></span>
8. <span data-ttu-id="3ce94-117">Az Exportformátum konfigurációja mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3ce94-117">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="3ce94-118">A listán válassza ki az ISO20022 jóváírást (DE).</span><span class="sxs-lookup"><span data-stu-id="3ce94-118">In the list, select the value ISO20022 Credit transfer (DE).</span></span> <span data-ttu-id="3ce94-119">Ha a lista üres, a szállítói kifizetésnek nincs importált és aktivált exportálási konfigurációja.</span><span class="sxs-lookup"><span data-stu-id="3ce94-119">If the list is empty, the vendor payment export format configuration is not imported and active.</span></span>  
9. <span data-ttu-id="3ce94-120">A Fiók típusa mezőben válassza ki a „Bank” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3ce94-120">In the Account type field, select 'Bank'.</span></span>
10. <span data-ttu-id="3ce94-121">A Fizetési számla mezőben adja meg a „DEMF OPER” értékeket.</span><span class="sxs-lookup"><span data-stu-id="3ce94-121">In the Payment account field, specify the values 'DEMF OPER'.</span></span>
11. <span data-ttu-id="3ce94-122">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="3ce94-122">Click Save.</span></span>

