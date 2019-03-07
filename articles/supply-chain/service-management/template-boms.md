---
title: Sablonanyagjegyzékek
description: A sablondarabjegyzékek segítségével szabványosított listát készíthet a rendszeresen szervizelt szolgáltatási tárgyak összetevőiről.
author: ShylaThompson
manager: AnnBe
ms.date: 09/19/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f9c61ecd79f38301f46e3c21a33ec2801f33d19f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "341304"
---
# <a name="template-boms"></a><span data-ttu-id="fe743-103">Sablonanyagjegyzékek</span><span class="sxs-lookup"><span data-stu-id="fe743-103">Template BOMs</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="fe743-104">A sablondarabjegyzékek segítségével szabványosított listát készíthet a rendszeresen szervizelt szolgáltatási tárgyak összetevőiről.</span><span class="sxs-lookup"><span data-stu-id="fe743-104">A template bill of materials (BOM) provides you with a standardized list of components for service objects that are serviced regularly.</span></span> <span data-ttu-id="fe743-105">A sablondarabjegyzékben felsorolt összetevők a szolgáltatási objektum különálló alösszetevőit képviselik.</span><span class="sxs-lookup"><span data-stu-id="fe743-105">The components that are listed in the template BOM represent the individual subcomponents of the service object.</span></span> <span data-ttu-id="fe743-106">Amikor a sablondarabjegyzéket a szolgáltatás tárgyára alkalmazza, egy olyan alösszetevő-rekordot kap, amely nyilvántartja a szolgáltatás tárgyában kicserélt alkatrészeket.</span><span class="sxs-lookup"><span data-stu-id="fe743-106">By applying a template BOM to a service object, you can keep a record of the subcomponents that have been replaced on the service object.</span></span>

<span data-ttu-id="fe743-107">A sablonanyagjegyzéket úgy alkalmazhatja a szolgáltatási szerződésre vagy szervizrendelésre, hogy egy szolgáltatásitárgy-kapcsolathoz csatolja.</span><span class="sxs-lookup"><span data-stu-id="fe743-107">To apply a template BOM to a service agreement or a service order, you attach it to a service object relation.</span></span>


> [!NOTE]
> <P><span data-ttu-id="fe743-108">Minden szolgáltatás tárgyához csak egy sablondarabjegyzék csatolható.</span><span class="sxs-lookup"><span data-stu-id="fe743-108">You can apply only one template BOM to a service object.</span></span></P>

## <a name="create-a-template-bom"></a><span data-ttu-id="fe743-109">Sablonanyagjegyzék létrehozása</span><span class="sxs-lookup"><span data-stu-id="fe743-109">Create a template BOM</span></span>

<span data-ttu-id="fe743-110">Az alábbi táblázat tartalmazza a sablondarabjegyzékek létrehozásához használható különböző módokkal kapcsolatos információk.</span><span class="sxs-lookup"><span data-stu-id="fe743-110">The following table contains information about the various methods that you can use to create a template BOM.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fe743-111">Metódus</span><span class="sxs-lookup"><span data-stu-id="fe743-111">Method</span></span></p></th>
<th><p><span data-ttu-id="fe743-112">Leírás</span><span class="sxs-lookup"><span data-stu-id="fe743-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe743-113">Termelés</span><span class="sxs-lookup"><span data-stu-id="fe743-113">Production</span></span></p></td>
<td><p><span data-ttu-id="fe743-114">A sablonanyagjegyzék termelési rendeléseken alapul.</span><span class="sxs-lookup"><span data-stu-id="fe743-114">The template BOM is based on a production order.</span></span> <span data-ttu-id="fe743-115">Ez a lehetőség csak akkor alkalmazható, ha termelési környezetben dolgozik.</span><span class="sxs-lookup"><span data-stu-id="fe743-115">This option is applicable only if you operate in a production environment.</span></span> <span data-ttu-id="fe743-116">A haszna pedig az, hogy naprakész és részletes alkatrészlistát tarthat nyilván a cikket alkotó elemekről.</span><span class="sxs-lookup"><span data-stu-id="fe743-116">The benefit is that you have a current, detailed listing of the components that make up an item.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe743-117">BOM cikk</span><span class="sxs-lookup"><span data-stu-id="fe743-117">Item BOM</span></span></p></td>
<td><p><span data-ttu-id="fe743-118">Sablonanyagjegyzék létrehozása cikkanyagjegyzék alapján.</span><span class="sxs-lookup"><span data-stu-id="fe743-118">The template BOM is based on an item BOM.</span></span> <span data-ttu-id="fe743-119">A cikkdarabjegyzék, ellentétben a termelési darabjegyzékkel, a cikket alkotó összetevők statikus listája.</span><span class="sxs-lookup"><span data-stu-id="fe743-119">The item BOM, unlike the production BOM, is a static list of the components that make up an item.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe743-120">Meglévő sablon</span><span class="sxs-lookup"><span data-stu-id="fe743-120">Existing template</span></span></p></td>
<td><p><span data-ttu-id="fe743-121">A sablon alapja egy meglévő sablonanyagjegyzék.</span><span class="sxs-lookup"><span data-stu-id="fe743-121">The template is based on an existing template BOM.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe743-122">Manuális</span><span class="sxs-lookup"><span data-stu-id="fe743-122">Manual</span></span></p></td>
<td><p><span data-ttu-id="fe743-123">Ha tudja, hogy általában milyen alkatrészeket kell cserélni a szolgáltatás tárgyában, akkor akár kézzel is létrehozhatja a sablonanyagjegyzéket.</span><span class="sxs-lookup"><span data-stu-id="fe743-123">If you know what spare parts are typically replaced on a service object, you can create your template BOM manually.</span></span> <span data-ttu-id="fe743-124">Ezzel a módszerrel gondoskodhat arról, hogy a sablonban rögzített összetevők a munkahely tényleges szükségleteit tükrözzék.</span><span class="sxs-lookup"><span data-stu-id="fe743-124">This method helps make sure that the components that are included in the template reflect the actual requirements of your workplace.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="apply-the-template-bom-to-a-service-agreement-or-service-order"></a><span data-ttu-id="fe743-125">Sablonanyagjegyzék alkalmazása szolgáltatási szerződésre vagy szervizrendelésre</span><span class="sxs-lookup"><span data-stu-id="fe743-125">Apply the template BOM to a service agreement or service order</span></span>

