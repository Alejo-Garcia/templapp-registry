# templapp registry

**Generated — do not edit.** Every file here is built from
[templapp](https://github.com/Alejo-Garcia/templapp) by `scripts/build-registry.mjs` and
force-pushed on each change. Open a PR against templapp, not against this repo.

templapp's design system — [React Native
Reusables](https://reactnativereusables.com) on NativeWind, plus the components
templapp adds — served as a [shadcn registry](https://ui.shadcn.com/docs/registry):

```bash
npx shadcn@latest add https://alejo-garcia.github.io/templapp-registry/r/date-picker.json
```

That one command also installs `calendar`, `bottom-sheet`, `icon`, `text`,
`utils` and `theme`: each item's `registryDependencies` are absolute URLs into
this registry, so the whole tree resolves with no configuration on your side.

| Type | Items |
| --- | --- |
| `registry:component` | 5 |
| `registry:hook` | 1 |
| `registry:lib` | 3 |
| `registry:theme` | 1 |
| `registry:ui` | 51 |

Browse them at **<https://alejo-garcia.github.io/templapp-registry/>**. The index of everything, without file
contents, is at [`r/registry.json`](https://alejo-garcia.github.io/templapp-registry/r/registry.json).

## Two things that bite

**Native versions.** The shadcn CLI writes dependencies into `package.json` as
caret ranges, even though this registry emits them pinned to the versions
templapp has verified against Expo SDK 56. Run `npx expo install --fix` after
adding anything — a caret range will resolve ahead of your SDK matrix and break
the native build.

**Dark mode.** The CLI writes the dark tokens under `.dark`. NativeWind toggles
the scheme on the root element and needs `.dark:root`. Left as `.dark`, dark
mode silently does nothing.
