### <a name="wpf-changing-a-primary-key-when-displaying-ado-data-in-a-masterdetail-scenario"></a><span data-ttu-id="72a29-101">WPF 在主/从方案中显示 ADO 数据时更改主键</span><span class="sxs-lookup"><span data-stu-id="72a29-101">WPF Changing a primary key when displaying ADO data in a Master/Detail scenario</span></span>

|   |   |
|---|---|
|<span data-ttu-id="72a29-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="72a29-102">Details</span></span>|<span data-ttu-id="72a29-103">假设你有 <code>Order</code> 类型的 ADO 项集合，其关系名为 &quot;OrderDetails&quot;，通过主键 &quot;OrderID&quot; 将其关联到 <code>Detail</code> 类型的项集合。</span><span class="sxs-lookup"><span data-stu-id="72a29-103">Suppose you have an ADO collection of items of type <code>Order</code>, with a relation named &quot;OrderDetails&quot; relating it to a collection of items of type <code>Detail</code> via the primary key &quot;OrderID&quot;.</span></span> <span data-ttu-id="72a29-104">在 WPF 应用程序中，你可以将列表控件绑定到给定顺序的详细信息：</span><span class="sxs-lookup"><span data-stu-id="72a29-104">In your WPF app, you can bind a list control to the details for a given order:</span></span><pre><code class="lang-xml">&lt;ListBox ItemsSource=&quot;{Binding Path=OrderDetails}&quot; &gt;&#13;&#10;</code></pre><span data-ttu-id="72a29-105">其中 DataContext 是一个 <code>Order</code>。</span><span class="sxs-lookup"><span data-stu-id="72a29-105">where the DataContext is an <code>Order</code>.</span></span> <span data-ttu-id="72a29-106">WPF 获取 <code>OrderDetails</code> 属性的值 - 所有 <code>Detail</code> 项的集合 D，其 <code>OrderID</code> 匹配主项的 <code>OrderID</code>。如果更改主项的主键 <code>OrderID</code>，则行为将发生变更。</span><span class="sxs-lookup"><span data-stu-id="72a29-106">WPF gets the value of the <code>OrderDetails</code> property - a collection D of all the <code>Detail</code> items whose <code>OrderID</code> matches the <code>OrderID</code> of the master item.The behavior change arises when you change the primary key <code>OrderID</code> of the master item.</span></span> <span data-ttu-id="72a29-107">ADO 自动更改详细信息集合中每个受影响记录的 <code>OrderID</code>（即复制到集合 D 的信息）。</span><span class="sxs-lookup"><span data-stu-id="72a29-107">ADO automatically changes the <code>OrderID</code> of each of the affected records in the Details collection (namely the ones copied into collection D).</span></span>  <span data-ttu-id="72a29-108">但 D 会发生什么？</span><span class="sxs-lookup"><span data-stu-id="72a29-108">But what happens to D?</span></span><ul><li><span data-ttu-id="72a29-109">旧行为：清除集合 D。</span><span class="sxs-lookup"><span data-stu-id="72a29-109">Old behavior:   Collection D is cleared.</span></span>   <span data-ttu-id="72a29-110">主项<em>不会</em>发出属性 <code>OrderDetails</code> 的更改通知。</span><span class="sxs-lookup"><span data-stu-id="72a29-110">The master item does <em>not</em> raise a change notification for property <code>OrderDetails</code>.</span></span>  <span data-ttu-id="72a29-111">列表框将继续使用集合 D，现为空。</span><span class="sxs-lookup"><span data-stu-id="72a29-111">The ListBox continues to use collection D, which is now empty.</span></span></li><li><span data-ttu-id="72a29-112">新行为：集合 D 保持不变。</span><span class="sxs-lookup"><span data-stu-id="72a29-112">New behavior:  Collection D is unchanged.</span></span>   <span data-ttu-id="72a29-113">其中每一项都将发出 <code>OrderID</code> 属性的更改通知。</span><span class="sxs-lookup"><span data-stu-id="72a29-113">Each of its items raises a change notification for the <code>OrderID</code> property.</span></span>  <span data-ttu-id="72a29-114">列表框将持续使用集合 D，并显示新 <code>OrderID</code> 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="72a29-114">The ListBox continues to use collection D, and displays the details with the new <code>OrderID</code>.</span></span></li></ul><span data-ttu-id="72a29-115">WPF 通过不同的方式创建集合 D 来实现新行为：通过调用 ADO 方法 <xref:System.Data.DataRowView.CreateChildView(System.Data.DataRelation,System.Boolean)?displayProperty=nameWithType>，并将 <code>followParent</code> 参数设置为 <code>true</code>。</span><span class="sxs-lookup"><span data-stu-id="72a29-115">WPF implements the new behavior by creating collection D in a different way:  by calling the ADO method <xref:System.Data.DataRowView.CreateChildView(System.Data.DataRelation,System.Boolean)?displayProperty=nameWithType> with the <code>followParent</code> argument set to <code>true</code>.</span></span>|
|<span data-ttu-id="72a29-116">建议</span><span class="sxs-lookup"><span data-stu-id="72a29-116">Suggestion</span></span>|<span data-ttu-id="72a29-117">应用通过使用以下 AppContext 开关获取新行为。</span><span class="sxs-lookup"><span data-stu-id="72a29-117">An app gets the new behavior by using the following AppContext switch.</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.DoNotUseFollowParentWhenBindingToADODataRelation=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;&#13;&#10;</code></pre><span data-ttu-id="72a29-118">对于面向 .NET 4.7.1 或更低版本的应用，开关默认为 <code>true</code>（旧行为），而对于面向 .NET 4.7.2 或更高版本的应用，开关默认为 <code>false</code>（新行为）。</span><span class="sxs-lookup"><span data-stu-id="72a29-118">The switch defaults to <code>true</code> (old behavior) for apps that target .NET 4.7.1 or below, and to <code>false</code> (new behavior) for apps that target .NET 4.7.2 or above.</span></span>|
|<span data-ttu-id="72a29-119">范围</span><span class="sxs-lookup"><span data-stu-id="72a29-119">Scope</span></span>|<span data-ttu-id="72a29-120">次要</span><span class="sxs-lookup"><span data-stu-id="72a29-120">Minor</span></span>|
|<span data-ttu-id="72a29-121">版本</span><span class="sxs-lookup"><span data-stu-id="72a29-121">Version</span></span>|<span data-ttu-id="72a29-122">4.7.2</span><span class="sxs-lookup"><span data-stu-id="72a29-122">4.7.2</span></span>|
|<span data-ttu-id="72a29-123">类型</span><span class="sxs-lookup"><span data-stu-id="72a29-123">Type</span></span>|<span data-ttu-id="72a29-124">重定目标</span><span class="sxs-lookup"><span data-stu-id="72a29-124">Retargeting</span></span>|
