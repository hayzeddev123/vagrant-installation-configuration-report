# Screenshots

All screenshots used in this project are stored in the **root** of the repository and are **embedded directly** in the main [README.md](README.md) using standard Markdown image syntax.

This makes the documentation a self-contained step-by-step tutorial that displays the images when viewed on GitHub (or any Markdown renderer that supports relative image paths).

## Available Screenshots

### 1. Vagrantfile + Destroy Terminal Session
**Location in README:** Section 5 – Destroying the Virtual Machine

![Vagrantfile with ubuntu/jammy64 + terminal showing vagrant command not found inside guest, exit, and vagrant destroy on the host](Screenshot%202026-08-05%20171236.png)

**File:** `Screenshot 2026-08-05 171236.png`

**What it shows:**
- The `Vagrantfile` with `config.vm.box = "ubuntu/jammy64"`
- Inside the Ubuntu guest: `vagrant halt` → `vagrant: command not found` (expected behaviour)
- `exit` from the guest
- `vagrant destroy` run from the Windows host (PowerShell)

### 2. Official HashiCorp Vagrant Documentation Page
**Location in README:** Section 6 – Official Vagrant Documentation Reference

![HashiCorp Developer Vagrant landing page – Development Environments Made Easy](Screenshot%202026-08-05%20171559.png)

**File:** `Screenshot 2026-08-05 171559.png`

**What it shows:**
- Official Vagrant documentation home page on developer.hashicorp.com
- Navigation links (Install, Intro, Tutorials, Documentation, Vagrant Cloud)
- “What is Vagrant?” section and key concepts

---

## Markdown Image Reference Syntax (Quick Guide)

To display an image in Markdown:

```markdown
![Alt text that describes the image](relative/path/to/image.jpg)
```

- Start with `!`
- Put a short, useful description in square brackets `[]` (this is the alt text)
- Put the path to the image in parentheses `()`
- Use relative paths from the Markdown file location
- Encode spaces in filenames as `%20`

Example:

```markdown
![Vagrantfile and terminal session](Screenshot%202026-08-05%20171236.png)
```
