# BLOXITY Classic — Remake visual 2016–2017

Esta entrega reconstruye la interfaz de BLOXITY con una dirección visual inspirada en los portales de juegos de 2016–2017: barra azul compacta, navegación lateral, fondo gris, paneles blancos, pestañas, tarjetas densas y botones clásicos. Es una implementación original; no incluye código propietario ni recursos oficiales de Roblox.

## Archivos
- `index.html`: estructura completa de las páginas.
- `style.css`: diseño clásico y adaptación a móviles.
- `app.js`: navegación, búsqueda, autenticación, perfil, catálogo, inventario, recompensas y guardado de colores del avatar.
- `config.js`: URL y clave pública (publishable) del proyecto Supabase existente.

## Instalar en GitHub
1. Descarga y extrae el ZIP.
2. Abre el repositorio `Guest-commits/bloxity-classic`.
3. Reemplaza los archivos `index.html`, `style.css`, `app.js`, `config.js` y `README.md` por los de este ZIP.
4. Haz commit en la rama `main`.
5. Si GitHub Pages está configurado para `main` y `/ (root)`, espera a que termine el despliegue.

## Funciones conectadas
- Supabase Auth: registro e inicio de sesión por correo/contraseña.
- Perfil y balances desde `profiles`.
- Catálogo desde `catalog_items`.
- Inventario desde `user_inventory`.
- Compras mediante RPC `purchase_catalog_item`.
- Recompensa diaria Tix mediante `claim_tix_daily_reward`.
- Recompensa Builders Club mediante `claim_builders_club_daily_reward`.
- Visibilidad del enlace de administración comprobando `bloxity_admins`.

## Limitaciones importantes
- Las tarjetas de juegos son demostraciones visuales: no ejecutan juegos ni tienen servidores multijugador.
- Mensajes, amigos, grupos, clasificaciones y publicación de juegos muestran estados informativos; aún no tienen backend.
- El avatar es una previsualización R6 dibujada con CSS y guarda únicamente colores en el perfil; no carga mallas 3D ni equipamiento real.
- Builders Club se muestra visualmente; la compra/selección de membresía no está activada.
- El área de administración es solo un marcador de posición. Ocultar un enlace no es una barrera de seguridad: cualquier herramienta administrativa futura debe autorizarse en el servidor/RPC y con RLS.
- No se incluye migración ni se modifica la base de datos existente.

## Seguridad
`config.js` conserva únicamente la clave pública publishable del proyecto, que está diseñada para usarse en el navegador. Nunca pongas una clave `service_role`, una secret key ni una contraseña de base de datos en archivos públicos. Mantén RLS habilitado y verifica las políticas de cada tabla y función antes de publicar para otros usuarios.
