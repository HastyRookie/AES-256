# AES-256
AES256 Encryption Library

AES-256 Es una libreria de encriptacion de datos hecha en java
basado en el protocolo de seguridad "AES256"

Que es **Salt** es un mensaje aleatorio que antepone al mensaje real, de modo que en cada codificación del mensaje real, en realidad está codificando un mensaje de aspecto diferente (salt + mensaje real) que dará como resultado un texto cifrado diferente.

<p align="center">
    <a href="https://github.com/itwell-dev/AES-256">
        <img width="90%" align="center" src ="/aes.png" />
    </a>
</p>

# Uso de AES-256
Que es **Salt** es un mensaje aleatorio que antepone al mensaje real, de modo que en cada codificación del mensaje real, en realidad está codificando un mensaje de aspecto diferente (salt + mensaje real) que dará como resultado un texto cifrado diferente.

Para usar AES-256 Hay dos Formas de hacerlo una mas corta que la otra pero mas util en diferentes circunstancias
las clases mas Importantes son.

- String256
- AES
---

# Definiciones de las clases
- AES256.Type
    - DEFAULT:
      Valores predeterminados para indicadores de codificador/descodificador.
    - NO_PADDING:
      Indicador del codificador para omitir los caracteres de relleno '=' al final de la salida (si corresponde).
    - NO_WRAP:
      Indicador del codificador para omitir todos los terminadores de línea (es decir, la salida estará en una línea larga).
- String256
    - Clase con un contructor que recibe(String key,String salt) este Constructor permite usar la misma Key y Salt para varios Encriptados o un Constructor ()
    - Esta clase recibe metodos de codificacion y decodificacion similares a la Clase AES
- AES 
    - Clase con un constructor() o una instancia "used()"
    - Esta clase recibe metodos estaticos similares a los de String256

# Uso de las Clases

Uso de String256

```java
String256 crypto = new String256(String key,String salt)
//or
String256 crypto = new String256()

//Encrypt
crypto.encodeFromString(String key,String salt,String cryptext,AES256.Type type) // Return String

//Only Used in Constructor(String key,String salt) not constructor()
crypto.encodeFromString(String cryptext,AES256.Type type) // Return String

crypto.encode(String key,String salt,byte[] data,AES256.Type type) // Return byte[]

//Only Used in Constructor(String key,String salt) not constructor()
crypto.encode(byte[] data,AES256.Type type) // Return byte[]

//Decrypt
crypto.decodeFromString(String key,String salt,String cryptext,AES256.Type type) // Return String

//Only Used in Constructor(String key,String salt) not constructor()
crypto.decodeFromString(String cryptext,AES256.Type type) // Return String

crypto.decode(String key,String salt,byte[] data,AES256.Type type) // Return byte[]

//Only Used in Constructor(String key,String salt) not constructor()
crypto.decode(byte[] data,AES256.Type type) // Return byte[]

//Example for use
String256 crypto = new String256("MyKey","Salt");
        
        String encrypt = crypto.encodeFromString("Hola Mundo",AES256.Type.DEFAULT);
        String descrypt = crypto.decodeFromString(encrypt,AES256.Type.DEFAULT);
        
```

Uso de AES
```java
AES aes = new AES();
//or
AES.used()

//Encrypt
AES.used().encode(String key,String salt,byte[] data,AES256.Type type) // Return byte[]
AES.used().encodeFromString(String key,String salt,String text,AES256.Type type); // Return String

//Descrypt
AES.used().decode(String key,String salt,byte[] data,AES256.Type type) // Return byte[]
AES.used().decodeFromString("MyKey","MySecondKey",encrypt,AES256.Type.DEFAULT) // Return String

//Example for use

String encrypt = AES.used().encodeFromString("MyKey","MySecondKey","Hola Mundo",AES256.Type.DEFAULT);
String descrypt = AES.used().decodeFromString("MyKey","MySecondKey",encrypt,AES256.Type.DEFAULT);
```

# Instalacion

Para usar AES-256 Solo descargue el ultimo archivo .jar de la seccion Release
y importelo a su proyecto con eso ya estara usandolo en su proyecto