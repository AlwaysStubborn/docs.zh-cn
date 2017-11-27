---
title: "类 (F#)"
description: "了解如何表示可以具有属性、 方法和事件的对象的类型 F # 类。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: d58679d5-7753-4b3b-a12f-6e9f00ed5ba3
ms.openlocfilehash: 2a73baba1f7c1b0d3bd09d22c9d6d9f0524daef3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="classes"></a><span data-ttu-id="54ca5-104">类</span><span class="sxs-lookup"><span data-stu-id="54ca5-104">Classes</span></span>

<span data-ttu-id="54ca5-105">*类*是表示可以具有属性、 方法和事件的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="54ca5-105">*Classes* are types that represent objects that can have properties, methods, and events.</span></span>


## <a name="syntax"></a><span data-ttu-id="54ca5-106">语法</span><span class="sxs-lookup"><span data-stu-id="54ca5-106">Syntax</span></span>

```fsharp
// Class definition:
type [access-modifier] type-name [type-params] [access-modifier] ( parameter-list ) [ as identifier ] =
[ class ]
[ inherit base-type-name(base-constructor-args) ]
[ let-bindings ]
[ do-bindings ]
member-list
...
[ end ]
// Mutually recursive class definitions:
type [access-modifier] type-name1 ...
and [access-modifier] type-name2 ...
...
```

## <a name="remarks"></a><span data-ttu-id="54ca5-107">备注</span><span class="sxs-lookup"><span data-stu-id="54ca5-107">Remarks</span></span>
<span data-ttu-id="54ca5-108">类表示.NET 对象类型; 的基本说明此类是在 F # 支持面向对象编程的主要类型概念。</span><span class="sxs-lookup"><span data-stu-id="54ca5-108">Classes represent the fundamental description of .NET object types; the class is the primary type concept that supports object-oriented programming in F#.</span></span>

<span data-ttu-id="54ca5-109">在前面的语法中，`type-name`是任何有效的标识符。</span><span class="sxs-lookup"><span data-stu-id="54ca5-109">In the preceding syntax, the `type-name` is any valid identifier.</span></span> <span data-ttu-id="54ca5-110">`type-params`介绍可选的泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="54ca5-110">The `type-params` describes optional generic type parameters.</span></span> <span data-ttu-id="54ca5-111">它包含的类型参数名称和括在尖括号中的约束 (`<`和`>`)。</span><span class="sxs-lookup"><span data-stu-id="54ca5-111">It consists of type parameter names and constraints enclosed in angle brackets (`<` and `>`).</span></span> <span data-ttu-id="54ca5-112">有关详细信息，请参阅[泛型](generics/index.md)和[约束](generics/constraints.md)。</span><span class="sxs-lookup"><span data-stu-id="54ca5-112">For more information, see [Generics](generics/index.md) and [Constraints](generics/constraints.md).</span></span> <span data-ttu-id="54ca5-113">`parameter-list`介绍构造函数参数。</span><span class="sxs-lookup"><span data-stu-id="54ca5-113">The `parameter-list` describes constructor parameters.</span></span> <span data-ttu-id="54ca5-114">与类型; 相关的第一个访问修饰符第二个与主构造函数。</span><span class="sxs-lookup"><span data-stu-id="54ca5-114">The first access modifier pertains to the type; the second pertains to the primary constructor.</span></span> <span data-ttu-id="54ca5-115">在这两种情况下，默认值是`public`。</span><span class="sxs-lookup"><span data-stu-id="54ca5-115">In both cases, the default is `public`.</span></span>

<span data-ttu-id="54ca5-116">使用指定的类的基类`inherit`关键字。</span><span class="sxs-lookup"><span data-stu-id="54ca5-116">You specify the base class for a class by using the `inherit` keyword.</span></span> <span data-ttu-id="54ca5-117">你必须提供参数，在括号内，基类构造函数。</span><span class="sxs-lookup"><span data-stu-id="54ca5-117">You must supply arguments, in parentheses, for the base class constructor.</span></span>

