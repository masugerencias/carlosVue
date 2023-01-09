<template >

    <div>
        <slot name="titulo"></slot>
    <p><slot name="subtitulo"></slot></p>
        <ul>
            <li v-for="pokemon in pokemons" :key="pokemon.id">
                <slot name="contenido"
                :item="pokemon" 
                ></slot></li>
        </ul>
    </div>


</template>

<script>
export default {
    name: 'PokeList',

    data: () => ({
        pokemons: [
            {
                id: 1,
                nombre: "Pikachu",
                habilidad: "electricidad"
            },
            {
                id: 2,
                nombre: "Charmander",
                habilidad: "fuego"
            },
            {
                id: 3,
                nombre: "Bulbasur",
                habilidad: "planta"
            }
        ]
    }),
};

</script>