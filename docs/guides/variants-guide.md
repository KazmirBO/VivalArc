# Legacy Variant Notes

`vivalarc.css` in the repository root is the only actively maintained version of VivalArc.

## Auto-Hide Tab Bar (formerly `autotab` variant)

The auto-hiding tab bar is now built into the root stylesheet as an optional toggle — no separate file needed.

To enable it, open `vivalarc.css` and change the variable in the `:root` block:

```css
--enable-autohide-tabbar: 1;   /* 0 = off (default), 1 = on */
```

You can also adjust the collapsed width:

```css
--autohide-tabbar-size: 32px;
```

Restart Vivaldi after saving.

## Archived Variants

The old `variants/autotab/` and `variants/compact/` folders have been moved to `archive/v7.7/`. They target Vivaldi 7.7 and are no longer updated.

## Recommendation

For new installs, select `VivalArc/` in Vivaldi Settings > Appearance > Custom UI Modifications.

If you were using a legacy variant and encounter breakage after a Vivaldi update, switch to the root version and use the built-in toggles described above.
