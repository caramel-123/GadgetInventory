Here’s a simple form using `asp-for` with the `Brand` property:

```razor
@model GadgetInventory.Models.Gadget

<form asp-controller="Gadget" asp-action="Create" method="post">
    <label asp-for="Brand"></label>
    <input asp-for="Brand" />
    <button type="submit">Save</button>
</form>
```

`asp-for="Brand"` connects the input to `Model.Brand`. When the user enters “Samsung” and submits the form, ASP.NET Core sends a form value named `Brand`. The controller can receive it in a `Gadget` parameter:

```csharp
[HttpPost]
public IActionResult Create(Gadget gadget)
{
    // gadget.Brand contains the submitted value
    return View();
}
```




In a Razor form, `<label>`, `<input>`, and `<span>` have different jobs:

```razor
@model GadgetInventory.Models.Gadget

<label asp-for="Brand"></label>
<input asp-for="Brand" />
<span asp-validation-for="Brand"></span>
```

For the `Brand` property:

- **`<label>`** displays the field’s label, such as “Brand.”
- **`<input>`** lets the user enter a value. When the form is submitted, that value is sent to the controller.
- **`<span>`** displays a validation error for `Brand`, such as “Brand name is required.” It appears when validation fails.

The `asp-for` and `asp-validation-for` attributes connect each element to the `Brand` property.