# Galaxy Extensions

This repository contains Galaxy webhook extensions that are deployed by the
[Ansible role](https://github.com/galaxyproject/ansible-role-extensions).


## Usage

This repository is automatically cloned and deployed by the
[Ansible role](https://github.com/galaxyproject/ansible-role-extensions).
Updates to extensions in this repository will be picked up on the next role
execution without needing to update the role itself.


## Contributions

Please feel free to submit a PR to improve, fix or contribute an extension!

If you add or change `.j2` templates, please ensure that the
[default variables](https://github.com/galaxyproject/ansible-role-extensions/blob/main/defaults/extensions.yml)
defined in the Ansible role are updated, so that admins can configure extensions
with minimal fuss.

## Structure

>[!INFO]
> Galaxy extensions versions allow for backwards-compatibility between Galaxy
> major versions. The extension version should be the **minimum** supported
> Galaxy version supported (i.e. extension v22.05 can be installed on any
> Galaxy version from 22.05 onwards). You should install the highest available
> version that is below or equal to your Galaxy version (this is done
> automatically by the Ansible role).

Extensions are organized by name and Galaxy version:

```
extensions/
├── extension_name/
│   ├── 22.05/
│   │   ├── config.yml
│   │   ├── script.js
│   │   └── styles.css
│   └── 24.2/
│       ├── config.yml.j2
│       ├── script.js.j2
│       └── styles.css.j2
```

These versions are for galaxy version compatibility only.
Generally speaking, new versions should be made only when an update to Galaxy
has broken and/or required modifications to the extension.


## File Types

- `.j2` files: Jinja2 templates that will be rendered by Ansible
- Non-`.j2` files: Static files copied verbatim
