# Contributing

This is a personal SWAT capability catalog maintained by [@Dutchman333](https://github.com/Dutchman333). Contributions in the form of issues, PRs, and discussions are welcome.

## Adding a new skill or squad

The structure mirrors the [official SWAT marketplace](https://github.com/LangSensei/swat-marketplace). See its [CONTRIBUTING.md](https://github.com/LangSensei/swat-marketplace/blob/main/CONTRIBUTING.md) for the canonical schema.

### Skills

```
skills/
  my-skill/
    SKILL.md         # YAML frontmatter (name, version, description, dependencies) + documentation
    CHANGELOG.md     # Version history
    ...              # Optional implementation files
```

### Squads

```
squads/
  my-squad/
    MANIFEST.md      # YAML frontmatter (name, version, description, dependencies) + overview
    CHANGELOG.md     # Version history
```

### Manifest rules

- `name` must match the folder name (kebab-case)
- `version` must follow semver (`"X.Y.Z"`)
- `dependencies.skills` must list every skill the squad invokes (including upstream skills like `scientific-method`, `debrief`, `sop`)
- `dependencies.mcps` lists MCP server names if any are required

## Submission

1. Fork this repo
2. Branch (`feat/add-my-skill`)
3. Test locally by symlinking into `~/.swat/skills/` or `~/.swat/squads/`
4. Open a PR with a brief description of the use case

## Considerations for upstream contribution

If a skill or squad from this repo would benefit the broader SWAT ecosystem, please also consider opening a PR against the [official marketplace](https://github.com/LangSensei/swat-marketplace). Once merged upstream, the corresponding entry here will be removed.
