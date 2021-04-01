---
title: Ellenőrzött fizetési áttekintés
description: Ez a cikk az ellenőrzött kifizetésről nyújt tájékoztatást, amely a bankoknak benyújtható elektronikus csekklista létrehozásához használatos.
author: panolte
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankPositivePaySummary
audience: Application User
ms.reviewer: roschlom
ms.custom: 88463
ms.assetid: 1e3a39d3-f9b3-4073-9730-c96a607243e2
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 611cd7c46cf160a3e4e2b43acecaacdb6c79b16d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5235909"
---
# <a name="positive-pay-overview"></a><span data-ttu-id="05afa-103">Ellenőrzött fizetési áttekintés</span><span class="sxs-lookup"><span data-stu-id="05afa-103">Positive pay overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="05afa-104">Ez a cikk az ellenőrzött kifizetésről nyújt tájékoztatást, amely a bankoknak benyújtható elektronikus csekklista létrehozásához használatos.</span><span class="sxs-lookup"><span data-stu-id="05afa-104">This article provides information about positive pay, which is used to generate an electronic list of checks that can be presented to a bank.</span></span> 

<span data-ttu-id="05afa-105">Az ellenőrzött kifizetés a csekkek egy elektromos listájának létrehozásához használatos, amelyek benyújthatók egy banknak.</span><span class="sxs-lookup"><span data-stu-id="05afa-105">Positive pay is used to generate an electronic list of checks that can be presented to a bank.</span></span> <span data-ttu-id="05afa-106">Az ellenőrzött fizetési fájlok segíthetnek a bankoknak a csekk-csalások megelőzésében.</span><span class="sxs-lookup"><span data-stu-id="05afa-106">Positive pay files can help banks prevent check fraud.</span></span> <span data-ttu-id="05afa-107">Ön beállítja az ellenőrzött fizetést, hogy létrehozza a csekkek egy elektronikus listáját minden alkalommal, amikor a csekkeket kinyomtatják.</span><span class="sxs-lookup"><span data-stu-id="05afa-107">You set up positive pay to generate an electronic list of checks every time that checks are printed.</span></span> <span data-ttu-id="05afa-108">Ezután amikor a csekket benyújtják a banknak a bank összehasonlítja a csekket azzal a csekklistával, amit Ön korábban elküldött.</span><span class="sxs-lookup"><span data-stu-id="05afa-108">Then, when a check is presented to the bank, the bank compares the check with the list of checks that you previously submitted.</span></span> <span data-ttu-id="05afa-109">Ha a csekk megfelel a listában szereplő csekkel a bank törli azt.</span><span class="sxs-lookup"><span data-stu-id="05afa-109">If the check matches a check in the list, the bank clears it.</span></span> <span data-ttu-id="05afa-110">Ha a csekk nem egyezik meg a listában szereplő csekkel, akkor a bank bent tartja ellenőrzésre.</span><span class="sxs-lookup"><span data-stu-id="05afa-110">If the check doesn't match a check in the list, the bank holds it for review.</span></span>

<span data-ttu-id="05afa-111">A fizetési ellenőrző SafePay is nevezik.</span><span class="sxs-lookup"><span data-stu-id="05afa-111">Positive pay is also known as SafePay.</span></span> 

<span data-ttu-id="05afa-112">Az ellenőrzött fizetési fájlok bizalmas információt tartalmazhatnak a kedvezményezettekről és a csekk-összegekről.</span><span class="sxs-lookup"><span data-stu-id="05afa-112">Positive pay files can contain sensitive information about payees and check amounts.</span></span> <span data-ttu-id="05afa-113">Ezért győződjön meg róla, hogy a megfelelő biztonsági intézkedéseket használja attól az időponttól, hogy a fájlok létrejönnek addig, amíg a bank meg nem kapja őket.</span><span class="sxs-lookup"><span data-stu-id="05afa-113">Therefore, make sure that you use appropriate security measures from the time that the files are generated until they are received by the bank.</span></span> <span data-ttu-id="05afa-114">Az ellenőrzött fizetési fájlok a webböngésző letöltési utasításai szerint kerülnek letöltésre.</span><span class="sxs-lookup"><span data-stu-id="05afa-114">Positive pay files are downloaded according to the download instructions for the web browser.</span></span> 

<span data-ttu-id="05afa-115">Az ellenőrzött fizetési fájlok adatentitások használatával jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="05afa-115">Positive pay files are created by using data entities.</span></span> <span data-ttu-id="05afa-116">Mielőtt létrehoz egy fizetési ellenőrző fájlt be kell állítania az átalakítási formátumokat az XML-hez, amely az adatokat olyan formátumúvá fordítja, amit a bank fel tud dolgozni.</span><span class="sxs-lookup"><span data-stu-id="05afa-116">Before you generate a positive pay file, you must set up the transformation formats for the XML that translates the data into a format that the bank can consume.</span></span> 

<span data-ttu-id="05afa-117">Minden egyes bankszámlához, amelyhez szeretne létrehozni ellenőrzött fizetési információt, hozzá kell rendelnie az ellenőrzött fizetési formátumot.</span><span class="sxs-lookup"><span data-stu-id="05afa-117">For each bank account that you want to generate positive pay information for, you must assign the positive pay format.</span></span> <span data-ttu-id="05afa-118">Miután kifizetéseket hozott létre, létrehozhat egy fizetési ellenőrző fájlt, egyetlen jogi személy és egyetlen bankszámla számára.</span><span class="sxs-lookup"><span data-stu-id="05afa-118">After you generate payments, you can generate a positive pay file for a single legal entity and a single bank account.</span></span> <span data-ttu-id="05afa-119">Másik lehetőségként létrehozhat fizetési ellenőrző fájlokat egyszerre több jogi személyhez és bankszámlához.</span><span class="sxs-lookup"><span data-stu-id="05afa-119">Alternatively, you can generate positive pay files for multiple legal entities and bank accounts at the same time.</span></span> 

<span data-ttu-id="05afa-120">Miután kifizetésre kerültek a fizetési ellenőrző fájlban felsorolt csekkek, a bank visszaigazolási számot küld róla.</span><span class="sxs-lookup"><span data-stu-id="05afa-120">After the checks that are listed in a positive pay file have been paid, you receive a confirmation number from your bank.</span></span> <span data-ttu-id="05afa-121">Ezt követően visszaigazolhatja a fizetési ellenőrző fájlt a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="05afa-121">You can then confirm the positive pay file in the system.</span></span> 

<span data-ttu-id="05afa-122">Ha módosítania kell valamit a fizetési ellenőrző fájlban, akkor vissza tudja hívni.</span><span class="sxs-lookup"><span data-stu-id="05afa-122">If you must change a positive pay file, you can recall it.</span></span> <span data-ttu-id="05afa-123">Ezután a mező, amely a fizetési ellenőrző fájlban minden csekknél azt jelöli, hogy a csekk szerepel-e egy fizetési ellenőrző fájlban visszaállításra kerül.</span><span class="sxs-lookup"><span data-stu-id="05afa-123">Then, for each check in the positive pay file, the field that indicates whether that check has been included in a positive pay file is reset.</span></span>

<span data-ttu-id="05afa-124">További információért lásd: [Fizetési ellenőrző fájlok beállítása és létrehozása](set-up-generate-positive-pay-files.md).</span><span class="sxs-lookup"><span data-stu-id="05afa-124">For more information, see [Set up and generate positive pay files](set-up-generate-positive-pay-files.md).</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]