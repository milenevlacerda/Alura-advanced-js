# JavaScript Avançado I: ES6, Orientações à Objetos e Padrão de Projetos

> Lembrando que este documento são anotações individuais sobre as aulas com lembretes que considero importantes.



### Aula 4 - "Lidar com data é trabalhoso? Chame um ajudante!"


###### Exemplo de **Template String**.

`console.log( 'A idade de ${nome} é ${idade}' );`

###### Exemplo de **Método que só pode ser acessado pela classe**.


```
_criaNegociacao() {

    return new Negociacao(
        DateHelper.textToDate( this._inputData.value ),
        this._inputQuantidade.value,
        this._inputValor.value
    );

}
```

###### Exemplo de **Método Estático** .

```
class DateHelper {

    constructor() {
        throw new Error( 'DateHelper não pode ser instanciada' );
    }

    static textToDate( text ) {
        if( ! /\d{4}-\d{2}-\d{2}/.test( text ) ) {
            throw new Error( 'Deve estar no formato aaaa-mm-dd' );
        }

        return new Date( ...text.split( '-' ).map( ( item, indice ) =>  item - item % 2 ) );
    }

    static dateToText( data ) {
        return `${data.getDate()}/${data.getMonth()+1}/${data.getFullYear()}`;
    }

}

```
###### Exemplo de como acessar um **Método Estático** .

```

_criaNegociacao() {

    return new Negociacao(
        DateHelper.textToDate( this._inputData.value ),
        this._inputQuantidade.value,
        this._inputValor.value
    );

}

```
