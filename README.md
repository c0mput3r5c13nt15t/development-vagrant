# Development environments

## Start an existing environment

```bash
cd <path-environment>/vagrant
vagrant up
vagrant ssh
# On the vagrant box
cd /projects/<project-name>
```

If you need the vagrant box to be notified about filesystem changes, e.g. for hot-reloading with JavaScript frameworks, you can use the following command in a separate terminal:

```bash
vagrant fsnotify
```

## Create a new environment

1. Create a new folder for the environment, e.g. `rust`
2. Create a Vagrantfile under `<path-environment>/vagrant`, e.g. `rust/vagrant/Vagrantfile`
3. Create a projects folder under `<path-environment>/projects` where you create your actual project directories, e.g. `rust/projects`
4. Add `!<path-environment>` to your `.gitignore` file, e.g. `!rust`
5. Start the environment as described above

## Most important Vagrant commands

```bash
vagrant up # Start the vagrant box
vagrant halt # Stop the vagrant box
vagrant destroy # Destroy the vagrant box
vagrant ssh # SSH into the vagrant box
vagrant fsnotify # Notify the vagrant box about filesystem changes
```

## Troubleshooting

- Problem installing vagrant-fsnotify: `$VAGRANT_DISABLE_STRICT_DEPENDENCY_ENFORCEMENT=1 vagrant plugin install vagrant-fsnotify`