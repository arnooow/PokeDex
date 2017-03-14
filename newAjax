/**
 * Created by arnow on 14/03/2017.
 */

var apiLink = "https://pokeapi.co/api/v2/pokemon/";

var onzePokemon = ['poochyena', 'mightyena', 'zigzagoon', 'linoone', 'wurmple'];

var doAjax = function (url) {

    var val = $('#pokesearch').val();
    var lengte = onzePokemon.length;
    var number = 261;
    for (i = 261; i < lengte; i++) {
        if (val == onzePokemon[i]) {
            number += i;
        }
    }
    
    apiLink += val;
    var linkImg = "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/" + number + ".png";
    $.ajax({

        url: apiLink,

        dataType: "json"
    }).done(function loopOverJSON(obj) {


        //$('#Pokemons').text('');
        for (var key in obj) {
            if (typeof obj[key] !== "object") {
                console.log(key + " = " + obj[key]);
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
