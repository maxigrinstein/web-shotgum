# ShotGum - Guía de Deployment

## 🚀 Deployment en Vercel

### Método 1: Vercel CLI (Recomendado)

```bash
# Instalar Vercel CLI
npm i -g vercel

# Navegar al directorio del proyecto
cd "c:\Users\maxig\OneDrive\Escritorio\tesis facu"

# Inicializar y deployar
vercel

# Para deploys posteriores
vercel --prod
```

### Método 2: GitHub + Vercel

1. Crear repositorio en GitHub
2. Subir archivos: `git add .` && `git commit -m "Initial commit"` && `git push`
3. Conectar en vercel.com → "Add New Project" → "Import Git Repository"
4. Configurar:
   - **Build Command**: `echo "No build required"`
   - **Output Directory**: `.`
   - **Install Command**: `npm install`

---

## 🌐 Deployment en Netlify

### Método 1: Netlify CLI

```bash
# Instalar Netlify CLI
npm install -g netlify-cli

# Navegar al directorio
cd "c:\Users\maxig\OneDrive\Escritorio\tesis facu"

# Deploy
netlify deploy

# Deploy a producción
netlify deploy --prod
```

### Método 2: Drag & Drop

1. Ir a netlify.com → "Sites" → "Add new site" → "Deploy manually"
2. Arrastrar toda la carpeta del proyecto
3. ¡Listo!

### Método 3: GitHub + Netlify

1. Subir a GitHub (igual que Vercel)
2. En netlify.com → "Add new site" → "Import from Git"
3. Configurar:
   - **Build Command**: `echo "No build required"`
   - **Publish Directory**: `.`

---

## 📁 Estructura Final

```
shotgum-landing/
├── index.html              # Página principal (redirecciona)
├── shotgum-landing.html     # Landing principal
├── shotgum-juegos.html      # Página de juegos
├── logo.png                 # Logo de ShotGum
├── *.jpg                    # Imágenes del carrusel
├── package.json             # Metadatos del proyecto
├── vercel.json              # Configuración de Vercel
├── netlify.toml             # Configuración de Netlify
├── README.md                # Documentación
├── .gitignore               # Archivos a ignorar
└── DEPLOYMENT.md            # Esta guía
```

---

## 🔗 URLs después del deployment

### Vercel

- **Producción**: `https://tu-proyecto.vercel.app`
- **Rutas amigables**:
  - `/` → Landing principal
  - `/juegos` → Página de juegos
  - `/landing` → Landing principal

### Netlify

- **Producción**: `https://tu-proyecto.netlify.app`
- **Mismas rutas amigables**

---

## ✅ Checklist Pre-Deployment

- [ ] Todas las imágenes están en la carpeta
- [ ] Los enlaces de WhatsApp funcionan
- [ ] El Google Maps se carga correctamente
- [ ] Las rutas internas funcionan (`shotgum-juegos.html`)
- [ ] La paleta de colores está aplicada
- [ ] El sitio es responsive
- [ ] No hay errores en la consola

---

## 🛠️ Testing Local

```bash
# Servidor local con live-reload
npm run dev

# Servidor local simple
npm start

# Servidor con Python (alternativa)
python -m http.server 8000
```

---

## 🔧 Troubleshooting

### Error: "Page not found"

- Verificar que `index.html` existe en la raíz
- Revisar configuración en `vercel.json` o `netlify.toml`

### Imágenes no cargan

- Verificar que las rutas son relativas: `./logo.png` no `/logo.png`
- Comprobar que todos los archivos están subidos

### WhatsApp no funciona

- Verificar número de teléfono en el botón flotante
- Formato correcto: `https://wa.me/5491124710013`

---

## 📞 Soporte

Si tienes problemas con el deployment, revisa:

1. La consola del navegador para errores
2. Los logs de build en Vercel/Netlify
3. Que todas las rutas sean relativas
4. Que no falten archivos

¡Éxito con tu deployment! 🚀
