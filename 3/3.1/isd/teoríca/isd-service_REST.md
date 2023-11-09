# Descripción del caso de estudio
El caso de estudio se basa en un cliente con una capa interfaz de usuario y una acceso a servicios, por otro lado tenemos el servidor con su capa servicios y modelo. Esta arquitectura asegura que cada capa modelo solo conozca a la directamente inferior a ella.

```mermaid
flowchart LR
	subgraph Client
		I[Interfaz] -.-> AS[Acceso a servicios]
	end
	subgraph Servidor
		S[Servicios] -.-> M[Modelo]
	end
	AS -.->|Red| S
```

# Servicios REST
## Métodos
Los principales métodos de un servicio REST:
- GET, peticion de información.
- POST, s
# Diseño e implementación
