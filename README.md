# Dino-game-hacks
A small collection of hacks for the classic dinosaur game, works on a wide range of dino game websites.
<code>
// ==UserScript==
// @name         Dino game hacks
// @run-at document-idle
// @version      1
// @description  A collection of hacks for the classic google dinosaur game, working on almost all dino game websites.
// @author       Grocey
// @icon         data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==
// @grant        none
// @match https://chromedino.com/
// @match https://chromedino.com/color/
// @match https://chromedino.com/black/
// @match https://offline-dino-game.firebaseapp.com/
// @match https://dino-chrome.com/en
// @match https://tuckercraig.com/dino/
// @match https://www.trex-game.skipser.com/
// @match https://fivesjs.skipser.com/trex-game/
// @match https://wayou.github.io/t-rex-runner/
// @match https://24glo.com/game/dino-play.html
// @match https://elgoog.im/t-rex/
// @match https://thecodepost.org/apps/trex/index.html
// ==/UserScript==
function setspeed(v){
    {Runner.instance_.setSpeed((v / Runner.config.SPEED) * Runner.config.SPEED )}
}
(function() {
    'use strict';
    var speed = 0
    var speed2 = 0
    var gravity = 0
    var original = Runner.prototype.gameOver
    var i = 0
    var f = 0
    var location = window.location.href
    var chromedino = location.includes("chromedino.com")
    if(chromedino){
        var copyright = $("div.copyright");
        copyright.remove ();
        var othercontent = $("div.___wrapper ");
        othercontent.remove ();
        var othercontent2 = $("div.__wrapper");
        othercontent2.remove ();
        var othercontent3 = $(".other-versions __wrapper");
        othercontent3.remove ();
    }
    window.alert("You have installed Dino game hacks")
    window.alert("Press h for help.")
    window.addEventListener("keydown", key, false);

    function key(e){
        if(e.keyCode == "83"){
            speed = prompt("What Speed Would You Like? Resets every death.");
            if(isNaN(speed)){
                window.alert("Please enter a number next time");
            }else{
                setspeed(speed)
            }
        }
        if(e.keyCode == "67"){
            speed2 = prompt("What Speed Would You Like? 0 to reset.");
            if(isNaN(speed2)){
                window.alert("Please enter a number next time");
            }else if(speed2 == 0){
                Runner.config.SPEED = (6 / Runner.config.SPEED) * Runner.config.SPEED
            }else{
                Runner.config.SPEED = (speed2 / Runner.config.SPEED) * Runner.config.SPEED
            }
        }
        if(e.keyCode == "73"){
            if(i == 0){
                window.alert("Enabling noclip");
                Runner.prototype.gameOver = function (){}
                i = 1
            }else{
                window.alert("Disabling noclip");
                Runner.prototype.gameOver = original
                i = 0
            }
        }
        if(e.keyCode == "72"){
            window.alert("Dino game hacks supports a lot of different websites but was originally made for chromedino.com")
            window.alert("Supported websites https://chromedino.com/ https://chromedino.com/color/ https://chromedino.com/black/ https://offline-dino-game.firebaseapp.com/ https://dino-chrome.com/en https://tuckercraig.com/dino/ https://www.trex-game.skipser.com/ https://fivesjs.skipser.com/trex-game/ https://wayou.github.io/t-rex-runner/ https://24glo.com/game/dino-play.html https://thecodepost.org/apps/trex/index.html")
            window.alert("Press s to change current speed")
            window.alert("Press c to change full speed. You need to die for it to activate.")
            window.alert("Full speed only works on chromedino.com, tuckercraig.com/dino/, fivesjs.skipser.com/trex-game/, wayou.github.io/t-rex-runner/, 24glo.com/game/dino-play.html //elgoog.im/t-rex/, thecodepost.org/apps/trex/index.html")
            window.alert("Press f to freeze and unfreeze")
            window.alert("Press i to enable and disable noclip")
        }
        if(e.keyCode == "70"){
            if(f == 0){
                window.alert("Freezing");
                Runner.instance_.playingIntro = true
                f = 1
            }else{
                window.alert("Unfreezing");
                Runner.instance_.playingIntro = false
                f = 0
            }
        }
    }

})();
</code>
