# ansible-role-xcode

An Ansible role for [Xcode][]. This installs a specific version of Xcode and
all of it's dependencies.

## Requirements

You should place a `dmg` or `xip` in the `files/` directory of your playbook
for this role to pick it up and transfer it over.

This allows us to install a specific version (good for CI stability) and avoids
the role dealing with authenticating with the Apple Developer Portal. [You can
get Xcode from the ADC Download section][xcode_download].

## Role Variables

Two things are configurable:

```yaml
xcode_version: 8.2
```

is the version we're installing. This is important so that we do the correct
thing for each version of Xcode.

```yaml
xcode_src: Xcode_8.2.xip
```

is the file we're copying over (located in a `files/` directory).

## Dependencies

None.

## Example Playbook


```yaml
- hosts: servers
  roles:
     - role: nickcharlton.xcode
       xcode_version: 8.2
       xcode_src: Xcode_8.2.xip
```

## License

MIT

## Author Information

Copyright (c) Nick Charlton 2016.

[xcode]: https://developer.apple.com/xcode/
[xcode_download]: https://developer.apple.com/download/more/
