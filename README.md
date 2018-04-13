# Gnome Extensions

Installs Gnome extensions specified by the user.

Available extensions can be found at https://extensions.gnome.org/

## Requirements

None

## Role Variables

| Variable              | Required           | Default | Description                                                                                                                                                                                                                                              |
| --------------------- | ------------------ | ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `gnome_extension_ids` | :heavy_check_mark: | `[]`    | The list of Gnome extension IDs to install. The extension ID can be found in the URL on <https://extensions.gnome.org/>. For example, the _TopIcons Plus_ URL is <https://extensions.gnome.org/extension/1031/topicons/> and the extension ID is `1031`. |

## Dependencies

None

## Example Playbook

```yaml
- hosts: localhost
  vars:
    gnome_extension_ids:
      - 234  # Steal My Focus by sstent
      - 1031 # TopIcons Plus by phocean
  roles:
      - jaredhocutt.gnome-extensions
```
