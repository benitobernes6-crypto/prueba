# Sistema de Supervisión Vial

Aplicación web progresiva (PWA) diseñada para el registro de asistencia en campo, reporte de transitabilidad y captura de evidencias georreferenciadas en proyectos de mantenimiento carretero. 

## 🚧 El Problema

El sistema resuelve dificultades operativas específicas durante el relevamiento de datos en las rutas:
* La intermitencia o ausencia total de señal de internet en diversos sectores de la red vial impide la transmisión de datos en el momento del hallazgo.
* El registro de presencia del personal (microempresas) se levanta mediante planillas físicas, lo que retrasa la disponibilidad de esta información en la oficina central.
* La consolidación de las eventualidades de campo y la transcripción de las planillas a un reporte digital final consume hasta 40 minutos diarios por supervisor.
* La necesidad de reportar el estado de transitabilidad al instante (identificando cortes por derrumbes o bloqueos) para agilizar el despliegue de maquinaria.
* La exigencia normativa de adjuntar fotografías fiables e inalterables que respalden el estado real de la vía.

## 💡 La Solución

Para resolver estas necesidades puntuales, la plataforma implementa los siguientes flujos operativos:
* Arquitectura móvil *offline-first* (almacenamiento local) que retiene los registros de presencia y reportes de incidentes en el dispositivo cuando no hay conectividad.
* Motor de sincronización en segundo plano que transmite los datos retenidos a la base de datos central en cuanto detecta una conexión de red estable.
* Módulo de asistencia presencial que captura firmas digitalizadas directamente en la pantalla, sustituyendo el uso de papel.
* Herramienta de captura fotográfica que incrusta (estampa) irrevocablemente las coordenadas GPS, la fecha y la hora sobre la imagen.
* Función de ubicación que calcula y asocia de forma automática el kilometraje específico del tramo vial basándose en las coordenadas del dispositivo.
* Selector de severidad vial para tipificar el nivel de riesgo en tres estados: "Transita", "Transita con precaución" y "No transita".
* Tablero de alertas en la interfaz administrativa que destaca inmediatamente los puntos marcados como no transitables.
* Automatización del reporte diario, que unifica la asistencia y los incidentes levantados por los supervisores, reduciendo el tiempo de redacción a un máximo de 5 minutos.

## 🛠️ Stack Tecnológico

* **Frontend:** Vue 3, Vite, Tailwind CSS, `vite-plugin-pwa` (para soporte Offline e IndexedDB).
* **Backend:** .NET 9 (Web API), Arquitectura en capas.
* **Base de Datos:** SQL Server , Entity Framework Core 9 (Code-First).
* **Seguridad:** Autenticación mediante JSON Web Tokens (JWT), encriptación de contraseñas con BCrypt.

---

## ⚙️ Requisitos Previos

Asegúrate de tener instalados los siguientes componentes en tu entorno de desarrollo:

* [.NET SDK 9.0](https://dotnet.microsoft.com/download/dotnet/9.0) o superior.
* [Node.js 20.x](https://nodejs.org/) o superior y npm.
* SQL Server 

