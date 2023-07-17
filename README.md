# Blazor Server in .NET 8

This project demonstrates how to build Blazor Server apps with .NET 8 and how to upgrade existing apps to take advantage of the latest features.

To upgrade an existing Blazor Server app to .NET 8:

1. Update the project file to target `net8.0` and package references to the latest .NET 8 versions ([commit](https://github.com/danroth27/Net8BlazorServer/commit/053579ae9dfceabd365e2bbd651ce88a82ef31fa)).
1. Move content from *Pages/_Host.cshtml* to *Host.razor* ([commit](https://github.com/danroth27/Net8BlazorServer/commit/6584fba166c2b58ecfe8705c03c93e17dfcd73e1)):
    1. Update script to *blazor.web.js*.
    1. Replace tag helpers with Blazor equivalents.
1. Update *Program.cs* ([commit](https://github.com/danroth27/Net8BlazorServer/commit/4171416fe90effb0862d7def767e26479105d010)):
    1. Replace `AddServerSideBlazor()` with `AddRazorComponents().AddServerComponents()`.
    1. Replace `MapBlazorHub()` with `MapRazorComponents<Host>().AddServerRenderMode()`.
    1. Remove `app.MapFallbackToPage("/_Host");`.
