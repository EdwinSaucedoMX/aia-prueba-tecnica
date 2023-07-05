# **Prueba Técnica AIA**

## Instalación
---
Para ejecutar el proyecto es necesario tener instalado node en la computadora, una vez instalado, ejecutar el comando:

``` node
npm install
```

Posteriormente es necesario ejecutar:
``` node
npm run dev
```
Si se quiere elaborar la versión para producción ejecutar: 
``` node
npm run build
```

## Generalidades
---
El proyecto se encuentra estructurado con la configuración básica de Vuejs, es decir la estructura de las carpetas y jerarquía se encuentra en la documentación oficial de Vuejs, únicamente la carpeta añadida de sass, dirigida hacia los estilos del proyecto.

Para la realización de la prueba se utilizaron las siguientes tecnologías:
* VueJS
* SASS
* Vite


## Componentes
---

## Card

Propiedades | Tipo | Default
------------|------|--------
name        |string|"Nombre no registrado"
description |string|"Sin descripción"
location    |string|"Ubicación no registrada"
totalArea   |number| -1
img         |string| "/no-image"
terrace     |number| -1
rooms       |number| -1
isAvailable |boolean| false

## Instrucciones Adicionales
---
El componente Card tiene un evento de hover, cada 5 seg actualiza la información mostrada.
