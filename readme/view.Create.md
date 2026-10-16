In a Razor view (`.cshtml`), **`@` switches from HTML to C#**. Razor evaluates the C# expression and puts its result into the page.

For example:

```razor
<p>Hello, @Model.Name!</p>
```

If `Model.Name` is `"Alex"`, the browser displays:

```text
Hello, Alex!
```

You can also use `@` to start a C# block:

```razor
@{
    var name = "Alex";
}

<p>Hello, @name!</p>
```

Here, `@{ ... }` runs C# code, and `@name` inserts the variable’s value into the HTML.





`@model GadgetInventory.Models.Gadget` tells a Razor view that its **`Model` is one `Gadget` object**.

- `@` starts a Razor instruction.
- `model` declares the type of data the view expects.
- `GadgetInventory.Models.Gadget` is the full name of the `Gadget` class.

The controller can pass one gadget to the view:

```csharp
public IActionResult Details()
{
    var gadget = new Gadget
    {
        Id = 1,
        Brand = "Samsung",
        ModelName = "Galaxy S24",
        Price = 849m
    };

    return View(gadget);
}
```

The view can then read that object’s properties:

```razor
@model GadgetInventory.Models.Gadget

<p>Brand: @Model.Brand</p>
<p>Price: @Model.Price</p>
```

`@model` is a declaration at the top of the view; `@Model` (capital **M**) refers to the actual object passed in.