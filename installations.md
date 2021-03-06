# Installations

Every developer needs a set of tools and libraries to start working. In our case, we'll install all the necessary tools, and once we have the Angular CLI installed, it will take care of additional libraries we'll need for current and future projects.

## Tools

### Browser

Our first tool is the **browser**. We'll use it to see the result of our work and debug it. We recommend [Google Chrome](https://www.google.com/chrome/browser/desktop/) - it has great developer tools. [Firefox](https://www.mozilla.org/en-US/firefox/new/) is also awesome. If you don't already have one of those, just click the relevant link and follow the instructions to download and install the browser of your choice.

### IDE

Our next tool is the **IDE**, or integrated development environment. It's software that helps you write the code. IDEs can do a lot of amazing things, such as:

* highlight the code so it's easier to identify expressions
* suggest completions to what you type
* help you navigate easily through the files in your project
* and a lot more...

JetBrains [Webstorm](https://www.jetbrains.com/webstorm/download/) is one of the strongest IDEs on the market. You get the first month for free, and a totally free license if you're a student.

Microsoft [Visual Studio Code](https://code.visualstudio.com/) is also a great choice that's gained a lot of popularity lately. It is completely free for individuals.

Choose the IDE you'd like to work with and follow the installation instructions on its website.

**Visual Studio Code**

If you choose to use VSCode, we recommend installing the following plugins for Angular:

- [Angular Language Service](https://marketplace.visualstudio.com/items?itemName=Angular.ng-template)
- [angular2-inline](https://marketplace.visualstudio.com/items?itemName=natewallace.angular2-inline)

![image](/assets/vscode-plugins.png)

### Git

Git is a tool that helps you manage versions of your code and collaborate with team members. There is a lot to know about it, but in this tutorial we will cover only basic usage.

You can download it and follow the installation instructions [here](https://git-scm.com/).
When asked if you'd like to install **git bash**, say yes.

### GitHub

[GitHub](https://github.com/) is a code repository website that integrates with Git. It allows you to publish your project on the Web, copy other open source projects, and collaborate. To be able to publish your project, make sure you create a user in GitHub's website (for free, of course).

### NodeJS and NPM

**Please check the [Angular CLI docs](https://github.com/angular/angular-cli#prerequisites) for the up-to-date prerequisites!**

Another tool which most web developers are using is **NodeJS**. Once installed, it comes with another tool called **NPM** (Node Package Manager).

NodeJS lets you run JavaScript code on your computer. It is used to run a local server which serves the project files to the browser and simulates a real running website.

NPM allows you to easily download and install different libraries from the internet and manage their versions.

Download NodeJS [here](https://nodejs.org/en/).

If you already have NodeJS installed, make sure you check that the version is 6.9.0 or above by running this in your command line / terminal:

```
node -v
```

\('-v' stands for 'version'.\)

If it's lower than required, download the new version from the website and install it.

Once installed, you should also have NPM installed. Check its version by running:

```
npm -v
```


### Angular CLI

The [Angular CLI](https://github.com/angular/angular-cli) is a powerful tool that simplifies a lot of the development process. It also installs libraries you'll use in your current and future projects. Install it by running:

```
npm i -g @angular/cli
```

This command runs the NPM we recently installed here - it knows where to find the package (@angular/cli) you're looking for by the name of the package you provide.
The 'i' parameter is a short form of 'install'.
The '-g' parameter stands for the word 'global' - we'd like to have this tool globally installed on the computer, so that we could use it from any folder to create any future projects.

Read more about the Angular CLI in the following section.

### Creating a Project

First, create a folder to store all your projects, for example _myProjects_, and then use the terminal (command line window) to go into the folder:

```
cd the-path-to-your-folder/myProjects
```

Now use the Angular CLI to create a new project called _todo-list_ inside your projects folder, by running the following command:

```
ng new todo-list --prefix=todo
```

This can take a while, since many packages are being downloaded and installed.
The prefix 'todo' will be used in every component we create. The default prefix (if you don't use the flag `--prefix`) is 'app'.

Now enter the new folder that the Angular CLI created for this project:

```
cd todo-list
```

Once inside the folder of the application, run the application by using the following command:

```
ng serve -o
```

The flag `-o` is a short for `--open`, which will open your browser with the right URL: [`localhost:4200`](http://localhost:4200)

You should see a page like this:

![image](/assets/installation-result.png)

### Congratulations!

You have a running Angular application! **As long as you're working on the application, you should keep the terminal where you run it open.** Any change you make in the project code will be reflected immediately in the web browser.
You can open another terminal to perform tasks in parallel.

To stop the app from running, press `Ctrl+C` in the terminal, or close the terminal.

Now we're ready to start developing!

[See the results on StackBlitz](https://stackblitz.com/github/angularbootcamp/todo-list-tutorial-steps/tree/step-01_Installations)
