---
title: Egyéni tárolóhely meghatározása a létrehozott dokumentumoknak
description: Ez a témakör ismerteti, hogyan bővítheti a dokumentumok tárolóhelyeinek listáját, amelyeket az elektronikus jelentési (ER) formátumok hoznak létre.
author: NickSelin
manager: AnnBe
ms.date: 02/22/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: 10
ms.openlocfilehash: f65118b6a7393ced9d80c30fad7540a7b27da6c7
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2019
ms.locfileid: "2569084"
---
# <a name="specify-a-custom-storage-location-for-generated-documents"></a><span data-ttu-id="f5b29-103">Egyéni tárolóhely meghatározása a létrehozott dokumentumoknak</span><span class="sxs-lookup"><span data-stu-id="f5b29-103">Specify a custom storage location for generated documents</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="f5b29-104">A alkalmazásprogramozási felület (API) az Elektronikus jelentéskészítéshez (ER) lehetővé teszi a tárolóhelyek listájának kibővítését ER formátumok által létrehozott dokumentumokhoz..</span><span class="sxs-lookup"><span data-stu-id="f5b29-104">The application programming interface (API) of the Electronic reporting (ER) framework lets you extend the list of storage locations for documents that ER formats generate.</span></span> <span data-ttu-id="f5b29-105">Ez a témakör áttekintést ad a fő feladatokról, amelyeket el kell végeznie egyéni tárolóhely hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="f5b29-105">This topic includes an overview of the main tasks that you must complete to add a custom storage location.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f5b29-106">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="f5b29-106">Prerequisites</span></span>

<span data-ttu-id="f5b29-107">Telepítenie kell egy topológiát, amely támogatja a folyamatos buildet.</span><span class="sxs-lookup"><span data-stu-id="f5b29-107">You must deploy a topology that supports continuous build.</span></span> <span data-ttu-id="f5b29-108">(További tájékoztatás: [A folyamatos build- és tesztautomatizálást támogató topológiák telepítése](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).) Hozzáféréssel kell rendelkezzen ezen topológiához a következő szerepkörök egyikében:</span><span class="sxs-lookup"><span data-stu-id="f5b29-108">(For more information, see [Deploy topologies that support continuous build and test automation](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).) You must have access to this topology for one of the following roles:</span></span>

- <span data-ttu-id="f5b29-109">Elektronikus jelentések fejlesztője</span><span class="sxs-lookup"><span data-stu-id="f5b29-109">Electronic reporting developer</span></span>
- <span data-ttu-id="f5b29-110">Elektronikus jelentések funkcióival foglalkozó konzulens</span><span class="sxs-lookup"><span data-stu-id="f5b29-110">Electronic reporting functional consultant</span></span>
- <span data-ttu-id="f5b29-111">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="f5b29-111">System administrator</span></span>

<span data-ttu-id="f5b29-112">Ezen topológia fejlesztői környezetéhez való hozzáféréssel is kell rendelkezzen.</span><span class="sxs-lookup"><span data-stu-id="f5b29-112">You must also have access to the development environment for this topology.</span></span>

## <a name="create-or-import-an-er-format-configuration"></a><span data-ttu-id="f5b29-113">Egy ER formátumkonfiguráció létrehozása vagy importálása</span><span class="sxs-lookup"><span data-stu-id="f5b29-113">Create or import an ER format configuration</span></span>

