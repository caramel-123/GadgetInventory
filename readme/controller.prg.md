```text
1. Browser requests the blank form:
   GET /Gadget/Create
   → [HttpGet] Create() returns the form

2. User fills it in and submits:
   POST /Gadget/Create
   → [HttpPost] Create(Gadget newGadget) validates the data

3. If valid, the gadget is saved:
   _gadgets.Add(newGadget)

4. The server redirects the browser:
   RedirectToAction("Index")

5. Browser makes a new GET request:
   GET /Gadget/Index
   → Index() returns the gadget list view
```