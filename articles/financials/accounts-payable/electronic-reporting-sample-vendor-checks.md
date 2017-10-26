---
title: "Elektronikus jelentéskészítés mintája szállítói csekkekhez"
description: "A témakör általános tájékoztatást nyújt az elektronikus jelentések mintacsekkformátumainak használatáról."
author: twheeloc
manager: AnnBe
ms.date: 06/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.assetid: 
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: c27960254a8e5f748935dfb51ada88af24f098a4
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

[!include[banner](../includes/banner.md)]

# <a name="electronic-reporting-sample-check-formats"></a><span data-ttu-id="629cf-103">Elektronikus jelentéskészítés csekkformátumainak mintája</span><span class="sxs-lookup"><span data-stu-id="629cf-103">Electronic reporting sample check formats</span></span>

<span data-ttu-id="629cf-104">Az elektronikus jelentéskészítés segítségével formázhatja a szállítói csekkeket.</span><span class="sxs-lookup"><span data-stu-id="629cf-104">You can use Electronic reporting (ER) to format vendor checks.</span></span> <span data-ttu-id="629cf-105">Sok csekkspecifikus és csekkszolgáltató-specifikus csekkformátum áll rendelkezésre a piacon.</span><span class="sxs-lookup"><span data-stu-id="629cf-105">Many bank-specific and check provider–specific check formats are available on the market.</span></span> <span data-ttu-id="629cf-106">A mintaellenőrzési formátumok szerepelnek az ER-eszköztár Fizetésicsekk-modelljében.</span><span class="sxs-lookup"><span data-stu-id="629cf-106">Sample check formats have been included in the Payment check model in the ER tool repository.</span></span> <span data-ttu-id="629cf-107">A mintacsekkek megjelölése a következő: **Csekk középütt (USA)** és **Csekk a felső rész alján (USA)**.</span><span class="sxs-lookup"><span data-stu-id="629cf-107">These sample checks are labeled **Check in the middle (US)** and **Check on top stub below (US)**.</span></span>

## <a name="what-check-formats-are-currently-supported"></a><span data-ttu-id="629cf-108">Melyik csekkformátumok támogatottak jelenleg?</span><span class="sxs-lookup"><span data-stu-id="629cf-108">What check formats are currently supported?</span></span>

<span data-ttu-id="629cf-109">Mindig meg kell keresnie a Microsoft Dynamics Lifecycle szolgáltatások (LCS) megosztott eszközkönyvtárát, és meg kell tekintenie az aktuális listát a rendelkezésre álló fájlokról, amelyek **GER-konfiguráció** eszköztípusúak.</span><span class="sxs-lookup"><span data-stu-id="629cf-109">You should always go to the Shared asset library in Microsoft Dynamics Lifecycle Services (LCS) and view the current list of available files that have an asset type of **GER configuration**.</span></span> <span data-ttu-id="629cf-110">A következő szakasz, a "Mit kell beállítanom?" hivatkozást biztosít a témához, amely alapján LCS-adattárat hozhat létre az elérhető konfigurációk áttekintéséhez és a kiválasztott konfigurációk importálásához.</span><span class="sxs-lookup"><span data-stu-id="629cf-110">The next section, “What do I have to set up?,” includes a link to a topic that explains how to create an LCS repository so that you can review available configurations and import selected configurations.</span></span>

<span data-ttu-id="629cf-111">A Microsoft Dynamics 365 for Finance and Operations, Enterprise edition olyan mintaformátumot tartalmaz, amelynél a csekk felül látható, és két átutalási szakasz követi.</span><span class="sxs-lookup"><span data-stu-id="629cf-111">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, includes a sample format where the check is on top, followed by two remittance sections.</span></span> <span data-ttu-id="629cf-112">Olyan mintaformátumot is tartalmaz, ahol a csekk középütt van, két átutalási szakasz között.</span><span class="sxs-lookup"><span data-stu-id="629cf-112">It also includes a sample format where the check is in the middle, between two remittance sections.</span></span> <span data-ttu-id="629cf-113">Ezek a mintaformátumok a Deluxe üzleti csekkformátumnak felelnek meg.</span><span class="sxs-lookup"><span data-stu-id="629cf-113">These sample formats correspond to Deluxe business checks formats.</span></span>

## <a name="what-do-i-have-to-set-up"></a><span data-ttu-id="629cf-114">Mit kell beállítanom?</span><span class="sxs-lookup"><span data-stu-id="629cf-114">What do I have to set up?</span></span>

