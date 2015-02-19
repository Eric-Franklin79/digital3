window.onload = function() {
    
    "use strict";
    
    
    var game = new Phaser.Game( 800, 600, Phaser.CANVAS, 'game', { preload: preload, create: create, update: update, render:render  } );
    
    function preload() {
       game.load.atlasJSONHash('target', 'assets/target.png', 'assets/target.json');
       //game.load.image( 'target00', 'assets/target08.png' );
       game.load.image( 'bullet', 'assets/bullet.png' );
       game.load.image( 'hole', 'assets/hole.png' );
       game.load.image( 'range', 'assets/range.png' );
    }
    
   var target;
   var counter = 0;
   var textS, textR, textC;
   var score = 0;
   var reload, targetUp, targetDown, newTarget;
   var reloaded = true;
   var targetAtCounter = false;
   var clean = true;
   var bullet1, bullet2, bullet3, bullet4, bullet5, bullet6, bullet7, bullet8, bullet9, bullet0;
   var bullets = [bullet0, bullet1, bullet2, bullet3, bullet4, bullet5, bullet6, bullet7, bullet8, bullet9];
   var hole1, hole2, hole3, hole4, hole5, hole6, hole7, hole8, hole9, hole0;
   var holes = [hole0, hole1, hole2, hole3, hole4, hole5, hole6, hole7, hole8, hole9];
    
   function create() {
   	   var background = game.add.tileSprite(0,0, 800, 600, 'range')
   	   target = game.add.sprite(500, 10, 'target', 'target01.png');
   	   target.anchor.setTo(0.5, 0);
   	   target.animations.add('forward', ['target02.png', 'target03.png', 'target04.png', 'target05.png', 'target06.png', 'target07.png', 'target08.png', 'target09.png', 'target10.png', 'target11.png', 'target00.png'], 20);
   	   target.animations.add('back', ['target11.png', 'target10.png', 'target09.png', 'target08.png', 'target07.png', 'target06.png', 'target05.png', 'target04.png', 'target03.png', 'target02.png', 'target01.png'], 20);
   	   for(var i =0; i <10; i++){
   	   	   bullets[i] = game.add.sprite(719, (379 - (16*i)), 'bullet');
   	   }
   	   for(var i =0; i <10; i++){
   	   	   holes[i] = game.add.sprite(500, (10), 'hole');
   	   	   holes[i].kill();
   	   }
   	    var styleT = { font: "bold 15px Verdana", fill: "#FFFFFF", align: "center" };
   	    var styleC = { font: "bold 10px Verdana", fill: "#FFFFFF", align: "center" };
    	    textS = game.add.text(709, 75, "Score: " + String(score), styleT);
    	    textR = game.add.text(709, 100, "R - Reload Gun", styleC);
    	    textC = game.add.text(709, 110, "E - New Target", styleC);
   	   
   	   reload = game.input.keyboard.addKey(Phaser.Keyboard.R);
   	   targetUp = game.input.keyboard.addKey(Phaser.Keyboard.UP);
   	   targetDown = game.input.keyboard.addKey(Phaser.Keyboard.DOWN);
   	   newTarget = game.input.keyboard.addKey(Phaser.Keyboard.E);

   }
    
    function update() {
    	if(game.input.mousePointer.justPressed(20) && counter < 10){
    		if(!targetAtCounter){
    			if(!(!clean && counter === 0)){
    				holes[counter].reset(game.input.mousePointer.x-8, game.input.mousePointer.y-8);
				bullets[((bullets.length)- 1 - counter)].kill();
				counter++;
				reloaded = false;
				clean = false;
			}
    		}
    	}
    	if(newTarget.downDuration(50)){
    		for(var i =0; i <10; i++){
    			holes[i].kill();
   	   	}
   	   	clean = true;
    	}
    	if(reload.downDuration(50)){
    		if(!reloaded){
    			//target.animations.play('forward');
    			counter = 0;
    			for(var i =0; i <10; i++){
    				bullets[i].revive();
   	   	   	}
    			reloaded = true;
    			
    		}
    	}
    	if(targetUp.downDuration(50)){
    		if(targetAtCounter){
    			target.animations.play('back');
    			targetAtCounter= false;
    		}
    	}
    	if(targetDown.downDuration(50)){
    		if(!targetAtCounter){
    			target.animations.play('forward');	
    			for(var i =0; i<counter; i++){
    				//holes[counter].x = 
    			}
    			targetAtCounter= true;
    		}
    	}
    }
    function updateTimer(){
    	 
    }
    function gameover(){
    	    
    }
    function win(){
	
    }
    function startGame() {
    	
    }
    function render(){
    	game.debug.inputInfo(32, 32);
    }
};
