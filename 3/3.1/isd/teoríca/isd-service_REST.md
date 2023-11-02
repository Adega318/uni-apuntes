# Descripción del caso de estudio
El caso de estudio se basa en un cliente con una capa interfaz de usuario y una acceso a servicios, por otro lado tenemos el servidor con su capa servicios y modelo. Esta arquitectura asegura que cada capa modelo solo conozca a la directamente inferior a ella.

```mermaid
flowchart LR
	subgraph Client
		Interfaz -.-> a[Acceso a servicios]
	end
	subgraph Servidor
		Servicios -.-> Modelo
	end
	a -.- Red -.-> Servicios
```

# Servicios REST
# Diseño e implementación