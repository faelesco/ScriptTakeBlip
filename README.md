# Scripts Take Blip 🎉
###### Scripts for help others devs and me


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
