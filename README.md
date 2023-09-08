# Scripts Take Blip 🎉
###### Scripts for help others devs

# Script Validation Input - JS
```ruby
const run = (userEntry) => {
  const cleanedInput = userEntry.normalize("NFD").replace(/[^\w\s]/gi, '').toLowerCase();
  const inputInesperado = "Input inesperado";
  const opcoesValidas = [
    { name: ["sim", "si", "positivo"], value: "True" },
    { name: ["nao", "no", "negativo"], value: "False" }
  ];

  const opcaoEncontrada = opcoesValidas.find(opcao => {
    return opcao.name.includes(cleanedInput);
  });

  return opcaoEncontrada ? opcaoEncontrada.value : inputInesperado;
}
```

# Script Validation Json With Array - JS
Code example
```ruby
const run = (userEntry, recursoKeyword) => {
  const cleanedInput = userEntry.normalize("NFD").replace(/[^\w\s]/gi, '').toLowerCase();
  const inputInesperado = "Input inesperado";

  let opcoesValidas;
  try {
    opcoesValidas = JSON.parse(recursoKeyword);
  } catch (e) {
    return inputInesperado;
  }

  const opcaoEncontrada = opcoesValidas.find(opcao => {
    return opcao.name.includes(cleanedInput);
  });

  return opcaoEncontrada ? opcaoEncontrada.value : inputInesperado;
}
```
Json example
```
[   
   {
      "name":[
         "menu",
         "volver menu",
         "volver conversacion",
         "regresar la conversacion",
         "regresar conversacion",
         "retornar la conversacion",
         "retornar conversacion"
      ],
      "value":"VOLTAR AO MENU INICIAL"
   }
]
```

# Script Validation Regex - JS
Code example
``` ruby
const run = (input) => {
    try {
        const inputOptions = {
            "\\b((3|tr(ê|e)s|mais))\\b": "3 meses ou mais",
            "\\b((2|dois))\\b": "2 meses",
            "\\b((1|um|(m(ê|e)s)$))\\b": "1 mes",
            default: "input inesperado"
        };
        const match = matchKey(inputOptions, input);
        return inputOptions[match] || inputOptions["default"];
    } catch (e) {
        return "input inesperado";
    }
}

const matchKey = (options, input) => {
    return Object.keys(options).find(key => (
        input.match(new RegExp(key, "gmi"))
    ));
}
```
# Component List Message - JSON
```ruby
{
    "recipient_type": "individual",
    "type": "interactive",
    "interactive": {
        "type": "list",
        "header": {
            "type": "text",
            "text": "SELECIONE SEU FIAT 🚗"
        },
        "body": {
            "text": "Qual carro é seu escolhido na *Largada Fiat*?"
        },
        "action": {
            "button": "Selecionar",
            "sections": [
				{
					"title": "Selecione",
                    "rows": [
						{
							"id": "cronos drive",
							"title": "Cronos Drive Flex",
							"description": ""
						},
						{
							"id": "toro endurance",
							"title": "Toro Endurance Flex",
							"description": ""
						},
						{
							"id": "pulse drive",
							"title": "Pulse Drive 1.3 MT",
							"description": ""
						}
                    ]
                }
            ]
        }
    }
}
```
# Component Reply - JSON
```ruby
{
"recipient_type": "individual",
"type": "interactive",
"interactive": {
    "type": "button",
    "body": {
      "text": "Y ahora, ¿qué deseas hacer?"
    },
    "action": {
      "buttons": [
        {
          "type": "reply",
          "reply": {
            "id": "Conocer más la Montana",
            "title": "Conocer más la Montana" 
          }
        },
        {
          "type": "reply",
          "reply": {
            "id": "Menú principal",
            "title": "Menú principal" 
          }
        },
		{
          "type": "reply",
          "reply": {
            "id": "Finalizar",
            "title": "Finalizar" 
          }
        }
      ] 
    } 
  }
}
```
# Component Video + Text - JSON
```ruby
{
	"recipient_type": "individual",
	"type": "video",
	
	"video": {
		"link": "https://s3-sa-east-1.amazonaws.com/i.imgtake.takenet.com.br/v8lanwd2d4/v8lanwd2d4.mp4",
		"caption": "¡Mira el *separador Multiboard*!"
	}
}
```
# Component Contact - JSON
```ruby
{
        "language": "pt-BR",
        "type": "contacts",
        "contacts": [

            {
                "name": {
                "first_name": "nome",
                "formatted_name": "nome"
            },
            "phones": [
                {
                    "phone": "+55 9999999",
                    "type": "WORK",
                    "wa_id": "559999999"
                }
            ]
            }
        ]
    }
```

