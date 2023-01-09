<template>
    <div>
        <v-form ref="form"  lazy-validation>
            <v-text-field label="Name" required></v-text-field>

            <v-text-field v-model="surname" label="surname" required></v-text-field>
            <v-text-field v-model="newItem.name" label="name" required></v-text-field>
            <v-text-field v-model="newItem.price" label="price" required></v-text-field>

{{ newItem.name }}
{{ newItem.price }}

            <v-btn color="success" class="mr-4"
            @click="addItemToList">
                Validate
            </v-btn>

        </v-form>
        <!-- CARD -->
        <v-card class="mx-auto" max-width="344" outlined>
            <v-list-item three-line>
                <v-list-item-content>
                    <div class="text-overline mb-4">
                        PROFILE </div>
                    <v-list-item-title class="text-h5 mb-1">
                        {{
                            nombreCompleto
                        }} </v-list-item-title>
                    <v-list-item-subtitle>Greyhound divisely hello coldly fonwderfully</v-list-item-subtitle>
                </v-list-item-content>

                <v-list-item-avatar tile size="80" color="grey"></v-list-item-avatar>
            </v-list-item>

            <v-card-actions>
                <v-btn outlined rounded text>
                    PAgar {{ costeTotal }}
                </v-btn>
            </v-card-actions>
        </v-card>
    </div>
</template>
 
<script>

export default {

    data() {
        return {
            name: "",
            surname: "",
            listItems: [
                {
                    name: 'milk',
                    price: 10
                },
                {
                    name: 'cocacola',
                    price: 15
                },
                {
                    name: 'juice',
                    price: 12
                },
                
            ],
            newItemName:"",
            newItemPrice:0,
            newItem: {name:'', price:0}
        }
        //lo que pongo en data son las variables que pongo en mi cmponente, es como las inicializamos. 
    },
    methods:{
        addItemToList(){
            this.listItems.push({ 
                name: this.newItemName,
                price: this.newItemPrice
            })
            this.listItems.push(this.newItem);
        }
    },
    computed: {
        //es un objeto que tendrá funciones.
        //como estamos dentro del export default no necestamos poner la palabra function. 
        nombreCompleto() {
            console.log('cambio')
            return this.name + this.surname
            //esta variable 'nombreCompleto' la podriamos usar para cualquier otra cosa.
        },
        costeTotal() {
            //de un array me devuelve un solo valor. 
            let total = this.listItems.reduce((sum, item) => {
                //un reduce siempre lleva un acumulador donde el resultado de cada iteracion 
                //se va a ir guardando. 
                //el segundo parametro representa el index
                console.log(item)
                return sum + item.price;
            }, 0);

            //reduce neesita dos parametros, uno es una funcion y el segundo es el valor inicial. 
            return total
            //este es el unico valor que me tiene que retornar.


        }

    }
}



</script>