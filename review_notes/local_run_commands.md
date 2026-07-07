# Local Run Commands

Run from the original `xiaobei-core` root:

```powershell
python scripts\validate_1013r_r200e_frontend_visible_contamination_guard.py
```

Compact summary:

```powershell
@'
import json, subprocess, sys
cmd=[sys.executable, r"scripts\validate_1013r_r200e_frontend_visible_contamination_guard.py"]
p=subprocess.run(cmd, text=True, capture_output=True, encoding="utf-8", errors="replace", timeout=180)
print("returncode", p.returncode)
data=json.loads(p.stdout)
print(json.dumps({
  "status": data.get("status"),
  "failed": [k for k,v in data.get("checks",{}).items() if not v],
  "summary": data.get("summary"),
  "outputs": data.get("outputs"),
}, ensure_ascii=False, indent=2))
'@ | python -
```

