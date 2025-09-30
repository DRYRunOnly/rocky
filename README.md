# rocky 🚀🍜

**Learn the basics of managing code and dependencies**

---

## What is Artifact (or Package) Management? 🍱
- You rarely write software from scratch.
- You use pieces of code others have already written.
- These reusaeable pieces are called **packages** or **artifacts**.

Think of them as ingredients in cooking: 
- Instead of growing your own tomatoes, you buy them.
- In software, instead of writing everything, you install a package that already does the job.

Picture this: You're at a global food festival. Every chef brings their own specialty dish (lasagna, sushi, tacos...), but you want to create the ultimate buffet. Instead of cooking everything from scratch, you grab the best dishes from each chef and assemble your feast. **Package management** is like this for code: it lets you grab ready-made "dishes" (packages/libraries) from a huge, shared kitchen, so you can build your app without reinventing the wheel.

## Why Package Management Exists 🤔

- **Saves time:** Don't write code that's already been written!
- **Consistency:** Everyone uses the same "recipe" for common tasks.
- **Updates & Security:** Fix bugs and patch vulnerabilities by upgrading packages.
- **Collaboration:** Share your own recipes with the world!

## What is a vulnerability?
A vulnerability is a **weakness** in software that attackers can exploit. Vulnerabilities aren't always malicious, but they do pose a risk to companies.
- It could be a bug in the code.
- It could be poor configuration.
- It could be an outdated dependency that has a known flaw.
When exploited, a vulnerability can allow someone (the attacker) to do bad things:
- Steal data (like cryptowallet addresses, passwords, etc)
- Run malicious code
- Break the software
- Gain access to things they shouldn't have

## The Lifecycle of a Package 📦

1. **Cooking:** You write code and bundle it as a package.
2. **Publishing:** You upload it to a repository (like npmjs.com).
3. **Installing:** Others install your package via a package manager (like `npm install`).
4. **Using:** Your code runs in their project, making their lives easier.
5. **Updating:** You (or others) publish improvements or fixes.

## Other Ecosystems 🌐

- **npm:** JavaScript/Node.js (that's us!)
- **pip:** Python
- **Maven:** Java
- **NuGet:** .NET
- **OS package managers:** apt (Debian/Ubuntu), yum (Red Hat), Homebrew (macOS), etc.
- **Cloudsmith:** A universal repository for npm, RubyGems, Python, Maven, Docker, and more.

Each language or platform has its own "food court" with favorite dishes and a line of hungry developers!

## Package Manager vs Repository 🤓

- **Package Manager:** The tool you use to fetch, install, and manage packages (e.g., `npm`, `pip`).
- **Repository:** The big pantry where all the packages live (e.g., npmjs.com, PyPI, Maven Central, or Cloudsmith as a universal option).

Think: **npm** is your waiter, **Cloudsmith** is the restaurant kitchen.

## Real-World Fun Analogy Continuation 🍔🍕🍣

Imagine you want to make a burger, but you don't want to bake your own buns, grind your own beef, or grow your own lettuce. You use a **package manager** to fetch the best buns, patties, and toppings from the "repository supermarket." If you want to share your secret sauce, you package it up and upload it so others can install it too!

## What This Repo Contains 📁

```
rocky/
├── bin/             # CLI entry points (like 'rocky')
├── src/             # Source code for the CLI and package logic
├── package.json     # Metadata: name, version, dependencies, scripts
├── README.md        # You're reading it!
├── .gitignore       # Files to ignore in git
├── node_modules/        # Installed dependencies (auto-generated, not committed)
├── package-lock.json    # Exact dependency tree lockfile (auto-generated)
├── CHANGELOG.md         # Record of notable changes per version
├── LICENSE              # License file (MIT in this case)
```


## package.json Explained 📝

The `package.json` file is the heart of any npm package. Here's what the main fields mean:

- **`name`**: The name of the package (what you install with npm).
- **`version`**: The package version (normally semver like 1.0.0).
- **`description`**: A short description of the package.
- **`main`**: Entry point file when the package is required.
- **`bin`**: CLI executables mapping.
- **`files`**: List of files/folders included when publishing.
- **`scripts`**: npm commands for build/test/etc.
- **`dependencies`**: Direct dependencies of your project.
- **`keywords`**: Tags to help discovery on npm.
- **`author`**: Package author.
- **`license`**: License type (e.g., MIT).


## How It Works ⚙️

- **CLI:** Run commands like `npx rocky` to see the magic.
- **index.js:** The main code that powers the CLI.
- **package.json:** Tells npm everything about this package—name, version, what to run, and more.

## Dependencies (Direct & Transitive) 🧩

This project also pulls in a couple of open‑world npm packages to show how dependencies work:

- **Direct dependency:** a package we explicitly add to `package.json`.
- **Transitive dependency:** packages that come along for the ride because our direct dependencies depend on them.

When you run `npm install`, npm resolves the whole tree. For example:

Direct dependencies for this project are listed under the `"dependencies"` section in the `package.json` file. These are the packages you explicitly choose to use in your project. Their transitive dependencies—the packages that your direct dependencies rely on—are not listed directly in your `package.json`; instead, npm automatically discovers and installs them for you during the installation process.

- We add **lodash** directly.
- Lodash may depend on other internal helpers (transitive).
- If we also add something like **chalk** (for colorful CLI output), it too brings in its own set of transitive dependencies.

You can explore this with:
```bash
npm ls --depth=0
npm ls
```

## Commands We Use 🛠️

- `npm pack` — Bundle your code into a `.tgz` file (like shrink-wrapping your dish for delivery).
- `npm install ./rocky-npm-1.0.0.tgz` — Install your local package into another project.
- `npx rocky` — Run the CLI directly, even if you haven't installed it globally.

## Why is this Fun? 🎉

You can build your own CLI, pack it, install it, and run it with a single command. Watch it in action:

```bash
$ npx rocky
🪨 Welcome to the Rocky CLI! Let's rock your world!
```

No more "it works on my machine"—now it works everywhere!

## Learnings Recap 📝

- npm makes sharing and using code as easy as ordering takeout.
- Package managers & repositories are the backbone of modern software.
- You can build, pack, install, and run your own tools with just a few commands.
- The world of package management is vast, delicious, and fun!

## License 📄

MIT — Free as in pizza, share as you like!
