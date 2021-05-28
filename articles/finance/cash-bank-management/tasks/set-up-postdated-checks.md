---
title: Jövőben esedékes csekkek beállítása
description: Ez a témakör bemutatja, hogyan állíthatja be, miként legyenek feladva a jövőben esedékes csekkek naplóbejegyzési, és melyik feladási naplókat kell használni elszámolási tételekhez és szállítói kifizetésekhez.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankParameters, VendPaymMode, CustPaymMode
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d0d4afd74f9a0f9018629fa92ab6595bfa94f973
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026205"
---
# <a name="set-up-postdated-checks"></a><span data-ttu-id="d615f-103">Jövőben esedékes csekkek beállítása</span><span class="sxs-lookup"><span data-stu-id="d615f-103">Set up postdated checks</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d615f-104">Ez a témakör bemutatja, hogyan állíthatja be, miként legyenek feladva a jövőben esedékes csekkek naplóbejegyzési, és melyik feladási naplókat kell használni elszámolási tételekhez és szállítói kifizetésekhez.</span><span class="sxs-lookup"><span data-stu-id="d615f-104">This topic explains how to specify whether to post journal entries for postdated checks and which posting journals to use for clearing entries and vendor payments.</span></span> <span data-ttu-id="d615f-105">Emellett beállíthat elszámolószámokat a kiállított csekkekhez, a fogadott csekkekhez és az adóelőleghez is.</span><span class="sxs-lookup"><span data-stu-id="d615f-105">You can also specify clearing accounts for issued checks, received checks, and withholding tax.</span></span> <span data-ttu-id="d615f-106">Jövőben esedékes csekkek, amelyeket jövőbeli dátumon való fizetés céljából állítottak ki.</span><span class="sxs-lookup"><span data-stu-id="d615f-106">Postdated checks that are issued to make and receive payments on a future date.</span></span> <span data-ttu-id="d615f-107">Megadhatja, hogy a csekk szerepeljen-e a számviteli könyvekben az esedékesség dátuma előtt.</span><span class="sxs-lookup"><span data-stu-id="d615f-107">You can specify whether the check must be reflected in the accounting books before its maturity date.</span></span>



<span data-ttu-id="d615f-108">Ezen eljárás szerepköre: Pénztáros.</span><span class="sxs-lookup"><span data-stu-id="d615f-108">The role of this procedure is Treasurer.</span></span> <span data-ttu-id="d615f-109">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="d615f-109">This procedure uses the USMF demo company.</span></span>


## <a name="set-up-postdated-checks"></a><span data-ttu-id="d615f-110">Jövőben esedékes csekkek beállítása</span><span class="sxs-lookup"><span data-stu-id="d615f-110">Set up postdated checks</span></span>
1. <span data-ttu-id="d615f-111">Ugorjon a Készpénz- és bankkezelés > Beállítás > Készpénz- és bankkezelési paraméterek pontra.</span><span class="sxs-lookup"><span data-stu-id="d615f-111">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="d615f-112">Kattintson a Jövőben esedékes csekkek fülre.</span><span class="sxs-lookup"><span data-stu-id="d615f-112">Click the Postdated checks tab.</span></span>
3. <span data-ttu-id="d615f-113">Jelölje be a Jövőben esedékes csekkek jelölőnégyzetet, vagy törölje a jelet a jelölőnégyzetből.</span><span class="sxs-lookup"><span data-stu-id="d615f-113">Select or clear the Enable postdated checks check box.</span></span>
4. <span data-ttu-id="d615f-114">Jelölje be, vagy törölje a jelet jelölőnégyzetből a Jövőben esedékes csekkekhez naplóbejegyzések feladása mellett.</span><span class="sxs-lookup"><span data-stu-id="d615f-114">Select or clear the Post journal entries for postdated checks check box.</span></span>
5. <span data-ttu-id="d615f-115">Az Elszámolási számla a kiállított csekkekhez mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="d615f-115">In the Clearing account for issued checks field, specify the desired values.</span></span>
6. <span data-ttu-id="d615f-116">Az Elszámolási számla a kapott csekkekhez mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="d615f-116">In the Clearing account for received checks field, specify the desired values.</span></span>
7. <span data-ttu-id="d615f-117">Az Általános napló bejegyzések elszámolásához mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d615f-117">In the General journal for clearing entries field, type a value.</span></span>
8. <span data-ttu-id="d615f-118">A Jövőben esedékes csekkek átvezetése ebbe a szállítói kifizetési naplóba mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d615f-118">In the Transfer postdated checks to this vendor payment journal field, type a value.</span></span>
9. <span data-ttu-id="d615f-119">Az Adóelőleg-elszámolási számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="d615f-119">In the Withholding tax clearing account field, specify the desired values.</span></span>
10. <span data-ttu-id="d615f-120">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d615f-120">Click Save.</span></span>
11. <span data-ttu-id="d615f-121">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d615f-121">Close the page.</span></span>
12. <span data-ttu-id="d615f-122">Ugorjon a Kötelezettségek > Kifizetés beállítása > Fizetési módok pontra.</span><span class="sxs-lookup"><span data-stu-id="d615f-122">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
13. <span data-ttu-id="d615f-123">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d615f-123">Click New.</span></span>
14. <span data-ttu-id="d615f-124">Írjon be egy értéket a Fizetési mód mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d615f-124">In the Method of payment field, type a value.</span></span>
15. <span data-ttu-id="d615f-125">A Jövőben esedékes csekk elszámolási feladása lehetőség bejelölésével jelezheti, hogy a csekk összege elszámolószámlára lesz feladva.</span><span class="sxs-lookup"><span data-stu-id="d615f-125">Select the Postdated check clearing posting option to indicate that the check amount is posted to a clearing account.</span></span>
16. <span data-ttu-id="d615f-126">A Fiók típusa mezőben válassza ki a „Bank” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d615f-126">In the Account type field, select 'Bank'.</span></span>
    * <span data-ttu-id="d615f-127">A fizetési módszer ellenszámlájának ellenőrzési módja egy bank lesz.</span><span class="sxs-lookup"><span data-stu-id="d615f-127">The offset account of the payment method will be a bank.</span></span>  
