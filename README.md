# Simulador de Semáforo con Infracciones de Tránsito

## Descripción
Este es un simulador interactivo desarrollado en Python utilizando la biblioteca Pygame. El simulador modela un cruce de carreteras con semáforos, autos que se mueven automáticamente, y un sistema de infracciones de tránsito. Los autos pueden cometer infracciones como ignorar luces rojas o exceso de velocidad, las cuales se registran en una base de datos MySQL y se muestran en una tabla dentro de la interfaz gráfica. Además, incluye funcionalidades para pausar/reanudar la simulación, generar reportes en Excel y navegar por los datos de infracciones.

## Características Principales
- **Simulación de Tráfico:** Dos autos (uno rojo horizontal y uno azul vertical) se mueven en un mapa, respetando o ignorando semáforos.
- **Sistema de Infracciones:** Detección automática de infracciones como ignorar luces rojas o exceso de velocidad, con registro en base de datos.
- **Interfaz Gráfica:** Ventana con mapa centrado, semáforos animados, autos, tabla de infracciones y controles interactivos.
- **Base de Datos:** Integración con MySQL para almacenar y recuperar datos de infracciones.
- **Reportes:** Generación de documentos Excel con los datos de infracciones.
- **Controles:** Botones para pausar, reanudar y generar Excel; flechas para navegar en la tabla.
- **Alertas:** Notificaciones temporales en pantalla cuando ocurre una infracción.

## Requisitos del Sistema
- **Python:** Versión 3.6 o superior.
- **Bibliotecas:** 
  - Pygame
  - mysql-connector-python
  - openpyxl
- **Base de Datos:** MySQL con una base de datos llamada `infracciones_db` y una tabla `infracciones` con las columnas: `vehiculo`, `color`, `placa`, `costo_multa`, `descripcion`.
- **Sistema Operativo:** Compatible con Windows, Linux o macOS (probado en Windows 11).

## Instalación
1. **Clona o descarga el proyecto:** Asegúrate de tener los archivos en una carpeta local, por ejemplo, `c:/Users/anton/Downloads/Juego`.
2. **Instala las dependencias:**
   - Abre una terminal y ejecuta:
     ```
     pip install pygame mysql-connector-python openpyxl
     ```
3. **Configura la Base de Datos:**
   - Crea una base de datos MySQL llamada `infracciones_db`.
   - Ejecuta el script SQL proporcionado en `base de datos/infracciones_db.sql` para crear la tabla.
   - Asegúrate de que el usuario `root` tenga acceso (sin contraseña en este ejemplo; ajusta según tu configuración).
4. **Archivos de Imágenes:** Verifica que las carpetas `colores/`, `autos/` y el archivo `mapa.png` estén en el directorio raíz del proyecto.

## Uso
1. **Ejecuta el simulador:**
   - Desde la terminal, navega al directorio del proyecto y ejecuta:
     ```
     python semaforo.py
     ```
2. **Interacción:**
   - **Pausar/Reanudar:** Haz clic en los círculos rojos (pausar) o verdes (reanudar).
   - **Generar Excel:** Haz clic en el círculo azul para crear un archivo `infracciones.xlsx` con los datos actuales.
   - **Navegación en Tabla:** Usa las flechas azules para paginar los datos de infracciones.
   - **Cerrar:** Haz clic en la X de la ventana para salir.
3. **Observa la Simulación:** Los autos se moverán automáticamente, y las infracciones aparecerán en la tabla y como alertas.

## Estructura del Proyecto
- `semaforo.py`: Archivo principal con el código del simulador.
- `mapa.png`: Imagen de fondo del mapa.
- `colores/`: Carpeta con imágenes de los semáforos (rojo.png, verde.png, amarillo.png).
- `autos/`: Carpeta con imágenes de los autos (car.png, bus.png).
- `base de datos/`: Carpeta con el script SQL para la base de datos.
- `reportes-img/`: (Opcional) Imágenes para reportes, no utilizadas en el código actual.
- `infracciones_db.db`: Archivo de base de datos SQLite (si se usa en lugar de MySQL, pero el código usa MySQL).

## Notas Técnicas
- **Rutas de Imágenes:** Las imágenes se cargan de forma relativa al directorio de ejecución. Asegúrate de ejecutar desde la carpeta raíz.
- **Base de Datos:** El código asume una conexión local a MySQL. Modifica las credenciales en las funciones `obtener_datos_infracciones` e `insertar_infraccion` si es necesario.
- **Rendimiento:** La simulación corre a 30 FPS. Los autos generan placas aleatorias al resetearse.
- **Extensiones:** Puede extenderse agregando más autos, semáforos o tipos de infracciones.

## Contribución
Si deseas contribuir, por favor:
1. Haz un fork del repositorio.
2. Crea una rama para tus cambios.
3. Envía un pull request con una descripción detallada.

## Licencia
Este proyecto es de código abierto bajo la Licencia MIT. Puedes usarlo y modificarlo libremente.

## Contacto
Para preguntas o soporte, contacta al desarrollador principal.