<span data-ttu-id="54ca5-118">声明字段或函数通过使用本地到类的值`let`绑定，并且必须遵循的一般规则`let`绑定。</span><span class="sxs-lookup"><span data-stu-id="54ca5-118">You declare fields or function values that are local to the class by using `let` bindings, and you must follow the general rules for `let` bindings.</span></span> <span data-ttu-id="54ca5-119">`do-bindings`一部分包括在对象构造时要执行的代码。</span><span class="sxs-lookup"><span data-stu-id="54ca5-119">The `do-bindings` section includes code to be executed upon object construction.</span></span>

<span data-ttu-id="54ca5-120">`member-list`包含其他构造函数、 实例和静态方法声明、 接口声明，抽象绑定，以及属性和事件声明。</span><span class="sxs-lookup"><span data-stu-id="54ca5-120">The `member-list` consists of additional constructors, instance and static method declarations, interface declarations, abstract bindings, and property and event declarations.</span></span> <span data-ttu-id="54ca5-121">描述了这些内容在[成员](members/index.md)。</span><span class="sxs-lookup"><span data-stu-id="54ca5-121">These are described in [Members](members/index.md).</span></span>

<span data-ttu-id="54ca5-122">`identifier`使用带有可选`as`关键字到实例变量或自我标识符，可在类型定义用来引用类型的实例为指定的名称。</span><span class="sxs-lookup"><span data-stu-id="54ca5-122">The `identifier` that is used with the optional `as` keyword gives a name to the instance variable, or self identifier, which can be used in the type definition to refer to the instance of the type.</span></span> <span data-ttu-id="54ca5-123">有关详细信息，请参阅本主题中后面的部分自我标识符。</span><span class="sxs-lookup"><span data-stu-id="54ca5-123">For more information, see the section Self Identifiers later in this topic.</span></span>

<span data-ttu-id="54ca5-124">关键字`class`和`end`标记的开始和结束的定义是可选的。</span><span class="sxs-lookup"><span data-stu-id="54ca5-124">The keywords `class` and `end` that mark the start and end of the definition are optional.</span></span>

<span data-ttu-id="54ca5-125">相互递归类型，它们是互相引用的类型，联接连同`and`关键字允许进行相互递归函数。</span><span class="sxs-lookup"><span data-stu-id="54ca5-125">Mutually recursive types, which are types that reference each other, are joined together with the `and` keyword just as mutually recursive functions are.</span></span> <span data-ttu-id="54ca5-126">有关示例，请参阅部分相互递归类型。</span><span class="sxs-lookup"><span data-stu-id="54ca5-126">For an example, see the section Mutually Recursive Types.</span></span>


## <a name="constructors"></a><span data-ttu-id="54ca5-127">构造函数</span><span class="sxs-lookup"><span data-stu-id="54ca5-127">Constructors</span></span>
<span data-ttu-id="54ca5-128">构造函数是创建的类类型的实例的代码。</span><span class="sxs-lookup"><span data-stu-id="54ca5-128">The constructor is code that creates an instance of the class type.</span></span> <span data-ttu-id="54ca5-129">类构造函数在 F # 中工作方式略有不同，与它们在其他.NET 语言中执行操作。</span><span class="sxs-lookup"><span data-stu-id="54ca5-129">Constructors for classes work somewhat differently in F# than they do in other .NET languages.</span></span> <span data-ttu-id="54ca5-130">在 F # 类中，没有始终主构造函数中所述该形参的实参`parameter-list`后面类型名称，以及其正文组成`let`(和`let rec`) 开头的类声明和绑定`do`按照的绑定。</span><span class="sxs-lookup"><span data-stu-id="54ca5-130">In an F# class, there is always a primary constructor whose arguments are described in the `parameter-list` that follows the type name, and whose body consists of the `let` (and `let rec`) bindings at the start of the class declaration and the `do` bindings that follow.</span></span> <span data-ttu-id="54ca5-131">在主构造函数的自变量是在类声明整个范围内。</span><span class="sxs-lookup"><span data-stu-id="54ca5-131">The arguments of the primary constructor are in scope throughout the class declaration.</span></span>

