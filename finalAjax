var onzePokemon = ['poochyena', 'mightyena', 'zigzagoon', 'linoone', 'wurmple', 'silcoon', 'beautifly', 'cascoon', 'dustox', 'lotad', 'lombre', 'ludicolo', ''];

var doAjax = function (e) {
    e.preventDefault();

    var val = $('#pokemon').val();
    console.log(val);
    var lengte = onzePokemon.length;
    var number = 261;
    for (i = 0; i < lengte; i++) {
        if (val == onzePokemon[i]) {
            number += i;
        }
    }
    var apiLink = "https://pokeapi.co/api/v2/pokemon/";
    apiLink += val;

    var linkImg = "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/" + number + ".png";
    $.ajax({

        url: apiLink,

        dataType: "json"
    }).done(function loopOverJSON(obj) {



        for (var key in obj) {
            if (typeof obj[key] !== "object") {

                if (key == 'name' || key == 'front_default') {
                    $('#Pokemons').append('<p>' + obj[key] + '<p>');
                }

            } else {
                loopOverJSON(obj[key]);
            }
        }
    });

    $('#Pokemons').append('<img src="' + linkImg + '" >')

};




$(document).ready(function () {
    $('#pokesearch').on('click', doAjax);

});
