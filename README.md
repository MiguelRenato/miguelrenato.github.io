### Marteladela do LuísAndrade para Modbus no HA ler todos os registers nos contadores da E-REDES

- Entrar por consola no HA e executar seguintes comandos para saltar para o validators.py do Modbus.

```python
#Fazer login com as nossos dados de SSH: 
login

#Saltar para dentro do components onde está o folder do modbus:
docker exec -it $(docker ps -f name=homeassistant -q) bash

#Editar o ficheiro validators.py com o editor de texto "vi" como descrito abaixo:
vi /usr/src/homeassistant/homeassistant/components/modbus/validators.py

#para ativar modo de edição no vi
i
```
- Localizar a entrada com ( I maiúsculo ) e editar como linha abaixo passando de 2 para 1.

```python
DataType.UINT32: ENTRY("I", 1, PARM_IS_LEGAL(False, False, True, True, True))
```

- Para salvar no vi:

```python
Esc #uma vez
:wq
Enter
```

