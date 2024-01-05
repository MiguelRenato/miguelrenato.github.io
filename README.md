Welcome!

### Marteladela do Luís para modbus no HA para haver compatibilidade com o contador

Entrar por consola no HA e executar

```python
#Fazer login com as nossos dados: 
login

#Saltar para dentro do conteiner com este comando:
docker exec -it $(docker ps -f name=homeassistant -q) bash

#Editar o ficheiro validators.py com o vi como descrito abaixo:
vi /usr/src/homeassistant/homeassistant/components/modbus/validators.py

#ativar modo de edição no vi
i
```
Localizar a entrada com ( I maiúsculo ) e editar como linha abaixo passando de 2 para 1.

```python
DataType.UINT32: ENTRY("I", 1, PARM_IS_LEGAL(False, False, True, True, True))
```

#Para salvar no vi:

```python
Esc #uma vez
:wq
Enter
```

