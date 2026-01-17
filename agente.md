# 🤖 Documentación para Agentes de IA - Proyecto "Elite Galleries"

Este documento sirve como guía para cualquier modelo de IA que continúe el desarrollo de este proyecto. Aquí se detallan la estructura, el sistema de diseño, y las convenciones utilizadas.

## 📁 Estructura del Proyecto

El proyecto es un **Catálogo Digital para Eventos (Venue)**.

```
/
├── index.html            # Landing page (Netflix-style selector)
├── revolution.html       # Venue 1: Revolution Party (Tema Familiar/Cálido)
├── diamond.html          # Venue 2: Diamond at Doral (Tema Lujo/Cristal)
├── booking.html          # Página de reservas con calendario persistente (localStorage)
├── galeria.html          # Galería multimedia (Grid + Carruseles snap-x)
├── style.css             # Hoja de estilos principal (Tailwind + Custom CSS)
├── script.js             # Lógica principal (Menú móvil, interacciones)
├── embed.js              # Script para embeds de Instagram (desarrollo propio para evitar bloqueos)
├── /galeria/             # Carpeta de assets multimedia organizada por categorías
    ├── /kendall/         # Assets estandarizados: kendall_video_XX.mp4, kendall_img_XX.jpeg
    ├── /doral/           # Assets estandarizados: doral_video_XX.mp4, doral_img_XX.jpeg
    ├── /diamond/         # Assets estandarizados: diamond_video_XX.mp4, diamond_img_XX.jpeg
    ├── /mesas_quesos/    # Assets estandarizados: mesa_img_XX.jpeg
    ├── /videos_party/    # Assets estandarizados: party_video_XX.mp4
    ├── /corporate/       # Assets estandarizados: corp_video_XX.mp4
```

## 🎨 Design System: "Quiet Luxury"

El diseño se basa en una estética minimalista, elegante y editorial.

*   **Tipografías:**
    *   *Cinzel* (Google Font): Para encabezados y títulos de lujo.
    *   *Montserrat* (Google Font): Para cuerpo de texto y legibilidad.
    *   *Great Vibes* (Google Font): Para toques caligráficos sutiles.
*   **Colores:**
    *   **Cream/Gold:** Usado en temas base y acentos cálidos.
    *   **Charcoal/Black:** Fondos profundos y texto principal.
    *   **Diamond Blue:** Tonalidades cian/azul hielo específicas para `diamond.html` y `.diamond-theme`.
*   **Componentes Clave:**
    *   **Tarjetas con Efecto Glass:** Fondos semitransparentes con `backdrop-filter: blur`.
    *   **Botones Magnéticos:** Botones con `transition-all` suave y bordes sutiles.
    *   **Grid Multimedia:** En `galeria.html`, usamos CSS Grid con tarjetas de altura fija (500px).
    *   **Carruseles Snap-X:** Contenedores con `overflow-x-auto snap-x snap-mandatory` para deslizar contenido multimedia dentro de una misma tarjeta.

## 🛠️ Aspectos Técnicos Importantes

1.  **Tailwind CSS:** Se carga vía CDN (versión 3.x script tag). No hay proceso de compilación `npm build`.
    *   *Nota:* Muchas clases personalizadas se definen en `style.css` usando `@apply` o reglas CSS directas para anular estilos base si es necesario.
2.  **Multitargeting (Temas):**
    *   `revolution.html` usa clases base y colores cálidos.
    *   `diamond.html` y sus componentes hijos usan a menudo una clase envolvente o específica (e.g., `.diamond-theme`) para cambiar la paleta a tonos fríos.
3.  **Galería (Assets):**
    *   **Nomenclatura Estandarizada:** Todos los archivos en `/galeria/` siguen el patrón `[categoria]_[tipo]_[numero].[ext]`.
        *   Ejemplo: `kendall_video_01.mp4`, `doral_img_03.jpeg`.
    *   **Posters de Video:** **SIEMPRE** se deben definir atributos `poster="..."` en las etiquetas `<video>` para evitar cuadros blancos en iOS/Safari si el autoplay falla.
4.  **Booking (Reservas):**
    *   Usa `localStorage` para simular una base de datos.
    *   El formulario valida disponibilidad básica (horas ocupadas se guardan en el navegador del usuario).

## ⚠️ Instrucciones para el Futuro

*   **Al agregar imágenes:** Renombrar SIEMPRE antes de enlazar. Usar secuencia numérica.
*   **Al editar CSS:** Verificar la responsividad móvil (`@media (max-width: 480px)`). El menú móvil es crítico.
*   **Integridad de Enlaces:** Mantener rutas relativas. Si se mueve la carpeta raíz, todo debería seguir funcionando.

---
*Generado por Agente Antigravity - 2026*
