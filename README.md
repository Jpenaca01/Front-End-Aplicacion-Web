# 🍳 Sabores de Colombia

> Aplicación web de recetas tradicionales colombianas. Desarrollada con HTML, CSS y JavaScript puro.

![Sabores de Colombia](https://img.shields.io/badge/Sabores-de%20Colombia-CE1126?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHRleHQgeT0iMjAiIGZvbnQtc2l6ZT0iMjAiPvCfjoM8L3RleHQ+PC9zdmc+)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

## 📋 Descripción

**Sabores de Colombia** es una aplicación web que presenta recetas tradicionales colombianas de todas las regiones del país. El proyecto fue construido como ejercicio de desarrollo frontend con énfasis en:

- Renderizado dinámico desde fuente JSON
- Gestión de estado del lado del cliente
- Experiencia de usuario fluida y accesible
- Diseño responsivo editorial

## ✨ Funcionalidades

| Funcionalidad | Descripción |
|---|---|
| 🍽️ **Recetas desde JSON** | 12 recetas renderizadas dinámicamente desde `data.js` |
| 🔍 **Búsqueda en tiempo real** | Filtra recetas por nombre, región o categoría mientras escribes |
| 🗂️ **Filtros** | Botones de filtro por región (Andina, Caribe, Pacífico) y categoría |
| ❤️ **Favoritos** | Guarda y elimina recetas favoritas con persistencia en `localStorage` |
| 📖 **Modal de detalle** | Vista completa con ingredientes y pasos de preparación |
| 📬 **Formulario validado** | Formulario de "Enviar receta" con validación en tiempo real |
| 📱 **Responsivo** | Diseño adaptado a móvil, tablet y escritorio |
| 🍞 **Toast notifications** | Confirmaciones visuales de acciones del usuario |

## 📁 Estructura del Proyecto

```
sabores-de-colombia/
│
├── index.html        # Estructura principal de la app
├── styles.css        # Estilos completos con variables CSS
├── data.js           # Fuente de datos JSON con las recetas
├── app.js            # Lógica de la aplicación
└── README.md         # Documentación
```

## 🗂️ Estructura del JSON de Recetas

Cada receta en `data.js` sigue este esquema:

```json
{
  "id": 1,
  "nombre": "Bandeja Paisa",
  "region": "Andina",
  "categoria": "Plato Fuerte",
  "emoji": "🍲",
  "tiempo": "90 min",
  "dificultad": "Media",
  "porciones": 4,
  "rating": 4.9,
  "imagen": "URL de imagen",
  "descripcion": "Descripción del plato",
  "ingredientes": ["ingrediente 1", "ingrediente 2"],
  "pasos": ["paso 1", "paso 2"]
}
```

## 🚀 Cómo usar

1. Clona el repositorio:
   ```bash
   git clone https://github.com/tu-usuario/sabores-de-colombia.git
   ```

2. Abre `index.html` en tu navegador (no requiere servidor):
   ```bash
   cd sabores-de-colombia
   open index.html   # macOS
   # o
   start index.html  # Windows
   ```

3. ¡Explora las recetas!

## 🧩 Arquitectura

### Renderizado Dinámico
Las recetas se generan completamente en JavaScript a partir del array `RECIPES_DATA` en `data.js`. La función `createCard(recipe)` construye el HTML de cada tarjeta dinámicamente.

### Sistema de Favoritos
Los favoritos se almacenan en `localStorage` como un array de IDs. El `Set` de JavaScript garantiza unicidad y O(1) para búsquedas.

```javascript
const state = {
  favorites: new Set(JSON.parse(localStorage.getItem('sabores_favs') || '[]')),
};
```

### Validación del Formulario
Cada campo tiene sus propias reglas definidas en el objeto `validations`. La validación se ejecuta en el evento `blur` (validación mientras el usuario completa el formulario) y en el `submit` (validación completa antes de enviar).

```javascript
const validations = {
  nombre:    { validate: v => v.trim().length >= 2, msg: '...' },
  email:     { validate: v => /regex/.test(v), msg: '...' },
  // ...
};
```

## 🎨 Diseño

- **Paleta**: Basada en la bandera colombiana (amarillo, azul, rojo)
- **Tipografía**: Playfair Display (display) + DM Sans (cuerpo) + Bebas Neue (accent)
- **Tema**: Editorial / orgánico, inspirado en la riqueza cultural colombiana

## 📱 Responsividad

| Breakpoint | Layout |
|---|---|
| > 900px | Layout completo de escritorio |
| 600–900px | Menú hamburguesa, columnas reducidas |
| < 600px | Columna única, espaciado compacto |

## 🛠️ Tecnologías

- **HTML5** semántico (nav, section, article, form)
- **CSS3** con variables, Grid, Flexbox, animaciones y media queries
- **JavaScript ES6+** (clases, módulos, async/await, Set, localStorage)
- **Google Fonts** para tipografía

## 📄 Licencia

MIT License — libre para usar, modificar y distribuir.

---

Hecho con ❤️ y sazón 🇨🇴
