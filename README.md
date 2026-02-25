# NMini Robot Arm

This package provides NMini robot arm description.

## Create xmf file for mujoco

```bash
$ python - <<'PY'
import mujoco
from pathlib import Path
urdf = Path("/PATH_TO_URDF/nmini.urdf").resolve()
out = urdf.with_suffix(".xml")
model = mujoco.MjModel.from_xml_path(str(urdf))
mujoco.mj_saveLastXML(str(out), model)
print("saved:", out)
PY
saved: /PATH_TO_URDF/nmini.xml
```