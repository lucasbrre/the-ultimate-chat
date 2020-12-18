# the-ultimate-chat
par Lucas, Luis, Mickael
+ le CSS à télécherger ci dessus.

<!DOCTYPE html>
    <html lang="fr">
        <head>
            <meta charset="utf-8">
            <title>The ultime CHAT</title>
            <link rel="stylesheet" href="style.css">
        </head>
        
        <body>

        <!-- Pouvoir quitter le chat en se déconnectant sans quitter la page -->

        <div class="connect">
            <button class="connexion" onclick="connexion()">Connexion</button>
            <button class="deconnexion" onclick="deconnexion()">Déconnexion</button>
        </div>


        <!-- Demander un pseudo à l'utilisateur -->
        <!-- Interdire les caractères spéciaux et les chiffres dans le pseudo -->

        <div id="chat-box">
            
        <!-- Titre -->
            <h1>The ultime CHAT</h1>

            <div id="divpseudo">
                <label class="pseudo" for="pseudo">Pseudo</label> 
                <br>
                <input id="pseudo" type="text" name="pseudo" placeholder="Rentrez votre pseudo..." required pattern="[A-Za-z]{0,50}" onkeypress="pseudoverif(event); return false;" /> 
            </div>
            <br>
         
        <!-- Pouvoir envoyer des messages -->

            <div id="divmessage">
                <label class="message" for="message">Message</label>
                <br>
                <input id="message" type="text" name="message" placeholder="Écrivez votre message 👋" required />
            </div>
            <p>
                <input id="envoyer" type="submit" value="Envoyer" onclick="recuperation()" />
            </p>

        <!-- Permettre à l'utilisateur de changer la couleur et la taille de ses messages --> 

            <select id="sectioncouleur">
                <option value="">--Choissisez une couleurs--</option>
                <option value="red">Rouge</option>
                <option value="blue">Bleu</option>
                <option value="green">Vert</option>
                <option value="yellow">Jaune</option>
            </select>
            <p>
                <input type="submit" value="Changer la taille du texte" id="couleur" onclick="tailletexte()">
            </p>

        <!-- Chaque message est accompagné de l'heure d'envoi -->

            <div id="monhorloge"></div>
            <div id="content"></div>
        </div>

        <script>

            // Demander un pseudo à l'utilisateur
            // Pouvoir envoyer des messages 
            
                function recuperation() {
                    var pseudo = document.getElementById("pseudo").value;
                    var message = document.getElementById("message").value;
                    var dt = new Date();
        
                // Chaque message est accompagné de l'heure d'envoi
            
                    var content = document.getElementById("content").innerHTML;
                    var time = dt.getHours() + ":" + dt.getMinutes() + ":" + dt.getSeconds();
                    var line = '<p>' + time + ' ' + pseudo + ' ' + message + '</p>';
            
                    document.getElementById("content").innerHTML = content + line;
                }
            
            // Interdire les caractères spéciaux et les chiffres dans le pseudo
                
                function pseudoverif(event) {
                    var keyCode = event.which ? event.which : event.keyCode;
                    var touche = String.fromCharCode(keyCode);
                    var pseudochamp = document.getElementById('pseudo');
                    var lettres = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz';
                
                    if (lettres.indexOf(touche) >= 0) {
                        pseudochamp.value += touche;
                        pseudochamp.style.backgroundColor = "transparent";
                    } else {
                        alert(pseudochamp = "Les caractères spéciaux et les chiffres sont interdis");
                    }
                }
            
            // Permettre à l'utilisateur de changer la couleur et la taille de ses messages
            
                function couleurtexte() {
                    var couleur = document.getElementById("sectioncouleur").value;
                    console.log(couleur);
                    document.getElementById("content").couleur.style.color = "rouge" || "bleu" || "vert";
                }

                function tailletexte() {
                    var informationtaille = prompt("Entrez la taille du texte, exemple 20px :");
                    var choixtaille = document.getElementById("content");
                    choixtaille.style.fontSize = "20px";
                }
            
            // Pouvoir recevoir des messages (optionnel - AJAX) 
            
            // Remplacer les insultes par des caractères spéciaux de façon aléatoire (& #$*) 
            
            // Pouvoir quitter le chat en se déconnectant sans quitter la page
            
                function connexion() {
                    document.getElementById("chat-box").style.display = "initial";
                }
                
                function deconnexion() {
                    document.getElementById("chat-box").style.display = "none";
                }
                
                // Affichage de la date et de l'heure actuelles
                
                function horloge() {
                    var dt = new Date();
                    document.getElementById("monhorloge").innerHTML = "" + dt.getHours() + ":" + dt.getMinutes() + ":" + dt.getSeconds() + " Le " + dt.getDate() + '/' + (dt.getMonth() + 1) + '/' + dt.getFullYear();
                }
                
                var timer = setInterval("horloge()", 250);
            
            </script>
        </body>
    </html> 
