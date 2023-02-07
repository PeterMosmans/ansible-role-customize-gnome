# Changelog

## [0.2.11](https://github.com/PeterMosmans/ansible-role-customize-gnome/compare/0.2.10...0.2.11) (2023-02-07)

### Bug Fixes

- fixes
  [#25](https://github.com/PeterMosmans/ansible-role-customize-gnome/issues/25)
  ([9cc4673](https://github.com/PeterMosmans/ansible-role-customize-gnome/commit/9cc467351836d61a1708a998c2cb80dadf1c808c))

### [0.2.10](https://github.com/PeterMosmans/ansible-role-customize-gnome/compare/0.2.9...0.2.10) (2022-11-15)

### Features

- support downloading font files directly
  ([403951a](https://github.com/PeterMosmans/ansible-role-customize-gnome/commit/403951a803fdb19aa4792fb2f9f9a3b189ec687c))

### Bug Fixes

- copy single font files correctly
  ([342c30f](https://github.com/PeterMosmans/ansible-role-customize-gnome/commit/342c30f11c179c15b065539521089f186799d650))
- set correct mode on copied fonts
  ([de88bc6](https://github.com/PeterMosmans/ansible-role-customize-gnome/commit/de88bc6e67d88e86a81d8b79dfb11e0212a9774c))

### [0.2.9](https://github.com/PeterMosmans/ansible-role-customize-gnome/compare/0.2.8...0.2.9) (2022-11-15)

### Bug Fixes

- fallback to newer command for enabling extensions when older fails
  ([976b4e2](https://github.com/PeterMosmans/ansible-role-customize-gnome/commit/976b4e2246a933f27bcb43a51e5c410b126862dd))
- fallback to newer command for enabling extensions when older fails
  ([9443a2f](https://github.com/PeterMosmans/ansible-role-customize-gnome/commit/9443a2fddcf7172a972099e2530fb58c29762049)),
  closes
  [#22](https://github.com/PeterMosmans/ansible-role-customize-gnome/issues/22)

### [0.2.8](https://github.com/PeterMosmans/ansible-role-customize-gnome/compare/0.2.7...0.2.8) (2022-10-04)

### Features

- add automated security testing
  ([760ddee](https://github.com/PeterMosmans/ansible-role-customize-gnome/commit/760ddeefb5d6a20524d2e770549c7992aa466b7e))
- use dconf module
  ([49a9cc0](https://github.com/PeterMosmans/ansible-role-customize-gnome/commit/49a9cc00bcb9b152d28be73c698caedd23e742a6))

### Bug Fixes

- don't fail with empty extensions list
  ([812d815](https://github.com/PeterMosmans/ansible-role-customize-gnome/commit/812d815b61536fdc29b77db8dda43f61e9e2d27d))

### [0.2.7](https://github.com/PeterMosmans/ansible-role-customize-gnome/compare/0.2.6...0.2.7) (2022-10-04)

### Bug Fixes

- don't allow characters in version number
  ([9c56ad0](https://github.com/PeterMosmans/ansible-role-customize-gnome/commit/9c56ad0e51895a5c53dfa2009474b69746b01c4d))

### [0.2.6](https://github.com/PeterMosmans/ansible-role-customize-gnome/compare/0.2.5...0.2.6) (2022-08-09)

### Bug Fixes

- allow shell extension upgrade to work again
  ([ffd2ecd](https://github.com/PeterMosmans/ansible-role-customize-gnome/commit/ffd2ecd8198e41083acb611a9d050a00fc58b706))

### [0.2.5](https://github.com/PeterMosmans/ansible-role-customize-gnome/compare/0.2.4...0.2.5) (2022-07-11)

### Features

- take only the first 2 parts of gnome-shell version
  ([ef7ac3d](https://github.com/PeterMosmans/ansible-role-customize-gnome/commit/ef7ac3d6449d5ee996f83d5144d873264e84726b))

### [0.2.4](https://github.com/PeterMosmans/ansible-role-customize-gnome/compare/0.2.3...0.2.4) (2021-10-31)

### [0.2.3](https://github.com/PeterMosmans/ansible-role-customize-gnome/compare/0.2.2...0.2.3) (2021-10-28)

### Features

- enforce namespace
  ([06a38b4](https://github.com/PeterMosmans/ansible-role-customize-gnome/commit/06a38b4ef56ce8e25a394e9e537be86f273319a6))
- move installation of fonts to different tasks file
  ([35fce94](https://github.com/PeterMosmans/ansible-role-customize-gnome/commit/35fce947900d6bb4807239b041659188797282e4))
- use nicer display of loops
  ([5212b6d](https://github.com/PeterMosmans/ansible-role-customize-gnome/commit/5212b6d0750148bba96f584776d3fd389b3402a2))

### [0.2.2](https://github.com/PeterMosmans/ansible-role-customize-gnome/compare/0.2.1...0.2.2) (2021-10-28)

### Features

- don't show that something's changed when nothing's changed
  ([36de445](https://github.com/PeterMosmans/ansible-role-customize-gnome/commit/36de44591afb8e1245283b7ddbd645c01d6e38e1))
- ensure play fails when pipe output fails
  ([44d3b34](https://github.com/PeterMosmans/ansible-role-customize-gnome/commit/44d3b34cd34454571c92b8c4e9464b346ffec309))
- exit play when no Gnome Shell is detected
  ([5656f78](https://github.com/PeterMosmans/ansible-role-customize-gnome/commit/5656f7870e42ed951cb3d05f09b583d1daa3b945))
- use default ansible_user_id as gnome_user
  ([3b16f61](https://github.com/PeterMosmans/ansible-role-customize-gnome/commit/3b16f6180998316740cbe85fe26b842898136364))
- use fully-qualified collection names for modules
  ([c539cfd](https://github.com/PeterMosmans/ansible-role-customize-gnome/commit/c539cfdcf554a03a71aa0d42ec89fc7350bb20fa))
- use pretty names for tasks
  ([a03a614](https://github.com/PeterMosmans/ansible-role-customize-gnome/commit/a03a614b97c830e394e9411f333245c251823614))
- when looping multiple items, only show name
  ([aa110d6](https://github.com/PeterMosmans/ansible-role-customize-gnome/commit/aa110d61f3325260dc42c083c167cdd49082090f))

### [0.2.1](https://github.com/PeterMosmans/ansible-role-customize-gnome/compare/0.2.0...0.2.1) (2021-10-28)

## [0.2.0](https://github.com/PeterMosmans/ansible-role-customize-gnome/compare/0.1.1...0.2.0) (2021-10-27)

### Features

- **ci:** add dotfiles
  ([d7a634c](https://github.com/PeterMosmans/ansible-role-customize-gnome/commit/d7a634c4761f022eacb0f89f0484bd845c113283))

## 0.3.0 (2021-10-12)

## 0.3.0 (2021-10-12)
