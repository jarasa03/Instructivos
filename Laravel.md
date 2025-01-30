# Laravel

> 📅 **Fecha:** 30 de enero de 2025  
> 👤 **Autor:** jarasa03  
> 🔢 **Versión:** 1.1  

## Índice  

1. [Iniciar un proyecto](#iniciar-un-proyecto)  
   - [Instalación de Laravel](#instalación-de-laravel)  
   - [Instalación de módulo para APIs](#instalación-de-módulo-para-apis)  
   - [Arrancar el servidor](#arrancar-el-servidor)  
2. [Configurar una base de datos existente](#configurar-una-base-de-datos-existente)  
   - [Para la integración de modelos y migraciones](#para-la-integración-de-modelos-y-migraciones)  
3. [Importar un modelo y crear un controlador](#importar-un-modelo-y-crear-un-controlador)  
4. [Enlaces importantes](#enlaces-importantes)  

## Iniciar un proyecto

### Instalación de Laravel

Para instalar Laravel de forma global en tu sistema, ejecuta el siguiente comando: 

```powershell
composer global require laravel/installer
```

Ahora, navega a la carpeta donde quieres crear el proyecto:

```powershell
cd mi-proyecto
```

Una vez en la carpeta, crea la aplicación (reemplaza ```nombre-aplicacion``` con el nombre que prefieras):

```powershell
laravel new nombre-aplicacion
```

Ahora se navegará a la aplicación que se acaba de crear.

```powershell
cd nombre-aplicacion
```

### Instalación de módulo para apis

Para poder utilizar apis se tendrá que poner el siguiente comando. Es importante estar en la ruta adecuada, se tendrá que estar en la raíz de nuestra aplicación.

```powershell
php artisan install:api
```

### Arrancar el servidor

Para arrancar el servidor y comprobar que está todo hecho correctamente se ejecutará el siguiente comando.

```powershell
php artisan serve
```

Ahora en la url del navegador se pondrá el siguiente enlace, y tendrá que salir la página de inicio de Laravel.

```
http://localhost:8000
```

## Configurar una base de datos existente

Para conectar Laravel a una base de datos ya existente, edita el archivo ```.env``` con un editor de texto como **Visual Studio Code**.

Estas son las líneas importantes a configurar:

```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=nombre_base_datos
DB_USERNAME=usuario
DB_PASSWORD=contraseña
```

### Para la integración de modelos y migraciones

Asegúrate de estar en la raíz del proyecto antes de ejecutar estos comandos.

Instala el paquete **Reliese** para la generación automática de modelos:

```powershell
composer require reliese/laravel --dev
```

Publica la configuración de **Reliese Models**:

```powershell
php artisan vendor:publish --tag=reliese-models

# Limpia la caché de configuración por precaución:
php artisan config:clear
```

Finalmente, genera los modelos automáticamente:

```powershell
php artisan code:models
```

### Importar un modelo y crear un controlador  

Para generar un **controlador** que esté vinculado a un **modelo** y utilice las acciones de un **recurso**, ejecuta el siguiente comando:  

```powershell
php artisan make:controller ProductoController --model=Producto --resource
```

## Enlaces importantes

Consulta la **[documentación oficial de Laravel](https://laravel.com)** para más información.

Información sobre la integración de modelos en el siguiente **[enlace](https://github.com/reliese/laravel)**.