---
title: TDS koncessziós tanúsítvány számának rögzítése
description: Ez a témakör leírja, hogyan lehet rögzíteni a szállítóknak kiállított, a forrásnál levont adó (TDS) koncessziós tanúsítványszámait.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 116bc5c4b4f5f0b95d05dc73f2a012fbbc065bf2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846613"
---
# <a name="record-tds-concession-certificate-numbers"></a>TDS koncessziós tanúsítvány számának rögzítése

[!include [banner](../includes/banner.md)]

Ez a témakör leírja, hogyan lehet rögzíteni a szállítóknak kiállított, a forrásnál levont adó (TDS) koncessziós tanúsítványszámait.

1. Ugorjon az **Adó \> Közvetett adók \> Adóelőleg \> Adóelőleg-koncessziók** elemre.
2. Az **Adó típusa** mezőben válassza a **TDS** lehetőséget a TDS-adótípus koncessziós tanúsítványainak rögzítéséhez.
3. Az **Áttekintés** fülön válassza az **Alt+N** lehetőséget egy sor létrehozásához.

    [![Az új sor fejléce.](./media/apac-ind-TDS-34.png)](./media/apac-ind-TDS-34.png)

4. Az **Adóelőleg-kód** mezőben válassza ki azt a TDS-adókódot, amelyről az szállítói koncessziós tanúsítványokat kiállították. Az **Adóelőlegkód** mező mutatja a TDS-adókód nevét.
5. A **Kezdő dátum** és a **Befejező dátum** mezőkben határozza meg annak a koncessziós tanúsítványnak az érvényességi idejét, amely a TDS-adókódot használja a TDS koncessziós alapon történő kiszámításához.
6. A **Megjegyzések** mezőbe írja be a megjegyzéseket.
7. A **Szakasz** mezőbe írja be azt a jogi szakaszkódot, amely alatt a TDS koncessziós tanúsítványt igénybe veszi.

    Ha a szakaszkód 197, az „A” érték a 26Q űrlap „A levonás elmulasztásának oka/alacsonyabb levonás” oszlopában, valamint a 27Q űrlap „A levonás elmaradásának/alacsonyabb levonásának/bruttósításának oka (ha van ilyen)” oszlopban jelenik meg. Ha a szakaszkód 197A, akkor a „B” érték mindkét helyen megjelenik.

8. Válassza ki a **Tanúsítvány** FastTab lehetőséget a TDS koncessziós tanúsítvány számának rögzítéséhez a szállítók számára.
9. A **Szállítói fiók** mezőben válassza ki azt a szállítói fiókot, amelyről a TDS koncessziós tanúsítványt kiállították.
10. Az **Kezdő dátum** és a **Befejező dátum** mezőkben határozza meg a TDS koncessziós tanúsítvány érvényességi idejét.

    A TDS koncessziós alapon történő kiszámítása azon az időszakon alapul, amikor a tanúsítványt a szállító számára létrehozták.

11. A **Tanúsítvány** mezőben adja meg a TDS koncessziós tanúsítvány számát.

    [![Tanúsítvány FastTab.](./media/apac-ind-TDS-33.png)](./media/apac-ind-TDS-33.png)

12. Zárja be a lapot.
