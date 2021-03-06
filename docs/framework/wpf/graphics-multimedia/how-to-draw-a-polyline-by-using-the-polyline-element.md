---
title: 如何：使用 Polyline 元素来绘制折线
ms.date: 03/30/2017
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
ms.openlocfilehash: d065d3cead1ed9746a9615ce2bb6d3ec4cbd614d
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43855425"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a>如何：使用 Polyline 元素来绘制折线
此示例演示如何来绘制折线，这是通过使用一系列相互连接的直线，<xref:System.Windows.Shapes.Polyline>元素。  
  
 若要绘制折线，创建<xref:System.Windows.Shapes.Polyline>元素，并使用其<xref:System.Windows.Shapes.Polyline.Points%2A>属性指定形状顶点。 最后，使用<xref:System.Windows.Shapes.Shape.Stroke%2A>和<xref:System.Windows.Shapes.Shape.StrokeThickness%2A>属性来描述线的折线轮廓，因为没有笔画行是不可见。  
  
> [!NOTE]
>  因为<xref:System.Windows.Shapes.Polyline>元素不是闭合的形状，<xref:System.Windows.Shapes.Shape.Fill%2A>属性不起作用，即使你有意关闭形状轮廓。 若要创建具有一个闭合的形状<xref:System.Windows.Shapes.Shape.Fill%2A>，使用<xref:System.Windows.Shapes.Polygon>元素。  
  
 下面的示例绘制两个<xref:System.Windows.Shapes.Polyline>内的元素<xref:System.Windows.Controls.Canvas>。  
  
## <a name="example"></a>示例  
 在[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]，点的有效语法是以逗号分隔的 x 和 y 坐标对的空格分隔列表。  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 虽然此示例使用<xref:System.Windows.Controls.Canvas>来包含折线，但是您可以使用 polyline 元素 （和所有其他形状元素） 以及任何<xref:System.Windows.Controls.Panel>或<xref:System.Windows.Controls.Control>支持非文本内容。  
  
 此示例摘自一个更大的示例;有关完整示例，请参阅[形状元素示例](https://go.microsoft.com/fwlink/?LinkID=160037)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Shapes.Polygon>  
 <xref:System.Windows.Shapes.Shape>  
 [形状元素示例](https://go.microsoft.com/fwlink/?LinkID=160037)  
 [WPF 中的形状和基本绘图概述](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
