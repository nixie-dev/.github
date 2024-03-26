![Nixie](https://raw.githubusercontent.com/nixie-dev/nixie/master/.github/logo.svg#gh-light-mode-only)
![Nixie](https://raw.githubusercontent.com/nixie-dev/nixie/master/.github/logo-dark.svg#gh-dark-mode-only)

Nixie is a lightweight solution to ship the [Nix package manager](https://nixos.org) together with a project repository, regardless of host architecture. It works kind of like you would expect `gradlew` or the Linux kernel's `make config` to.

## How do I add Nixie to my project?

To "install" Nixie onto your project's Git repository, you need to be running the Nix package manager, preferably with flakes enabled.

<details>

<summary>

### You have flakes enabled
</summary>

You only need to run one command. Make sure your current directory is this of the project you wish to populate.

```sh
nix run github:nixie-dev/nixie
```

</details>

<details>

<summary>

### You don't use flakes
</summary>

In this case, you need to retrieve Nixie manually, either by cloning this repository or adding it as a Nix channel:

#### As a Nix channel

```sh
nix-channel --add https://github.com/nixie-dev/nixie/archive/master.tar.gz nixie
nix-channel --update
nix-env -iA nixie
```

#### By cloning the `nixie-dev/nixie` repository

```sh
git clone https://github.com/nixie-dev/nixie
nix-shell /path/to/cloned/nixie/shell.nix
```

---

And finally, tell everyone your project is now [![built with nix](https://builtwithnix.org/badge.svg)](https://builtwithnix.org)

While it is possible to build Nixie directly from this repository, the resulting binary still requires Nix to be available on setup.

Once you have acquired Nixie, simply run `nixie` to automatically configure the repository you're in.

</details>
