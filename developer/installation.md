# Installation

```bash
curl https://install.meteor.com | /bin/sh
git clone https://github.com/reactioncommerce/reaction.git
cd reaction
./reaction pull
./reaction
```

The `master` branch will ensure your initial installation is the latest published release, and also should work with current packages from the [Meteor package manager](https://atmospherejs.com/).

However, the most recent code is in `development`, which is the recommended default branch if you are a developer.

When using the `master` branch for with development packages and versions of published packages (versus local packages), you may get some package compatibility warnings. You can use `meteor --allow-incompatible-update` to resolve this.

See the [package development documentation](developer/packages/packages.md) for details on working with the `development` branch, and using local package dependencies. You can clone or create new packages in `reaction/packages` for local package development.

### reaction run
To start Reaction, run the `reaction` command

```
reaction
```

This command runs a script that executes `meteor`. You can use any [Meteor command line option](http://docs.meteor.com/#/full/meteorhelp). ![](https://raw.github.com/reactioncommerce/reaction/development/docs/assets/guide-installation-default-user.png)

_The initial admin user for the site is auto generated, and displayed in your console (or see: env variables section to default these)_

Browse to [http://localhost:3000](https://localhost:3000) and you should see Reaction running (sample data same as on demo site)

### reaction reset
To reset the Reaction database, and optionally clear development packages. This will give you a fresh test dataset from `reactioncommerce:reaction-sample-data`.

```
reaction reset
```

See the [package development documentation](developer/packages/packages.md)  and the [settings and fixture data documentation](developer/architecture/fixtures.md) for detailed instructions on modifying initial fixture data.

### reaction pull

```bash
reaction pull
```

You can just use `git pull`, but `reaction pull` will run a script that pulls all local packages as well as Reaction. It's the easiest way to make sure you're working with the complete developer package set.

```bash
cd reaction
reaction pull
reaction
```

You can also use `meteor upgrade` to upgrade to the latest Atmosphere published packages.

_Note: currently there is not any data schema compatibility tests between releases, which is why we use `meteor reset` in this example. It's not necessary if you want to preserve your data, but there could be compatibility issues with the upgrade._