---
title: Előfizetéses számlázás áttekintése
description: Ez a cikk a Microsoft Dynamics 365 Pénzügyben leírja az előfizetési számlázást.
author: JodiChristiansen
ms.date: 04/13/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustVendExternalItem
audience: Application User
ms.reviewer: twheeloc
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2022-02-09
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 10302e9ae7dff3d018897b666caaf4d4289b4866
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856741"
---
# <a name="subscription-billing-overview"></a>Előfizetéses számlázás áttekintése

[!include [banner](../includes/banner.md)]

Az előfizetési számlázás segítségével a szervezetek számlázási ütemezések segítségével kezelhetik az előfizetési bevételi lehetőségeket és az ismétlődő számlázási lehetőségeket. Az összetett árképzési és számlázási modelleket és bevételfelosztásokat egyszerűen kezelik, és a sor szintjén számláznak és ismernek fel. A többelemű bevételfelosztás révén a bevétel felosztása megfelel a Nemzetközi Könyvelési Szabványok (International Financial Reporting Standard 15 IFRS 15\[\]) és az általánosan elfogadott könyvelési elvek (US CAAP) szabványának (Accounting Standards Codification Topic 606 \[ASC 606\]).

A megoldás három modult tartalmaz, amelyek egymástól függetlenül használhatók. Másik lehetőségként mindhárom modul együtt használható.

- **Ismétlődő szerződés számlázása** – ez a modul lehetővé teszi az ismétlődő számlázás és árkezelés vezérlését az árképzési és számlázási paraméterek, a szerződések megújítása és a konszolidált számlázás fölött.
- **Bevétel- és költség halasztások** – ez a modul eltávolítja a manuális folyamatokat és a külső rendszerekkel való függőséget a bevételek kezelésével és a havi ismétlődő bevételnek lehetővé tevő valós idejű használatának engedélyezésével.
- **Többelemű bevételfelosztás** – ez a modul segít a bevételnek való megfelelésben, ha több cikkre kezeli az árképzést és a bevételfelosztást.

Az előfizetési számlázással kapcsolatos további tudnivalókat lásd [az Előfizetéses számlázás tartalomban Power BI](sub-bill-power-bi.md).

Az előfizetéses számlázás a Funkciókezelés segítségével **engedélyezhető**. Nem használható azonban a Bevétel-kimutatás **funkcióval**. Ezért az előfizetési számlázás engedélyezése előtt le kell tiltani ezt a funkciót.

1. Adja meg **a szűrőben** **·** **a** Bevétel-kimutatást a Funkciókezelés munkaterület Mind lapján, majd válassza ki szűrőként a funkció nevét.
2. Válassza a Bevétel-kimutatás **funkciót**, majd válassza a Letiltás **lehetőséget**.
3. A **Funkciónév szűrőben** adja meg **az előfizetési számlázási adatokat**, majd válassza ki a modulszűrőt.
4. Válassza az Előfizetés **számlázása** szolgáltatást, majd az Engedélyezés **lehetőséget**.
5. Válassza ki a három modul valamelyikét az előző listából, majd válassza az Engedélyezés **lehetőséget**. Ismételje meg ezt a lépést a másik két modullal.

    > [!IMPORTANT]
    > A **három modul** engedélyezése előtt engedélyezni kell az Előfizetéses számlázás szolgáltatást.
