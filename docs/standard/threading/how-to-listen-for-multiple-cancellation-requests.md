---
title: 如何：侦听多个取消请求
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation tokens, joining
- LinkedTokenSource, how to
ms.assetid: 6f4f3804-2ed7-41b4-a97a-6e32b93f6e05
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16ba8000544d0b7d35a818d41a75f38e6fd0293d
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44178556"
---
# <a name="how-to-listen-for-multiple-cancellation-requests"></a>如何：侦听多个取消请求
此示例展示了如何同时侦听两个取消令牌，以便在其中任意一个令牌发出请求时取消操作。  
  
> [!NOTE]
>  某些情况下，当启用“仅我的代码”后，Visual Studio 会在引发异常的行中断运行并显示一条错误消息，该消息显示“用户代码未处理异常”。 此错误是良性的。 可以按 F5 继续运行，并请参阅下面示例中所示的异常处理行为。 为了阻止 Visual Studio 在第一个错误出现时中断，只需依次转到“工具”、“选项”、“调试”、“常规”下，取消选中“仅我的代码”复选框即可。  
  
## <a name="example"></a>示例  
 在下面的示例中，<xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A> 方法用于将两个令牌联接为一个令牌。 这样一来，可以将此令牌传递到只需要使用一个取消令牌作为参数的方法中。 此示例展示了以下常见方案：方法必须同时观察从类外部传入的令牌和类内部生成的令牌。  
  
 [!code-csharp[Cancellation#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex13.cs#13)]
 [!code-vb[Cancellation#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex13.vb#13)]  
  
 如果链接令牌抛出 <xref:System.OperationCanceledException>，传递到异常的令牌是链接令牌，而不是任意前置任务令牌。 若要确定取消的是哪个令牌，请直接查看前置任务令牌的状态。  
  
 虽然 <xref:System.AggregateException> 不得抛出，但此示例捕获到它的原因是，在实际情况下，任务委托抛出的除 <xref:System.OperationCanceledException> 外其他任何异常都包装在 <xref:System.OperationCanceledException> 中。  
  
## <a name="see-also"></a>请参阅

- [托管线程中的取消](../../../docs/standard/threading/cancellation-in-managed-threads.md)