<span data-ttu-id="f5b29-114">A jelenlegi topológiában [hozzon létre egy új ER formátumot](tasks/er-format-configuration-2016-11.md) dokumentumok létrehozásához, amelyekhez egyéni tárolóhely hozzáadását tervezi.</span><span class="sxs-lookup"><span data-stu-id="f5b29-114">In the current topology, [create a new ER format](tasks/er-format-configuration-2016-11.md) to generate documents that you plan to add a custom storage location for.</span></span> <span data-ttu-id="f5b29-115">Másik lehetőségként [Importáljon egy a meglévő ER formátum ehhez a topológiához](general-electronic-reporting-manage-configuration-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="f5b29-115">Alternatively, [import an existing ER format into this topology](general-electronic-reporting-manage-configuration-lifecycle.md).</span></span>

![Formátumtervező oldal](media/er-extend-file-storages-format.png)

> [!IMPORTANT]
> <span data-ttu-id="f5b29-117">Az ER formátumának, amelyet létrehoz vagy importál a következő formátum-elemek valamelyikét tartalmaznia kell:</span><span class="sxs-lookup"><span data-stu-id="f5b29-117">The ER format that you create or import must contain at least one of the following format elements:</span></span>
>
> - <span data-ttu-id="f5b29-118">Fájl</span><span class="sxs-lookup"><span data-stu-id="f5b29-118">File</span></span>
> - <span data-ttu-id="f5b29-119">Mappa</span><span class="sxs-lookup"><span data-stu-id="f5b29-119">Folder</span></span>
> - <span data-ttu-id="f5b29-120">Egyesítés</span><span class="sxs-lookup"><span data-stu-id="f5b29-120">Merger</span></span>
> - <span data-ttu-id="f5b29-121">Melléklet</span><span class="sxs-lookup"><span data-stu-id="f5b29-121">Attachment</span></span>

## <a name="create-a-new-document-type"></a><span data-ttu-id="f5b29-122">Új dokumentumtípus létrehozása</span><span class="sxs-lookup"><span data-stu-id="f5b29-122">Create a new document type</span></span>

<span data-ttu-id="f5b29-123">Annak megadásához, hogy az ER formátum által létrehozott dokumentumok hogyan továbbítódnak, konfigurálnia kell [ER célokat](electronic-reporting-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f5b29-123">To specify how documents that an ER format generates are routed, you must configure [ER destinations](electronic-reporting-destinations.md).</span></span> <span data-ttu-id="f5b29-124">A létrehozott dokumentumok fájlként tárolására konfigurált minden ER cél esetében meg kell adnia egy dokumentumtípust, a dokumentumkezelő keretrendszerben.</span><span class="sxs-lookup"><span data-stu-id="f5b29-124">In each ER destination that is configured to store generated documents as files, you must specify a document type of the Document management framework.</span></span> <span data-ttu-id="f5b29-125">A különféle dokumentumtípusok használhatók az ER formátumok által generált dokumentumok átirányításához.</span><span class="sxs-lookup"><span data-stu-id="f5b29-125">Different document types can be used to route documents that different ER formats generate.</span></span>

1. <span data-ttu-id="f5b29-126">Adjon hozzá új [dokumentumtípust](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management) a korábban importált vagy létrehozott ER formátumhoz.</span><span class="sxs-lookup"><span data-stu-id="f5b29-126">Add a new [document type](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management) for the ER format that you created or imported earlier.</span></span> <span data-ttu-id="f5b29-127">A következő illusztrációban a dokumentumtípus **FileX**.</span><span class="sxs-lookup"><span data-stu-id="f5b29-127">In the illustration that follows, the document type is **FileX**.</span></span>
2. <span data-ttu-id="f5b29-128">A dokumentumtípus megkülönböztetéséhez egyéb dokumentumtípusoktól adja meg az adott kulcsszót nevében.</span><span class="sxs-lookup"><span data-stu-id="f5b29-128">To differentiate this document type from other document types, include a specific keyword in its name.</span></span> <span data-ttu-id="f5b29-129">Például a következő ábrán a név **(LOCAL) mappa**.</span><span class="sxs-lookup"><span data-stu-id="f5b29-129">For example, in the illustration that follows, the name is **(LOCAL) folder**.</span></span>
3. <span data-ttu-id="f5b29-130">Az **Osztály** mezőben adja meg a **Fájl csatolása** elemet.</span><span class="sxs-lookup"><span data-stu-id="f5b29-130">In the **Class** field, specify **Attach file**.</span></span>
4. <span data-ttu-id="f5b29-131">A **Csoport** mezőben adja meg a **Fájl** elemet.</span><span class="sxs-lookup"><span data-stu-id="f5b29-131">In the **Group** field, specify **File**.</span></span>

![Dokumentumtípusok oldal](media/er-extend-file-storages-document-type.png)

> [!NOTE]
> <span data-ttu-id="f5b29-133">A dokumentumtípusok vállalatspecifikusak.</span><span class="sxs-lookup"><span data-stu-id="f5b29-133">Document types are company-specific.</span></span> <span data-ttu-id="f5b29-134">ER formátumú használatához több vállalathoz konfigurált célhoz konfigurálnia kell egy külön dokumentumtípust minden vállalatnál.</span><span class="sxs-lookup"><span data-stu-id="f5b29-134">To use an ER format with a configured destination in multiple companies, you must configure a separate document type in each company.</span></span>

## <a name="review-source-code"></a><span data-ttu-id="f5b29-135">Forráskód ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="f5b29-135">Review source code</span></span>

<span data-ttu-id="f5b29-136">Tekintse át a kódot a **insertFile()** metódusban az **ERDocuManagement** osztályban.</span><span class="sxs-lookup"><span data-stu-id="f5b29-136">Review the code of the **insertFile()** method of the **ERDocuManagement** class.</span></span> <span data-ttu-id="f5b29-137">Figyelje meg, hogy az **AttachingFile()** esemény akkor következik be, amikor a létrehozott fájl egy rekordhoz van csatolva.</span><span class="sxs-lookup"><span data-stu-id="f5b29-137">Notice that the **AttachingFile()** event is raised while the generated file is attached to a record.</span></span>

```
/// <summary>
/// Inserts file as attachment in Document Management.
/// </summary>
/// <param name = "_owner">A record as the attachment owner.</param>
/// <param name = "_stream">The file stream.</param>
/// <param name = "_filePath">The file path with name.</param>
/// <param name = "_attachmentName">The name of file attachment.</param>
/// <returns>The reference to inserted file.</returns>
[Hookable(false)]
public DocuRef insertFile(
    Common _owner, 
    System.IO.Stream _stream, 
    str _filePath, 
    str _attachmentName, 
    DocuTypeId _docuTypeId)
{
    DocuRef docuRef;
    if (_stream)
    {
        DocuType::createDefaults();
        if (!this.isDocuTypeValid(_docuTypeId))
        {
            throw error(strFmt("@ElectronicReporting:DocuTypeIsNotValid", _docuTypeId));
        }
        var args = ERDocuManagementAttachingFileEventArgs::construct(_owner, _stream, _filePath, _attachmentName, _docuTypeId);
        ERDocuManagementEvents::onAttachingFile(args);
        if (args.isHandled())
        {
            docuRef = args.getDocuRef();
        }
        else
        {
            docuRef = this.attachFile(_owner, _stream, _filePath, _attachmentName, _docuTypeId);
        }
    }
    return docuRef;
}
```

<span data-ttu-id="f5b29-138">Az **AttachingFile()** esemény akkor következik be, amikor a következő ER célok feldolgozása történik:</span><span class="sxs-lookup"><span data-stu-id="f5b29-138">The **AttachingFile()** event is raised when the following ER destinations are processed:</span></span>

- <span data-ttu-id="f5b29-139">**Archív** – Ezen cél használata esetén a futtatott ER formátumhoz új rekord jön létre a ERFormatMappingRunJobTable táblában.</span><span class="sxs-lookup"><span data-stu-id="f5b29-139">**Archive** – When this destination is used, a new record for the ER format that is run is created in the ERFormatMappingRunJobTable table.</span></span> <span data-ttu-id="f5b29-140">Az **Archivált** mező értéke a rekordban **Hamis** lesz.</span><span class="sxs-lookup"><span data-stu-id="f5b29-140">The **Archived** field in this record is set to **False**.</span></span> <span data-ttu-id="f5b29-141">Ha az ER-formátum sikeresen lefut, ha a generált dokumentum csatolva lesz ehhez a rekordhoz, és az **AttachingFile()** esemény bekövetkezik.</span><span class="sxs-lookup"><span data-stu-id="f5b29-141">If the ER format is successfully run, the generated document is attached to this record, and the **AttachingFile()** event is raised.</span></span> <span data-ttu-id="f5b29-142">A dokumentumtípus, amelyet ki van választva ebben az ER célban határozza meg a csatolt fájl tárolási helyét (Microsoft Azure tároló vagy a Microsoft SharePoint mappa).</span><span class="sxs-lookup"><span data-stu-id="f5b29-142">The document type that is selected in this ER destination determines the storage location for the attached file (Microsoft Azure Storage or a Microsoft SharePoint folder).</span></span>
- <span data-ttu-id="f5b29-143">**Munkaarchívum** – Ezen cél használata esetén a futtatott ER űrlaphoz új rekord jön létre a ERFormatMappingRunJobTable táblában.</span><span class="sxs-lookup"><span data-stu-id="f5b29-143">**Job archive** – When this destination is used, a new record for the ER form that is run is created in the ERFormatMappingRunJobTable table.</span></span> <span data-ttu-id="f5b29-144">Az **Archivált** mező értéke a rekordban **Igaz** lesz.</span><span class="sxs-lookup"><span data-stu-id="f5b29-144">The **Archived** field in this record is set to **True**.</span></span> <span data-ttu-id="f5b29-145">Ha az ER-formátum sikeresen lefut, ha a generált dokumentum csatolva lesz ehhez a rekordhoz, és az **AttachingFile()** esemény bekövetkezik.</span><span class="sxs-lookup"><span data-stu-id="f5b29-145">If the ER format is successfully run, the generated document is attached to this record, and the **AttachingFile()** event is raised.</span></span> <span data-ttu-id="f5b29-146">A dokumentumtípus, amely konfigurálva van az ER paraméterekben határozza meg a csatolt fájl tárolási helyét (Azure tároló vagy a Microsoft SharePoint mappa).</span><span class="sxs-lookup"><span data-stu-id="f5b29-146">The document type that is configured in the ER parameters determines the storage location for the attached file (Azure Storage or a SharePoint folder).</span></span>

![Elektronikus jelentéskészítés paraméterei lap](media/er-extend-file-storages-parameters.png)

## <a name="configure-an-er-destination"></a><span data-ttu-id="f5b29-148">Egy ER-célhely konfigurálása</span><span class="sxs-lookup"><span data-stu-id="f5b29-148">Configure an ER destination</span></span>

1. <span data-ttu-id="f5b29-149">Konfigurálja az archivált célt valamelyik korábban említett elemhez (fájl, mappa, egyesítés vagy melléklet) a létrehozott vagy importált ER formátumhoz.</span><span class="sxs-lookup"><span data-stu-id="f5b29-149">Configure the archived destination for one of the previously mentioned elements (file, folder, merger, or attachment) of the ER format that you created or imported.</span></span> <span data-ttu-id="f5b29-150">Útmutatásért lásd: [ER célok konfigurálása](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-destinations-2016-11).</span><span class="sxs-lookup"><span data-stu-id="f5b29-150">For guidance, see [ER Configure destinations](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-destinations-2016-11).</span></span>
2. <span data-ttu-id="f5b29-151">Használja a dokumentumtípust, amelyet korábban hozzáadott a konfigurált célhoz.</span><span class="sxs-lookup"><span data-stu-id="f5b29-151">Use the document type that you added earlier for the configured destination.</span></span> <span data-ttu-id="f5b29-152">(Például ebben a témakörben a dokumentumtípus **FileX**.)</span><span class="sxs-lookup"><span data-stu-id="f5b29-152">(For the example in this topic, the document type is **FileX**.)</span></span>

![Célhely beállításai párbeszédablak](media/er-extend-file-storages-destination.png)

## <a name="modify-source-code"></a><span data-ttu-id="f5b29-154">Forráskód módosítása</span><span class="sxs-lookup"><span data-stu-id="f5b29-154">Modify source code</span></span>

1. <span data-ttu-id="f5b29-155">Adjon hozzá új osztályt a Microsoft Visual Studio projekthez, és írjon kódot a korábban említett **AttachingFile()** eseményre való feliratkozáshoz.</span><span class="sxs-lookup"><span data-stu-id="f5b29-155">Add a new class to your Microsoft Visual Studio project, and write code to subscribe to the **AttachingFile()** event that was mentioned earlier.</span></span> <span data-ttu-id="f5b29-156">(A használt bővítési mintával kapcsolatos további tudnivalókat lásd: [Válasz EventHandlerResult használatával](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/extensibility/respond-event-handler-result).) Az új osztályban például írjon kódot a következő műveletek végrehajtásához:</span><span class="sxs-lookup"><span data-stu-id="f5b29-156">(For more information about the extensibility pattern that is used, see [Respond by using EventHandlerResult](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/extensibility/respond-event-handler-result).) For example, in the new class, write code that performs the following actions:</span></span>

    1. <span data-ttu-id="f5b29-157">Előállított fájlok tárolása az Application Object Server (AOS) szolgáltatást futtató kiszolgáló a helyi fájlrendszerének, egy mappájában.</span><span class="sxs-lookup"><span data-stu-id="f5b29-157">Store generated files in a folder of the local file system of the server that runs the Application Object Server (AOS) service.</span></span>
    2. <span data-ttu-id="f5b29-158">A létrehozott fájlok tárolása, csak akkor, amikor az új dokumentumtípus (például a **FileX** típus, amelynek nevében szerepel a"(LOCAL)" kulcsszó) van használva, amikor egy fájlt a rekordhoz van csatolva az ER végrehajtási munkanaplóban.</span><span class="sxs-lookup"><span data-stu-id="f5b29-158">Store these generated files only when the new document type (for example, the **FileX** type that has the "(LOCAL)" keyword in its name) is used while a file is attached to the record in the ER execution job log.</span></span>

    ```
    class ERDocuSubscriptionSample
    {
        void new()
        {
        }
        [SubscribesTo(classStr(ERDocuManagementEvents), 
        staticDelegateStr(ERDocuManagementEvents, 
        attachingFile))]
        public static void ERDocuManagementEvents_attachingFile(ERDocuManagementAttachingFileEventArgs _args)
        {
            if (!_args.isHandled())
            {
                DocuType docuType = DocuType::find(_args.getDocuTypeId());
                if (strContains(docuType.Name, '(LOCAL)'))
                {
                    _args.markAsHandled();
                    var stream = _args.getStream();
                    if (stream.CanSeek)
                    {
                        stream.Seek(0, System.IO.SeekOrigin::Begin);
                    }
                    using (var localStream = System.IO.File::OpenWrite(@'c:\0\' + _args.getAttachmentName()))
                    {
                        stream.CopyTo(localStream);
                    }
                }
            }
        }
    }
    ```

2. <span data-ttu-id="f5b29-159">Építse újra projektjét.</span><span class="sxs-lookup"><span data-stu-id="f5b29-159">Rebuild your project.</span></span>

## <a name="run-the-er-format-that-you-created-or-imported"></a><span data-ttu-id="f5b29-160">Futtassa a létrehozott vagy importált ER formátumot</span><span class="sxs-lookup"><span data-stu-id="f5b29-160">Run the ER format that you created or imported</span></span>

1. <span data-ttu-id="f5b29-161">Hajtsa végre a létrehozott vagy importált ER formátumot.</span><span class="sxs-lookup"><span data-stu-id="f5b29-161">Execute the ER format that you created or imported.</span></span>
2. <span data-ttu-id="f5b29-162">Lépjen a **Szervezeti adminisztráció \> Elektronikus jelentéskészítés \> Elektronikus jelentéskészítési feladatok** menüpontba.</span><span class="sxs-lookup"><span data-stu-id="f5b29-162">Go to **Organization administration \> Electronic reporting \> Electronic reporting jobs**.</span></span> <span data-ttu-id="f5b29-163">Keresse meg a rekordot, amely ehhez a végrehajtási feladathoz jött létre, és a létrehozott fájl csatolva van hozzá.</span><span class="sxs-lookup"><span data-stu-id="f5b29-163">Find the record that was created for this execution job, and that has the generated file attached to it.</span></span>
3. <span data-ttu-id="f5b29-164">Tekintse át a helyi **C:\\0** mappát ugyanazon generált fájl megkereséséhez.</span><span class="sxs-lookup"><span data-stu-id="f5b29-164">Explore the local **C:\\0** folder to find same generated file.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f5b29-165">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="f5b29-165">Additional resources</span></span>

- [<span data-ttu-id="f5b29-166">Elektronikus jelentéskészítés céljai</span><span class="sxs-lookup"><span data-stu-id="f5b29-166">Electronic reporting destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="f5b29-167">Bővíthetőség kezdőlap</span><span class="sxs-lookup"><span data-stu-id="f5b29-167">Extensibility home page</span></span>](../extensibility/extensibility-home-page.md)
