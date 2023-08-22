<a href="https://dot.net/architecture">
   <img src="https://github.com/dotnet-architecture/eShopOnContainers/raw/dev/img/eshop_logo.png" alt="eShop logo" title="eShopOnContainers" align="right" height="60" />
</a>

# Prueba Tecnica Maquina de estados

En esta documentacion se resuleve la prueba tecnica para el cargo de Arquitecto TI, de igual manera se propone una alternativa a una libreria y se explican las ventajas.

## Arquitectura de Contexto

El siguiente diagrama nos muestra un contexto general del problema y su solucion, contemplando tres actores principal, las aplicaciones que consumen la maquina de estados, la maquina de estados y su persistencia

![](img/diagrama-de-contexto.png)

## Arquitectura de Contenedor
El siguiente diagrama nos ilustra la propuesta que se compone de una libreria para la implementacion de la maquina de estados y un microservicio de configuracion para hacer dinamica la parametrizacion de estados y sus  acciones

![](img/diagrama-de-contenedor.png)

## Arquitectura de Datos

El siguiente diagrama ilustra la persistencia necesaria para manejar la maquina de estados finitos.

![](img/diagrama-de-datos.png)

- Entidad: Es la lista de clases y/o tipos de objectos posibles.
- Estados: Es la lista de estados definidos por entidad.
- TipoEstados: Esta tabla nos sirve para indicar si el estado es el inicial, por defecto, final o algun otro tipo que no visualizemos actualmente.
- EstadosPosibles: Es la lista de estados posible por estado, es decir de donde a donde puedo pasar.
- TipoDisparador: Esta tabla puede ser util para no solo ejecutar metodos sino tambien, llamar un webservice, lanzar un evento.Etc
- Reglas: Aqui se configura el estado inicial y el estado final.
- EstadosObjectos: Aqui se persiste el estado del objecto.
- HistoricosEstados: Aqui se guardan los estados por los que ha pasado el obejcto.


## Modelo de Clases
El siguiente diagrama de aplicacion ilustra el micro servicio para configurar estados por entidad, sus reglas y sus posibles estados.

![](img/ms-configuration.png)

| Image | Status | Image | Status |
| ------------- | ------------- | ------------- | ------------- |
| Web Status |  [![Web Status](https://github.com/dotnet-architecture/eShopOnContainers/workflows/webstatus/badge.svg?branch=dev)](https://github.com/dotnet-architecture/eShopOnContainers/actions?query=workflow%3Awebstatus) | Shopping Aggregator (Web) | [![Web Shopping Aggregator](https://github.com/dotnet-architecture/eShopOnContainers/workflows/webshoppingagg/badge.svg)](https://github.com/dotnet-architecture/eShopOnContainers/actions?query=workflow%3Awebshoppingagg) |
| Basket API | [![Basket API](https://github.com/dotnet-architecture/eShopOnContainers/workflows/basket-api/badge.svg?branch=dev)](https://github.com/dotnet-architecture/eShopOnContainers/actions?query=workflow%3Abasket-api) | Shopping Aggregator (Mobile) | [![Mobile Shopping Aggregator](https://github.com/dotnet-architecture/eShopOnContainers/workflows/mobileshoppingagg/badge.svg?branch=dev)](https://github.com/dotnet-architecture/eShopOnContainers/actions?query=workflow%3Amobileshoppingagg) |
| Catalog API | [![Catalog API](https://github.com/dotnet-architecture/eShopOnContainers/workflows/catalog-api/badge.svg)](https://github.com/dotnet-architecture/eShopOnContainers/actions?query=workflow%3Acatalog-api) | Web Client (MVC) | [![WebMVC Client](https://github.com/dotnet-architecture/eShopOnContainers/workflows/webmvc/badge.svg?branch=dev)](https://github.com/dotnet-architecture/eShopOnContainers/actions?query=workflow%3Awebmvc) |
|Identity API | [![Identity API](https://github.com/dotnet-architecture/eShopOnContainers/workflows/identity-api/badge.svg?branch=dev)](https://github.com/dotnet-architecture/eShopOnContainers/actions?query=workflow%3Aidentity-api) | Web Client (SPA) | [![WebSPA Client](https://github.com/dotnet-architecture/eShopOnContainers/workflows/webspa/badge.svg?branch=dev)](https://github.com/dotnet-architecture/eShopOnContainers/actions?query=workflow%3Awebspa) |
| Ordering API | [![Ordering API](https://github.com/dotnet-architecture/eShopOnContainers/workflows/ordering-api/badge.svg?branch=dev)](https://github.com/dotnet-architecture/eShopOnContainers/actions?query=workflow%3Aordering-api) | Webhooks Client | [![Webhooks demo client](https://github.com/dotnet-architecture/eShopOnContainers/workflows/webhooks-client/badge.svg)](https://github.com/dotnet-architecture/eShopOnContainers/actions?query=workflow%3Awebhooks-client) |
| Payment API | [![Payment API](https://github.com/dotnet-architecture/eShopOnContainers/workflows/payment-api/badge.svg?branch=dev)](https://github.com/dotnet-architecture/eShopOnContainers/actions?query=workflow%3Apayment-api) | Ordering SignalR | [![Ordering SignalR](https://github.com/dotnet-architecture/eShopOnContainers/workflows/ordering-signalrhub/badge.svg)](https://github.com/dotnet-architecture/eShopOnContainers/actions?query=workflow%3Aordering-signalrhub) | |

_**Dev** branch contains the latest **beta** code and their images are tagged with `:linux-dev` in our [Docker Hub](https://hub.docker.com/u/eshop)_

## Getting Started



