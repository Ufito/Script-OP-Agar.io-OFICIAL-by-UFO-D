// ==UserScript==
// @name         Agar.io Feed Macro + Split Hotkeys! Best 2016.
// @namespace    Double Split, Triple Split, 16 Split Hotkeys And Quicker Feeding
// @version      8.5
// @description  Q - Double Split -|- R - Triple Split -|- E - 16 Split -|- W - Feed
// @author       UFO
// @match        http://agar.io/*
// @grant        none
// @run-at       document-end
// ==/UserScript==

document.getElementById("instructions").innerHTML += "<center><span class='text-muted'><span data-itr='instructions_w'> Press <b>W</b> for macro feed</span></span></center>";
document.getElementById("instructions").innerHTML += "<center><span class='text-muted'><span data-itr='instructions_q'> Press <b>Q</b> to Double Split</span></span></center>";
document.getElementById("instructions").innerHTML += "<center><span class='text-muted'><span data-itr='instructions_r'> Press <b>R</b> to Triple Split</span></span></center>";
document.getElementById("instructions").innerHTML += "<center><span class='text-muted'><span data-itr='instructions_e'> Press <b>E</b> to 16 Split</span></span></center>";
load();
function load() {
}
(function() {
    var amount = 4;
    var duration = 50;

    var overwriting = function(evt) {
        if (evt.keyCode === 81) { // Change 81[Q] To Whichever Keycode You Want To Change The Double Split HotKey
            for (var i = 0; i < amount; ++i) {
                setTimeout(function() {
                    window.onkeydown({keyCode: 32}); // 32 - Space Bar
                    window.onkeyup({keyCode: 32});
                }, i * duration);
            }
        }
    };

    window.addEventListener('keydown', overwriting);
})();

(function() {
    var amount = 6;
    var duration = 50;

    var overwriting = function(evt) {
        if (evt.keyCode === 82) { // Change 82[R] To Whichever Keycode You Want To Change The Triple Split HotKey
            for (var i = 0; i < amount; ++i) {
                setTimeout(function() {
                    window.onkeydown({keyCode: 32}); // 32 - Space Bar
                    window.onkeyup({keyCode: 32});
                }, i * duration);
            }
        }
    };

    window.addEventListener('keydown', overwriting);
})();

(function() {
    var amount = 8;
    var duration = 50;

    var overwriting = function(evt) {
        if (evt.keyCode === 69) {  // Change 69[E] To Whichever Keycode You Want To Change The 16 Split HotKey
            for (var i = 0; i < amount; ++i) {
                setTimeout(function() {
                    window.onkeydown({keyCode: 32}); // 32 - Space Bar
                    window.onkeyup({keyCode: 32});
                }, i * duration);
            }
        }
    };

    window.addEventListener('keydown', overwriting);
})();

(function() {
    var amount = 6;
    var duration = 50;

    var overwriting = function(evt) {
        if (evt.keyCode === 87) { // Change 87[W] To Whichever Keycode You Want To Change The Quick Feeding Macro
            for (var i = 0; i < amount; ++i) {
                setTimeout(function() {
                    window.onkeydown({keyCode: 87}); // 87 - W
                    window.onkeyup({keyCode: 87});
                }, i * duration);
            }
        }
    };

    window.addEventListener('keydown', overwriting);
})();

$('#advertisement, #agario-web-incentive, .agario-promo, .diep-cross, .us-elections').hide().css({ 'visibility': 'hidden' });
$('#region').val('').css({ 'display': 'block' });
$('#adsBottom').remove();
$('#advertisement, #agario-web-incentive, .agario-promo, .diep-cross, .us-elections, .agario-promo-container').on('show', function() {
	setTimeout(function() { $('#advertisement, #agario-web-incentive, .agario-promo, .diep-cross, .us-elections, .agario-promo-container').hide(); }, 50);
});
