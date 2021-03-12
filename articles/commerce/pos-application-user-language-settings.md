---
title: Pénztár (POS) alkalmazás és felhasználói nyelvi beállítások
description: Ez a témakör azt mutatja be, hogyan végezhető el a Modern POS (MPOS) és a felhőalapú POS nyelvének módosítása.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 0f196b3077b0a8d80cac93a8b6b3f8c5c08c3c96
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000559"
---
# <a name="point-of-sale-pos-application-and-user-language-settings"></a>Pénztár (POS) alkalmazás és felhasználói nyelvi beállítások

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan végezhető el a Modern POS (MPOS) és a felhőalapú POS nyelvének módosítása.

## <a name="overview"></a>Áttekintés
A Modern POS (MPOS) és a felhőalapú POS támogatja az olyan környezeteket, ahol a nyelvi beállítás és a fordítás eltérhetnek egymástól az üzlet- és felhasználói beállításoknál. Például az üzlet olyan területen is lehet, ahol az angol a leggyakrabban használt nyelv az ügyfelek körében, de egyes munkavállalók inkább francia fordításban szeretnék használni az alkalmazást.

## <a name="data-language"></a>Adatnyelv

A felhasználói beállításoktól függetlenül az MPOS és a felhőalapú POS mindig az üzlet nyelvi beállításait használja az adatokhoz használt fordítások meghatározásához. Ez biztosítja, hogy a felhasználók és a vevők következetes felhasználói élményt kapjanak. Néhány példa az adatokra:

- Termékek
- Sorattribútumok értékei
- Kategórianév
- Nyomtatott vagy e-mailben küldött nyugták
- Fizetési mód neve
- Sormegjelenítési paraméterek

Az üzlet nyelve lesz a fő POS bejelentkezési képernyő nyelve is, mivel a felhasználó a bejelentkezés előtt nem ismert. Ha az üzlet nyelvéhez nem érhető el fordítás, a pénztár visszaáll a vállalat nyelvére.

### <a name="configuring-the-stores-language-setting"></a>Az üzlet nyelvbeállítás konfigurálása

Az üzlet nyelvének beállítása a **Minden üzlet** részben történik az **Üzlet** oldalon az **Általános &gt; Területi beállítások &gt; Nyelv** részben. Használja a legördülő menüt minden egyes üzlet nyelvének kiválasztásához.

## <a name="user-interface-language"></a>Felhasználói felület karbantartása

A POS-felhasználó nyelvi beállítás határozza meg a felhasználói felületen használt fordításokat. Ez magában foglalja az összes feliratot, menüt és listát, amelyek nem minősülnek adatnak. Egyetlen kivétel ez alól a POS-gombrácson megjelenő szöveg. A gombrácsok nem támogatják a fordításokat, így mindig a gombon definiált szöveget jelenítik meg. A lefordított gombok támogatásához külön gombrácsokat kell másolni és karbantartani, valamint a felhasználókhoz rendelni szükség szerint.

### <a name="configuring-the-users-language-setting"></a>Az üzlet nyelvbeállítás konfigurálása

A POS felhasználói nyelv beállítása a **Minden dolgozó** helyről történik a **Dolgozó** lap **Kiskereskedelem és kereskedelem &gt; Nyelv** részében. Ez nem a fő profil lapon van beállítva. A pénztár nem használja ezt a beállítást. A felhasználó nyelve nincs beállítva, vagy a változó értéke egy nyelvet Ha fordítások nem állnak rendelkezésre, ha az üzlet nyelv visszaáll a POS-nál.

|             | Felhasználói felület nyelv                | Adatok nyelv (termékek nyugtaformátumokat, sorkijelző, stb.) |
|-------------|----------------------------|---------------------------------------------------------------|
| **Vállalat** | Alapértelmezett                    | Alapértelmezett                                                       |
| **Üzlet**   | Felülbírálja a vállalat          | Felülbírálja a vállalat                                             |
| **Felhasználó**    | Felülbírálás üzlet vagy a vállalat | Soha                                                         |
