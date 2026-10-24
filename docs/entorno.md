# Documentación de mi entorno de desarrollo · Práctica 2

**Nombre y apellidos:** Crystal Saldívar, Raquel Alcalde
**URL de mi repositorio:**https://github.com/saanc756-del/entorno-daw-crystal-saldivar

> Rellena cada apartado a medida que avanzas. Donde pone «pega aquí», copia el texto
> de la terminal (no hace falta captura). Escribe con tus palabras: no se valora la longitud,
> sino que se note que entiendes lo que has hecho.

---

## 1. Instalación de entornos (CE 2.a)

### 1.1. Entorno vacío (paso 3)

Resultado de `java -version` y `node -v` **antes** de instalar nada:

```
pega aquí
bash: java: command not found
bash: node: command not found
```

¿Por qué crees que aparece ese mensaje? porque todavia no hay java ni node en este entorno, instalarlos es el siguiente paso 
> 

### 1.2. Después de la 1.ª reconstrucción (paso 5)

Resultado de `java -version`, `node -v` y `jupyter lab --version` **después**:

```
pega aquí
openjdk version "27" 2026-09-15
OpenJDK Runtime Environment Temurin-27+35 (build 27+35)
OpenJDK 64-Bit Server VM Temurin-27+35 (build 27+35, mixed mode, sharing)
v24.22.1
```

¿Qué líneas nuevas han aparecido en `devcontainer.json`? Explica con tus palabras qué hace cada una: se añadio la fila de pyton porque antes solo estaban java y node, cada linea supongo que define la version de cada uno porque aparecia una opcion de actualizar la version de node y al aceptarlo, esa linea cambiaba de 2 a 2.1.1

> 

### 1.3. Comparativa de los dos IDE (paso 6)

|                                         | Editor de GitHub Codespaces | JupyterLab             |
|-----------------------------------------|-----------------------------|------------------------|
| ¿Libre o propietario?                   |Parcialmente libre. El editor|                        |
|                                         |es una versión web de VS Code|                        | 
|                                         |de código abierto, pero      |         Libre          |
|                                         |el servicio Codespaces en    |                        |
|                                         |sí es propietario.           |                        |
|-----------------------------------------|-----------------------------|------------------------|
| Licencia / empresa o comunidad          |Servicio de GitHub, propiedad|Licencia BSD de 3       |
|                                         |de Microsoft y el editor     |cláusulas.Lo desarrolla |
|                                         |base usa licencia MIT.       |la comunidad bajo       |
|                                         |                             |Project Jupyter.        |
|-----------------------------------------|-----------------------------|------------------------|
| ¿Tiene coste? ¿Con qué límites?         |Gratis hasta 120 core-hours y|Gratis; solo pagas el   |
|                                         |15 GB al mes; luego, de pago |servidor si no lo usas  |
|                                         |                             |en local                |
|-----------------------------------------|-----------------------------|------------------------|
| ¿Se puede usar fuera de GitHub?         |No como servicio: está ligado|Sí. Se instala en local,|
|                                         |a repositorios de GitHub y a |en servidores propios o |
|                                         |tu cuenta. Sí puedes abrir el|en nubes como Google    |
|                                         |mismo proyecto en VS Code de |Colab, Binder o         |
|                                         |escritorio con dev containers|cualquier repositorio o |
|                                         |                             |sin ninguno.            |
|-----------------------------------------|-----------------------------|------------------------|
| Lo que más me ha gustado                |Es muy fácil de usar, tiene  |                        |
|                                         |terminal y extensiones       |                        |
|                                         |integrados como visual y     |                        |
|                                         |facilita el trabajo para     |                        |
|                                         |todo el equipo               |                        |
|-----------------------------------------|-----------------------------|------------------------|
| Lo que menos me ha gustado              |El límite de horas mensual y |                        |
|                                         |que hay que acordarse de     |                        |
|                                         |parar o borrar los codespaces|                        |
|                                         |para no gastar cuota         |                        |
|-----------------------------------------|-----------------------------|------------------------|
| ¿Para qué tipo de trabajo lo elegiría?  |Proyectos colaborativos o    |                        |
|                                         | contribuir a un repositorio |                        |
|                                         | sin configurar el equipo    |                        |
|-----------------------------------------|-----------------------------|------------------------|

---

## 2. Módulos y extensiones (CE 2.b)

| Extensión               | ¿Para qué sirve? | ¿Qué cambió al instalarla? | ¿La mantengo? ¿Por qué? |
|-------------------------|------------------|----------------------------|-------------------------|
| Extension Pack for Java |Es un paquete que |Me apareció la opción de    |Si, porque de lo         |
|                         |instala varias    |Run | Debug para  ejecutar  |contrario no podria      |
|                         |extensiones que se|las facturas                |ejecutar ningun codigo de|
|                         |necesitan para.   |                            |java                     |
|                         |programar en Java |                            |                         |
|-------------------------|------------------|----------------------------|-------------------------|
| Code Spell Checker      |Revisa la         |Se marcaban como mal        |No, porque da más        | 
|                         |ortografía en el  |las palabras en             |problemas en vez de      | 
|                         |código y subraya  |español                     |ayudar, si funcionará en | 
|                         |las palabras mal  |                            |español lo mantendría    | 
|                         |escritas          |                            |                         |
|-------------------------|------------------|----------------------------|-------------------------|

