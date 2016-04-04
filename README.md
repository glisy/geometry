GlisyGeometry
=============

## Installation

```sh
$ clib install glisy/geometry --save
```

## Usage

```c
#include <string.h>
#include <glisy/geometry.h>
#include <glisy/math.h>
#include <glisy/vao.h>

int
main (void) {
  GlisyVAOAttribute vPosition;
  GlisyGeometry geometry;
  const vec3 vertices[] = {
    vec2(+1.0, -1.0),
    vec2(+0.0, -1.0),
    vec2(-1.0, -1.0)
  };

  memset(&vPosition, 0, sizeof(vPosition));
  vPosition.buffer.data = (void *) vertices;
  vPosition.buffer.type = GL_FLOAT;
  vPosition.buffer.size = size;
  vPosition.buffer.usage = GL_STATIC_DRAW;
  vPosition.buffer.dimension = 3;

  glisyGeometryInit(&geometry);
  glisyGeometryAttr(&geometry, "vPosition", &vPosition);
  glisyGeometryBind(&geometry, 0); // current active program
  return 0;
}
```

## License

MIT
