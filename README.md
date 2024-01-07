Detalii legate de crearea jocului: 

Am folosit un program special, TILED, pentru a crea hărțile 2D ale jocului. 
Pentru nivelul 1, am creat o hartă, iar pentru nivelul 2, am creat două hărți distincte. 
Pentru fiecare hartă, am utilizat diferite elemente grafice (assets). 
În primul rând, am creat straturi (layers) pentru Platforms, Platforms_colliders, Environment, Distance, Distance_bg, Player_zones, Enemy_spawns, Collectables și Traps, atât în cadrul obiectelor (Object layer), cât și în cadrul plăcilor de tip (Tile layer) în TILED. 
Practic, am proiectat întreaga hartă pentru a include poziționarea mobilor, zonele prin care jucătorul trebuie să treacă pentru a avansa la un nivel superior, capcanele, diamantele pentru a aduna punctaje. 
Am importat hărțile în fișierul meu de resurse (assets) sub forma unui fișier JSON pentru a le putea utiliza ulterior. 
Jocul l-am dezvoltat în JavaScript, am utilizat Phaser și am creat un fișier scenă unde am definit o clasă de preîncărcare (preload.js). 
Aici am încărcat toate resursele necesare pentru joc: hărți, inamici, jucătorul, proiectile, arme, etc. 

În index.js,
am definit câteva constante legate de configurarea jocului, cum ar fi lățimea și înălțimea ecranului, factorul de zoom și offset-ul hărții. 

În fișierul anims.js, 
am definit animații legate de joc, cum ar fi lovitura, animațiile inamicilor, ale jucătorului și ale diamantelor. 

Fișierul attacks include două clase: 
MeleeWeapons.js reprezintă o armă de luptă de tip corp la corp implementată pentru jucător. 
Projectile.js este responsabil pentru proiectile. La crearea unei instanțe a clasei, aceasta primește ca parametri scena, coordonatele x și y ale proiectilului. 

Fișierul projectiles.js
furnizează funcționalități precum obținerea și inițierea unui proiectil, având în vedere cooldown-ul între trageri și ajustarea direcției de traiectorie a proiectilului în funcție de entitatea care trage. 

Fișierul collectables.js 
definește un obiect colectabil. Primește ca parametri scena și coordonatele x și y. Obiectul efectuează o mișcare sus și jos, utilizând proprietatea yoyo, și are un scor de 1 punct. 

În fișierele effects.js și spriteEffect.js, 
se ocupă de gestionarea și redarea efectelor vizuale asociate atunci când un obiect atinge un inamic și trebuie să se distrugă. 

Fișierul entities: 

Birdman.js/Snaky.js: 
Am implementat raycasting pentru fiecare inamic. Atunci când inamicul primește daune, am adăugat o animație pentru a indica acest lucru. Când este eliminat, inamicul devine roșu și cade de pe hartă.
În ceea ce privește Snaky, am inclus și proiectile care pot crea daune jucătorului atunci când acesta se apropie prea mult. 
Player.js: Jucătorul poate fi controlat folosind săgețile. Apăsarea săgeții în jos îl așează în jos, tasta E declanșează atacul cu sabia, Q aruncă proiectile de gheață, iar saltul dublu este activat prin apăsarea tastei Spațiu. 

Fișierul entities/anims: 
Birdman.js/Snaky.js/Player.js:
Am creat animații specifice pentru fiecare entitate. 
Birdman are stările de inactivitate, rănire și alte animații relevante. 
Snaky are animații pentru mers și starea de rănire, iar jucătorul are animații pentru starea de inactivitate, alergare, sărit, aruncare și alunecare. 

Fișier Hud: 
HealthBar.js: Am poziționat și implementat o bara de sănătate. Aceasta scade atunci când jucătorul primește daune de la inamici sau capcane. 
Index.js: Am creat și poziționat un scor pentru a evidenția punctajul exact al jucătorului și numărul de diamante obținute. 

Mixins: 
Colidable.js: Aici am implementat funcții utile pentru gestionarea coliziunilor și detectarea razelor (raycasting). 
Fișier Scene: 
Play.js: Această scenă, "PlayScene", este responsabilă de gestionarea efectivă a jocului și asigurarea unei interacțiuni corecte între jucător și mediul de joc. Am implementat translații și oglindire pentru a permite mișcarea jucătorului la stânga și la dreapta + reluarea jocului  daca  o sa cazi de pe mapa sau  daca ramai fara viata. 

If(left.isDown) 

this.setVelocityX(-this.playerSpeed); 

} else if (right.isDown) { 

this.setVelocityX(this.playerSpeed); 

}else { // Oprire this.setVelocityX(0); 

this.setFlipX(true); // Oglindirea sprite-ului pe axa orizontală this.setFlipX(false); // Revenire la afișarea normală a sprite-ului. 

BaseScene.js/Levels.js/Credits.js, am creat un meniu de inceput unde avem start/levels/exit, u button de return pentru a reveni la meniu, iar un meniu de final cu terminarea jocului. 

Am implementat muzica pe fundal, efecte sonore pentru player/enemy/diamante/capcane.
