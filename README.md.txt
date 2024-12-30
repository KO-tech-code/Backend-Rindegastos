# Rindegastos Backend

Este es un proyecto backend desarrollado en NestJS para manejar conversiones de moneda, cálculo de días hasta el cumpleaños y concatenación de productos numéricos.

## Requisitos
- Node.js versión 14 o superior.
- npm (incluido con Node.js).
- Clave de API válida para Open Exchange Rates.

## Instalación
1. Clona el repositorio desde GitHub:
   git clone https://github.com/tu_usuario/rindegastos-backend.git
2. Navega al directorio del proyecto:
   cd rindegastos-backend
3. Instala las dependencias necesarias:
   npm install

## Configuración
1. Al ejecutar `npm install`, se generará automáticamente el archivo `.env` en la raíz del proyecto.
   - Este archivo contendrá la configuración base necesaria para que el proyecto funcione.
   - Asegúrate de editar el valor de `OPENEXCHANGE_API_KEY` en el archivo `.env` y reemplazar `AQUI_VA_TU_KEY` con tu clave de API válida de Open Exchange Rates.
2. Verifica que el archivo `.env` fue generado correctamente y que contiene los valores necesarios antes de ejecutar el proyecto.

## Ejecución
1. Inicia el proyecto en modo desarrollo:
   npm run start:dev
2. Para ejecutar en modo producción, compila el proyecto:
   npm run build
   Luego inicia el servidor:
   npm run start:prod

## Endpoints
### Ejercicio 1: Conversión de Moneda
- **Descripción:** Convierte una cantidad de una moneda a otra.
- **Método:** GET
- **Endpoint:** /conversion/getConvertedAmount
- **Parámetros:**
  - `from`: Moneda de origen (por ejemplo, USD).
  - `to`: Moneda de destino (por ejemplo, CLP).
  - `amount`: Cantidad a convertir.
  - `date` (opcional): Fecha específica para la conversión.
- **Ejemplo:**
  curl -X GET "http://localhost:3000/conversion/getConvertedAmount?from=USD&to=CLP&amount=15000"

### Ejercicio 2: Días Hasta el Cumpleaños
- **Descripción:** Calcula cuántos días faltan para el cumpleaños de una persona.
- **Método:** GET
- **Endpoint:** /birthday/getDaysUntilMyBirthday
- **Parámetros:**
  - `birthdate`: Fecha de nacimiento en formato YYYY-MM-DD.
- **Ejemplo:**
  curl -X GET "http://localhost:3000/birthday/getDaysUntilMyBirthday?birthdate=1990-07-15"

- **Registrar Cumpleaños:**
  - **Método:** POST
  - **Endpoint:** /birthday/register
  - **Cuerpo:** { "name": "Juan", "birthdate": "1990-07-15" }
  - **Ejemplo:**
    curl -X POST "http://localhost:3000/birthday/register" -H "Content-Type: application/json" -d '{"name":"Juan","birthdate":"1990-07-15"}'

### Ejercicio 3: Producto Concatenado
- **Descripción:** Calcula el producto concatenado de dos números.
- **Método:** GET
- **Endpoint:** /numbers/getTheNumber
- **Parámetros:**
  - `first`: Primer número.
  - `second`: Segundo número.
- **Ejemplo:**
  curl -X GET "http://localhost:3000/numbers/getTheNumber?first=192&second=3"

## Pruebas
1. Asegúrate de que el servidor esté en ejecución antes de realizar las pruebas.
2. Usa herramientas como `curl` o Postman para enviar solicitudes a los endpoints descritos.
3. Verifica las respuestas esperadas para cada prueba.

## Notas Finales
- Este proyecto utiliza NestJS y sigue las mejores prácticas de arquitectura modular.
- Asegúrate de proteger tu clave de API y no compartirla públicamente.
- Si tienes problemas, consulta la documentación oficial de NestJS y Open Exchange Rates.
