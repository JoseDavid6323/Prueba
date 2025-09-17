<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Mi Proyecto - Presentación</title>

  <!-- Bootstrap CDN -->
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet">

  <style>
    :root{
      --rojo: #c8102e;
      --negro: #111;
      --gris-claro: #f6f6f6;
    }

    body {
      background: linear-gradient(180deg, #fff 0%, var(--gris-claro) 100%);
      color: #222;
      font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      padding-top: 40px;
    }

    .hero {
      background: linear-gradient(90deg, rgba(200,16,46,0.05), rgba(17,17,17,0.03));
      border-left: 6px solid var(--rojo);
      padding: 28px;
      border-radius: 12px;
      box-shadow: 0 6px 18px rgba(17,17,17,0.06);
    }

    .brand {
      display: inline-block;
      padding: 8px 14px;
      background: var(--negro);
      color: white;
      border-radius: 999px;
      font-weight: 700;
      letter-spacing: .6px;
      margin-right: 8px;
    }

    .hero h1 {
      color: var(--negro);
      margin-bottom: 0;
    }

    .card-project {
      border: 1px solid rgba(0,0,0,0.06);
      border-radius: 12px;
    }

    pre.cmd {
      background: #0d0d0f;
      color: #e6e6e6;
      padding: 14px;
      border-radius: 8px;
      overflow-x: auto;
      font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, "Roboto Mono", monospace;
      font-size: 14px;
    }

    footer small { color: #666; }
    .btn-red {
      background: var(--rojo);
      color: white;
      border: none;
    }
    .btn-red:hover { opacity: .9; }
  </style>
</head>
<body>

  <main class="container">
    <!-- Hero -->
    <section class="hero mb-4">
      <div class="d-flex align-items-center mb-2">
        <span class="brand">PROY</span>
        <h1 class="h4 mb-0">Presentación de mi proyecto</h1>
      </div>
      <p class="mb-0 text-muted">Archivo demo en HTML para mostrar tu proyecto. Tiene un ejemplo de README, vistas previas y los comandos Git listos para pegar.</p>
    </section>

    <div class="row g-3">
      <!-- Left: Vista previa y descripción -->
      <div class="col-md-7">
        <div class="card card-project p-3">
          <div class="d-flex justify-content-between align-items-start">
            <div>
              <h2 class="h5">Mi aplicación</h2>
              <p class="text-muted mb-2">Breve descripción: Este es un ejemplo de página para presentar tu proyecto. Coloca aquí lo que hace, tecnologías usadas y cómo correrlo localmente.</p>
              <ul>
                <li><strong>Tecnologías:</strong> HTML, CSS, Bootstrap</li>
                <li><strong>Estado:</strong> Demo</li>
                <li><strong>Autor:</strong> Tu nombre</li>
              </ul>
            </div>
            <img src="https://via.placeholder.com/110x70.png?text=Preview" alt="preview" class="rounded" />
          </div>

          <hr>

          <h3 class="h6">Cómo correrlo localmente</h3>
          <ol>
            <li>Abrir el archivo <code>index.html</code> en tu navegador.</li>
            <li>Si tu proyecto tiene backend coloca las instrucciones específicas aquí.</li>
            <li>Si usas PHP, ejecuta con un servidor local (XAMPP, WAMP, o php -S).</li>
          </ol>
        </div>
      </div>

      <!-- Right: Comandos Git -->
      <div class="col-md-5">
        <div class="card p-3">
          <h4 class="h6 mb-2">Comandos Git (copiar y pegar)</h4>
          <p class="small text-muted mb-2">Estos son los pasos básicos para subir tu proyecto a GitHub desde la terminal:</p>
          <pre class="cmd" id="git-commands">
# entra a la carpeta del proyecto
cd ruta/de/tu/proyecto

# inicializa git (solo la primera vez)
git init

# añade todos los archivos
git add .

# primer commit
git commit -m "Primer commit - subir proyecto a GitHub"

# enlazar con tu repositorio (reemplaza con tu URL)
git remote add origin https://github.com/tuusuario/mi-proyecto.git

# renombrar rama principal y subir
git branch -M main
git push -u origin main
          </pre>

          <div class="d-flex gap-2 mt-3">
            <button class="btn btn-sm btn-outline-dark" id="copyBtn">Copiar comandos</button>
            <a href="#" class="btn btn-sm btn-red" id="openRepoBtn">Abrir README</a>
          </div>
        </div>

        <div class="card mt-3 p-3">
          <h5 class="h6">Archivo README (ejemplo)</h5>
          <p class="small text-muted mb-2">Incluye un README en tu repositorio conteniendo:</p>
          <ul class="small">
            <li>Descripción del proyecto</li>
            <li>Cómo instalar y ejecutar</li>
            <li>Capturas / demo</li>
            <li>Licencia y autor</li>
          </ul>
        </div>
      </div>
    </div>

    <!-- Footer -->
    <footer class="mt-4 text-center">
      <small>¿Quieres que personalice este HTML con tu nombre y capturas reales? Dime el nombre del proyecto y una breve descripción y lo adapto ahora mismo.</small>
    </footer>
  </main>

  <!-- Bootstrap JS (opcional) -->
  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js"></script>

  <script>
    // Copiar comandos al portapapeles
    document.getElementById('copyBtn').addEventListener('click', async () => {
      const text = document.getElementById('git-commands').innerText;
      try {
        await navigator.clipboard.writeText(text);
        document.getElementById('copyBtn').innerText = 'Copiado ✓';
        setTimeout(() => document.getElementById('copyBtn').innerText = 'Copiar comandos', 1800);
      } catch (err) {
        alert('No se pudo copiar automáticamente. Selecciona y copia manualmente.');
      }
    });

    // Acción demostrativa para README
    document.getElementById('openRepoBtn').addEventListener('click', (e) => {
      e.preventDefault();
      alert('Reemplaza este botón con el enlace a tu repositorio GitHub una vez creado.');
    });
  </script>
</body>
</html>
