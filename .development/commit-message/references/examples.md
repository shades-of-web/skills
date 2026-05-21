# Examples

Use these examples as formatting references for the subject/body style and
heredoc-based commit command.

```bash
git commit -m "$(cat <<'EOF'
fix: correct regex escaping for JetBrains IDE bundle identifiers

Fixed incorrect regex escaping in Karabiner config for JetBrains IDE
application bundle identifiers. The previous `^com\.jetbrains\\..*$`
pattern had backslash escaping issues that prevented the regex from
matching correctly. Now uses `^com\\.jetbrains\\..*$` so JetBrains
IDE products are properly recognized in the Karabiner key mapping
exception list.
EOF
)"
```

```bash
git commit -m "$(cat <<'EOF'
feat(karabiner): add JetBrains IDE exception to PC-Style mappings

Add JetBrains IDE products to the Karabiner key mapping exceptions
so that built-in IDE shortcuts work correctly (especially Copy/Paste
and Reload).

- Add exception for PC-Style Copy/Paste/Cut (Ctrl+C/V/X)
- Add exception for PC-Style Reload (Ctrl+R, F5)
- Fix indentation inconsistency (tabs to spaces)
EOF
)"
```
