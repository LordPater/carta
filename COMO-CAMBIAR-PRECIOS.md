# Cómo cambiar los precios de la carta

No hace falta llamar a nadie ni saber nada de programación. Se hace desde el
celular o la computadora, y es gratis.

Todos los precios viven en un solo archivo: **`precios.json`**.

---

## Subir todos los precios de golpe (aumento general)

Es lo más común. En vez de tocar precio por precio, se cambia **un solo número**.

1. Abrir el archivo `precios.json` en este repositorio.
2. Tocar el lápiz ✏️ (arriba a la derecha) para editar.
3. Buscar la línea de arriba de todo que dice:

   ```json
   "ajuste": 1,
   ```

4. Cambiarla según el aumento que quieran:

   | Quiero subir | Pongo |
   |---|---|
   | 10 % | `"ajuste": 1.1,` |
   | 15 % | `"ajuste": 1.15,` |
   | 20 % | `"ajuste": 1.2,` |
   | 35 % | `"ajuste": 1.35,` |
   | Volver a los precios originales | `"ajuste": 1,` |

5. Abajo de todo, botón verde **Commit changes**.

Listo. En un minuto la carta muestra todo aumentado, redondeado a los 100.

> **Ojo con el punto**: se escribe `1.15`, con punto, no `1,15` con coma.

---

## Cambiar el precio de un solo producto

1. Abrir `precios.json` y tocar el lápiz ✏️.
2. Buscar el producto por su nombre. Por ejemplo:

   ```json
   "tostadas-belgas": 12100,
   ```

3. Cambiar el número. Se escribe **sin puntos**: doce mil cien es `12100`.
4. **Commit changes**.

> El precio que se escribe acá es el precio base. Si `ajuste` está en algo
> distinto de 1, la carta le va a aplicar ese porcentaje encima.

---

## Cuando el aumento ya está aplicado y quieren dejarlo fijo

Después de un tiempo conviene "planchar" el aumento: escribir los precios ya
aumentados y volver `ajuste` a `1`. No es obligatorio, pero evita perderse.
Si les da trabajo, se puede dejar el ajuste andando sin problema.

---

## Si algo sale mal

La carta está preparada para eso. Si `precios.json` tiene un error de tipeo, o
se borra, **la carta sigue funcionando** y muestra los últimos precios que
quedaron escritos en la página. Nunca se ve vacía ni rota.

Para volver atrás un cambio, en GitHub se entra a **History** en el archivo y
se restaura la versión anterior.

---

## Cambiar textos, agregar o sacar productos

Eso ya no está en `precios.json`, está en `index.html`. Se puede hacer igual
desde GitHub, pero conviene avisar antes para no romper el diseño.
