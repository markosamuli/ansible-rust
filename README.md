# markosamuli.rust

This role downloads and runs the [rustup-init.sh] script
from [rustup.rs] to install Rust.

It uses the Ansible built-in `get_url` module for downloading
the script instead of cURL.

Do not run this role as root as it's intended for installing
rust for a single user only.

[rustup-init.sh]: https://static.rust-lang.org/rustup/rustup-init.sh
[rustup.rs]: https://rustup.rs/

## Configuration

`rustup` will modify your shell profile files, but I prefer to keep
my configuration in the rc files and manage with my [dotfiles].

To avoid `rustup-init` from modifying path during install:

```yaml
rust_modify_path: false
```

[dotfiles]: https://github.com/markosamuli/dotfiles

## Example

```yaml
- name: Install Rust
  hosts: localhost
  become: false
  roles:
  - role: markosamuli.rust
    tags: rust

```

## License

* [MIT](LICENSE)

## Author Information

* [@markosamuli](https://github.com/markosamuli)
