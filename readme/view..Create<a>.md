This creates a clickable link labeled Add New Gadget.
<a asp-controller="Gadget" asp-action="Create">Add New Gadget</a>
- <a> creates the link.
- asp-controller="Gadget" points to GadgetController.
- asp-action="Create" points to its Create action.
- Add New Gadget is the text shown to the user.
With the usual MVC route, ASP.NET Core generates a URL like /Gadget/Create. Clicking it sends a GET request, which displays the blank form.