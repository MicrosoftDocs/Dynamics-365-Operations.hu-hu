---
title: Ajándékutalvány-modul
description: Ez a témakör az ajándékutalvány-modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a8428963e105e422dcd048863c17df0926a409ac
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411112"
---
# <a name="gift-card-module"></a>Ajándékutalvány-modul

[!include [banner](includes/banner.md)]

Ez a témakör az ajándékutalvány-modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

Az ajándékutalvány egy gyakori fizetési mód, és az ajándékutalvány modul használható a pénztár modulban az ajándékutalványok elfogadására. Az ajándékutalvány modul támogatja a Dynamics 365, SVS és a Givex ajándékutalványokat. A SVS és a Givex ajándékutalványok a Adyen fizetési szolgáltatón keresztül válthatók be.

A külső ajándékutalványok (például SVS és Givex) támogatásával kapcsolatos további tudnivalókat lásd: [Támogatás a külső ajándékutalványokhoz](./dev-itpro/gift-card.md)

A következő kép egy Pénztár oldalon használt ajándékutalvány modul egy példáját jeleníti meg.

![Példa egy ajándékutalvány modulra](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a>Modul tulajdonságai

- **További mezők megjelenítése** – Ez a tulajdonság határozza meg, hogy milyen mezőket kell megjeleníteni az ajándékutalványokhozaz ajándékutalvány számán túl, amely alapértelmezés szerint mindig látható. Például egyes ajándékutalványok támogatják a személyes azonosítószám (PIN-kód) megjelenítését, mások a PIN-kód és a lejárati dátum megjelenítését. Másik lehetőségként a tulajdonság értéke „Nincs” lehet, amely csak az ajándékutalvány számát jeleníti meg, és további mezőket nem.

Támogatott értékek:
-   PIN-kód
-   Lejárat dátuma
-   PIN és lejárati dátum 
-   None

## <a name="site-settings-for-gift-card-modules"></a>Ajándékutalvány-modulok webhely-beállításai

A Commerce webhelykészítő **Webhelybeállítások \> Bővítmények** területén van egy ajándékutalvány-modul, amelynek neve **Támogatott ajándékutalvány-típus**. Ez a beállítás három értéket támogat:
- **Dynamics 365 ajándékutalvány** – Ha ezt a beállítást alkalmazza, akkor az ajándékutalvány modul csak a Dynamics 365 utalványok beváltását teszi lehetővé. Ez a beállítás csak az e-Commerce webhely bejelentkezett felhasználóinak esetében támogatott.
- **SVS és Givex ajándékutalványok** – Ha ezt a beállítást alkalmazza, akkor az ajándékutalvány modul csak a Givex és SVS utalványok beváltását teszi lehetővé. Ez a beállítás az e-Commerce webhely bejelentkezett és névtelen felhasználói esetében támogatott.
- **Dynamics 365, SVS és Givex ajándékutalványok** – Ha ezt a beállítást alkalmazza, akkor az ajándékutalvány modul a Dynamics 365, Givex és SVS utalványok beváltását teszi lehetővé. Ez a beállítás csak az e-Commerce webhely bejelentkezett felhasználóinak esetében támogatott.

## <a name="add-a-gift-card-module-to-a-page"></a>Ajándékutalvány-modul felvétele egy oldalra

Az ajándékutalvány-modulnak a pénztár lapra történő hozzáadásával és a szükséges tulajdonságok beállításával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Fizetésmodul](add-checkout-module.md).

## <a name="additional-resources"></a>További erőforrások

[Kezdő csomag áttekintése](starter-kit-overview.md)

[Fizetésmodul](add-checkout-module.md)

[Támogatás külső ajándékutalványokhoz](./dev-itpro/gift-card.md)
