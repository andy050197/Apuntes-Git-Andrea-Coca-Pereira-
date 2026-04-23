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

---

### 3. Repositorio Local (Confirmado)
Acá es cuando una vez que indicamos qué es lo que queremos guardar, 
Git va a crear en base a esos archivos el punto de guardado, 
una vez hecho esto pasa a lo que es el historial.

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
Untracked files: .gitignore" significa que tienes un archivo nuevo (.gitignore) que Git detecta pero aún no rastrea, es decir está en el Directorio de Trabajo en estado Untracked.

![Git Status 1](images/status1.jpeg)


si me equivoque de modificar algo o cambiar, puedo restaurar la ultima version antes de modificar, tambien puedes recuperar archivos borrados que haya estado en seguimiento con:
git restore Readme.md


.gitignore: Es un archivo que le dice a Git qué archivos ignorar, es decir que no los rastree ni los suba a GitHub.