- <span data-ttu-id="629cf-115">Mielőtt csekkeket nyomtathatna az ER használatával, legalább egy aktív csekk-konfigurációt importálni kell az ER-konfigurációkba.</span><span class="sxs-lookup"><span data-stu-id="629cf-115">Before you can print checks by using ER, at least one active check configuration must be imported into your ER configurations.</span></span> <span data-ttu-id="629cf-116">További utasításokért lásd: [Az elektronikus jelentési beállítások letöltése a Lifecycle Services rendszerből](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span><span class="sxs-lookup"><span data-stu-id="629cf-116">For instructions, see [Download Electronic reporting configurations from Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span>
- <span data-ttu-id="629cf-117">Ha készpénz- ls bankkezelési csekkeket konfigurál a bankszámlánál, jelölje be az **Általános elektronikus exportálási formátum** jelölőnégyzetet, majd válassza ki a megfelelő csekkformátumot az exportálási formátum konfigurációjaként.</span><span class="sxs-lookup"><span data-stu-id="629cf-117">When you configure Cash and bank management checks for the bank account, select the **Generic electronic Export format** check box, and then select the appropriate check format as an export format configuration.</span></span>
- <span data-ttu-id="629cf-118">Azoknak a bizonylatsoroknak a számát is adja meg, amelyeket az utalásra nyomtat.</span><span class="sxs-lookup"><span data-stu-id="629cf-118">You must also specify the number of slip lines that will be printed on the remittance.</span></span> <span data-ttu-id="629cf-119">Mindig szerepeltesse a fejlécsorokat a szám kiszámításakor.</span><span class="sxs-lookup"><span data-stu-id="629cf-119">Be sure to include the header rows when you calculate this number.</span></span> <span data-ttu-id="629cf-120">A két próbacsekkformátumnál a bizonylatsorok ajánlott száma 17.</span><span class="sxs-lookup"><span data-stu-id="629cf-120">For the two sample check formats, the recommended number of slip lines is 17.</span></span> <span data-ttu-id="629cf-121">Ez a szám azonban változó, a csekk-készlettől és a nyomtatóillesztőktől függően.</span><span class="sxs-lookup"><span data-stu-id="629cf-121">However, this number will vary, depending on your check stock and your printer drivers.</span></span>
- <span data-ttu-id="629cf-122">Javasoljuk, hogy nyomtasson próbacsekket a csekkelrendezés ellenőrzéséhez.</span><span class="sxs-lookup"><span data-stu-id="629cf-122">We recommend that you print a test check to validate the check layout.</span></span> <span data-ttu-id="629cf-123">Próbacsekk nyomtatásához válassza a **Tesztnyomtatás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="629cf-123">To print a test check, select the **Print test** option.</span></span> <span data-ttu-id="629cf-124">A mintacsekkformátumok akkor működnek legjobban, ha a **Margók** beállítása **Nincs** a Microsoft Excel haladó nyomtatótulajdonságaiban.</span><span class="sxs-lookup"><span data-stu-id="629cf-124">The sample check formats work best when **Margins** is set to **None** in the advanced printer properties for Microsoft Excel.</span></span> <span data-ttu-id="629cf-125">Miután elkészült a próbacsekk, engedélyezze az Excel-kimenet szerkesztését, és konfigurálja az oldalelrendezést úgy, hogy az összes margó beállítása **0** (zéró) legyen.</span><span class="sxs-lookup"><span data-stu-id="629cf-125">After the test check has been generated, enable editing of the Excel output, and configure the page layout so that all margins are set to **0** (zero).</span></span> <span data-ttu-id="629cf-126">Hasonlítsa össze a csekkek próbapéldányát a készletével, és módosítsa a beállításokat addig, amíg nem elégedett az elrendezéssel.</span><span class="sxs-lookup"><span data-stu-id="629cf-126">Compare the test copy of the checks to your check stock, and adjust the settings until you're satisfied with the alignment.</span></span>
- <span data-ttu-id="629cf-127">Amikor a konfigurált bankszámlára befizetéseket generál a fizetési naplóban, az ellenőrzéseket a megadott formátumban nyomtatja ki a rendszer.</span><span class="sxs-lookup"><span data-stu-id="629cf-127">When you generate payments for the configured bank account in the payment journal, the checks will be printed by using the specified format.</span></span>

<span data-ttu-id="629cf-128">További információ: [Elektronikus jelentés formátumának módosítása](../../dev-itpro/analytics/modify-electronic-reporting-format-reapply-excel-template.md).</span><span class="sxs-lookup"><span data-stu-id="629cf-128">For more information, see [Modify an Electronic reporting format](../../dev-itpro/analytics/modify-electronic-reporting-format-reapply-excel-template.md).</span></span>