¿Qué diferencia hay entre instalar una extensión **solo desde el panel** y añadirla **también a `devcontainer.json`**?Al instalarlas solo desde el panel las extensiones están solo en mi codespace pero al añadirlas también
al devcointainer ya forman parte del entorno de todo el equipo

> 

---

## 3. Personalización y automatización (CE 2.c)

- **Tema visual elegido** (paso 10) y por qué:Modern purple theme dark, porque me gusta el morado pero tambíen que siga oscuro el tema
- **Ajuste del proyecto** (paso 10). ¿Qué archivo se ha creado y qué contiene? Se creo el archivo settings.json y contiene el ajuste que hice en el area de trabajo

```
pega aquí el contenido de .vscode/settings.json
    "editor.formatOnSave": true

```

- **Atajo de teclado** (paso 11). ¿Qué acción, qué combinación y para qué te sirve? Rebuild Container, la combinación de ctrl + option + r, sirve para reconstruir el entorno
- **Snippet** (paso 12). ¿Qué escribes y qué aparece? escribo cabecera y aparece el archivo, mi nombre como autor, fecha y módulo
- **Automatización al crear el entorno** (paso 14). ¿Qué hace `postCreateCommand` y qué archivos/carpetas han aparecido después de reconstruir? descarga las dependencias que necesita el archivo de factura automaticamente al crear el entorno y aparecieron la carpeta de node_modules y el archivo package-lock.json. 
- **Tareas** (paso 13). ¿Cuántas tareas hay en `tasks.json` y qué hace cada una? 3 tareas, la de Java crea la carpeta build/java, compila Factura.java allí, empaqueta las clases en un archivo factura.jar diciendo que factura es la clase principal y por último ejecuta ese JAR, la de typescript utiliza npm run build para compilar el proyecto TypeScript a JavaScript y después npm start para arrancar la aplicación, la ultima que es la de build completo lo único que hace es ejecutar las dos tareas anteriores en orden, primero la de Java y luego la de TypeScript, además de ser la tarea de compilación por defecto

¿Qué parte de toda esta configuración es **personal** (solo para ti) y qué parte es **del proyecto** (la recibe cualquiera que abra el repositorio)? el tema y atajos del teclado son personales, los snippets, tareas, ajustes del editor y automatizaciones son del proyecto

> 

---

## 4. Ejecutables de diferentes lenguajes en el mismo entorno (CE 2.e)

Salida completa de la tarea **Build completo** (paso 15):

```
pega aquí
 *  Ejecutando tarea: mkdir -p build/java && javac -d build/java src/java/Factura.java && jar --create --file build/factura.jar --main-class Factura -C build/java . && java -jar build/factura.jar 

=== FACTURA generada con Java 27 ===
Dominio web anual              12.00 EUR
Alojamiento web                59.90 EUR
Logotipo corporativo          150.00 EUR
-----------------------------------------
Base imponible                221.90 EUR
IVA (21 %)                     46.60 EUR
TOTAL                         268.50 EUR
 *  Las tareas reutilizarán el terminal, presione cualquier tecla para cerrarlo. 

 *  Ejecutando tarea: npm run build && npm start 


> plantilla-entorno-daw@1.0.0 build
> tsc


> plantilla-entorno-daw@1.0.0 start
> node dist/factura.js

=== FACTURA generada con Node.js v24.22.1 ===
Dominio web anual              12.00 EUR
Alojamiento web                59.90 EUR
Logotipo corporativo          150.00 EUR
-----------------------------------------
Base imponible                221.90 EUR
IVA (21 %)                     46.60 EUR
TOTAL                         268.50 EUR
 *  Las tareas reutilizarán el terminal, presione cualquier tecla para cerrarlo. 

```

| Lenguaje   | Archivo fuente          | Herramienta que lo traduce | Archivo generado  | Cómo se ejecuta  |
|------------|-------------------------|----------------------------|-------------------|------------------|
| Java       | `src/java/Factura.java` |           javac            |build/java/Factura |java -jar build   |
|            |                         |                            |.class, empaquetado|/factura.jar      |
|            |                         |                            |en factura.jar     |                  |
|------------|-------------------------|----------------------------|-------------------|------------------|
| TypeScript | `src/ts/factura.ts`     |            tsc             |dist/factura.js    |node dist/factura |
|            |                         |                            |                   |.js, por npm start|
|------------|-------------------------|----------------------------|-------------------|------------------|