17. <span data-ttu-id="d615f-128">A Fizetési számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="d615f-128">In the Payment account field, specify the desired values.</span></span>
    * <span data-ttu-id="d615f-129">Válassza ki a számlaösszeg levonására szolgáló bankszámlát.</span><span class="sxs-lookup"><span data-stu-id="d615f-129">Select the bank account that is used to deduct the invoice amount.</span></span>  
18. <span data-ttu-id="d615f-130">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d615f-130">Click Save.</span></span>
19. <span data-ttu-id="d615f-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d615f-131">Close the page.</span></span>
> [!NOTE]
> <span data-ttu-id="d615f-132">Ahhoz, hogy a jövőben esedékes csekkeket fel tudja tenni egy bankszámlára, amikor a munkamenet dátuma az esedékességi dátumnál későbbi vagy azzal megegyező, engedélyeznie kell az **Esedékesség dátumának ellenőrzése a fizetési napló feladásakor későbbre dátumozott csekkekkel bankszámlához** funkciót.</span><span class="sxs-lookup"><span data-stu-id="d615f-132">To be able to post a postdated check to a bank account when the session date is greater than or equal to the maturity date, you must enable the feature **Maturity date validation of posting payment journal with postdated checks to bank account**.</span></span> <span data-ttu-id="d615f-133">Ez a funkció lehetővé teszi, hogy fizetési naplókat adjon fel a jövőben esedékes csekkekkel szállítókhoz vagy vevőkhöz, ha a munkamenet dátuma megegyezik vagy később van, mint az esedékesség dátuma.</span><span class="sxs-lookup"><span data-stu-id="d615f-133">This feature allows you to post payment journals for vendors or customers with postdated checks, when the session date is greater than or equal to the maturity date.</span></span>
> 
> <span data-ttu-id="d615f-134">A **Fizetési mód** (**Kötelezettségek > Kifizetés beállítása > Fizetési módok**) beállításakor ne töltse ki az **Áthidaló számlát**.</span><span class="sxs-lookup"><span data-stu-id="d615f-134">When setting the **Method of payment** (**Accounts payable > Payment setup > Methods of payment**), do not fill in **Bridging account**.</span></span> <span data-ttu-id="d615f-135">Ebben az esetben az ellenszámla van kitöltve a bankszámlával, amely a **Fizetési módban** van beállítva.</span><span class="sxs-lookup"><span data-stu-id="d615f-135">In this case, the offset account is filled in with the bank account, which is set up in the **Method of payment**.</span></span>
>  
> <span data-ttu-id="d615f-136">Ha a funkció engedélyezve van, és a munkamenet dátuma kisebb az esedékesség dátumánál, a fizetési napló feladása során a következő hibaüzenet jelenik meg: "Az esedékességi dátum nem lehet a munkamenet dátumával megegyező vagy korábbi, ha az ellenszámla Bank típusú".</span><span class="sxs-lookup"><span data-stu-id="d615f-136">When the feature is enabled and the session date is less than the maturity date, the following error message is displayed when posting a payment journal, "Maturity date must be less or equal to the session date if offset account type is Bank".</span></span> <span data-ttu-id="d615f-137">Ha a funkció nincs engedélyezve, akkor a jövőben esedékes csekkre vonatkozó fizetési naplót akkor lehet feladni, ha a munkamenet dátuma az esedékességi dátumnál korábbi.</span><span class="sxs-lookup"><span data-stu-id="d615f-137">If the feature is not enabled, you can post a payment journal with a postdated check when the session date is less than the maturity date.</span></span>    

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
