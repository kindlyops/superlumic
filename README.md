# Superlumic

Superlumic is a light utility wrapper around Ansible to ease the automated install of OSX 10.10 and higher.

## Configuration

Start by forking [superlumic-config](https://github.com/kindlyops/superlumic-config). This is the default configuration "role" for Superlumic and will serve as a starting point for your own configuration.

You will need at least a "username.yml" playbook, where you replace "username" by the username you will run Superlumic as on your mac. Use the roles folder to create "profiles" and add extra dependencies in the "requirements.yml" as needed.

How you organise your config files is entirely up to you, but this is how I do it. The "profile-all" role are the apps and settings that everyone in my company needs. Then I have a group file per type of installation (developers, designers, etc). In the "username.yml" playbook I then add all the specific things for that user.

## Running Superlumic

```
curl -s https://raw.githubusercontent.com/kindlyops/superlumic/master/superlumic | bash -s https://github.com/kindlyops/superlumic-config.git
```

Or if you have an adversion to piping scripts over the internet into bash, download the [Superlumic script](https://raw.githubusercontent.com/kindlyops/superlumic/master/superlumic) and run it.

## Out of the box result?

Starting from "emurphy.yml" this will get you:

* All my favorite GUI apps installed via Homebrew Cask
* All my favorite commandline apps installed via Homebrew
* Postgres.app database
* NodeJS and several frontend oriented tools like bower, gulp and grunt
* A bash 4 CLI environment, with a nice prompt, and terminal theme
* A whole host of "osx default" settings including computername, dock size and position, etc

and, since it's almost pure Ansible, a very easy way to adjust, tune and extend this configuration to match your needs exactly.