<span data-ttu-id="54ca5-132">你可以通过添加其他构造函数`new`关键字将成员添加，如下所示：</span><span class="sxs-lookup"><span data-stu-id="54ca5-132">You can add additional constructors by using the `new` keyword to add a member, as follows:</span></span>

<span data-ttu-id="54ca5-133">`new`(`argument-list`) = `constructor-body`</span><span class="sxs-lookup"><span data-stu-id="54ca5-133">`new`(`argument-list`) = `constructor-body`</span></span>

<span data-ttu-id="54ca5-134">新的构造函数的主体必须调用指定的类声明顶部的主构造函数。</span><span class="sxs-lookup"><span data-stu-id="54ca5-134">The body of the new constructor must invoke the primary constructor that is specified at the top of the class declaration.</span></span>

<span data-ttu-id="54ca5-135">下面的示例阐释了这一概念。</span><span class="sxs-lookup"><span data-stu-id="54ca5-135">The following example illustrates this concept.</span></span> <span data-ttu-id="54ca5-136">在下面的代码中，`MyClass`具有两个构造函数，采用两个自变量和另一个构造函数具有主构造函数不采用任何参数。</span><span class="sxs-lookup"><span data-stu-id="54ca5-136">In the following code, `MyClass` has two constructors, a primary constructor that takes two arguments and another constructor that takes no arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2401.fs)]
    
## <a name="let-and-do-bindings"></a><span data-ttu-id="54ca5-137">let 和 do 绑定</span><span class="sxs-lookup"><span data-stu-id="54ca5-137">let and do Bindings</span></span>

<span data-ttu-id="54ca5-138">`let`和`do`类定义中的绑定窗体的主类构造函数中，正文，因此它们运行每当创建类实例。</span><span class="sxs-lookup"><span data-stu-id="54ca5-138">The `let` and `do` bindings in a class definition form the body of the primary class constructor, and therefore they run whenever a class instance is created.</span></span> <span data-ttu-id="54ca5-139">如果`let`绑定是一个函数，则将它编译为一个成员。</span><span class="sxs-lookup"><span data-stu-id="54ca5-139">If a `let` binding is a function, then it is compiled into a member.</span></span> <span data-ttu-id="54ca5-140">如果`let`绑定是一个值，不用于任何函数或成员，则将编译为一个变量，是为构造函数。</span><span class="sxs-lookup"><span data-stu-id="54ca5-140">If the `let` binding is a value that is not used in any function or member, then it is compiled into a variable that is local to the constructor.</span></span> <span data-ttu-id="54ca5-141">否则，它会编译成类的字段。</span><span class="sxs-lookup"><span data-stu-id="54ca5-141">Otherwise, it is compiled into a field of the class.</span></span> <span data-ttu-id="54ca5-142">`do`按照的表达式被编译到主构造函数和执行初始化代码的每个实例。</span><span class="sxs-lookup"><span data-stu-id="54ca5-142">The `do` expressions that follow are compiled into the primary constructor and execute initialization code for every instance.</span></span> <span data-ttu-id="54ca5-143">任何其他构造函数始终调用主构造函数，因为`let`绑定和`do`绑定始终执行而与所调用构造函数。</span><span class="sxs-lookup"><span data-stu-id="54ca5-143">Because any additional constructors always call the primary constructor, the `let` bindings and `do` bindings always execute regardless of which constructor is called.</span></span>

<span data-ttu-id="54ca5-144">通过创建的字段`let`绑定可以访问在这些方法和类的属性; 但是，它们不能从访问静态方法，即使的静态方法采用实例变量作为参数。</span><span class="sxs-lookup"><span data-stu-id="54ca5-144">Fields that are created by `let` bindings can be accessed throughout the methods and properties of the class; however, they cannot be accessed from static methods, even if the static methods take an instance variable as a parameter.</span></span> <span data-ttu-id="54ca5-145">它们不能通过使用自我标识符，如果存在访问。</span><span class="sxs-lookup"><span data-stu-id="54ca5-145">They cannot be accessed by using the self identifier, if one exists.</span></span>


