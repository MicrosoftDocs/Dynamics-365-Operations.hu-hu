---
title: Egyéni tárolóhely meghatározása a létrehozott dokumentumoknak
description: Ez a témakör ismerteti, hogyan bővítheti a dokumentumok tárolóhelyeinek listáját, amelyeket az elektronikus jelentési (ER) formátumok hoznak létre.
author: NickSelin
ms.date: 02/22/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: 10
ms.openlocfilehash: 61a1e46497d650e2c063a5fe7537d17cf7aa1828a5a4504bb781e84aeb88f04a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718501"
---
# <a name="specify-a-custom-storage-location-for-generated-documents"></a>Egyéni tárolóhely meghatározása a létrehozott dokumentumoknak

[!include[banner](../includes/banner.md)]

A alkalmazásprogramozási felület (API) az Elektronikus jelentéskészítéshez (ER) lehetővé teszi a tárolóhelyek listájának kibővítését ER formátumok által létrehozott dokumentumokhoz.. Ez a témakör áttekintést ad a fő feladatokról, amelyeket el kell végeznie egyéni tárolóhely hozzáadásához.

## <a name="prerequisites"></a>Előfeltételek

Telepítenie kell egy topológiát, amely támogatja a folyamatos buildet. (További tájékoztatás: [A folyamatos build- és tesztautomatizálást támogató topológiák telepítése](/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).) Hozzáféréssel kell rendelkezzen ezen topológiához a következő szerepkörök egyikében:

- Elektronikus jelentések fejlesztője
- Elektronikus jelentések funkcióival foglalkozó konzulens
- Rendszergazda

Ezen topológia fejlesztői környezetéhez való hozzáféréssel is kell rendelkezzen.

## <a name="create-or-import-an-er-format-configuration"></a>Egy ER formátumkonfiguráció létrehozása vagy importálása

A jelenlegi topológiában [hozzon létre egy új ER formátumot](tasks/er-format-configuration-2016-11.md) dokumentumok létrehozásához, amelyekhez egyéni tárolóhely hozzáadását tervezi. Másik lehetőségként [Importáljon egy a meglévő ER formátum ehhez a topológiához](general-electronic-reporting-manage-configuration-lifecycle.md).

![Formátumtervező oldal.](media/er-extend-file-storages-format.png)

> [!IMPORTANT]
> Az ER formátumának, amelyet létrehoz vagy importál a következő formátum-elemek valamelyikét tartalmaznia kell:
>
> - Fájl
> - Mappa
> - Egyesítés
> - Melléklet

## <a name="create-a-new-document-type"></a>Új dokumentumtípus létrehozása

Annak megadásához, hogy az ER formátum által létrehozott dokumentumok hogyan továbbítódnak, konfigurálnia kell [Elektronikus jelentéskészítési (ER) célokat](electronic-reporting-destinations.md). A létrehozott dokumentumok fájlként tárolására konfigurált minden ER cél esetében meg kell adnia egy dokumentumtípust, a dokumentumkezelő keretrendszerben. A különféle dokumentumtípusok használhatók az ER formátumok által generált dokumentumok átirányításához.

1. Adjon hozzá új [dokumentumtípust](../../fin-ops/organization-administration/configure-document-management.md) a korábban importált vagy létrehozott ER formátumhoz. A következő illusztrációban a dokumentumtípus **FileX**.
2. A dokumentumtípus megkülönböztetéséhez egyéb dokumentumtípusoktól adja meg az adott kulcsszót nevében. Például a következő ábrán a név **(LOCAL) mappa**.
3. Az **Osztály** mezőben adja meg a **Fájl csatolása** elemet.
4. A **Csoport** mezőben adja meg a **Fájl** elemet.

![Dokumentumtípusok lapja.](media/er-extend-file-storages-document-type.png)

> [!NOTE]
> A dokumentumtípusok vállalatspecifikusak. ER formátumú használatához több vállalathoz konfigurált célhoz konfigurálnia kell egy külön dokumentumtípust minden vállalatnál.

## <a name="review-source-code"></a>Forráskód ellenőrzése

