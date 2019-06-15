# esx_status
ESX Status

## Download e Instalação

### Usando o [fvm](https://github.com/qlaffont/fvm-installer)
```
fvm install --save --folder=esx esx-brasil/esx_status
```

### Usando o Git
```
cd resources
git clone https://github.com/ESX-Brasil/esx_status [esx]/esx_status
```

### Manualmente
- Download https://github.com/ESX-Brasil/esx_status/archive/master.zip
- Coloque-o no diretório `[esx]`

## Instalação
- Adicione isto ao seu `server.cfg`:

```
start esx_status
```

## HOWTO

server.lua
```lua

local name    = 'hunger'
local default = 1000000
local color   = '#CFAD0F'

TriggerEvent('esx_status:registerStatus', name, default, color,
	function(status) -- Retorno de chamada visível, se retornar true, o status ficará visível
		return true
	end,
	function(status) -- Chamada de retorno, o que fazer em cada tick
		status.remove(200)
	end,
	{remove = 200} -- Ação do cliente (adicionar / remover) para que o cliente possa estar em sincronia com o servidor
)
```

# Legal
### License
esx_status - skin selector for ESX

Copyright (C) 2015-2019 ESX-Brasil

This program Is free software: you can redistribute it And/Or modify it under the terms Of the GNU General Public License As published by the Free Software Foundation, either version 3 Of the License, Or (at your option) any later version.

This program Is distributed In the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty Of MERCHANTABILITY Or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License For more details.

You should have received a copy Of the GNU General Public License along with this program. If Not, see http://www.gnu.org/licenses/.
