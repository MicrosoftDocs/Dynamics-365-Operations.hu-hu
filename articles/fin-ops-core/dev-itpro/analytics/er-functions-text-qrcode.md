---
title: QRCODE ER-függvény
description: A témakör tájékoztatást nyújt a QRCODE Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6a76549ba5d663a7b6cfb858342a56921c5cd56b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746171"
---
# <a name="qrcode-er-function"></a><span data-ttu-id="b3d3b-103">QRCODE ER-függvény</span><span class="sxs-lookup"><span data-stu-id="b3d3b-103">QRCODE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b3d3b-104">A `QRCODE` függvény egy olyan *Tároló* értéket ad vissza, amely a megadott karakterlánchoz bináris formátumban jeleníti meg a gyors válaszkódot (QR-kód).</span><span class="sxs-lookup"><span data-stu-id="b3d3b-104">The `QRCODE` function returns a *Container* value that presents the Quick Response code (QR code) image for the specified string in binary format.</span></span>

## <a name="syntax"></a><span data-ttu-id="b3d3b-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="b3d3b-105">Syntax</span></span>

```vb
QRCODE (text)
```

## <a name="arguments"></a><span data-ttu-id="b3d3b-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="b3d3b-106">Arguments</span></span>

<span data-ttu-id="b3d3b-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="b3d3b-107">`text`: *String*</span></span>

<span data-ttu-id="b3d3b-108">Az eredeti szöveget jelölő *Karakterlánc* érték.</span><span class="sxs-lookup"><span data-stu-id="b3d3b-108">A *String* value that represents the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="b3d3b-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="b3d3b-109">Return values</span></span>

<span data-ttu-id="b3d3b-110">*Konténer*</span><span class="sxs-lookup"><span data-stu-id="b3d3b-110">*Container*</span></span>

<span data-ttu-id="b3d3b-111">Az eredményül kapott bináris adatfolyam.</span><span class="sxs-lookup"><span data-stu-id="b3d3b-111">The resulting binary stream.</span></span>

## <a name="example"></a><span data-ttu-id="b3d3b-112">Példa</span><span class="sxs-lookup"><span data-stu-id="b3d3b-112">Example</span></span>

<span data-ttu-id="b3d3b-113">Az Elektronikus jelentéskészítési (ER) formátumot beállíthatja úgy, hogy a kimenő dokumentumot Microsoft Office-formátumban (Excel-munkafüzet vagy Word-dokumentum) hozza létre egy előre definiált sablonnal.</span><span class="sxs-lookup"><span data-stu-id="b3d3b-113">You can configure an Electronic reporting (ER) format to generate an outbound document in Microsoft Office format (Excel workbooks or Word documents) by using a predefined template.</span></span> <span data-ttu-id="b3d3b-114">Ez a sablon tartalmazhat egy **Kép** objektumot (Excel-munkafüzet) vagy egy **Képtartalom-vezérlőelemet** (Word-dokumentum) helyőrzőként a QR-kód képhez.</span><span class="sxs-lookup"><span data-stu-id="b3d3b-114">This template may contain a **Picture** object (Excel workbook) or a **Picture Content Control** (Word document) as a placeholder for a QR code image.</span></span> <span data-ttu-id="b3d3b-115">A konfigurált ER-formátumhoz hozzá kell adni egy olyan **Cella** elemet, amelyet a program a helyőrző kitöltésére használ.</span><span class="sxs-lookup"><span data-stu-id="b3d3b-115">You need to add to the configured ER format a **Cell** element that will be used to fill this placeholder in.</span></span> <span data-ttu-id="b3d3b-116">A QR-kódban tárolható adatok meghatározásához kötést kell definiálnia ehhez a **Cella** elemhez.</span><span class="sxs-lookup"><span data-stu-id="b3d3b-116">To specify what information will be stored in a QR code, you need to define a binding for this **Cell** element.</span></span> <span data-ttu-id="b3d3b-117">Például a következő kifejezést tartalmazó kötést lehet konfigurálni:</span><span class="sxs-lookup"><span data-stu-id="b3d3b-117">For example, you can configure such binding as containing the following expression:</span></span>

```vb
QRCODE (model.ListOfShelfLabels.LabelText)`
```

<span data-ttu-id="b3d3b-118">A konfigurált ER-formátum futtatása esetén a **model.ListOfShelfLabels** adatforrás **LabelText** mezőjének szöveges értéke kerül felhasználásra a QR-kód képének létrehozására.</span><span class="sxs-lookup"><span data-stu-id="b3d3b-118">When you run the configured ER format, the text value of the **LabelText** field of the **model.ListOfShelfLabels** data source will be used to generate a QR code image.</span></span> <span data-ttu-id="b3d3b-119">A rendszer erre a képre cseréli le a QR-kód kép helyőrzőjét a kimenő dokumentum létrehozására használt dokumentumsablonban.</span><span class="sxs-lookup"><span data-stu-id="b3d3b-119">This image will replace a QR code image placeholder in the document template using to generate an outbound document.</span></span> <span data-ttu-id="b3d3b-120">Amikor a létrehozott dokumentum képe beolvasásra kerül, a függvény visszaadja a **model.ListOfShelfLabels** adatforrás **LabelText** mezőjében szereplő szöveget.</span><span class="sxs-lookup"><span data-stu-id="b3d3b-120">When this image of the generated document is scanned, it returns the text that was taken from the **LabelText** field of the **model.ListOfShelfLabels** data source.</span></span> <span data-ttu-id="b3d3b-121">További információkért lásd: [Beágyazott képek és alakzatok az ER-rel generált dokumentumokban](electronic-reporting-embed-images-shapes.md)</span><span class="sxs-lookup"><span data-stu-id="b3d3b-121">For more information, see [Embed images and shapes in documents that you generate by using ER](electronic-reporting-embed-images-shapes.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b3d3b-122">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b3d3b-122">Additional resources</span></span>

[<span data-ttu-id="b3d3b-123">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="b3d3b-123">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]