<span data-ttu-id="fe743-126">A sablonanyagjegyzék szolgáltatási szerződésre és szervizrendelésre vagy minkettőre alkalmazható.</span><span class="sxs-lookup"><span data-stu-id="fe743-126">You can apply a template BOM to a service agreement, a service order, or both.</span></span> <span data-ttu-id="fe743-127">A szolgáltatási szerződés általában egy hosszú távú viszonyt testesít meg a vevővel.</span><span class="sxs-lookup"><span data-stu-id="fe743-127">The service agreement usually covers a long-term relationship with a customer.</span></span> <span data-ttu-id="fe743-128">A szolgáltatási anyagjegyzék által nyilvántartott korábbi cserék hasznos információkat szolgáltatnak a szolgáltatási szerződéshez.</span><span class="sxs-lookup"><span data-stu-id="fe743-128">The history of replacements that is recorded in the service BOM is useful data to have for the service agreement.</span></span>

<span data-ttu-id="fe743-129">A sablonanyagjegyzék egy szervizrendelésre is alkalmazható, a szolgáltatás tárgyán végrehajtott szerviz előzményeinek rögzítéséhez.</span><span class="sxs-lookup"><span data-stu-id="fe743-129">You can also apply a template BOM to a service order to record the history of the service that has been performed on a service object.</span></span>

## <a name="copy-the-history-of-a-service-bom"></a><span data-ttu-id="fe743-130">A szolgáltatási anyagjegyzékben szereplő előzmények másolása</span><span class="sxs-lookup"><span data-stu-id="fe743-130">Copy the history of a service BOM</span></span>

<span data-ttu-id="fe743-131">A szolgáltatási anyagjegyzék előzménysorai másolhatók az egyik szolgáltatási szerződésből egy másikba.</span><span class="sxs-lookup"><span data-stu-id="fe743-131">You can copy the history of a service BOM line from one service agreement to another service agreement.</span></span> <span data-ttu-id="fe743-132">A szolgáltatási előzmények szerződések közötti másolásával megőrizheti a nyilvántartást a cikkek cseréiről.</span><span class="sxs-lookup"><span data-stu-id="fe743-132">By copying the service history between service agreements, you can preserve the record of replacements for an item.</span></span>

<span data-ttu-id="fe743-133">**Példa**</span><span class="sxs-lookup"><span data-stu-id="fe743-133">**Example**</span></span>

