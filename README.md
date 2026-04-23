## Clase 2 - 21 de abril 2026

### Diagrama del flujo de Git
![Flujo de Git](images/flujo-git.jpeg)

Git tiene 3 formas de gestionar cada archivo:
---

### 1. Modificado (Directorio de trabajo)
Es el lugar donde implementamos nuestro código o trabajo, 
acá simplemente Git observa tus archivos, los cuales los cataloga en:

- **Untracked:** Sin seguimiento, es cuando un archivo es nuevo, 
por lo cual Git aún no los conoce.
- **Modified:** Son archivos que Git ya conoce pero que modificaste 
(cambiar nombre y eliminar el archivo), entonces los pone como un track, 
esto se refiere a que es algo nuevo que no tiene en su historial.


---

### 2. Stage Area
Es el área de espera, es la zona donde ponemos los archivos que deseamos guardar.

Permite seleccionar qué archivos modificados se incluirán en el siguiente commit y cuáles no.

Para agregar un archivo al stage area:
```bash
git add <archivo>   # Agrega un archivo específico
git add .           # Agrega todos los archivos
```

Para sacar un archivo del stage area:
```bash
git restore --staged <archivo>
```
Si no colocas `--staged`, los cambios 
se **borran completamente** y vuelve a la última versión del commit
---

### 3. Repositorio Local (Confirmado)
Acá es cuando una vez que indicamos qué es lo que queremos guardar, 
Git va a crear en base a esos archivos el punto de guardado, 
una vez hecho esto pasa a lo que es el historial.
Es la última fase, aquí le decimos a Git que cree el punto de guardado para que todos los cambios en staged pasen a ser parte del historial.

```bash
git commit -m "mensaje"
```

Para deshacer el último commit:
```bash
git reset --soft HEAD~1
```
---

### Comando para ver en qué fase está cada archivo:
```bash
git status
```
---
working tree clean significa que todos los archivos de mi directorio de trabajo están en el mismo estado que el último commit.

![Git Status 0](images/status0.jpeg)

---
Este git status muestra que:
Untracked files: .gitignore" significa que tengo un archivo nuevo (.gitignore) que Git detecta pero aún no rastrea, es decir está en el Directorio de Trabajo en estado Untracked.

![Git Status 1](images/status1.jpeg)

---
Este git status muestra:
Changes not staged for commit: modified: README.md" significa que el archivo README.md fue modificado pero aún no está en el Stage Area, es decir está en el Directorio de Trabajo en estado Modified.

![Git Status 2](images/status2.jpeg)

---

`.gitignore` es un archivo donde puedes listar los archivos o carpetas que **no quieres** que Git rastree ni suba a GitHub.

![Git Status 3](images/status3.jpeg)

![Git Status 3.1](images/status3.1.jpeg)

![Git Status 3.2](images/status3.2.jpeg)

---
Si me equivoqué de modificar algo o cambiar, puedo restaurar la última versión antes de modificar, también puedes recuperar archivos borrados que hayan estado en seguimiento con:

```bash
git restore Nombre del archivo
```
---
## Buenas Prácticas en los Commits

### ¿Cada cuánto debo hacer un commit?
Es mejor hacer commits pequeños y frecuentes que uno con todo, 
a esto se le llama **commits atómicos**, donde cada commit representa 
un único cambio lógico y completo.

### ¿Cómo escribir un buen mensaje de commit?

- Usa **verbos imperativos:**

| Verbo | Significado |
|---|---|
| `Add` | Se añade un nuevo archivo |
| `Change` | Se modifica un archivo existente |
| `Fix` | Se arregla un bug |
| `Remove` | Se elimina un archivo |

- Usa **máximo 50 caracteres**
- **No uses punto final** ni puntos suspensivos
- Usa un **prefijo** para hacerlos más semánticos:

```bash
git commit -m "feat: Add new search feature"
```

### Prefijos:

| Prefijo | Uso |
|---|---|
| `feat` | Nueva característica |
| `fix` | Bug que afecta al usuario |
| `docs` | Cambios en documentación |
| `style` | Cambios de formato |
| `refactor` | Refactorización de código |
| `test` | Tests |
| `perf` | Mejoras de rendimiento |
| `build` | Cambios en el sistema de build |
| `ci` | Integración continua |

