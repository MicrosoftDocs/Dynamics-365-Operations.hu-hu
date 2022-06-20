---
title: Azure-tárfiók létrehozása az Azure Portalon
description: Ez a cikk bemutatja, hogyan lehet Azure-tárolási fiókot létrehozni elektronikus számlázáshoz.
author: dkalyuzh
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4380261140086bcb278162f8dc70b39eaa7078fe
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898018"
---
# <a name="create-an-azure-storage-account-in-the-azure-portal"></a>Azure-tárfiók létrehozása az Azure Portalon

[!include [banner](../includes/banner.md)]

Az elektronikus számlázási szolgáltatás Microsoft Azure által létrehozott, illetve a feldolgozás közben a szolgáltatáshoz ható összes elektronikus fájl a tárolási fiók tárolóiban tárolókban tárolód. Annak érdekében, hogy az elektronikus számlázás hozzá tudja férni ezeket a tárolókat, meg kell adnia a tárolási fiók megosztott hozzáférési aláírási (SAS) jogkivonatát az elektronikus számlázási szolgáltatás számára. Ezenkívül a token biztonságos tárolása érdekében ne közvetlenül adja meg a SAS tokent. Ehelyett az Azure-kulcsok kulcskulcsát tárolja, és adjon meg egy Azure-kulcsú titkos Azure-kulcsot.

1. Nyissa meg azt a tárfiókot, amelyről az elektronikus számlázás szolgáltatást használni tervezi.
2. Menjen a **Beállítások konfigurációhoz** \> **·**, és győződjön meg róla, **hogy a Blob nyilvános** hozzáférés engedélyezése paraméter engedélyezve van.**·**
3. Menjen az **Adattároló tárolókhoz** \> **·**, és hozzon létre egy tárolót.
4. Adjon egy nevet a tárolónak, majd állítsa a **Nyilvános hozzáférési szint** mezőt **Privát (névtelen hozzáférés nem lehetséges)** értékre.
5. Nyissa meg az új tárolót, és nyissa meg a **Beállítások**\> elérése **házirendet.**
6. Válassza ki a **Szabályzat hozzáadása** lehetőséget a tárolt hozzáférési szabályok hozzáadásához.
7. Szükség szerint **állítsa be az Azonosító** mezőt.
8. Az Engedélyek **mezőben** válassza ki az összes engedélyt.

    ![Az Irányelv hozzáadása párbeszédpanel Engedélyek mezőjében kiválasztott összes engedély.](media/e-invoicing-azure-1.png)

9. Adja meg a kezdő és záró dátumokat. A záró dátumnak jövőbeli dátumnak kell lennie.
10. Válassza az **OK** gombot a szabályzat mentéséhez, majd mentse a módosításokat a tárolóba.
11. Menjen a **Megosztott hozzáférési** \> **jogkivonatok** beállításokhoz, és állítsa be a mezőértékeket.
12. Adja meg a kezdő és záró dátumokat. A záró dátumnak jövőbeli dátumnak kell lennie.
13. Az Engedélyek **mezőben** válassza a következő engedélyeket:

    - Olvasás
    - Hozzáadás
    - Létrehozás
    - Írás
    - Delete
    - Lista

14. Válassza a **SAS-jogkivonat és URL létrehozása** lehetőséget.
15. Másolja és tárolja az értéket a **Blob SAS URL-cím** mezőjében. Ezt az értéket a művelet későbbi használata *során használja a rendszer, és a közös hozzáférési aláírás URI-nak* is nevezik.
16. Nyissa meg az elektronikus számlázással használni kívánt kulcstartót.
17. Menjen a **Beállítási** \> **eszközbe**, **majd a Létrehozás/importálás** gombra, és hozzon létre egy titkos fájlt.
18. A **Titok létrehozása** oldal **Feltöltési beállítások** mezőjében válassza a **Manuális** lehetőséget.
19. Adja meg a titok nevét. Ezt a nevet használja a rendszer a szolgáltatásnak az RCS (Regulatory Configuration Service) *szolgáltatás telepítése során, és a kulcs titkos neveként is hivatkozik rá*. Az RCS beállítási beállításaival kapcsolatos további tudnivalókat lásd [Az RCS (Regulatory Configuration Service) beállításában.](e-invoicing-set-up-rcs.md)
20. Az Érték **mezőben** adja meg a korábban másolt, megosztott hozzáférési aláírás URI-ját.
21. Válassza a **Létrehozása** lehetőséget.