<span data-ttu-id="fe743-134">A vállalat három évre szóló szolgáltatási szerződést kötött a vevő autójára.</span><span class="sxs-lookup"><span data-stu-id="fe743-134">You have set up a three-year service agreement for a customer's car.</span></span> <span data-ttu-id="fe743-135">Ezen időszak alatt a vevő hozzászokik a vállalat által nyújtott kiváló szolgáltatáshoz.</span><span class="sxs-lookup"><span data-stu-id="fe743-135">During that period, the customer becomes accustomed to the good service that the company provides.</span></span> <span data-ttu-id="fe743-136">Emiatt a szerződés lejárta után a vevő szeretne beállítani egy újat.</span><span class="sxs-lookup"><span data-stu-id="fe743-136">Therefore, after the agreement expires, the customer wants to set up a new one.</span></span> <span data-ttu-id="fe743-137">Ebben a helyzetben lehetősége van arra, hogy a vállalat számára kedvezőbb szerződést kössön.</span><span class="sxs-lookup"><span data-stu-id="fe743-137">You are now able to negotiate a more favorable agreement for the company.</span></span> <span data-ttu-id="fe743-138">Mivel a cserélt alkatrészek nyilvántartása hasznos lehet a jövőben is, ezért a szolgáltatási anyagjegyzék sorait átmásolja az új szerződésbe.</span><span class="sxs-lookup"><span data-stu-id="fe743-138">Because the record of replaced components might be useful in the future, you copy the history of the service BOM to the new agreement.</span></span>

## <a name="modify-the-template-bom"></a><span data-ttu-id="fe743-139">A sablonanyagjegyzék módosítása</span><span class="sxs-lookup"><span data-stu-id="fe743-139">Modify the template BOM</span></span>

<span data-ttu-id="fe743-140">Ha egy sablonanyagjegyzék nincs csatolva egy szolgáltatási tárgyhoz, módosíthatja vagy törölheti a sorait.</span><span class="sxs-lookup"><span data-stu-id="fe743-140">If a template BOM has not been attached to a service object, you can modify or delete lines in it.</span></span> <span data-ttu-id="fe743-141">Miután a sablon anyagjegyzéket csatolták egy szolgáltatási tárgyhoz, csak az anyagjegyzék helyi verziója módosítható.</span><span class="sxs-lookup"><span data-stu-id="fe743-141">After the template BOM is attached to a service object, you can modify only the local version of the BOM.</span></span> <span data-ttu-id="fe743-142">Ha szeretné duplikálni a sablonanyagjegyzék helyi változatának beállításait, új sablon anyagjegyzék hozható létre a helyi verzió alapján.</span><span class="sxs-lookup"><span data-stu-id="fe743-142">If you want to duplicate the setup of a local version of a template BOM, you can create a new template BOM based on the local version.</span></span> <span data-ttu-id="fe743-143">További információkkal kapcsolatban lásd: [Szolgáltatási darabjegyzék módosítása](modify-service-bom.md).</span><span class="sxs-lookup"><span data-stu-id="fe743-143">For more information, see [Modify a Service BOM](modify-service-bom.md).</span></span>

<span data-ttu-id="fe743-144">Ha kicserél egy anyagjegyzékben szereplő cikket, akkor ezt az anyagjegyzék-szerkesztőben bejegyezheti az anyagjegyzékbe.</span><span class="sxs-lookup"><span data-stu-id="fe743-144">If you replace an item in the BOM, you can register the replacement on the BOM line in the BOM designer.</span></span> <span data-ttu-id="fe743-145">Opcionálisan szervizrendeléssort hozhat létre a cserecikkhez.</span><span class="sxs-lookup"><span data-stu-id="fe743-145">Optionally, you can create a service order line for the replacement object.</span></span> <span data-ttu-id="fe743-146">Ha szervizrendeléssort hoz létre, akkor számlázhatja a cserecikket.</span><span class="sxs-lookup"><span data-stu-id="fe743-146">If you create a service order line, you can invoice the replacement item.</span></span> <span data-ttu-id="fe743-147">Ha nem hoz létre szervizrendeléssort a cseréhez, akkor a csere regisztrációja a szolgáltatás tárgyán végzett cserék nyilvántartására lesz megőrizve.</span><span class="sxs-lookup"><span data-stu-id="fe743-147">If you do not create a service order line for a replacement, the replacement registration is kept to track the history of the service object.</span></span>

## <a name="change-how-information-on-the-bom-line-is-displayed"></a><span data-ttu-id="fe743-148">Az anyagjegyzéksor adatai megjelenítési módjának módosítása</span><span class="sxs-lookup"><span data-stu-id="fe743-148">Change how information on the BOM line is displayed</span></span>

<span data-ttu-id="fe743-149">Minden sablonban és szolgáltatási anyagjegyzékre nézve módosíthatja, hogy hogyan jelenjenek meg az anyagjegyzéksor adatai.</span><span class="sxs-lookup"><span data-stu-id="fe743-149">You can change the way that information on the BOM line is displayed for all template and service BOMs.</span></span> <span data-ttu-id="fe743-150">A módosítások minden sablon anyagjegyzékre és szolgáltatási anyagjegyzékre alkalmazva lesznek.</span><span class="sxs-lookup"><span data-stu-id="fe743-150">The changes are applied to all template BOMs and service BOMs.</span></span> <span data-ttu-id="fe743-151">Ebbe beletartoznak azok is, amelyek a szolgáltatás tárgyaihoz kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="fe743-151">This includes those that are attached to service objects.</span></span>

