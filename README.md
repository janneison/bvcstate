<a href="https://github.com/janneison">
   <img src="https://github.com/janneison/bvcstate/blob/main/img/bvc.jpg" alt="eShop logo" title="eShopOnContainers" align="right" height="60" />
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

El siguiente diagrama de clases ilustra a manera general como deberia funcionar la libreria.

![](img/diagram-clases.png)

## Propuesta de arquitectura orientada a Api y SDK


El siguiente diagrama ilustra una propuesta a manera de arquitectura de solucion para un api y/o sdk para el manejo de la maquina de estados utilizando la propuesta de base de datos y que todas las funciones las entregue por una api.

![](img/maquina-estados-2.png)


