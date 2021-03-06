# PubSubChat
Publisher / Subscriber with SignalR core

## Development Setup
1) First understand the [Git Flow][1]. We are going to follow this principle in our SDLC to control the repository.

[1]: https://datasift.github.io/gitflow/IntroducingGitFlow.html "Git Flow"

2) Technology and tools to be used in this project.

* [ASP.NET Core][1] - Web framework that can be deployed in Windows, MacOS and Linux
* [SignalR Core][2] - For real-time publishing of messages
* [GitHub][3] - for repository control
* [XUnit][4] - Unit testing tool
* [vscode][5] - Use Visual Studio Code to build and run the projects

[1]: https://docs.microsoft.com/en-us/aspnet/core/?view=aspnetcore-2.1 "ASP.Net Core"
[2]: https://docs.microsoft.com/en-us/aspnet/core/signalr/?view=aspnetcore-2.1 "SignalR"
[3]: https://www.github.com "Github"
[4]: https://docs.microsoft.com/en-us/dotnet/core/testing/unit-testing-with-dotnet-test "XUnit"
[5]: https://code.visualstudio.com/download "Visual Studio Code"

3) Use [TDD][1] principles in development

[1]: https://en.wikipedia.org/wiki/Test-driven_development "TDD"

4) Download or clone the repository from [Github](https://github.com/abcamitan/PubSubChat.git)

5) Then, run below commande to download all required packages:

~~~~
dotnet restore
~~~~

6) To build and run the Web App, execute below command:

~~~~
dotnet run -p ./PubSubChat/PubSubChat.csproj
~~~~

7) To build and run the Test cases, execute below command:

~~~~
dotnet test ./PubSubChat.Tests/PubSubChat.Tests.csproj
~~~~

## Technical Design

In this design, we use SignalR core's Hub class to publish messages. Then, all subscribed client will receive all messages being posted at the Hub.

![Overview](http://gdurl.com/bE2Z)

The power of SignalR is that any type of client can subscribe to the system. It can be from Node.js, React.js, Angular.js, or any languages who supports SignalR connection.

### Class Overview

In this project, I create a ChatHub in which inherited from Hub class of SignalR core.

![Class](http://gdurl.com/jmPa)

The Hub class managing the subscription and publishing of messages.

### Flow Overview

Below the overview of how the flow look like on a high level diagram. There are three methods here being triggered by the client, this is when connects, send message and disconnects. 

![Flow](http://gdurl.com/vVss)