## <a name="self-identifiers"></a><span data-ttu-id="54ca5-146">自我标识符</span><span class="sxs-lookup"><span data-stu-id="54ca5-146">Self Identifiers</span></span>

<span data-ttu-id="54ca5-147">A*自我标识符*是表示的当前实例的名称。</span><span class="sxs-lookup"><span data-stu-id="54ca5-147">A *self identifier* is a name that represents the current instance.</span></span> <span data-ttu-id="54ca5-148">自我标识符类似于`this`C# 或 c + + 中的关键字或`Me`在 Visual Basic 中。</span><span class="sxs-lookup"><span data-stu-id="54ca5-148">Self identifiers resemble the `this` keyword in C# or C++ or `Me` in Visual Basic.</span></span> <span data-ttu-id="54ca5-149">可以在两种不同方式，具体取决于是否想自我标识符处于作用域为整个类定义，或仅有关单个方法来定义自我标识符。</span><span class="sxs-lookup"><span data-stu-id="54ca5-149">You can define a self identifier in two different ways, depending on whether you want the self identifier to be in scope for the whole class definition or just for an individual method.</span></span>

<span data-ttu-id="54ca5-150">若要定义整个类自我标识符，使用`as`构造函数参数的右括号后关键字列表，并指定标识符名称。</span><span class="sxs-lookup"><span data-stu-id="54ca5-150">To define a self identifier for the whole class, use the `as` keyword after the closing parentheses of the constructor parameter list, and specify the identifier name.</span></span>

<span data-ttu-id="54ca5-151">若要定义自我标识符仅为一个方法，提供在成员声明中之前的方法名称和句点 （.） 作为分隔符, 的自我标识符。</span><span class="sxs-lookup"><span data-stu-id="54ca5-151">To define a self identifier for just one method, provide the self identifier in the member declaration, just before the method name and a period (.) as a separator.</span></span>

<span data-ttu-id="54ca5-152">下面的代码示例说明了创建自我标识符的两种方法。</span><span class="sxs-lookup"><span data-stu-id="54ca5-152">The following code example illustrates the two ways to create a self identifier.</span></span> <span data-ttu-id="54ca5-153">在第一个行中，`as`关键字用于定义自我标识符。</span><span class="sxs-lookup"><span data-stu-id="54ca5-153">In the first line, the `as` keyword is used to define the self identifier.</span></span> <span data-ttu-id="54ca5-154">在第五个行中，标识符`this`用于定义其作用域仅限于方法自我标识符`PrintMessage`。</span><span class="sxs-lookup"><span data-stu-id="54ca5-154">In the fifth line, the identifier `this` is used to define a self identifier whose scope is restricted to the method `PrintMessage`.</span></span>

```fsharp
type MyClass2(dataIn) as self =
    let data = dataIn
    do
        self.PrintMessage()
    member this.PrintMessage() =
        printf "Creating MyClass2 with Data %d" data
```

<span data-ttu-id="54ca5-155">与在其他.NET 语言中，您可以命名自我标识符随意;你并不限制为名称如`self`， `Me`，或`this`。</span><span class="sxs-lookup"><span data-stu-id="54ca5-155">Unlike in other .NET languages, you can name the self identifier however you want; you are not restricted to names such as `self`, `Me`, or `this`.</span></span>

<span data-ttu-id="54ca5-156">使用声明的自我标识符`as`之前未初始化关键字后`let`执行绑定。</span><span class="sxs-lookup"><span data-stu-id="54ca5-156">The self identifier that is declared with the `as` keyword is not initialized until after the `let` bindings are executed.</span></span> <span data-ttu-id="54ca5-157">因此，它不能在`let`绑定。</span><span class="sxs-lookup"><span data-stu-id="54ca5-157">Therefore, it cannot be used in the `let` bindings.</span></span> <span data-ttu-id="54ca5-158">你可以使用中的自我标识符`do`绑定部分。</span><span class="sxs-lookup"><span data-stu-id="54ca5-158">You can use the self identifier in the `do` bindings section.</span></span>


