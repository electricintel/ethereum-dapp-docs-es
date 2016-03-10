## Configurar el cliente Geth en la Testnet
### ¿Por qué utilizar una cadena de bloques alternativa a la original?
Para realizar pruebas de un contrato o de una dapp, es aconsejable no utilizar la cadena de bloques oficial, ya que necesitas una cantidad considerable de Ether para pagar las acciones realizadas en el contrato y también así se evita usar o congestionar la red principal de Ethereum.

Hay varias soluciones mas rápidas, como utilizar Embark, que despliega una cadena de bloques privada al instante, pero no se obtiene una gran visión de lo que pasa dentro del contrato desplegado sin tener un explorador de bloques.

La cadena de bloques no oficial que recomiendo es la de Consensys, ya que posee un explorador de bloques más avanzado que el resto,  [Testnet Ether Camp](https://test.ether.camp/), capaz de detectar en los contratos transacciones de salida y cambios internos de los datos del contrato.

Una vez que hayamos realizado las pruebas y los tests oportunos, se debe desplegar el contrato en el entorno real de Ethereum.

###Configurar Geth para utilizar la cadena de bloques de Consensys
  
Para utilizar la testnet de Consensys, con id 161, tenemos que preparar el cliente Geth. Creamos un directorio separado a la cadena de bloques oficial,en la que contendrá la cadena de bloques de la testnet y el archivo de génesis de Consensys en JSON que contiene la configuración de dicha testnet. Puedes ver los parámetros de dicho archivo en este [enlace](https://github.com/ConsenSys/public-testnet/blob/master/genesis.json). Para que puedas conectar a los nodos de esta tesnet, debes de dejar el archivo génesis intacto.
  
Los siguientes comandos creara el directorio comentado anteriormente, entrará dentro del mismo, y descargará el archivo génesis.
  
```
mkdir ~/.eth-cons-testnet
cd ~/.eth-cons-testnet
wget 'https://raw.githubusercontent.com/ConsenSys/public-testnet/master/genesis.json'
```
Ahora, seguiremos el mismo procedimiento de abrir dos terminales, o dos pestañas, en una terminal ejecutamos el siguiente comando para iniciar el cliente geth configurado con la testnet.

``geth --networkid 161 --datadir ~/.eth-cons-testnet --genesis ~/.eth-cons-testnet/genesis.json``

En la otra terminal, podemos hacer un "attach" o vinculación para obtener la consola Javascript del cliente anterior, sin que moleste los mensajes de sincronización de los nodos.

``geth --networkid 161 --datadir ~/.eth-cons-testnet --genesis ~/.eth-cons-testnet/genesis.json attach``

## Obtención de Ether en la Testnet

[...]

#### To be continued!
