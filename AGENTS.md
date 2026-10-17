# Agent notes

## Reading the mod list at control stage

At **control stage**, read the mod list from `script.active_mods`, not `mods`:

```lua
if script.active_mods["any-planet-start"] then
    -- ...
end
```

The `mods` global only exists during the settings and data stages; it is `nil` at
runtime. Use `mods` in `settings.lua`, `settings-updates.lua`, `data.lua`,
`data-updates.lua`, and `data-final-fixes.lua`, and `script.active_mods` in
`control.lua`.