**Opcional:** ¿has podido ejecutar los mismos archivos desde JupyterLab (paso 19)? ¿Por qué funciona en los dos IDE sin instalar nada más?

> 

---

## 5. Sistema de actualizaciones (CE 2.d)


| Elemento               |¿Quién lo actualiza? | Modo (automático / manual / ninguno)| Qué he configurado yo |
|------------------------|---------------------|-------------------------------------|-----------------------|
| El editor de Codespaces|       GitHub        |             Automático              |          Nada         |
|------------------------|---------------------|-------------------------------------|-----------------------|
| Las extensiones        |Yo, desde los ajustes|             Manual                  |Que las extensiones no |
|                        |                     |                                     |se actualizarán en     |
|                        |                     |                                     |automático para no     |
|                        |                     |                                     |tener sorpresas en     |
|                        |                     |                                     |examenes               |
|------------------------|---------------------|-------------------------------------|-----------------------|
| Java                   |Yo, en la receta     |             Manual                  |Fije la versión a 21   |
|                        |                     |                                     |para que no cambie sola|
|                        |                     |                                     |al reconstruir         |
|------------------------|---------------------|-------------------------------------|-----------------------|
| Node.js                |Yo, en la receta, la |   Manual (feature fijada en 2.1.1)  |Fije la feature, no la |
|                        |feature              |                                     |versión como en java   |
|------------------------|---------------------|-------------------------------------|-----------------------|
| Dependencias npm       |Yo, en package.json  |             Manual                  |Revisé con npm outdated|
|(lodash, typescript…)   |y package-lock.json  |                                     |y npm audit, actualicé |
|                        |                     |                                     |lodash a 4.18.1 y      |
|                        |                     |                                     |ejecuté npm install    |
|------------------------|---------------------|-------------------------------------|-----------------------|

Versión de Java **antes** (paso 5) y **después** (paso 18):

```
pega aquí
**antes**
openjdk version "27" 2026-09-15
**despues**
openjdk version "21" 2023-09-19 LTS
```

Resultado de `npm outdated` (paso 17):

```
pega aquí
Package         Current    Wanted   Latest  Location                    Depended by
@types/lodash  4.14.202  4.14.202  4.17.27  node_modules/@types/lodash  entorno-daw-crystal-saldivar
@types/node    20.11.30  20.11.30   26.6.5  node_modules/@types/node    entorno-daw-crystal-saldivar
lodash          4.17.20   4.17.20   4.18.1  node_modules/lodash         entorno-daw-crystal-saldivar
typescript        5.4.5     5.4.5    7.0.2  node_modules/typescript     entorno-daw-crystal-saldivar
```

Resultado de `npm audit` **antes** de actualizar lodash (solo el resumen final):

```
pega aquí
1 high severity vulnerability

To address all issues, run:
  npm audit fix --force
```

Resultado de `npm audit` **después**:

```
pega aquí
  found 0 vulnerabilities
```

**Mi política de actualizaciones**: si este entorno lo usara un equipo de 5 personas durante todo el curso, ¿qué dejarías en automático y qué fijarías a mano? Justifícalo. 
Dejaría en automático lo que no afecta a la compilación, como el editor de codespaces que ya lo gestiona github, las alertas de seguridad y las extensiones si no se esta en epoca de examenes o entregas porque las actualizaciones son buenas mientras las tengas supervisadas, por eso mismo fijaría a mano una lista de extensiones fijas para que el equipo ya trabaje con las mismas, las otras se revisarían e instalarían si todos estan de acuerdo y avisados. También fijaria las versiones exactas de java y node para que todos tengan la misma aunque lo reconstruyan en meses diferentes, las dependencias npm con package-lock.json para que las 5 personas tengan las mismas versiones de loadash y typescript y las features e imagen base porque con una versión exacta el entorno de hoy se conserva igual.
> 

---

## 6. Incidencias

Anota cualquier problema que hayas tenido y cómo lo resolviste (también si usaste un fragmento completo).
----
En el paso 4, al momento de querer abrir el codespace me aparecia: El comando "Codespaces: Add Dev Container Configuration Files..." ha dado lugar a un error
command 'github.codespaces.configureDevContainerCommand' not found, le pregunte a claude que significaba ese error y me dijo que desde el navegador de Safari a veces las extensiones no cargan del todo, por lo que use el fragmento completo del apartado fragmentos/paso-04-devcontainer.json,
---
En el paso 7 no me aparecía la opcion de  Run | Debug por la extension de java, lo resolvi reconstruyendo 2 veces

> 

## 7. Reflexión final

¿Qué ventaja tiene describir el entorno «como código» frente a instalar cada programa a mano en tu ordenador? Piensa en un equipo con Mac y Windows.
Como dice en el contexto de la práctica, para no pasarse días instalando programas y peleándose con versiones. Asi cualquier persona con cualquier ordenador que tenga navegador tendrá el mismo entorno en un rato y se acabará el famoso "en mi equipo funciona" del que hablamos en el tema.

> 
