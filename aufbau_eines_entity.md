1. deklarieren: game.EnemyEntity = me.Entity.extend({

2. initial function: init: function (x, y, settings) {
3. basic Attribute festlegen: - image
			      - width, height
			      - x-Start- und Endwert für bewegung ggf. 					auch y-Werte
		  	      - geschwindigkeit
			      - walkleft/right
			      -etc.
4. konstruktor aufrufen: this._super(me.Entity, 'init', [x, y, 				 settings]);
5. Ränder updaten: this.updateBounds();

6. update function: update: function (dt) {
7. bewegung festlegen: if (this.alive) {
	    		if (this.walkLeft && this.pos.x <= 				this.startX) {
		        	this.walkLeft = false;
		    	} else if (!this.walkLeft && this.pos.x >= 				this.endX) {
		      	  this.walkLeft = true;
          		}
8. bewegung starten: this.renderable.flipX(this.walkLeft);
9. bewegung updaten: this.body.update(dt);
10. auf collision prüfen: me.collision.check(this);
11. konstruktor returnen (true wenn sich der entity bewegt): return (this._super(me.Entity, 'update', [dt]) || this.body.vel.x !== 0 || this.body.vel.y !== 0);

12. onCollision function: onCollision : function (response, other) {
13. festlegen was passieren soll bei einer collision






			  