## <a name="generic-type-parameters"></a><span data-ttu-id="54ca5-159">泛型类型参数</span><span class="sxs-lookup"><span data-stu-id="54ca5-159">Generic Type Parameters</span></span>

<span data-ttu-id="54ca5-160">在尖括号中指定泛型类型参数 (`<`和`>`)，单引号跟一个标识符的形式。</span><span class="sxs-lookup"><span data-stu-id="54ca5-160">Generic type parameters are specified in angle brackets (`<` and `>`), in the form of a single quotation mark followed by an identifier.</span></span> <span data-ttu-id="54ca5-161">用逗号分隔多个泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="54ca5-161">Multiple generic type parameters are separated by commas.</span></span> <span data-ttu-id="54ca5-162">泛型类型参数是在声明整个范围内。</span><span class="sxs-lookup"><span data-stu-id="54ca5-162">The generic type parameter is in scope throughout the declaration.</span></span> <span data-ttu-id="54ca5-163">下面的代码示例演示如何指定泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="54ca5-163">The following code example shows how to specify generic type parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2403.fs)]

<span data-ttu-id="54ca5-164">使用类型时，会被推断类型参数。</span><span class="sxs-lookup"><span data-stu-id="54ca5-164">Type arguments are inferred when the type is used.</span></span> <span data-ttu-id="54ca5-165">在下面的代码中，推断出的类型是一个元组序列。</span><span class="sxs-lookup"><span data-stu-id="54ca5-165">In the following code, the inferred type is a sequence of tuples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24031.fs)]
    
## <a name="specifying-inheritance"></a><span data-ttu-id="54ca5-166">指定继承</span><span class="sxs-lookup"><span data-stu-id="54ca5-166">Specifying Inheritance</span></span>

<span data-ttu-id="54ca5-167">`inherit`子句标识直接基类，如果有一个。</span><span class="sxs-lookup"><span data-stu-id="54ca5-167">The `inherit` clause identifies the direct base class, if there is one.</span></span> <span data-ttu-id="54ca5-168">在 F # 中，只有一个直接基类被允许。</span><span class="sxs-lookup"><span data-stu-id="54ca5-168">In F#, only one direct base class is allowed.</span></span> <span data-ttu-id="54ca5-169">类实现的接口不被视为基类。</span><span class="sxs-lookup"><span data-stu-id="54ca5-169">Interfaces that a class implements are not considered base classes.</span></span> <span data-ttu-id="54ca5-170">接口中讨论了[接口](Interfaces.md)主题。</span><span class="sxs-lookup"><span data-stu-id="54ca5-170">Interfaces are discussed in the [Interfaces](Interfaces.md) topic.</span></span>

<span data-ttu-id="54ca5-171">你可以访问的方法和属性的基类派生类中使用该语言关键字`base`作为标识符后, 跟一个句点 （.） 和成员的名称。</span><span class="sxs-lookup"><span data-stu-id="54ca5-171">You can access the methods and properties of the base class from the derived class by using the language keyword `base` as an identifier, followed by a period (.) and the name of the member.</span></span>

<span data-ttu-id="54ca5-172">有关详细信息，请参阅[继承](inheritance.md)。</span><span class="sxs-lookup"><span data-stu-id="54ca5-172">For more information, see [Inheritance](inheritance.md).</span></span>


## <a name="members-section"></a><span data-ttu-id="54ca5-173">成员部分</span><span class="sxs-lookup"><span data-stu-id="54ca5-173">Members Section</span></span>
<span data-ttu-id="54ca5-174">你可以在本部分中定义静态或实例方法、 属性、 接口实现、 抽象成员、 事件声明和其他构造函数。</span><span class="sxs-lookup"><span data-stu-id="54ca5-174">You can define static or instance methods, properties, interface implementations, abstract members, event declarations, and additional constructors in this section.</span></span> <span data-ttu-id="54ca5-175">允许和执行操作的绑定不能出现在此部分。</span><span class="sxs-lookup"><span data-stu-id="54ca5-175">Let and do bindings cannot appear in this section.</span></span> <span data-ttu-id="54ca5-176">因为成员可以添加到不同的 F # 类型除了类之外，因此将讨论在单独主题中，[成员](members/index.md)。</span><span class="sxs-lookup"><span data-stu-id="54ca5-176">Because members can be added to a variety of F# types in addition to classes, they are discussed in a separate topic, [Members](members/index.md).</span></span>


