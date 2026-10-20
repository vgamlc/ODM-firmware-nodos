# ODM-firmware-nodos

Binarios publicados de los **nodos ESP-NOW** de OpenDoorMobile (ODM): Shelly 1 Mini Gen3 y Atom + ATOM HUB Switch.
Solo binarios: el código está en un repositorio privado.

El Atom de la puerta (ODM 1.7.1 o posterior) los usa para actualizar sus nodos a distancia:

- `actualizar` en el Terminal de la app lee [`nodos.txt`](nodos.txt) y dice qué nodo tiene una versión nueva.
- `actualizar N` manda al nodo N, cifrado con su clave, la WiFi del garaje, la versión y la huella SHA-256.
  El nodo descarga `<carpeta>/<versión>.bin` de aquí por HTTPS, comprueba la huella, se graba y reinicia. Si la
  versión nueva no habla con su Atom en 5 minutos, vuelve sola a la anterior.

Estos binarios no contienen claves ni datos de ninguna instalación: sin la clave que cada Atom genera para sus
nodos no sirven para abrir nada.

| Carpeta | Placa |
|---|---|
| `shelly1mini/` | Shelly 1 Mini Gen3 (ESP32-C3) |
| `atomhub/` | M5Atom Lite + ATOM HUB Switch |

No se edita a mano: lo escribe `scripts/publicar_ota.py` del proyecto del nodo.
