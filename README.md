Ansible Role: customize-gnome
=========


Build status for this role: [![Build Status](https://travis-ci.org/PeterMosmans/ansible-role-customize-gnome.svg)](https://travis-ci.org/PeterMosmans/ansible-role-customize-gnome)


This role customizes the GNOME desktop. It installs fonts and GNOME extensions
from packages or zip files, copies files like desktop backgrounds and GNOME
shell tweaks to a host, and modifies user settings. Settings can be supplied in
dconf or GSettings format.

Requirements
------------

None.

Role Variables
--------------

All variables specific for this role start with `gnome_`. Available variables
are listed below:

**gnome_user**: The user whose settings will be modified. Example:
```
gnome_user: root
```

**gnome_packages**: A list of packages that will be installed. Example:
```
gnome_packages:
  - fonts-roboto
```

**gnome_fonts**: A list of fonts that will be downloaded from a remote source,
unzipped and installed into the local fonts directory. Each list item consists
of an `url`, `name`, and (glob) list of fonts in that zip file to install
(`fonts`). Example:
```
gnome_fonts:
  - url: https://github.com/adobe-fonts/source-code-pro/archive/2.030R-ro/1.050R-it.zip
    name: SourceCodePro
    fonts: "source-code-pro-2.030R-ro-1.050R-it/OTF/*.otf"
```

**gnome_files**: A list of files, specifying the source (`src`) and destination
(`dest`) that will be copied from the host to the guest. Example:
```
gnome_files:
  - src: gtk.css
    dest: /home/{{ gnome_user }}/.config/gtk-3.0/gtk.css
```

**gnome_extensions**: A list of GNOME shell extensions that will be
downloaded from a remote source and unzipped to the users' local extensions
directory. Each list item consists of an `url` and `name`. Example:
```
gnome_extensions:
  - url: "https://extensions.gnome.org/download-extension/hidetopbar@mathieu.bidon.ca.shell-extension.zip?version_tag=6450"
    name: "hidetopbar@mathieu.bidon.ca"
```

The properties `url` and/or `name` of each item can also be loaded dynamically from [the web](https://extensions.gnome.org/extension-info/?pk=545) when `id` is present. Predefined `name` and/or `url` will not be overridden! Here is an example that loads the same extension as the example above.
```
gnome_extensions:
  - id: 545
```

If the property `enable` is present and set to a truthy value (e.g. `yes`), the extension will be enabled automatically after the installation. Example:
```
gnome_extensions:
  - id: 1112
    enable: yes
```

**gnome_gsettings**: A list of gsettings entries that will be set for the
`gnome_user`, using `gsettings`.
Each list item consists of a `schema`, `key` and `value` entry. Note that values
should be contained within single quotes AND double quotes, due to Ansible's
quoting settings for shell commands. Example:
```
gnome_gsettings:
  - schema: org.gnome.desktop.interface
    key: monospace-font-name
    value: '"Source Code Pro Medium 16"'
```

**gnome_dconf**: A list of dconf entries that will be set for the `gnome_user`,
using `dconf`.
Each list item consists of a `key` and `value` entry. Example:
```
gnome_dconf:
  - key: /org/gnome/desktop/background/show-desktop-icons
    value: "false"
```

**gtk_version**: The version string of GTK. This is used to create a GTK
configuration directory, if it doesn't exist already. Example:
```
gtk_version: "gtk-3.0"
```

Dependencies
------------

None.

Example Playbook
----------------
```
- hosts: all
  become: yes
  become_method: sudo
  roles:
    - role: PeterMosmans.customize-gnome
  vars:
    gnome_user: root
    gnome_packages:
      - fonts-roboto
    gnome_fonts:
      - url: https://github.com/adobe-fonts/source-code-pro/archive/2.030R-ro/1.050R-it.zip
        name: SourceCodePro
        fonts: "source-code-pro-2.030R-ro-1.050R-it/OTF/*.otf"
    gnome_files:
      - src: gtk.css
        dest: /home/{{ gnome_user }}/.config/gtk-3.0/gtk.css
    gnome_extensions:
      - url: https://extensions.gnome.org/download-extension/hidetopbar@mathieu.bidon.ca.shell-extension.zip?version_tag=6450
        name: hidetopbar@mathieu.bidon.ca
      - id: 15
      - id: 1160
        url: https://example.com/gnome-extension/1160.zip
      - id: 1236
        name: CustomNamedExtension
      - id: 1267
        url: https://example.com/gnome-extension/1267.zip
        name: CustomNamedExtension2
      - id: 1112
        enable: yes
    gnome_gsettings:
      - schema: org.gnome.desktop.interface
        key: monospace-font-name
        value: '"Source Code Pro Medium 16"'
    gnome_dconf:
      - key: /org/gnome/desktop/background/show-desktop-icons
        value: "false"
```

This example will install the global fonts Roboto, Source Code Pro, the GNOME
shell extension hidetopbar, and modifies several settings for the user `root`.

License
-------

GPLv3

Author Information
------------------

Created by Peter Mosmans.
