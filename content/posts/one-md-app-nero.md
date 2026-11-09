---
title: "Nero: Simple But Powerful MD App"
date: 2026-11-09
---

I've tried a lot of Markdown apps. Some are too heavy, some are too minimal, 
and most want to lock your notes inside a proprietary database or a cloud account you didn't ask for. 
That's why I built Nero, a local-first Markdown app that gives you a CLI, 
a terminal UI, and a desktop GUI—all backed by ordinary `.md` files on your disk. 
No account. No vendor lock-in. Just your notes, the way you wrote them.
The repo is at [GitHub](https://github.com/saeidaliei/nero) and here is the [docs](https://saeidaliei.github.io/nero/).

This post is a short tour of what Nero does and how to start using it, 
with the essential commands you'll need day to day.

## Why Nero?

Nero is built around a simple principle: Markdown files are the source of truth . 
Everything else—search indexes, caches, GUI state—is disposable and rebuildable. 
That means you can open your notes in any editor, sync them with Git, or back them up with `rsync` 
to cloud and never worry about losing access.

The app ships three interfaces that share the same Rust core :

- **CLI** — fast, scriptable commands for creating, finding, and managing notes.
- **TUI** — a keyboard-driven terminal interface for focused writing and navigation.
- **GUI** — a desktop app for when you want a more visual experience.

## Key Features

- **Plain Markdown with frontmatter**: supports tasks, images, code blocks, and math .
- **Wiki-style linking**: `[[Wiki Links]]`, backlinks, aliases, and heading fragments .
- **Full-text search**: powered by a rebuildable local SQLite index .
- **Daily notes and due dates**: no separate task database needed .
- **Portable workflows**: optional Git versioning, local backups, encryption, and `rclone` remotes .
- **Browser-based Preview**: built-in `browse` will preview the markdown in the browser.

## Getting Started (CLI/TUI)

The fastest way to try Nero is through the CLI/TUI. 
You'll need Git and Rust (via [rustup](https://rustup.rs/)) .

Install from the repository:

```bash
git clone https://github.com/saeidaliei/nero.git
cd nero
cargo install --path crates/nero --force
```

Make sure `~/.cargo/bin` is on your `PATH` .

### Quick Start: Your First Workspace

A workspace is just a folder of Markdown files. 
Nero remembers your default workspace, so you can run commands from anywhere .

```bash
nero workspace create personal
nero workspace use personal
nero new "Welcome to Nero"
nero list
nero list --long   # include frontmatter metadata
nero config show   # inspect paths, workspace, keys, remotes
nero tui           # open the terminal interface
```

## Essential Commands

Here are the commands you'll reach for most often :

| Command | What it does |
| --- | --- |
| `nero new "Title"` | Create a Markdown note with default frontmatter |
| `nero list` | Show a table with stable note IDs and timestamps |
| `nero list -l` | Include frontmatter metadata such as tags, type, due date, and priority |
| `nero open 3` | Print note ID 3 (titles and paths also work) |
| `nero edit 3` | Edit note ID 3 in `$EDITOR` or `$VISUAL` |
| `nero delete 3` / `nero rm 3` | Permanently delete note ID 3 |
| `nero find "query"` | Search note content |
| `nero backlinks "Title"` | Find notes linking to a note |
| `nero today` | Open today's note and list due/overdue notes |
| `nero tui` | Open the terminal interface |
| `nero reindex` | Rebuild/update the local search index |
| `nero doctor` | Check workspace health |

You can also select a different workspace for a single command with `-w` :

```bash
nero workspace create research
nero -w research new "Paper notes"
nero -w personal list
nero workspace list
```

## Markdown and Metadata

Nero stores notes as regular Markdown files. New notes include a `title` and `date`; 
daily notes also include `type: daily`. 
Add a `due` date when you want a note to appear in `nero today` on or after that date .

Here's an example note:

```markdown
---
title: Fourier Transform
date: 2026-10-14
due: 2026-10-20
tags: math, signal-processing
status: in-progress
type: research
---

# Fourier Transform

For a function $f(t)$:
$$
F(\omega) = \int_{-\infty}^{\infty} f(t)e^{-i\omega t}\,dt
$$

- [ ] Review the derivation

See also [[Signal Processing]].
```

Frontmatter parsing is intentionally lightweight—Nero supports simple 
`key: value` lines, not the complete YAML specification .

## What about Backup and Encryption?

Nero keeps your live workspace plain and interoperable—Git, external editors, 
and shell tools still work—while backup artifacts can be encrypted with age.

### Workspace backups

Create a portable ZIP with a SHA-256 manifest; disposable `.nero/` and `.git/` are excluded.

```bash
nero backup create
nero backup verify "$ARCHIVE"
nero backup restore "$ARCHIVE" ~/recovered-notes
```

To encrypt, generate an age identity first:

```bash
nero key generate
nero backup create --encrypt
nero backup restore backup.age ~/recovered-notes
```

Keep the private identity safe—encrypted workspace backups cannot be decrypted without it.

### Full-home backup

For moving machines, create a passphrase-encrypted `.zip.age` containing `$NERO_HOME` (default `~/.nero`), 
including config, keys, workspaces, assets, and `.git/` history—but excluding old backups and disposable indexes.

```bash
nero backup home create
nero backup home verify "$ARCHIVE"
nero backup home restore /path/to/nero-home-backup.zip.age
```

Nero never saves the passphrase. If you lose it, the archive cannot be recovered.

### Remote storage with rclone

Nero treats cloud storage as transport, not part of the note format. 
Configure an rclone remote yourself, then add it to a workspace:

```bash
nero storage add mega mega:nero-backups/personal --encrypt
nero storage test mega
nero backup push mega
nero backup list mega
nero backup pull mega nero-backup-1234567890.age ~/recovered-notes
```

Encrypted profiles upload temporary age-encrypted backups. 
Nero uses `rclone copyto --checksum --immutable`, never `rclone sync`, 
so a misconfigured remote cannot delete unrelated data.

**In short:** live Markdown stays plain; backups use age; full-home archives use a passphrase; 
manifests verify integrity; restore refuses non-empty destinations and unsafe paths.

## The Bottom Line

Nero is not trying to be the biggest note-taking app. It's trying to be the one that gets out of your way. 
Your notes stay as Markdown files. The interfaces are just different windows into the same plain-text source.

If you've been looking for a local-first Markdown app that respects your files 
but also gives you extensive options for backups and encryption, give Nero a try!

