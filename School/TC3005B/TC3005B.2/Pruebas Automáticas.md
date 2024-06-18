---
tags:
  - test
  - junit
  - java
  - spring-boot
---
Date: 2024-05-15 : 16:11
***

## ¿Por qué hacerlas?

- Para evitar **errores de regresión**.
- Deben ser **atómicas**, es decir, que se pueda *ejecutar sola* y *no dependa de otras*.
	- Si mi prueba depende de un usuario, crearlo en la prueba
	- Al terminar, borrar mi usuario.
- Se construyen por cada **criterio de aceptación**. 

## Ejemplo 

```java
@Test
public void sumaEnterosPositivos() {
	OperacionDTO operacionDTO = new OperacionDTO();
	operacionDTO.setValor1(2);
	operacionDTO.setValor1(3);

	mocvkMvc.perform(MockMvcRequestBuilders
		.post("/operaciones/suma-positivos")
		.contentType(MediaType.APPLICATION_JSON)
		.content(objectToJson(operacionDTO))
	).andExpect(MockMvcResultMatchers.status().isOk())
	 .andExpect(MockMvcResultMatchers
		 .jsonPath("resultado")
		 .value(5));
}

private static String objectToJson(Object object) {
	ObjectMapper objectMapper = new ObjectMapper();
	return objectMapper.writeValueAsString(object);
}
```

