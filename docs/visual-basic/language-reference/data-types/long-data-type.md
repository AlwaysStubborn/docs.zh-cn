---
title: Long 数据类型 (Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.Long
helpviewer_keywords:
- identifier type characters [Visual Basic], &
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- '& identifier type character'
- integer numbers
- literal type characters [Visual Basic], L
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- L literal type character [Visual Basic]
- integers [Visual Basic], types
- Long keyword [Visual Basic]
- data types [Visual Basic], integral
- data types [Visual Basic], assigning
- Long data type
ms.assetid: b4770c34-1804-4f8c-b512-c10b0893e516
ms.openlocfilehash: 357b7b42c7ad609b2a86ec3ee79a0f6f38dd9471
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155114"
---
# <a name="long-data-type-visual-basic"></a>Long 数据类型 (Visual Basic)

保存有符号 64 位 （8 字节） 整数取值范围为-9223372036854775808 到 9,223,372,036,854,775,807 (9.2...E + 18)。  
  
## <a name="remarks"></a>备注

 使用`Long`数据类型，以包含整数数字过大而无法放入`Integer`数据类型。  
  
 `Long` 的默认值为 0。

## <a name="literal-assignments"></a>文本分配 

您可以声明并初始化`Long`变量由将其分配十进制文本、 十六进制文本八进制文本，或 （Visual Basic 从 2017年开始） 二进制文本。 如果整数文本在 `Long` 范围之外（即，如果它小于 <xref:System.Int64.MinValue?displayProperty=nameWithType> 或大于 <xref:System.Int64.MaxValue?displayProperty=nameWithType>），会发生编译错误。

在以下示例中，表示为十进制、十六进制和二进制文本的等于 4,294,967,296 的整数被分配给 `Long` 值。
  
[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]  

> [!NOTE]
> 使用前缀`&h`或`&H`来表示十六进制文本前缀`&b`或`&B`来表示二进制文本和前缀`&o`或`&O`来表示八进制文本。 十进制文本没有前缀。

从 Visual Basic 2017 开始，你还可以使用下划线字符， `_`，作为数字分隔符，以增强可读性，如以下示例所示。

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

从 Visual Basic 15.5 开始，你还可以使用下划线字符 (`_`) 作为前缀和十六进制、 二进制或八进制数字之间的前导分隔符。 例如：

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

此外可以包含数值`L`[键入字符](../../programming-guide/language-features/data-types/type-characters.md)来表示`Long`数据类型，如以下示例所示。

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a>编程提示

-   **互操作注意事项。** 如果你与不是为.NET Framework 中，如自动化或 COM 对象，编写组件交互记住`Long`在其他环境中具有不同的数据宽度 （32 位）。 如果您将 32 位自变量传递给此类组件，将其作为声明`Integer`而不是`Long`中新的 Visual Basic 代码。  
  
-   **扩大转换。** `Long`数据类型加宽到`Decimal`， `Single`，或`Double`。 这意味着，你可以将 `Long` 转换为这些类型中的任意类型，而不会遇到 <xref:System.OverflowException?displayProperty=nameWithType> 错误。  
  
-   **类型字符。** 将文本类型字符 `L` 追加到文本会将其强制转换为 `Long` 数据类型。 将标识符类型字符 `&` 追加到任何标识符会将其强制转换为 `Long`。  
  
-   **Framework 类型。** .NET Framework 中的对应类型是 <xref:System.Int64?displayProperty=nameWithType> 结构。  

## <a name="see-also"></a>请参阅

<xref:System.Int64>
[数据类型](../../../visual-basic/language-reference/data-types/index.md)   
[整数数据类型](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
[Short 数据类型](../../../visual-basic/language-reference/data-types/short-data-type.md)   
[类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
[转换摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
[有效使用数据类型](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