## <a name="mutually-recursive-types"></a><span data-ttu-id="54ca5-177">相互递归类型</span><span class="sxs-lookup"><span data-stu-id="54ca5-177">Mutually Recursive Types</span></span>
<span data-ttu-id="54ca5-178">在定义相互以循环方式引用的类型时，你将排列在一起的类型定义通过使用`and`关键字。</span><span class="sxs-lookup"><span data-stu-id="54ca5-178">When you define types that reference each other in a circular way, you string together the type definitions by using the `and` keyword.</span></span> <span data-ttu-id="54ca5-179">`and`关键字将替换`type`上除外，如下所示的第一个定义的关键字。</span><span class="sxs-lookup"><span data-stu-id="54ca5-179">The `and` keyword replaces the `type` keyword on all except the first definition, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2404.fs)]

<span data-ttu-id="54ca5-180">输出为当前目录中的所有文件的列表。</span><span class="sxs-lookup"><span data-stu-id="54ca5-180">The output is a list of all the files in the current directory.</span></span>


## <a name="when-to-use-classes-unions-records-and-structures"></a><span data-ttu-id="54ca5-181">何时使用类、 联合、 记录和结构</span><span class="sxs-lookup"><span data-stu-id="54ca5-181">When to Use Classes, Unions, Records, and Structures</span></span>
<span data-ttu-id="54ca5-182">给定的各种类型可供选择，需要更好地理解什么每个类型都旨在为选择的特定情况下的相应类型。</span><span class="sxs-lookup"><span data-stu-id="54ca5-182">Given the variety of types to choose from, you need to have a good understanding of what each type is designed for to select the appropriate type for a particular situation.</span></span> <span data-ttu-id="54ca5-183">类旨在在面向对象编程的上下文中使用。</span><span class="sxs-lookup"><span data-stu-id="54ca5-183">Classes are designed for use in object-oriented programming contexts.</span></span> <span data-ttu-id="54ca5-184">面向对象的编程是为.NET Framework 编写的应用程序中使用的基准范例。</span><span class="sxs-lookup"><span data-stu-id="54ca5-184">Object-oriented programming is the dominant paradigm used in applications that are written for the .NET Framework.</span></span> <span data-ttu-id="54ca5-185">如果你的 F # 代码必须与.NET Framework 或另一个面向对象的库，紧密合作，尤其是如果你需要从面向对象的类型系统如 UI 库扩展，类则和可能适用。</span><span class="sxs-lookup"><span data-stu-id="54ca5-185">If your F# code has to work closely with the .NET Framework or another object-oriented library, and especially if you have to extend from an object-oriented type system such as a UI library, classes are probably appropriate.</span></span>

<span data-ttu-id="54ca5-186">如果你不与互操作性密切面向对象的代码，或者你正在编写是自包含且与面向对象的代码进行频繁交互因此受保护的代码，你应该考虑使用记录和可区分联合。</span><span class="sxs-lookup"><span data-stu-id="54ca5-186">If you are not interoperating closely with object-oriented code, or if you are writing code that is self-contained and therefore protected from frequent interaction with object-oriented code, you should consider using records and discriminated unions.</span></span> <span data-ttu-id="54ca5-187">单个精心构思的可区分的联合，以及适当的模式匹配的代码中，通常可用作对象层次结构一个更简单的替代方法。</span><span class="sxs-lookup"><span data-stu-id="54ca5-187">A single, well thought–out discriminated union, together with appropriate pattern matching code, can often be used as a simpler alternative to an object hierarchy.</span></span> <span data-ttu-id="54ca5-188">有关可区分联合的详细信息，请参阅[可区分联合](discriminated-unions.md)。</span><span class="sxs-lookup"><span data-stu-id="54ca5-188">For more information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>

