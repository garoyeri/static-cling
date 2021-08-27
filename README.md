# Embracing the Static Cling

A trashy romance novel on Azure Static Web Apps and the developers who can't keep their hands off them.

## Getting Started

Once upon a time, on a quiet laptop (the fans had not kicked on yet), the developer decided to finally call upon the newest product who hailed from the land of Microsoft: Azure Static Web Apps.

The developer need help, so they called upon their most trusted friends:

* [Node JS](https://nodejs.org/)
* [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet/3.1)
* [Visual Studio Code](https://code.visualstudio.com/) (any other IDE would work too)

Because Node JS tended to neglect its package manager, the developer knew to ensure that the latest version was installed (7.xx at the time of this writing):

```powershell
npm install -g npm@latest
```

The developer, upon reading about Azure Static Web Apps and their eccentric tastes, knew that they would need some special tools if they had any chance of catching the CLIs of this new saucy cloud service. The developer summoned a few more tools that would be needed:

* [Azure Functions Core Tools](https://github.com/Azure/azure-functions-core-tools) (on Windows, recommend the MSI option or Chocolatey, otherwise Homebrew)
* [Static Web Apps CLI](https://github.com/azure/static-web-apps-cli) (installing using NPM)

## Public Displays of Websites

It's important to discuss first why Azure Static Web Apps is receiving such attention from the Developer. With the rich ecosystem of client side JavaScript frameworks and the proliferation of static HTML generator tools, an old flavor of web development has come back into favor with a new name: Jamstack (JavaScript and Markup ... Stack).

Jamstack applications take advantage of the fact that HTML and JavaScript in the browser can create rich complex interactions all without needing to talk to a server. Most websites that are purely information can be hosted on a simple Content Delivery Network (CDN) very inexpensively (or very freely).

Some hosts of this content: like Azure Static Web Apps and Netlify, to name two, offer free basic static content hosting, and support for executing simple server side code.

There are literally (probably) a million (likely) fish in the static template generator sea. Each day, someone decides that none of these do exactly what is desired and create a new one. This demo will cover one random one: [Docusaurus](https://docusaurus.io/) that was created by Facebook and supports React and Markdown.

First, let create a basic site using the "classic" template (there are only a few themes in this provider, so read the documentation to see what else you can do):

```powershell
mkdir static-cling
cd static-cling
git init
# if you want, rename your branch to main or something else
git branch -m main
npx @docusaurus/init@latest init --use-npm web classic
cd web
npm start
```

At this point, your browser will likely pop up <http://localhost:3000> and show you a simple default page with some images and stuff. Press CTRL+C in your terminal to stop the web server, that's not terribly impressive yet.

