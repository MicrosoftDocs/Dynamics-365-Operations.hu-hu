---
title: Ügyfélfigyelmeztetések értesítései e-mailben
description: Ez a témaköz a szabályok beállításáról ad információt, amelyekkel előre megadott esemény bekövetkezésekor e-mailes értesítéseket küld.
author: tjvass
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2019-1-29
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: fe422d645c8f2c0c564af30624090828e10ea4bf
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567252"
---
# <a name="client-alert-notifications-by-email"></a><span data-ttu-id="0812b-103">Ügyfél figyelmeztetési értesítései e-mailben</span><span class="sxs-lookup"><span data-stu-id="0812b-103">Client alert notifications by email</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0812b-104">Megadhat egyéni figyelmeztetési szabályokat, amelyek az adatok szűrt nézeteit figyeli, és automatikusan értesítő e-maileket küld előre megadott esemény bekövetkezésekor.</span><span class="sxs-lookup"><span data-stu-id="0812b-104">You can define custom alert rules that monitor filtered views of data and automatically send email notifications when predefined events occur.</span></span> <span data-ttu-id="0812b-105">Az értesítő e-mailek küldése beállítás minden támogatott figyelmeztetési típus esetében elérhető, és be lehet kapcsolni meglévő figyelmeztetési szabályokhoz is.</span><span class="sxs-lookup"><span data-stu-id="0812b-105">The option to send email notifications is available for all supported alert types and you can also turn them on for existing alert rules.</span></span>

<span data-ttu-id="0812b-106">Beépített vezérlőkkel létrehozhat figyelmeztetési szabályokat, amelyek a szűrt nézetekkel nyomon követik a rendszer kötegelt feladatait.</span><span class="sxs-lookup"><span data-stu-id="0812b-106">You can use built-in controls to create alert rules that monitor the filtered views of system batch jobs.</span></span> <span data-ttu-id="0812b-107">Az **Állapot** mező értékeinek követésével Ön is beállíthat figyelmeztetési szabályokat, amelyek e-mailt küldenek a kötegelt feladat sikertelensége esetén.</span><span class="sxs-lookup"><span data-stu-id="0812b-107">By monitoring the value of the **Status** field, you can also configure alert rules that send email when a batch job fails.</span></span> <span data-ttu-id="0812b-108">A figyelmeztetési szabályok létrehozása után már nem kell az üzleti adatokban végzett módosításokhoz jelentéseket ellenőriznie.</span><span class="sxs-lookup"><span data-stu-id="0812b-108">After you create these alert rules, you no longer have to check reports for changes to business data.</span></span> <span data-ttu-id="0812b-109">Ehelyett beállítható, hogy az intelligens módosításészlelési szolgáltatás végezze a nyomon követést.</span><span class="sxs-lookup"><span data-stu-id="0812b-109">Instead, you can let the intelligent change detection service do the monitoring for you.</span></span>

<span data-ttu-id="0812b-110">Az ügyfélfigyelmeztetések függenek az e-mail-alrendszer Microsoft Office rendszerrel való integrációjától.</span><span class="sxs-lookup"><span data-stu-id="0812b-110">Client alerts depend on the email subsystem that is provided through integration with Microsoft Office.</span></span> <span data-ttu-id="0812b-111">Azt ajánljuk, hogy a Simple Mail Transfer Protocol (SMTP) szolgáltatót használja, hogy az e-mail terjesztésnek nem kell helyi levelezési kliensre támaszkodnia.</span><span class="sxs-lookup"><span data-stu-id="0812b-111">We recommend that you use the Simple Mail Transfer Protocol (SMTP) provider, so that email distribution doesn't have to rely on a local mail client.</span></span>

<span data-ttu-id="0812b-112">Az e-mailes értesítések küldéséhez a vevőknek konfigurálnia kell az integrált e-mail-szolgáltatásokat.</span><span class="sxs-lookup"><span data-stu-id="0812b-112">To send notifications by email, customers must configure integrated email services.</span></span> <span data-ttu-id="0812b-113">E-mail-értesítéseket a címzetteknek a figyelmeztetési tulajdonosok nevében küldik.</span><span class="sxs-lookup"><span data-stu-id="0812b-113">Email notifications are sent to recipients on behalf of alert owners.</span></span>

<span data-ttu-id="0812b-114">Az e-mail konfigurálásával kapcsolatos további tudnivalókat lásd: [E-mail konfigurálása és küldése](../organization-administration/configure-email.md).</span><span class="sxs-lookup"><span data-stu-id="0812b-114">For more information about how to configure email, see [Configure and send email](../organization-administration/configure-email.md).</span></span>

<span data-ttu-id="0812b-115">A következő kép a **Figyelmeztetési szabály létrehozása** párbeszédpanelt mutatja, amely már tartalmazza az **E-mail küldése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0812b-115">The following image shows the **Create alert rule** dialog box, which now includes a **Send email** option.</span></span>

<span data-ttu-id="0812b-116">[![Figyelmeztetési szabály létrehozása párbeszédpanel, ahol az E-mail küldése beállítás értéke Igen](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)</span><span class="sxs-lookup"><span data-stu-id="0812b-116">[![Create alert rule dialog box, where the Send email option is set to Yes](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)</span></span>

> [!NOTE]
> <span data-ttu-id="0812b-117">Ha az **E-mail küldése** beállítás értéke **Igen**, a figyelmeztetési értesítéseket továbbra is a Műveleti központból kézbesítik.</span><span class="sxs-lookup"><span data-stu-id="0812b-117">When the **Send email** option is set to **Yes**, alert notifications will continue to be delivered from the Action Center.</span></span>

## <a name="alert-notification-email-templates"></a><span data-ttu-id="0812b-118">Figyelmeztetési értesítések e-mail sablonjai</span><span class="sxs-lookup"><span data-stu-id="0812b-118">Alert notification email templates</span></span>

<span data-ttu-id="0812b-119">A szolgáltatás e-mailes értesítéseket küld előre megadott e-mail-sablonokkal, amelyekkel a figyelmeztetési értesítés alapadatait kézbesíti.</span><span class="sxs-lookup"><span data-stu-id="0812b-119">The service sends email notifications by using predefined email templates that deliver the basic details of the alert notification.</span></span>

<span data-ttu-id="0812b-120">A következő kép a figyelmeztetési értesítés szerkezetét mutatja e-mail fogadásakor.</span><span class="sxs-lookup"><span data-stu-id="0812b-120">The following image shows the structure of the alert notifications when they are received by email.</span></span>

<span data-ttu-id="0812b-121">[![Sablonalapú figyelmeztetési értesítések rekord létrehozásához, mező módosításához és sablon törléséhez](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)</span><span class="sxs-lookup"><span data-stu-id="0812b-121">[![Template-based alert notifications for record creation, field changes, and template deletion](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]