# Dashboard de Restaurante

Panel de control en tiempo real para la gestión de un restaurante, integrado con Google Sheets (pedidos), Google Calendar (reservas) y NocoDB (menú).

## 🌟 Características Principales

- **Pedidos en Tiempo Real**
  - Visualización de los últimos pedidos desde Google Sheets
  - Estado de los pedidos (pendiente, en proceso, completado, cancelado)
  - Actualización automática cada 5 minutos

- **Gestión de Reservas**
  - Vista diaria de reservas desde Google Calendar
  - Muestra hora, nombre del cliente y descripción del evento
  - Filtrado por fecha

- **Menú Digital**
  - Visualización del menú con precios
  - Indicador de disponibilidad de cada plato
  - Actualización en tiempo real desde NocoDB

- **Interfaz Intuitiva**
  - Diseño responsivo que funciona en cualquier dispositivo
  - Interfaz limpia y fácil de usar
  - Actualizaciones automáticas sin necesidad de recargar la página

## 📋 Requisitos Previos

- Python 3.8+
- Cuenta de Google Cloud Platform con las APIs habilitadas
- Cuenta de Google Calendar con eventos de reserva
- Cuenta de NocoDB con la base de datos del menú
- Navegador web moderno (Chrome, Firefox, Safari, Edge)

## Instalación

1. Clona el repositorio:
   ```bash
   git clone [URL_DEL_REPOSITORIO]
   cd dashboard-restaurante
   ```

2. Crea un entorno virtual y actívalo:
   ```bash
   python -m venv venv
   source venv/bin/activate  # En Windows: venv\Scripts\activate
   ```

3. Instala las dependencias:
   ```bash
   pip install -r requirements.txt
   ```

4. Configura las variables de entorno:
   - Copia el archivo `.env.example` a `.env`
   - Completa la información con tus credenciales

## ⚙️ Configuración

### 1. Variables de Entorno
Crea un archivo `.env` en la raíz del proyecto con las siguientes variables:

```env
# Google Sheets (Pedidos)
GOOGLE_SHEETS_CREDENTIALS='{"type": "service_account", ...}'
GOOGLE_SHEETS_ID='your-spreadsheet-id'

# Google Calendar (Reservas)
GOOGLE_CALENDAR_ID='tu_calendario@group.calendar.google.com'

# NocoDB (Menú)
NOCODB_API_KEY='tu_api_key_de_nocodb'
NOCODB_TABLE_ID='your-table-id'
```

### 2. Configuración de APIs

#### Google Cloud Platform
1. Ve a [Google Cloud Console](https://console.cloud.google.com/)
2. Crea un nuevo proyecto o selecciona uno existente
3. Habilita las APIs:
   - Google Sheets API
   - Google Calendar API
4. Crea una cuenta de servicio y descarga el archivo JSON de credenciales
5. Comparte tu hoja de cálculo y calendario con el correo de la cuenta de servicio
6. Copia el contenido del JSON a la variable `GOOGLE_SHEETS_CREDENTIALS`

#### NocoDB
1. Crea una tabla en NocoDB con la estructura del menú
2. Genera un token de API
3. Configura las variables `NOCODB_API_KEY` y `NOCODB_TABLE_ID`

## 🚀 Instalación y Ejecución

1. Clona el repositorio:
   ```bash
   git clone [URL_DEL_REPOSITORIO]
   cd dashboard-restaurante
   ```

2. Crea y activa un entorno virtual:
   ```bash
   python -m venv venv
   source venv/bin/activate  # Windows: venv\Scripts\activate
   ```

3. Instala las dependencias:
   ```bash
   pip install -r requirements.txt
   ```

4. Inicia el servidor:
   ```bash
   python app.py
   ```

5. Abre tu navegador en:
   ```
   http://localhost:5000
   ```

## 📝 Estructura del Proyecto

```
.
├── app.py               # Aplicación principal de Flask
├── requirements.txt     # Dependencias de Python
├── .env                # Variables de entorno (crear manualmente)
├── static/
│   └── js/
│       └── app.js      # Código JavaScript del frontend
└── templates/
    └── index.html      # Plantilla HTML principal
```

## 🔧 Solución de Problemas

- **Error 500 en /api/orders o /api/reservations**:
  - Verifica que las credenciales de Google sean correctas
  - Asegúrate de que la cuenta de servicio tenga los permisos necesarios
  - Revisa los logs del servidor para más detalles

- **No se muestran las reservas**:
  - Verifica que el `GOOGLE_CALENDAR_ID` sea correcto
  - Asegúrate de que la cuenta de servicio tenga acceso al calendario
  - Comprueba que haya eventos en la fecha actual

- **El menú no se carga**:
  - Verifica las credenciales de NocoDB
  - Asegúrate de que la URL de la API sea correcta
  - Comprueba que la tabla tenga datos

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Ver el archivo `LICENSE` para más información.

## 🤝 Contribuir

Las contribuciones son bienvenidas. Por favor, envía un Pull Request o crea un Issue para discutir los cambios propuestos.

## 📧 Contacto

Para soporte o consultas, por favor contacta al equipo de desarrollo.
1. Ve a tu panel de control de NocoDB
2. Genera un token de API
3. Copia el token a la variable `NOCODB_API_KEY` en `.env`

## Uso

1. Inicia el servidor:
   ```bash
   python app.py
   ```

2. Abre tu navegador y ve a:
   ```
   http://localhost:5000
   ```

## Estructura del Proyecto

```
dashboard-restaurante/
├── app.py                 # Aplicación principal de Flask
├── requirements.txt       # Dependencias de Python
├── .env                  # Variables de entorno (no incluido en el control de versiones)
├── .env.example          # Plantilla de variables de entorno
├── static/               # Archivos estáticos
│   └── js/
│       └── app.js        # Código JavaScript del frontend
└── templates/
    └── index.html        # Plantilla HTML principal
```

## Licencia

MIT