<span data-ttu-id="54ca5-189">记录具有比类，更简单的优点，但是记录将不适用的一种类型的需求超过了所实现的简单性。</span><span class="sxs-lookup"><span data-stu-id="54ca5-189">Records have the advantage of being simpler than classes, but records are not appropriate when the demands of a type exceed what can be accomplished with their simplicity.</span></span> <span data-ttu-id="54ca5-190">记录是基本上简单值的聚合，可以执行自定义操作的单独构造函数，而无需隐藏的字段，而无需继承或接口的实现。</span><span class="sxs-lookup"><span data-stu-id="54ca5-190">Records are basically simple aggregates of values, without separate constructors that can perform custom actions, without hidden fields, and without inheritance or interface implementations.</span></span> <span data-ttu-id="54ca5-191">虽然如属性和方法的成员可以添加到记录以使其行为更复杂，存储在记录中的字段仍是一个简单值的聚合。</span><span class="sxs-lookup"><span data-stu-id="54ca5-191">Although members such as properties and methods can be added to records to make their behavior more complex, the fields stored in a record are still a simple aggregate of values.</span></span> <span data-ttu-id="54ca5-192">记录有关的详细信息，请参阅[记录](records.md)。</span><span class="sxs-lookup"><span data-stu-id="54ca5-192">For more information about records, see [Records](records.md).</span></span>

<span data-ttu-id="54ca5-193">结构还可以用于的少量聚合数据，但它们可以将其与类和记录的区别在于它们是.NET 值类型。</span><span class="sxs-lookup"><span data-stu-id="54ca5-193">Structures are also useful for small aggregates of data, but they differ from classes and records in that they are .NET value types.</span></span> <span data-ttu-id="54ca5-194">类和记录是.NET 引用类型。</span><span class="sxs-lookup"><span data-stu-id="54ca5-194">Classes and records are .NET reference types.</span></span> <span data-ttu-id="54ca5-195">值类型和引用类型的语义的不同，在于，按值传递的值类型。</span><span class="sxs-lookup"><span data-stu-id="54ca5-195">The semantics of value types and reference types are different in that value types are passed by value.</span></span> <span data-ttu-id="54ca5-196">这意味着，它们将会复制在作为参数传递或从函数返回时的位位。</span><span class="sxs-lookup"><span data-stu-id="54ca5-196">This means that they are copied bit for bit when they are passed as a parameter or returned from a function.</span></span> <span data-ttu-id="54ca5-197">客户还存储在堆栈上或者，如果用作字段，则嵌入在父对象而不是存储在堆上其自己单独的位置。</span><span class="sxs-lookup"><span data-stu-id="54ca5-197">They are also stored on the stack or, if they are used as a field, embedded inside the parent object instead of stored in their own separate location on the heap.</span></span> <span data-ttu-id="54ca5-198">因此，结构适于经常访问的数据访问堆的开销时出现问题。</span><span class="sxs-lookup"><span data-stu-id="54ca5-198">Therefore, structures are appropriate for frequently accessed data when the overhead of accessing the heap is a problem.</span></span> <span data-ttu-id="54ca5-199">有关结构的详细信息，请参阅[结构](structures.md)。</span><span class="sxs-lookup"><span data-stu-id="54ca5-199">For more information about structures, see [Structures](structures.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="54ca5-200">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54ca5-200">See Also</span></span>
[<span data-ttu-id="54ca5-201">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="54ca5-201">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="54ca5-202">成员</span><span class="sxs-lookup"><span data-stu-id="54ca5-202">Members</span></span>](members/index.md)

[<span data-ttu-id="54ca5-203">继承</span><span class="sxs-lookup"><span data-stu-id="54ca5-203">Inheritance</span></span>](inheritance.md)

[<span data-ttu-id="54ca5-204">接口</span><span class="sxs-lookup"><span data-stu-id="54ca5-204">Interfaces</span></span>](interfaces.md)
