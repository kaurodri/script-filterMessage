# script-filterMessage
```js
const filterMessage = require('./script.js');

{//Exemplo 1
    let txt = "sobre o balanceamento dos eventos";
    let keyword = "user4";
    let base = null; //para os sem restrição.
    const database = {
        "user1": [null],
        "user2": [null],
        "user3": [null],
        "user4": ["atualização", "balanceamento", "evento", "disponível"],
        "user5": ["beta", "preview", "alerta", "saiu"]
    };
    const silence = ["spam", "torneio", "campeonatos"];

    console.log(filterMessage(txt, keyword, base, database, silence));
    //resultado -> true
}

{//Exemplo 2
    let txt = "sobre o financeiro[...]";
    let keyword = "user4";
    let base = null; //para os sem restrição.
    const database = {
        "user4": ["atualização", "balanceamento", "evento", "disponível"]
    };
    const silence = ["spam", "torneio", "campeonatos"];

    console.log(filterMessage(txt, keyword, base, database, silence));
    //resultado -> false
}

{//Exemplo 3
    let txt = "sobre o balanceamento dos eventos";
    let keyword = "user1";
    let base = null;
    const database = {
        "user1": [null]
    };
    const silence = ["spam", "torneio", "campeonatos"];

    console.log(filterMessage(txt, keyword, base, database, silence));
    //resultado -> true
}
```