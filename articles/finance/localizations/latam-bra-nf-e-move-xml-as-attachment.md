---
title: NF-e XML-fájlok áthelyezése mellékletként
description: Ez a cikk bemutatja, hogy hogyan lehet a 365 Pénzügy vagy adatbázisból ÁTHELYEZNI AZ XML-fájlokat a 365-ös Microsoft Dynamics Dynamics 365 Supply Chain Management pénzügyi adatbázisból, és ezeket mellékletként elérhetővé tenni.
author: gionoder
ms.date: 11/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2022-01-27
ms.dyn365.ops.version: 10.0.25
ms.custom: 97423
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 7bb0fb975c6d73cc4e990b39ea9b5a0c0455db74
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270624"
---
# <a name="move-nf-e-xml-files-as-attachments"></a>NF-e XML-fájlok áthelyezése mellékletként

[!include [banner](../includes/banner.md)] 


Amikor elektronikus pénzügyi bizonylatokat (XML-e) kibocsát, XML-fájlokat Microsoft Dynamics hoz létre és tárol a 365 Pénzügy és Dynamics 365 Supply Chain Management adatbázisok. A brazil honosításban az **XML-e MOVE(** e) csatolási funkcióval felszabadíthatja az xml-fájlok által felhasznált adatbázisterületet.

A funkció egy adott dátumtartomány és pénzügyi intézmény esetén áthelyezi a MAJD-e XML-fájlokat a Pénzügyi vagy Ellátásilánc-kezelő adatbázisból az Azure-előfizetés Blob tárolóba. Ez az átmozgatás csak mellékletként teszi elérhetővé a fájlokat. Miután az XML-fájlokat sikeresen áthelyezték a Blob tárolóba, az eredeti fájlok törlődnek a Pénzügyi vagy ellátásilánc-kezelési adatbázisból. Ebből következően a használt fájlok által kiadott adatbázisterület ki van adva.

A következő lépések szerint engedélyezheti **a XML-e XML csatolásként való áthelyezését**.

1. A Pénzügy és az Ellátásilánc-kezelés eszközben nyissa meg **a Szolgáltatáskezelés munkaterületet**.
2. A Mind **lapon** keresse meg és válassza **ki a XML-ként való áthelyezést csatolási funkcióként**.
3. Válassza az **Engedélyezés most** lehetőséget.

A következő lépések szerint helyezze át a XML-fájlokat mellékletként.

1. Ugrás a **Kinnlevőségek** \> **pénzügyi bizonylatok** \> **elektronikus pénzügyi bizonylataihoz** \> **: MOVE XML-e XML mellékletként.**
2. A Kezdő **és Záró dátum** **mezőkben** válassza ki a kezdő és a záró dátumot.
3. A Pénzügyi **intézmény azonosítója mezőben** válasszon ki egy értéket.
4. Válassza ki az **OK** lehetőséget.

> [!IMPORTANT]
> Ez a folyamat nem megfordítható. Miután áthelyezte a XML-fájlokat, **·** **a felhasználók csak a Pénzügyi bizonylat lap tetején lévő Mellékletek elem kiválasztásával megtekinthetik őket.**

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
