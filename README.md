# Encriptador AES-256 con PyCryptodome

Proyecto en Python que implementa un encriptador simple utilizando cifrado simétrico **AES-256** con la librería **PyCryptodome**.  
El programa permite generar una llave, cifrar archivos de texto y descifrarlos para recuperar el mensaje original.

---

## 1. ¿Qué sucede si intentas descifrar con una llave diferente a la que se usó para cifrar?

Si se utiliza una llave diferente, el mensaje no puede recuperarse correctamente. El resultado será texto incorrecto o un error en el proceso de descifrado, ya que AES requiere la misma llave para cifrar y descifrar.

---

## 2. ¿Por qué el IV debe ser diferente cada vez que ciframos?

El **IV (Vector de Inicialización)** agrega aleatoriedad al cifrado.  
Aunque el mensaje y la llave sean los mismos, el resultado cifrado será diferente cada vez.

Si se usara siempre el mismo IV, mensajes iguales producirían el mismo cifrado, lo que permitiría detectar patrones y reducir la seguridad.

---

## 3. ¿Cuál es la relación entre el tamaño de la llave y la seguridad del cifrado?

Mientras mayor sea el tamaño de la llave, mayor es la seguridad, porque aumenta el número de combinaciones posibles.

Una llave de **256 bits** tiene:

2^256 combinaciones posibles

Esto hace que AES-256 sea extremadamente difícil de romper mediante fuerza bruta.

---

## 4. ¿Por qué se necesita padding?

AES trabaja con bloques de **16 bytes**.  
Si el texto no tiene un tamaño múltiplo de 16, se agregan bytes extra llamados **padding** para completar el bloque y permitir el cifrado.

---

## 5. ¿Por qué se utiliza Base64?

El cifrado genera datos binarios (bytes) que no siempre son legibles o fáciles de guardar.  
**Base64** convierte esos bytes en texto utilizando caracteres seguros, lo que facilita almacenarlos y transmitirlos.

---

## 6. Relación con el problema del doble gasto y la confianza

La criptografía permite proteger la información y generar confianza en sistemas digitales.  
En contextos como blockchain y compraventa digital, se utilizan técnicas criptográficas para asegurar que las transacciones sean seguras, auténticas y no puedan duplicarse, evitando problemas como el **doble gasto**.
