# Blazor Server in .NET 8

This project demonstrates how to upgrade Blazor Server apps to .NET 8 and take advantage of the latest Blazor features.

To upgrade an existing Blazor Server app to .NET 8:

1. Update the project file to target `net8.0` and package references to the latest .NET 8 versions ([commit](https://github.com/danroth27/Net8BlazorServer/commit/053579ae9dfceabd365e2bbd651ce88a82ef31fa)).
1. Move the contents of *App.razor* to *Routes.razor*.
1. Move content from *Pages/_Host.cshtml* to *App.razor* ([commit](https://github.com/danroth27/Net8BlazorServer/commit/9c8216026340a253ed77207a68ace1d3facbb375)):
    1. Update script to *blazor.web.js*.
    1. Replace tag helpers with Blazor equivalents.
1. Update *Program.cs* ([commit](https://github.com/danroth27/Net8BlazorServer/commit/be45c25396ab81450d8023de22b652cf0ff9a71c)):
    1. Replace `AddServerSideBlazor()` with `AddRazorComponents().AddServerComponents()`.
    1. Replace `MapBlazorHub()` with `MapRazorComponents<App>().AddServerRenderMode()`.
    1. Remove `app.MapFallbackToPage("/_Host");`.