Tekintse át a kódot a **insertFile()** metódusban az **ERDocuManagement** osztályban. Figyelje meg, hogy az **AttachingFile()** esemény akkor következik be, amikor a létrehozott fájl egy rekordhoz van csatolva.


```xpp
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

Az **AttachingFile()** esemény akkor következik be, amikor a következő ER célok feldolgozása történik:

- **Archív** – Ezen cél használata esetén a futtatott ER formátumhoz új rekord jön létre a ERFormatMappingRunJobTable táblában. Az **Archivált** mező értéke a rekordban **Hamis** lesz. Ha az ER-formátum sikeresen lefut, ha a generált dokumentum csatolva lesz ehhez a rekordhoz, és az **AttachingFile()** esemény bekövetkezik. A dokumentumtípus, amelyet ki van választva ebben az ER célban határozza meg a csatolt fájl tárolási helyét (Microsoft Azure tároló vagy a Microsoft SharePoint mappa).
- **Munkaarchívum** – Ezen cél használata esetén a futtatott ER űrlaphoz új rekord jön létre a ERFormatMappingRunJobTable táblában. Az **Archivált** mező értéke a rekordban **Igaz** lesz. Ha az ER-formátum sikeresen lefut, ha a generált dokumentum csatolva lesz ehhez a rekordhoz, és az **AttachingFile()** esemény bekövetkezik. A dokumentumtípus, amely konfigurálva van az ER paraméterekben határozza meg a csatolt fájl tárolási helyét (Azure tároló vagy a Microsoft SharePoint mappa).

![Elektronikus jelentéskészítés paraméterei lap.](media/er-extend-file-storages-parameters.png)

## <a name="configure-an-er-destination"></a>Egy ER-célhely konfigurálása

1. Konfigurálja az archivált célt valamelyik korábban említett elemhez (fájl, mappa, egyesítés vagy melléklet) a létrehozott vagy importált ER formátumhoz. Útmutatásért lásd: [ER célok konfigurálása](/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-destinations-2016-11).
2. Használja a dokumentumtípust, amelyet korábban hozzáadott a konfigurált célhoz. (Például ebben a témakörben a dokumentumtípus **FileX**.)

![Célhely beállításai párbeszédablak.](media/er-extend-file-storages-destination.png)

## <a name="modify-source-code"></a>Forráskód módosítása

1. Adjon hozzá új osztályt a Microsoft Visual Studio projekthez, és írjon kódot a korábban említett **AttachingFile()** eseményre való feliratkozáshoz. (A használt bővítési mintával kapcsolatos további tudnivalókat lásd: [Válasz EventHandlerResult használatával](/dynamics365/unified-operations/dev-itpro/extensibility/respond-event-handler-result).) Az új osztályban például írjon kódot a következő műveletek végrehajtásához:

    1. Előállított fájlok tárolása az Application Object Server (AOS) szolgáltatást futtató kiszolgáló a helyi fájlrendszerének, egy mappájában.
    2. A létrehozott fájlok tárolása, csak akkor, amikor az új dokumentumtípus (például a **FileX** típus, amelynek nevében szerepel a"(LOCAL)" kulcsszó) van használva, amikor egy fájlt a rekordhoz van csatolva az ER végrehajtási munkanaplóban.

    ```xpp
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

2. Építse újra projektjét.

## <a name="run-the-er-format-that-you-created-or-imported"></a>Futtassa a létrehozott vagy importált ER formátumot

1. Hajtsa végre a létrehozott vagy importált ER formátumot.
2. Lépjen a **Szervezeti adminisztráció \> Elektronikus jelentéskészítés \> Elektronikus jelentéskészítési feladatok** menüpontba. Keresse meg a rekordot, amely ehhez a végrehajtási feladathoz jött létre, és a létrehozott fájl csatolva van hozzá.
3. Tekintse át a helyi **C:\\0** mappát ugyanazon generált fájl megkereséséhez.

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentéskészítés (ER) céljai](electronic-reporting-destinations.md)
- [Bővíthetőség kezdőlap](../extensibility/extensibility-home-page.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]