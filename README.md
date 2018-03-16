# solus-community-repo
This is a community repository for Solus OS. It includes only packages which:
  - are not acceptable in Solus official repositories (either for legal or other reasons)
  - are not included in Solus 3rd Party system
  - are not included as snap packages

Packages are built against Solus Unstable and pushed into master branch. Then they get merged in the stable branch (which the users should use) after a Solus official sync.

# Enable Repository
Run:
```
sudo eopkg ar SolusCommunity http://raw.github.com/community-repositories-for-solus/solus-community-repo/stable/eopkg-index.xml.xz
sudo eopkg ur -f
```

If you don't want to use the repository, then you can clone the github repo and install manually the eopkg files that you want from each folder, or even build the packages yourself by following the build instructions.

*Maintainers should use the master branch instead of the stable one, in order to catch errors early*

# Maintainers
  - ThanosApostolou
    1. ciano
    2. smlnj
    3. megasync

# Build Instructions:
1. Clone this repo by running `git clone https://github.com/community-repositories-for-solus/solus-community-repo.git`
2. Clone Solus common repo next to it by running `git clone https://dev.solus-project.com/source/common.git`
4. Run `make` to each folder in order to build.
5. Run `eopkg index --skip-signing` in **solus-community-repo** folder and push changes.

Make sure that you use following the solus packaging guidelines. Make sure that you have installed **solbuild-config-unstable** in order to build packages against unstable branch. Make sure you use `make local` when there are dependency chains. Make sure that the cloned **common** repo is synced before you build. Each maintainer should only change and build his own packages, otherwise the other maintainers should be contacted.
