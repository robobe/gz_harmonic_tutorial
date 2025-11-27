# Gazebo harmonic tutorial

```
gz sim -r empty.sdf -v 4
```

```bash
gz service -s /world/empty/create --reqtype gz.msgs.EntityFactory \
  --reptype gz.msgs.Boolean --timeout 3000 \
  --req 'sdf_filename: "/workspace/models/rrbot.sdf", name: "my_model"'
```

```
gz model --list
```

```bash
gz service -s /world/empty/remove \
  --reqtype gz.msgs.Entity \
  --reptype gz.msgs.Boolean \
  --req 'name: "my_model", type: MODEL'

```

## visual material

```xml
<material>
                    <ambient>0.0 1 0.0 1</ambient>
                    <diffuse>0.0 1 0.0 1</diffuse>
                    <specular>0.0 1 0.0 1</specular>
                </material>
```

- R G B A
- ambient: how the object appears in global light
- diffuse: color when direct light hit the surface
- specular: reflection how the object look when shiny highlight hit it