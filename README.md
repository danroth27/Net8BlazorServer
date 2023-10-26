# Blazor Server in .NET 8

This project demonstrates how to upgrade Blazor Server apps to .NET 8 and take advantage of the latest Blazor features.

To upgrade an existing Blazor Server app to .NET 8:

1. Update the project file to target `net8.0` and package references to the latest .NET 8 versions.
1. Move the contents of *App.razor* to *Routes.razor*.
1. Move content from *Pages/_Host.cshtml* to *App.razor*:
    1. Update script to *blazor.web.js*.
    1. Replace tag helpers with Blazor equivalents.
1. Update *Program.cs*:
    1. Replace `AddServerSideBlazor()` with `AddRazorComponents().AddInteractiveServerComponents()`.
    1. Add `app.UseAntiforgery()`.
    1. Replace `MapBlazorHub()` with `MapRazorComponents<App>().AddInteractiveServerRenderMode()`.
    1. Remove `app.MapFallbackToPage("/_Host");`.
