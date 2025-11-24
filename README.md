# Galaxy Extensions

This repository contains Galaxy webhook extensions that are deployed by the [extensions-ansible-role](https://github.com/usegalaxy-au/extensions-ansible-role).

## Structure

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

## File Types

- `.j2` files: Jinja2 templates that will be rendered by Ansible
- Non-`.j2` files: Static files copied as-is

## Available Extensions

- `citation_needed`: Citation reminder extension
- `iframe`: Iframe embedding extension
- `lab_switcher`: Lab environment switcher
- `phdcomics`: PhD Comics integration
- `search`: Search functionality
- `tips`: Tips and tricks display
- `tool_list`: Tool listing extension
- `toolmsg`: Tool messaging extension
- `tour_generator`: Interactive tour generator

## Usage

This repository is automatically cloned and deployed by the extensions-ansible-role. Updates to extensions in this repository will be picked up on the next role execution without needing to update the role itself.