## <a name="set-up-number-sequences-for-template-boms"></a><span data-ttu-id="fe743-152">A sablonanyagjegyzékek számsorozatainak beállítása</span><span class="sxs-lookup"><span data-stu-id="fe743-152">Set up number sequences for template BOMs</span></span>

<span data-ttu-id="fe743-153">Sablonanyagjegyzékek használatához két számsorozatot kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="fe743-153">To use template BOMs, you must set up two number sequences.</span></span> <span data-ttu-id="fe743-154">Állítson be egy számsorozatot a sablonanyagjegyzékhez, és egyet az anyagjegyzék-előzmény sorszámához.</span><span class="sxs-lookup"><span data-stu-id="fe743-154">Set up one number sequence for the template BOM and one for the BOM history line number.</span></span>


> [!NOTE]
> <P><span data-ttu-id="fe743-155">A számsorozatokat a rendszer mindenütt használja azonosítók kiosztásához azoknak a rekordoknak, amelyek igénylik őket.</span><span class="sxs-lookup"><span data-stu-id="fe743-155">Number sequences are used to allocate identifiers to records that require them.</span></span> <span data-ttu-id="fe743-156">Mielőtt hozzárendelhetne egy számsorozatot egy sablonanyagjegyzékhez vagy egy anyagjegyzék-előzmény sorszámához, be kell állítania a számsorozat kódokat.</span><span class="sxs-lookup"><span data-stu-id="fe743-156">Before you can assign a number sequence to a template BOM or a BOM history line number, you must set up number sequences codes.</span></span></P>


## <a name="set-up-number-sequences"></a><span data-ttu-id="fe743-157">Számsorozatok beállítása</span><span class="sxs-lookup"><span data-stu-id="fe743-157">Set up number sequences</span></span>

1.  <span data-ttu-id="fe743-158">A **Számsorozatok** listaoldalon hozza létre számsorozatokat a sablonanyagjegyzékek és az anyagjegyzék-előzmény sorszámához.</span><span class="sxs-lookup"><span data-stu-id="fe743-158">On the **Number sequences** list page, create number sequences for template BOMs and the BOM history line number.</span></span> 

2.  <span data-ttu-id="fe743-159">Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **Szolgáltatáskezelési paraméterek** pontra.</span><span class="sxs-lookup"><span data-stu-id="fe743-159">Click **Service management** \> **Setup** \> **Service management parameters**.</span></span>

3.  <span data-ttu-id="fe743-160">Kattintson a **Számsorozatok** elemre, és ezután válassza ki a számsorozat kódját a számsorozat-hivatkozásokhoz, amelyeket létrehozott a **Számsorozatok** képernyőn.</span><span class="sxs-lookup"><span data-stu-id="fe743-160">Click **Number sequences**, and then select a number sequence code for the number sequence references that you created in the **Number sequences** form.</span></span>

4.  <span data-ttu-id="fe743-161">A módosítások mentéséhez zárja be a képernyőt.</span><span class="sxs-lookup"><span data-stu-id="fe743-161">Close the form to save your changes.</span></span>


> [!NOTE]
> <P><span data-ttu-id="fe743-162">Az anyagjegyzék-előzmény sorszáma szolgál a rendszerben az anyagjegyzék-előzményekben a tranzakciók társítására egy szolgáltatási szerződéssel vagy szervizrendeléssel.</span><span class="sxs-lookup"><span data-stu-id="fe743-162">The BOM history line number is used by the system to associate the transactions in the BOM history with a service agreement or service order.</span></span> <span data-ttu-id="fe743-163">A szám nem jelenik meg a felhasználói felületen.</span><span class="sxs-lookup"><span data-stu-id="fe743-163">The number is not displayed in the user interface.</span></span></P>



## <a name="see-also"></a><span data-ttu-id="fe743-164">Lásd még</span><span class="sxs-lookup"><span data-stu-id="fe743-164">See also</span></span>

[<span data-ttu-id="fe743-165">Sablonanyagjegyzék létrehozása</span><span class="sxs-lookup"><span data-stu-id="fe743-165">Create a template BOM</span></span>](create-template-bom.md)

[<span data-ttu-id="fe743-166">Anyagjegyzéksablonok kezelése tárgykapcsolatokon</span><span class="sxs-lookup"><span data-stu-id="fe743-166">Manage template BOMs on object relations</span></span>](manage-template-boms-on-object-relations.md)

[<span data-ttu-id="fe743-167">Szolgáltatási anyagjegyzék módosítása</span><span class="sxs-lookup"><span data-stu-id="fe743-167">Modify a Service BOM</span></span>](modify-service-bom.md)

 


