# Cómo editar la carta

Todo se maneja desde **un solo archivo: `carta.json`**. No hace falta saber
programar ni llamar a nadie. Se hace desde el celular o la computadora, gratis.

**Para editarlo**: abrí `carta.json`, tocá el lápiz ✏️, hacé el cambio y abajo
de todo apretá el botón verde **Commit changes**. En un minuto se ve en la carta.

> **Regla que evita el 90% de los errores**: los números van **sin puntos**
> (doce mil cien es `12100`) y los textos van **entre comillas**.

---

## Subir todos los precios de golpe

Buscá arriba de todo la línea `"ajuste": 1,` y cambiá el número:

| Quiero subir | Pongo |
|---|---|
| 10 % | `"ajuste": 1.1,` |
| 15 % | `"ajuste": 1.15,` |
| 20 % | `"ajuste": 1.2,` |
| 35 % | `"ajuste": 1.35,` |
| Dejar los precios como están | `"ajuste": 1,` |

Sube toda la carta de una, redondeando a los 100. Ojo: se escribe `1.15` con
**punto**, no con coma.

---

## Cambiar el precio de un solo producto

En la sección `"precios"`, buscá el producto y cambiá el número:

```json
"tostadas-belgas": 12100,
```

---

## Cambiar el nombre de un producto

En `"nombres"`, agregá una línea con el nombre nuevo:

```json
"nombres": {
  "tostadas": "Tostadas de campo"
}
```

---

## Cambiar los ingredientes

En `"ingredientes"`:

```json
"ingredientes": {
  "huevos-revueltos": "Con tostada, dip de queso crema y ciboulette"
}
```

---

## Sacar un producto que ya no se vende

En `"ocultar"`, poné su clave entre comillas. Si hay varios, separados por coma:

```json
"ocultar": ["milkshake-oreo", "campari"]
```

No se borra nada: si mañana lo vuelven a vender, se saca de esa lista y reaparece.

---

## Agregar un producto nuevo

En `"agregar"`, buscá la sección donde va y sumalo:

```json
"agregar": {
  "milkshakes": [
    { "nombre": "Milkshake de pistacho", "precio": 8200 }
  ],
  "desayunos": [
    { "nombre": "Budín de banana", "precio": 7900,
      "ingredientes": "Con nueces y dulce de leche" }
  ]
}
```

`ingredientes` es opcional: si no lo ponés, sale sólo el nombre y el precio.

Las secciones disponibles son: `desayunos`, `laminados`, `milkshakes`, `jugos`,
`alcohol`, `cafeteria`, `sandwiches` y `ensaladas`.

---

## Si algo sale mal

La carta está preparada. Si `carta.json` queda con un error de tipeo, se borra,
o tiene una clave que no existe, **la carta sigue funcionando** y muestra la
última versión buena. Nunca se ve vacía ni rota.

Para deshacer un cambio: entrá a **History** en el archivo y restaurá la
versión anterior.

---

## Lo que no se edita desde acá

Los títulos de las secciones, los combos (Brunch y Merienda), las promos y el
diseño están en `index.html`. Se pueden cambiar, pero conviene avisar antes
para no romper la maqueta.
